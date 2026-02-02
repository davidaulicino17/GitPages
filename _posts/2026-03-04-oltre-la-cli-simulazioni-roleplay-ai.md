---
layout: post
title: "Oltre la CLI: Allenare il 'Muscolo della Consulenza' simulando scenari reali"
date: 2026-02-02
author: "David Aulicino"
categories: [Carriera, Formazione, AI]
tags: [Soft Skills, Network Design, Roleplay, Artificial Intelligence, Consulting]
---

## Il limite dei Laboratori Virtuali
Chi fa il nostro mestiere conosce a memoria strumenti come Packet Tracer, EVE-NG o GNS3. Io personalmente, negli anni, mi sono innamorato di Pnetlab.
Passiamo notti e weekend a configurare protocolli di routing, a debuggare OSPF e a tirare su tunnel VPN. È la palestra tecnica fondamentale, quella che ti permette di passare le certificazioni.

Tuttavia, c'è una parte del lavoro che nessun simulatore tecnico ti insegna: **l'interazione con il cliente**.

In un lab, se configuri una rotta statica, il router obbedisce. Nel mondo reale, se proponi una soluzione tecnicamente perfetta ma fuori budget, il progetto viene bocciato. Se spieghi un disservizio usando termini troppo tecnici a un manager non IT, perdi la sua fiducia.

## Il "Flight Simulator" per Network Architect
Recentemente ho iniziato a sperimentare un nuovo metodo di studio per colmare questo gap tra teoria tecnica e realtà consulenziale. Invece di chiedere all'Intelligenza Artificiale di scrivermi uno script o spiegarmi un concetto, le chiedo di **diventare il mio cliente**.

L'idea è semplice: creare un gioco di ruolo (Roleplay) in cui l'AI interpreta un IT Manager o un CTO con un problema specifico, e io devo gestire l'intero ciclo di vita della richiesta, dalla prima email di contatto alla proposta commerciale, passando per le obiezioni tecniche.

### Come funziona la simulazione
Non serve un software complesso, basta un prompt ben strutturato. Ecco quello che uso io:

> "Agisci come se fossi il Responsabile IT di un'azienda [inserire settore, es. Logistica]. Inviami una mail in cui lamenti un problema sulla tua infrastruttura di rete attuale e chiedi una mia consulenza. Non darmi subito tutti i dettagli: aspetta che sia io a farti le domande giuste. Se propongo soluzioni troppo costose o complesse, fammi obiezioni realistiche. Il nostro obiettivo è arrivare a una proposta tecnica approvata."

## Cosa si impara (e dove si sbaglia)
In una delle mie ultime sessioni, ho simulato un progetto di migrazione da MPLS a SD-WAN per un'azienda di logistica. L'esperienza è stata illuminante.

1.  **Requirement Gathering:** Il "cliente" (l'AI) inizialmente era vago ("La rete è lenta"). Ho dovuto fare le domande giuste per scoprire che il vero problema era il blocco del gestionale SAP durante le videochiamate. In un lab tecnico, il problema è sempre chiaro; nella realtà, va estratto con le pinze.
2.  **Gestione del Budget vs. Tecnica:** Ho proposto una soluzione tecnicamente ineccepibile (cambio totale dell'hardware con un mix di vendor per risparmiare), ma il "cliente" mi ha fermato: la complessità di gestione di tre vendor diversi spaventava il suo piccolo team IT. Ho dovuto fare "rollback" sulla mia proposta e semplificare l'architettura.
3.  **Comunicazione:** Ho imparato (o meglio, ripassato) l'importanza di adattare il tono. Passare dal "Lei" formale al "Tu" collaborativo al momento giusto, e spiegare concetti complessi come l'Overlay SD-WAN rassicurando sul fatto che "l'IP non cambia".

## Perché dovresti provarlo
Come Network Engineer, spesso ci concentriamo solo sul "come" configurare le cose. Ma il "cosa" proporre e il "perché" sono ciò che distingue un tecnico da un consulente o un architetto.

Queste simulazioni sono una palestra a costo zero per sbagliare le email, gestire clienti difficili e affinare la sensibilità commerciale, prima di trovarsi davanti a un cliente vero con un contratto in mano.

La CLI è importante, ma saper scrivere una mail che convince un CFO a firmare il budget lo è altrettanto.