---
layout: post
title: "Pillola #1 — OSPF Multi-Area: perché una sola area non basta mai"
date: 2026-04-29
author: "David Aulicino"
categories: [Networking, Pillole]
tags: [OSPF, Routing, Multi-Area, ABR, LSA]
difficulty: fondamentale
reading_time: 3
chapter_ref: Cap 1
---

**Difficoltà:** ⬜⬜⬜⬜⬜ Fondamentale | **Lettura:** ~3 min | **Capitolo di riferimento:** Cap 1

---

**Il problema**
Immagina una rete OSPF con 500 router tutti nella stessa area. Ogni volta che un link va giù, tutti e 500 i router ricalcolano l'intera topologia. Non è un problema di banda: è un problema di CPU, di convergenza e di esplosione delle LSA.

---

**Il concetto in 30 secondi**

```
         [ Area 1 ]          [ Area 0 — Backbone ]        [ Area 2 ]
  R1 — R2 — R3 — ABR1 ———————— ABR1 — Core — ABR2 ———————— ABR2 — R4 — R5
                  |                                          |
            filtra LSA                                  filtra LSA
            Type 1/2                                    Type 1/2
            pubblica                                    pubblica
            Type 3                                      Type 3
```

L'**ABR (Area Border Router)** è il confine: dentro l'area circolano le LSA di dettaglio (Type 1 e Type 2), fuori escono solo i summary (Type 3). Un flap in Area 1 non fa girare SPF in Area 2.

---

**I 4 punti chiave**

- **LSA Type 1 (Router LSA):** generata da ogni router, descrive i suoi link. Rimane nell'area.
- **LSA Type 2 (Network LSA):** generata dal DR su segmenti multi-access. Rimane nell'area.
- **LSA Type 3 (Summary LSA):** generata dall'ABR per pubblicare le subnet delle aree adiacenti verso l'Area 0 e viceversa.
- **Stub / Totally Stubby Area:** blocca le LSA esterne (Type 5) o anche le Type 3, riducendo ulteriormente la tabella nei siti periferici.

---

**Perché conta in produzione**

Un'area OSPF mal dimensionata è una delle cause più comuni di convergenza lenta. La regola pratica: mai più di 50-100 router per area. Il design multi-area non è ottimizzazione — è prerequisito per scalare.

---

> **Prossima pillola →** Restiamo sul Layer 2: domani scopriamo come isolare dispositivi nella stessa subnet senza sprecare un singolo indirizzo IP.

---

*Vuoi consolidare la teoria con lab pratici? Ho pubblicato un libro di laboratori di networking — **[disponibile su Amazon →](https://www.amazon.it/dp/B0GYD89B5N)***
