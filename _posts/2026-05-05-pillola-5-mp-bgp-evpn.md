---
layout: post
title: "Pillola #5 — MP-BGP EVPN: quando BGP diventa il control plane del datacenter"
date: 2026-05-05
author: "David Aulicino"
categories: [Networking, Pillole]
tags: [EVPN, BGP, VXLAN, Datacenter, Control Plane]
difficulty: avanzato-esperto
reading_time: 5
chapter_ref: Cap 8
---

**Difficoltà:** ⬛⬛⬛⬛⬜ Avanzato-Esperto | **Lettura:** ~5 min | **Capitolo di riferimento:** Cap 8

---

**Il problema**
Lo Spine-Leaf con VXLAN statico funziona — ma non scala. Aggiungere un nuovo Leaf significa aggiornare manualmente la lista dei VTEP su ogni altro nodo. Il flooding BUM (Broadcast, Unknown unicast, Multicast) consuma banda su tutto il fabric. Non c'è un modo efficiente di fare routing inter-VXLAN senza uscire dal fabric.

---

**Il concetto in 30 secondi**

```
  [ Leaf 1 ]──────────────────────────[ Leaf 2 ]
      │  pubblica su BGP:                  │  pubblica su BGP:
      │  MAC: AA:BB:CC  IP: 10.0.1.1       │  MAC: DD:EE:FF  IP: 10.0.2.1
      │  VNI: 10001  VTEP: 1.1.1.1         │  VNI: 10001  VTEP: 2.2.2.2
      │                                    │
      └──────────[ Route Reflector ]───────┘
                  (Spine con RR)
                  distribuisce RT-2 e RT-3
                  a tutti i Leaf
```

**EVPN (Ethernet VPN)** è una famiglia di Route Type BGP. I VTEP non si configurano più manualmente: si "scoprono" tramite le route BGP pubblicate dagli altri Leaf.

---

**I 4 punti chiave**

- **Route Type 2 (MAC/IP Advertisement):** ogni Leaf pubblica i MAC e gli IP degli host connessi. Gli altri Leaf costruiscono la tabella di forwarding senza flooding.
- **Route Type 3 (Inclusive Multicast):** ogni VTEP annuncia se stesso. Sostituisce la lista statica dei peer: un nuovo Leaf si aggiunge al fabric pubblicando la sua RT-3.
- **L3VNI — Distributed Anycast Gateway:** ogni Leaf ha lo stesso IP e MAC virtuale per ogni gateway di subnet. L'ARP non lascia mai il Leaf locale. Il routing inter-VXLAN avviene dentro il fabric, nel VRF del tenant.
- **Route Reflector sugli Spine:** evita il mesh iBGP full-mesh tra tutti i Leaf. Ogni Leaf ha due session BGP (una per Spine); gli Spine riflettono le route a tutti.

---

**Perché conta in produzione**

MP-BGP EVPN è il control plane di Arista EOS, Cisco Nexus NX-OS, Juniper Junos e della maggior parte dei vendor SDN. Chiunque lavori su infrastrutture datacenter enterprise o cloud-provider lo incontra. Conoscere il meccanismo — non solo i comandi — permette di diagnosticare problemi che i tool automatici non vedono.

---

> **La serie continua →** Nei prossimi episodi: MPLS L3VPN, SD-WAN, e sicurezza pervasiva. Segui per non perdere le prossime pillole.

---

*Vuoi consolidare la teoria con lab pratici? Ho pubblicato un libro di laboratori di networking — **[disponibile su Amazon →](https://www.amazon.it/dp/B0GYD89B5N)***
