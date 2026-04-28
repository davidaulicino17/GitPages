---
layout: post
title: "Pillola #2 — Private VLAN: isolare dispositivi nella stessa subnet senza sprecare IP"
date: 2026-04-30
author: "David Aulicino"
categories: [Networking, Pillole]
tags: [VLAN, PVLAN, Switching, Datacenter, Sicurezza]
difficulty: intermedio
reading_time: 3
chapter_ref: Cap 4
---

**Difficoltà:** ⬛⬜⬜⬜⬜ Intermedio | **Lettura:** ~3 min | **Capitolo di riferimento:** Cap 4

---

**Il problema**
Hai un datacenter hosting con 20 clienti, ognuno con 2 server nella subnet 10.0.1.0/24. Vuoi che i server di tenant diversi non si parlino mai direttamente — ma creare una /24 separata per ogni cliente è uno spreco di IP e di complessità di routing.

---

**Il concetto in 30 secondi**

```
         VLAN 100 — Primary VLAN
         ┌─────────────────────────────────┐
         │  VLAN 101 — Isolated            │
         │  [ Server A ] [ Server B ]      │  ← non si parlano mai tra loro
         │                                 │
         │  VLAN 102 — Community (Tenant1) │
         │  [ Server C ] [ Server D ]      │  ← si parlano tra loro
         │                                 │
         │  Porta Promiscua ──► Firewall   │  ← parla con tutti
         └─────────────────────────────────┘
```

Una **VLAN Primaria** contiene più **VLAN Secondarie**. Il tipo di porta determina chi può parlare con chi.

---

**I 4 punti chiave**

- **Isolated port:** può comunicare solo con la porta promiscua. Mai con altre isolated, mai con community.
- **Community port:** comunica con le porte della stessa community VLAN secondaria e con la promiscua.
- **Promiscuous port:** comunica con tutti (uplink al router o al firewall).
- **VTP in Transparent mode:** obbligatorio. VTP non propaga correttamente le PVLAN in modalità server/client.

---

**Perché conta in produzione**

Le PVLAN sono lo strumento nativo per la microsegmentazione L2 in ambienti hosting, DMZ e PCI-DSS. Alternativamente si usano ACL, ma con PVLAN il blocco è a livello hardware di switch — zero overhead di processing.

---

> **Prossima pillola →** Usciamo dallo switch: domani estendiamo una VLAN tra due datacenter separati da centinaia di chilometri, senza toccare il routing.

---

*Vuoi consolidare la teoria con lab pratici? Ho pubblicato un libro di laboratori di networking — **[disponibile su Amazon →](https://www.amazon.it/dp/B0GYD89B5N)***
