---
layout: post
title: "Come effettuare rollback su Cisco IOS"
date: 2026-01-04
author: "David Aulicino"
categories: [Carriera, Networking, Storytelling]
tags: [Network Engineer, Cisco, CCNA, CCNP, Crescita Professionale]
---

**Di David Aulicino**

Spesso e volentieri capita di dover effettuare delle operazioni che potrebbero portare dietro di sé alcune problematiche, alle volte anche bloccanti.
Soprattutto quando si opera da remoto il rischio di perdere il controllo dell'apparato Cisco è sempre dietro l'angolo.

![Screenshot Cisco](/GitPages/assets/images/rollback_cisco/screenshot_cisco.png)

## Il metodo classico (e i suoi limiti)

Un metodo molto utilizzato per fare un "rollback" è il seguente:
1. Salvare la configurazione attuale.
2. Schedulare un reload dopo N minuti (`reload in 10`).
3. Effettuare la configurazione prevista.
4. Se tutto funziona, rimuovere il riavvio pianificato; in caso contrario, attendere il reboot del device.

In questo breve articolo voglio spiegare il **metodo nativo** per effettuare un rollback su Cisco, senza dover aspettare il riavvio dell'hardware per riprendere l'attività in caso di problemi.

---

## Configurazione della funzione Archive

Il rollback della configurazione avviene attraverso l'attivazione della feature **"archive"**. Per utilizzare questa funzionalità dobbiamo indicare al nostro router o switch dove salvare i file di backup temporanei.

Entriamo in modalità privilegiata e poi in configurazione:

```bash
Router# configure terminal
Router(config)# archive
Router(config-archive)# path flash:backup-config