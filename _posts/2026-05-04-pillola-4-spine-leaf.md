---
layout: post
title: "Pillola #4 — Spine-Leaf: l'architettura che ha reso obsoleto il datacenter a 3 livelli"
date: 2026-05-02
author: "David Aulicino"
categories: [Networking, Pillole]
tags: [Spine-Leaf, Datacenter, ECMP, BGP, Architettura]
difficulty: avanzato
reading_time: 4
chapter_ref: Cap 7
---

**Difficoltà:** ⬛⬛⬛⬜⬜ Avanzato | **Lettura:** ~4 min | **Capitolo di riferimento:** Cap 7

---

**Il problema**
Il modello Core-Distribution-Access nasce per traffico North-South (server → Internet). Nel datacenter moderno il 70-80% del traffico è East-West (server → server). In quel modello, due server sullo stesso rack devono attraversare Distribution e Core per parlarsi. STP blocca link ridondanti. L'oversubscription è asimmetrica e imprevedibile.

---

**Il concetto in 30 secondi**

```
         [ Spine 1 ]     [ Spine 2 ]     [ Spine 3 ]
            │  │  │         │  │  │         │  │  │
            │  └──┼─────────┘  └──┼─────────┘  │
            │     │               │             │
         [ Leaf1 ]             [ Leaf2 ]     [ Leaf3 ]
          Server A              Server B      Server C
```

Ogni **Leaf** si connette a ogni **Spine**. Nessun Leaf si connette a un altro Leaf. Nessun Spine si connette a un altro Spine. Il risultato: ogni coppia di server comunica sempre in esattamente **2 hop**, con latenza uniforme e prevedibile.

---

**I 4 punti chiave**

- **2-hop fisso:** Leaf sorgente → Spine → Leaf destinazione. Sempre. La latenza è deterministica.
- **ECMP nativo:** tra due Leaf esistono N path (uno per Spine). Il traffico viene distribuito in modo uniforme. Aggiungere uno Spine aumenta la banda aggregata East-West.
- **IP Fabric — niente STP:** ogni link tra Leaf e Spine è un /31 routed. Spanning Tree non esiste. Tutti i link sono attivi.
- **eBGP underlay:** ogni Leaf ha il proprio ASN privato, gli Spine condividono un ASN. BGP distribuisce le loopback dei VTEP — base per VXLAN EVPN sopra.

---

**Perché conta in produzione**

Spine-Leaf è l'architettura di riferimento di Cisco ACI, Arista CloudVision, Juniper Apstra. Non è una tendenza: è lo standard. Capire perché è stato adottato — non solo come configurarlo — è ciò che distingue chi progetta da chi esegue.

---

> **Prossima pillola →** Lo Spine-Leaf che abbiamo costruito oggi ha ancora un problema: VXLAN statico non scala. Domani aggiungiamo il cervello — MP-BGP EVPN.

---

*Vuoi consolidare la teoria con lab pratici? Ho pubblicato un libro di laboratori di networking — **[disponibile su Amazon →](https://www.amazon.it/dp/B0GYD89B5N)***
