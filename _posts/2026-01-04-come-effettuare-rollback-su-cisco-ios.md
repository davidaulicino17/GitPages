---
layout: post
title: "Come effettuare rollback su Cisco IOS"
date: 2026-01-04
author: "David Aulicino"
categories: [Carriera, Networking, Storytelling]
tags: [Network Engineer, Cisco, CCNA, CCNP, Crescita Professionale]
---

# Come effettuare rollback su Cisco IOS

**Di David Aulicino**

Spesso e volentieri capita di dover effettuare delle operazioni che potrebbero portare dietro di sé alcune problematiche, alle volte anche **bloccanti**.
Soprattutto quando si opera da remoto il rischio di **perdere il controllo** dell'apparato Cisco è sempre dietro l'angolo.

![Screenshot Cisco](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_cisco.png)

## Il metodo tradizionale (Reload)

Un metodo molto utilizzato per fare un "rollback" è il seguente:

* **Salvare** la configurazione;
* **Schedulare** un reload dopo *N* minuti;
* **Effettuare** la configurazione prevista;

Nel caso in cui tutto andasse come sperato ci basterà rimuovere il riavvio pianificato, in caso contrario dovremo aspettare il **reboot** del device.

In questo breve articolo voglio spiegare il **metodo vero e proprio** per effettuare un rollback su Cisco, senza dover aspettare più del dovuto per riprendere l'attività in caso di problemi.

---

## Configurazione della feature "Archive"

Per prima cosa entriamo in **modalità privilegiata** (#) e poi in **configuration mode**:

![Screenshot 1](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_1.png)

Il rollback della configurazione avviene attraverso l'attivazione della feature **"archive"**. Per utilizzare questa funzionalità dobbiamo indicare al nostro router/switch dove andare a salvare la configurazione con il comando `path`:

![Screenshot 2](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_2.png)

> **Nota:** Tra le opzioni solitamente è presente anche la memoria **flash**, in questo caso non è presente perché sto utilizzando un apparato virtuale.

Nel mio caso dovrò selezionare come percorso **"unix"** per salvare la configurazione di backup. Dopo aver effettuato la selezione, salviamo e facciamo un test.

**Consiglio:** Nel caso in cui si possa perdere il controllo dell'apparato, è preferibile scegliere come percorso una **memoria interna** al dispositivo per evitare rischi.

---

## Test della funzione di Rollback (Revert)

Terminata la configurazione, possiamo testare la funzione di **rollback** o, per essere più precisi, **"revert"**. Entriamo in modalità di configurazione con il comando specifico:

![Screenshot 3](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_3.png)

Allo scadere del **timer**, verrà automaticamente ripristinata la configurazione precedente presa dal backup creato in quel momento.

![Screenshot 4](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_4.png)

### Esempio Pratico
Per fare un test possiamo impostare un **hostname differente**, ad esempio:

![Screenshot 5](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_5.png)

Allo scadere del timer, verrà mostrato a schermo un **log** che indica il cambio di configurazione e i comandi utilizzati per il ripristino:

![Screenshot 6](https://davidaulicino17.github.io/GitPages/assets/images/rollback_cisco/screenshot_6.png)

### Confermare le modifiche
Nel caso in cui volessimo mantenere le modifiche apportate, possiamo confermarle con il comando:

`configure confirm`

A seguito della conferma è **sempre necessario salvare**.

---

## Riepilogo Comandi Utilizzati

<font face="courier">
enable<br>
configure terminal<br>
<br>
! Configurazione dell'archivio<br>
archive<br>
 path flash:<br>
end<br>
write memory<br>
<br>
! Avvio configurazione con rollback automatico (1 minuto)<br>
configure terminal revert timer 1<br>
hostname PROVA<br>
end<br>
<br>
! Conferma delle modifiche (se corrette)<br>
configure confirm
</font>