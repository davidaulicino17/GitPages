---
layout: default
title: Home
---

<style>
/* Reset e Sfondo Body (opzionale se non gestito dal tema principale) */
body {
    background-color: #0f172a;
    color: #e2e8f0;
}

/* Griglia della Home Page */
.grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
    margin: 20px 0 40px 0;
}

/* Link Card */
.card-link {
    text-decoration: none;
    color: inherit;
    display: block;
}

/* Card in Dark Mode Moderno */
.card {
    background: #1e293b;
    padding: 18px; 
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.2);
    border: 1px solid #334155;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    height: 100%; 
    display: flex;
    flex-direction: column;
}

/* Hover Effect con Glow */
.card-link:hover .card {
    transform: translateY(-5px);
    border-color: #3b82f6;
    box-shadow: 0 0 15px rgba(59, 130, 246, 0.3);
}

.card h3 {
    margin-top: 0;
    font-size: 1.1rem;
    color: #3b82f6; /* Blue accent */
    margin-bottom: 8px;
}

.card p {
    font-size: 0.9rem;
    color: #94a3b8;
    margin-bottom: 0;
    line-height: 1.4;
}

/* Lista Blog */
.post-list-home {
    list-style: none;
    padding: 0;
}
.post-list-home li {
    margin-bottom: 12px;
    padding: 10px;
    border-radius: 8px;
    transition: background 0.2s;
}
.post-list-home li:hover {
    background: #1e293b;
}
.post-list-home a {
    color: #f8fafc;
    text-decoration: none;
    font-weight: 500;
}

/* Bottoni Moderni */
.btn {
    display: inline-block;
    padding: 10px 20px;
    background: #3b82f6;
    color: white !important;
    border-radius: 6px;
    text-decoration: none;
    font-weight: bold;
    transition: opacity 0.2s;
}
.btn:hover {
    opacity: 0.9;
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
    <div class="card" style="border-left: 5px solid #3b82f6;">
      <h3>Exam Simulator - Pro Edition v3.0</h3>
      <p>Un simulatore d'esame desktop moderno e portatile in Python (CustomTkinter). Supporto JSON/CSV e statistiche avanzate.</p>
      <br>
      <em style="color: #64748b;">Database supportati: CCNA, CCNP, CCDE.</em>
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

</div>

---

### 📝 Ultimi Articoli dal Blog
<ul class="post-list-home">
  {% for post in site.posts %}
    <li>
      <span style="color: #64748b; font-size: 0.85rem; margin-right: 10px;">{{ post.date | date: "%d/%m/%Y" }}</span>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

---

<div style="text-align: center; margin-top: 40px;">
    <a href="https://www.linkedin.com/in/david-aulicino-b9371648" target="_blank" class="btn">LinkedIn</a>
    <a href="mailto:david.aulicino@tiscali.it" class="btn" style="background: #1e293b; border: 1px solid #334155;">Contattami</a>
</div>