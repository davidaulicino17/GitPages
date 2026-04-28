---
layout: post
title: "Modem, Router e Firewall: Perché chiamarli tutti 'il Wi-Fi' è un errore (e un rischio)"
date: 2026-04-02
author: "David Aulicino"
categories: [Networking, Sicurezza, IT]
tags: [Modem, Router, Firewall, ONT, Infrastruttura]
---

Nel mio lavoro quotidiano come Network Engineer, mi capita spesso di sentire la frase: *"Il modem non va"*. Nella maggior parte dei casi, però, quel dispositivo sta facendo tre o quattro lavori diversi contemporaneamente ed è proprio qui che nasce la confusione. Se non distinguiamo i ruoli, non possiamo capire perché la connessione sia lenta o, peggio, perché la nostra rete sia vulnerabile.

Facciamo un po' di ordine tecnico, ma senza paroloni inutili.

## 1. Il Modem (o l'ONT): Il Traduttore
Il modem è l'unico dispositivo che parla davvero con l'esterno. Il termine nasce da *MOdulatore-DEModulatore*: serviva a trasformare i bit in frequenze elettriche per viaggiare sul vecchio doppino in rame della rete telefonica.

**La precisione tecnica per chi ha la fibra (FTTH):**
Se hai la fibra ottica pura che ti arriva in casa, tecnicamente non usi più un modem, ma un **ONT** (*Optical Network Terminal*).
* **Cosa fa:** Mentre il modem traduce segnali elettrici, l'ONT traduce impulsi luminosi in dati digitali (Ethernet).
* **Perché lo chiamano ancora modem?** Puro marketing dei provider per non confondere l'utente medio, ma è quel "boxino" (esterno o integrato) che trasforma la luce in Internet.

## 2. Il Router: Il Vigile Urbano
Una volta che i dati sono stati "tradotti", entra in gioco il router. Il suo compito è la **direzione**. Immagina una rotonda trafficata: il router è il vigile al centro che sa che il pacchetto di dati "Netflix" deve andare alla Smart TV e non al portatile che sta scaricando una mail. Crea la tua rete privata (LAN) e assegna a ogni dispositivo un indirizzo IP, coordinando il traffico affinché non ci siano collisioni. 

Inoltre, il classico router casalingo si occupa anche della gestione del Wi-Fi, diventando a tutti gli effetti un **Access Point**.

## 3. Il Firewall: Il Buttafuori
Qui passiamo dalla connettività alla protezione. Se il router decide *dove* vanno i dati, il firewall decide *se* possono passare. 

La differenza filosofica tra i due è totale:
* **Il Router**, per default, tende a permettere tutto per garantire la comunicazione.
* **Il Firewall**, per default, nega tutto ciò che non è esplicitamente autorizzato.

È un setaccio professionale: analizza ogni bit che prova a entrare. Se vede un traffico sospetto o un tentativo di accesso non autorizzato, lo blocca prima ancora che raggiunga i tuoi dispositivi.

> **Il consiglio da professionista:** I router domestici hanno firewall molto basilari. In contesti aziendali o impianti critici, usiamo firewall dedicati — come **Palo Alto** o **Fortigate** — che analizzano profondamente il contenuto dei pacchetti per scovare minacce complesse.

---

### Il problema dello "scatolone unico"
Il motivo della confusione è che i provider ci consegnano quasi sempre dispositivi **"all-in-one"**. Quel box sulla mensola è contemporaneamente un ONT/Modem, un router, un firewall e un access point Wi-Fi.

È comodo, certo, ma è anche il motivo per cui, quando qualcosa non va, è difficile capire se il problema sia la linea (fibra/rame), la distribuzione interna (router) o un blocco di sicurezza (firewall). Capire chi fa cosa è il primo passo per riprendere davvero il controllo della propria rete.

---

*Vuoi consolidare la teoria con lab pratici? Ho pubblicato un libro di laboratori di networking — **[disponibile su Amazon →](https://www.amazon.it/dp/B0GYD89B5N)***