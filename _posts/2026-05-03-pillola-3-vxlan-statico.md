---
layout: post
title: "Pillola #3 — VXLAN Statico: il Layer 2 che attraversa qualsiasi rete IP"
date: 2026-05-01
author: "David Aulicino"
categories: [Networking, Pillole]
tags: [VXLAN, Overlay, Datacenter, VTEP, VNI]
difficulty: intermedio-avanzato
reading_time: 4
chapter_ref: Cap 5
---

**Difficoltà:** ⬛⬛⬜⬜⬜ Intermedio-Avanzato | **Lettura:** ~4 min | **Capitolo di riferimento:** Cap 5

---

**Il problema**
Due datacenter separati da un backbone IP devono condividere la stessa VLAN per far migrare le VM in live. GRE non porta il MAC address. OTV è vendor-locked. Serve un overlay standard, scalabile, e basato su UDP.

---

**Il concetto in 30 secondi**

```
  DC-A                              Underlay IP                        DC-B
  ┌──────────┐                                                    ┌──────────┐
  │ Server   │  Ethernet Frame                                    │ Server   │
  │ 10.0.1.1 │──► [ VTEP-A ]──────[ UDP / IP / VXLAN ]──────► [ VTEP-B ]──► 10.0.1.2 │
  └──────────┘    Encapsula                                       Decapsula  └──────────┘
                  VNI: 10001                                      VNI: 10001
```

Il **VTEP (VXLAN Tunnel Endpoint)** incapsula il frame Ethernet originale in un pacchetto UDP con un header VXLAN che contiene il **VNI (VXLAN Network Identifier)**. Il VNI è a 24 bit: 16 milioni di segmenti logici sullo stesso underlay.

---

**I 4 punti chiave**

- **VNI:** identifica il segmento logico indipendentemente dalla VLAN ID dell'underlay. VLAN 10 su DC-A e VLAN 20 su DC-B possono mappare sullo stesso VNI.
- **UDP porta 4789:** lo standard IANA. L'header UDP permette all'underlay di fare ECMP (hash su src/dst port).
- **Head-End Replication (HER):** nella versione statica, il traffico broadcast/multicast viene replicato dal VTEP sorgente verso tutti i VTEP remoti configurati manualmente.
- **Underlay OSPF:** i VTEP si raggiungono tramite le loro loopback ridistribuite da OSPF — il dato è VXLAN, il trasporto è IP puro.

---

**Perché conta in produzione**

VXLAN statico è il punto di ingresso per capire le overlay di datacenter. Non scala oltre decine di VTEP (la lista manuale diventa ingestibile) — ma capire ogni componente di questo modello è il prerequisito indispensabile per il passo successivo: EVPN.

---

> **Prossima pillola →** Dimentichiamo i 3 livelli Core-Distribution-Access: domani costruiamo un datacenter dove ogni flusso fa sempre e solo 2 hop.

---

*Vuoi consolidare la teoria con lab pratici? Ho pubblicato un libro di laboratori di networking — **[disponibile su Amazon →](https://www.amazon.it/dp/B0GYD89B5N)***
