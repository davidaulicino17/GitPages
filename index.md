---
layout: default
title: Home
---

# Ciao, sono David Aulicino 👋

Benvenuto nel mio spazio personale.
Sono un **Network & Infrastructure Engineer** con base in Italia, appassionato di reti, sicurezza informatica ed elettronica.

Attualmente lavoro presso **NADARA Spa**, gestendo infrastrutture critiche e distribuite (Cisco, Palo Alto, Fortigate).

---

### 🏆 Certificazioni
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

<div class="card" style="border-left: 5px solid #3b9cff;">
  <h3>Exam Simulator - Pro Edition v3.0</h3>
  <p>Un simulatore d'esame desktop moderno e portatile in Python (CustomTkinter). Nessuna installazione, supporto JSON/CSV, Dark Mode e statistiche avanzate.</p>
  <br>
  <em>Database supportati: CCNA, CCNP, CCDE.</em>
</div>

---

### 🔬 Laboratori di Networking (PNetLab)
<div class="grid-container">
  <div class="card">
    <h3>Design OSPF Scalabile</h3>
    <p>Analisi comparativa Single-Area vs. Multi-Area e impatto sulla stabilità LSDB.</p>
  </div>
  <div class="card">
    <h3>Fabric L3 Spine-Leaf</h3>
    <p>Data Center Fabric con OSPF come underlay e BGP per la distribuzione rotte.</p>
  </div>
  <div class="card">
    <h3>Greenfield DC con EVPN</h3>
    <p>Architettura moderna con MP-BGP EVPN per overlay e control plane.</p>
  </div>
  <div class="card">
    <h3>Nexus vPC & LACP</h3>
    <p>Alta affidabilità e aggregazione di banda su switch Cisco Nexus.</p>
  </div>
  <div class="card">
    <h3>DCI con VXLAN Statico</h3>
    <p>Estensione L2 tra siti (Data Center Interconnect) via tunnel VXLAN.</p>
  </div>
</div>

---

### 📝 Ultimi Articoli dal Blog
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a> - 
      <small style="color: #888;">{{ post.date | date: "%d/%m/%Y" }}</small>
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
[LinkedIn](https://www.linkedin.com/in/david-aulicino-b9371648) | [Contattami](mailto:david.aulicino@tiscali.it)
