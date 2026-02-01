---
layout: post
title: "Networking al Confine del Mondo: Perché la SD-WAN è il cuore dell’Eolico"
date: 2026-02-01
author: "David Aulicino"
categories: [Networking, SD-WAN, Industrial IT]
tags: [SD-WAN, Renewables, OT Security, Starlink, Network Engineering]
---

**Di David Aulicino**

# Networking al Confine del Mondo: Perché la SD-WAN è il cuore dell’Eolico

## 1. Il Miraggio della Banda Ultra-Larga
Nel mondo della consulenza IT o negli uffici direzionali delle grandi metropoli, diamo la connettività per scontata: fibra dedicata, latenze sotto i 5ms e ridondanza infinita. Sebbene anche in Italia la copertura in fibra (FTTH) sia talvolta ancora un miraggio in diverse zone, la situazione precipita drasticamente quando si lavora per un leader delle rinnovabili, come ho fatto io negli ultimi anni.

La prospettiva cambia radicalmente: ti trovi a dover connettere asset industriali situati in cima a una scogliera scozzese o in luoghi remoti sparsi per il mondo, dove l'unico cavo che arriva è quello dell'alta tensione. La fibra ottica non è nemmeno un'opzione il più delle volte.
Nella maggior parte dei casi, ci si deve "accontentare" di link xDSL su rame degradato, con un throughput massimo che, quando si è fortunati, raggiunge appena pochi megabit. In questi scenari "ostili", il networking smette di essere una commodity e diventa una sfida di ingegneria pura.

## 2. Legacy vs. Low Earth Orbit: Il Salto Evolutivo
Fino a pochi anni fa, connettere un sito remoto significava affidarsi a costosi link MPLS (dove disponibili) o a tunnel VPN IPsec statici su connessioni radio instabili. I limiti di queste architetture tradizionali erano evidenti:
* **Rigidità:** Se il link primario degradava, il failover era lento, causando spesso la caduta delle sessioni applicative.
* **Visibilità nulla:** Era impossibile capire perché la telemetria di una turbina arrivasse a scatti; il monitoraggio mostrava solo un tunnel "up" o "down", senza dettagli sulla qualità del trasporto.
* **Latenza e Jitter:** Le connessioni satellitari legacy o LTE instabili introducevano ritardi incompatibili con il monitoraggio in tempo reale (SCADA).

La vera rivoluzione per il livello fisico è stato l’avvento delle costellazioni satellitari LEO (Low Earth Orbit) come **Starlink**, che hanno permesso di portare connettività ad alte performance e bassa latenza in luoghi dove prima era inimmaginabile.

## 3. SD-WAN: L'Intelligence sopra il "Ferro"
La SD-WAN (*Software-Defined Wide Area Network*) non è solo una buzzword di marketing; per un Network Engineer che gestisce siti remoti, è il "coltellino svizzero" definitivo. Ecco come trasforma la gestione operativa di un parco eolico:

### Transport Independence (L’unione fa la forza)
La SD-WAN astrae l’hardware dal mezzo fisico. Possiamo combinare un link satellitare, una connessione 4G/5G industriale e, dove possibile, una xDSL locale. Il sistema vede un unico "tubo" logico aggregato, massimizzando la banda disponibile.

### Dynamic Path Selection: La telemetria prima di tutto
Non tutto il traffico ha la stessa importanza. Grazie alla SD-WAN, possiamo impostare policy granulari:
* **Traffico Critico (SCADA/Telemetria):** Viene instradato dinamicamente sul link con il minor jitter. Se il link A mostra un degrado anche minimo, il pacchetto viene duplicato o spostato sul link B senza perdere la sessione.
* **Traffico Business (Email/Web):** Può restare sul link più lento o economico, liberando le risorse pregiate per i dati di produzione.

### Zero Touch Provisioning (ZTP): L'obiettivo logistico
Immaginate di dover attivare 20 parchi eolici in tre paesi diversi. Con l'approccio tradizionale, servirebbe un ingegnere sul posto. Lo scenario ideale del ZTP prevede la spedizione di un apparato pre-configurato che, collegato alla rete elettrica e a un modem LTE da un tecnico locale, "chiama casa", scarica la configurazione e stabilisce i tunnel in autonomia.
Nel mio percorso, questo scenario è stato teorizzato come pilastro del progetto di refresh tecnologico infrastrutturale (Firewall, Switch, AP) per abbattere i costi di trasferta e velocizzare il deployment.

## 4. Architetture Critiche: Dai Data Center in L2 al Sito Remoto
Lavorare nelle rinnovabili significa proteggere infrastrutture critiche. La SD-WAN integra nativamente funzionalità di sicurezza (Next-Gen Firewall e segmentazione) essenziali per isolare il traffico delle turbine (OT) da quello gestionale (IT), riducendo la superficie di attacco in luoghi dove il controllo dell'accesso fisico è complesso.

L’architettura che ho gestito si basava su una struttura robusta: **due Data Center collegati in Layer 2** per garantire la continuità dei servizi core. Da qui, diverse decine di impianti e uffici remoti venivano connessi attraverso tunnel SD-WAN. L'accesso sicuro per gli utenti avveniva tramite un primo livello di **VPN SSL**, che permetteva di entrare nel perimetro aziendale per poi instradare il traffico verso gli asset remoti attraverso la maglia SD-WAN, garantendo controllo e cifratura end-to-end.

## Conclusione: Il Bit che fa Girare la Pala
In un settore dove l'efficienza è tutto, un ritardo nella ricezione dei dati di produzione può tradursi in perdite economiche o inefficienze nella rete elettrica nazionale. La tecnologia SD-WAN è il ponte che permette a un ingegnere, seduto comodamente in ufficio o in consulenza, di avere il controllo totale su un asset a mille chilometri di distanza, come se fosse nella stanza accanto.

Il networking moderno non riguarda più solo il "collegare cavi", ma il garantire che l'intelligenza dei dati fluisca costante, indipendentemente da quanto sia isolato il sito.