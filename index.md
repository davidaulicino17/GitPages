---
layout: default
title: Home
---

<style>
/* Stili specifici per la griglia della Home Page */
.grid-container {
    display: grid;
    /* Card fluide con spazio bilanciato */
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 25px; /* Leggermente ridotto per compattezza ma mantiene il respiro */
    margin: 20px 0 40px 0;
}

/* Stile per il link che avvolge la card */
.card-link {
    text-decoration: none;
    color: inherit;
    display: block;
}

.card {
    background: #ffffff;
    /* MODIFICA: Padding verticale ridotto per diminuire l'altezza */
    padding: 12px 18px; 
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.05);
    border: 1px solid #eee;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    /* MODIFICA: Altezza automatica per adattarsi al contenuto senza allungarsi troppo */
    height: auto; 
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.card-link:hover .card {
    transform: scale(1.03); /* Zoom leggermente ridotto per evitare sovrapposizioni visive eccessive */
    box-shadow: 0 8px 20px rgba(0,0,0,0.1);
}

.card h3 {
    margin-top: 0;
    font-size: 1rem; /* Titolo leggermente più piccolo per risparmiare spazio */
    color: #0056b3;
    margin-bottom: 4px; /* Margine ridotto */
}

.card p {
    font-size: 0.85rem;
    color: #555;
    margin-bottom: 0;
    line-height: 1.3; /* Interlinea più densa */
}

/* Stile per la lista post */
.post-list-home {
    list-style: none;
    padding: 0;
}
.post-list-home li {
    margin-bottom: 15px;
    padding-bottom: 15px;
    border-bottom: 1px dashed #eee;
}
</style>

# Ciao, sono David Aulicino 👋

Benvenuto nel mio spazio personale.
Sono un **Network & Infrastructure Engineer** con base in Italia, appassionato di reti, sicurezza informatica ed elettronica.

---

### 🏆 Certificazioni rilevanti
<div class="grid-container">
  <div class="card">
    <h3>Cisco CCNP ENARSI</h3>
    <p>300-410 Enterprise Advanced Routing</p>
  </div>
  <div class="card">
    <h3>Cisco CCNA</h3>
    <p>200-301 Network Associate</p>
  </div>
  <div class="card">
    <h3>Sophos Certified Engineer</h3>
    <p>XG Firewall & Central</p>
  </div>
  <div class="card">
    <h3>Arduino Certification</h3>
    <p>Electronics & Physical Computing</p>
  </div>
</div>

---

### 💻 Software & Tools

<div class="grid-container" style="grid-template-columns: 1fr;"> 
  <a href="https://github.com/davidaulicino17/EXAM-SIMULATOR-PUBLIC" class="card-link" target="_blank">
    <div class="card" style="border-left: 5px solid #3b9cff;">
      <h3>Exam Simulator - Pro Edition v3.0</h3>
      <p>Un simulatore d'esame desktop moderno e portatile in Python (CustomTkinter). Supporto JSON/CSV e statistiche avanzate.</p>
      <br>
      <em>Database supportati: CCNA, CCNP, CCDE.</em>
    </div>
  </a>
</div>

---

### 🔬 Laboratori di Networking (PNetLab)
<div class="grid-container">

  <a href="https://github.com/davidaulicino17/Laboratory_PNETLAB/tree/main/LAB_%20Design%20OSPF%20Scalabile_Single-Area_vs.%20Multi-Area" class="card-link" target="_blank">
      <div class="card">
        <h3>Design OSPF Scalabile</h3>
        <p>Analisi comparativa Single-Area vs. Multi-Area.</p>
      </div>
  </a>

  <a href="https://github.com/davidaulicino17/Laboratory_PNETLAB/tree/main/LAB_L3_Spine-Leaf_Fabric_BGP_and_OSPF" class="card-link" target="_blank">
      <div class="card">
        <h3>Fabric L3 Spine-Leaf</h3>
        <p>Data Center Fabric con OSPF e BGP.</p>
      </div>
  </a>

  <a href="https://github.com/davidaulicino17/Laboratory_PNETLAB/tree/main/LAB_Fabric_Datacenter_Greenfield_con_MP-BGP_EVPN" class="card-link" target="_blank">
      <div class="card">
        <h3>Greenfield DC con EVPN</h3>
        <p>Architettura moderna con MP-BGP EVPN.</p>
      </div>
  </a>

  <a href="https://github.com/davidaulicino17/Laboratory_PNETLAB/tree/main/LAB_Nexus_vPC_Domain_Setup_with_LACP" class="card-link" target="_blank">
      <div class="card">
        <h3>Nexus vPC & LACP</h3>
        <p>Alta affidabilità su switch Cisco Nexus.</p>
      </div>
  </a>

  <a href="https://github.com/davidaulicino17/Laboratory_PNETLAB/tree/main/LAB_Integrazione_Brownfield-Greenfield_con_DCI_VXLAN" class="card-link" target="_blank">
      <div class="card">
        <h3>DCI con VXLAN Statico</h3>
        <p>Estensione L2 tra siti via tunnel VXLAN.</p>
      </div>
  </a>

</div>

---

### 📝 Ultimi Articoli dal Blog
<ul class="post-list-home">
  {% for post in site.posts %}
    <li>
      <span style="color: #888; font-size: 0.85rem; margin-right: 10px;">{{ post.date | date: "%d/%m/%Y" }}</span>
      <a href="{{ post.url | relative_url }}" style="font-weight: bold;">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

---

### I miei interessi
* Network Engineering & Security
* Automazione (Python, C++)
* Elettronica & Arduino
* Cinema e Lettura

---
<div style="text-align: center; margin-top: 40px;">
    <a href="https://www.linkedin.com/in/david-aulicino-b9371648" target="_blank" class="btn">LinkedIn</a>
    <a href="mailto:david.aulicino@tiscali.it" class="btn">Contattami</a>
</div>