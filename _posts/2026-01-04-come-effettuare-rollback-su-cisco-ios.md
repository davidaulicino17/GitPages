---
layout: post
title: "Come effettuare rollback su Cisco IOS"
date: 2026-01-29
author: "David Aulicino"
categories: [Carriera, Networking, Storytelling]
tags: [Network Engineer, Cisco, CCNA, CCNP, Crescita Professionale]
---

# Come effettuare rollback su Cisco IOS

**Di David Aulicino**

In ambito networking, operare su apparati critici comporta sempre una certa dose di rischio. Un errore di sintassi o una modifica errata a una ACL possono causare problemi **bloccanti** e, se stiamo lavorando da remoto, il rischio di **perdere completamente l'accesso** al device è una minaccia costante.

![Screenshot Cisco](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_cisco.png)

## Il limite del metodo tradizionale (Reload)

Molti amministratori di rete si affidano a una procedura di sicurezza standard:

* **Salvataggio** della configurazione attuale (`write memory`);
* **Pianificazione** di un riavvio automatico (`reload in 10`);
* **Applicazione** delle modifiche.

Sebbene efficace, questo metodo ha un grande difetto: se qualcosa va storto, l'apparato deve riavviarsi completamente, causando un **down-time** prolungato e non necessario. 

Esiste però una soluzione più elegante e professionale integrata in Cisco IOS: la funzione di **Rollback**.

---

## Configurazione della feature "Archive"

Per abilitare il rollback, dobbiamo prima configurare la funzione **Archive**, che permette al sistema di creare snapshot della configurazione.

Entriamo in **modalità privilegiata** (#) e successivamente in **global configuration mode**:

![Screenshot 1](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_1.png)

Dobbiamo specificare al router (o switch) il percorso (`path`) dove memorizzare i file di backup:

![Screenshot 2](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_2.png)

> **Nota Tecnica:** In ambienti di produzione è fondamentale utilizzare la memoria **flash:** o un server esterno (TFTP/FTP). In questo esempio, essendo su un apparato virtuale, utilizzeremo il filesystem locale.

**Best Practice:** Assicurati sempre che il percorso scelto sia accessibile anche in caso di isolamento della rete, preferendo quindi lo storage locale dell'apparato.

---

## Esecuzione del Rollback (Revert)

Una volta configurato l'archivio, possiamo avviare una sessione di configurazione "temporanea" utilizzando il comando `revert`. Questo comando avvia un timer: se non confermiamo le modifiche entro il tempo stabilito, l'apparato **ripristinerà automaticamente** lo stato precedente senza riavviarsi.

![Screenshot 3](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_3.png)

Al termine del timer, se non interviene l'operatore, il sistema caricherà il file di backup salvato nell'archivio.

![Screenshot 4](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_4.png)

### Esempio Pratico: Cambio Hostname
Immaginiamo di voler testare un cambio di nome host:

![Screenshot 5](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_5.png)

Se non confermiamo l'operazione, il sistema genererà un **log** di sistema e applicherà i comandi necessari per tornare alla configurazione originale:

![Screenshot 6](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_6.png)

### Validazione delle modifiche
Se le modifiche sono corrette e il servizio risponde come previsto, dobbiamo rendere permanenti i cambiamenti con il comando:

`configure confirm`

**Ricorda:** Dopo la conferma, esegui sempre un `copy running-config startup-config` per rendere le modifiche persistenti anche al prossimo riavvio fisico.

---

## Riepilogo Comandi Utilizzati

<font face="courier">
enable<br>
configure terminal<br>
<br>
! 1. Attivazione del sistema di archiviazione<br>
archive<br>
 path flash:config-backup<br>
 write-memory<br>
end<br>
<br>
! 2. Configurazione con protezione rollback (es. 5 minuti)<br>
configure terminal revert timer 5<br>
<br>
! 3. (Esempio modifica)<br>
hostname CORE-SWITCH-01<br>
end<br>
<br>
! 4. Conferma definitiva (se tutto ok)<br>
configure confirm
</font>