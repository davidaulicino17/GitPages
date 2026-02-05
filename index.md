---
layout: default
title: Home
---

<style>
/* 1. CONFIGURAZIONE GLOBALE */
body {
    background-color: #0f172a !important; /* Slate 900 */
    font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    color: #e2e8f0; /* Slate 200 */
}

/* 2. HERO SECTION */
.hero-section {
    text-align: center;
    padding: 60px 20px 40px 20px;
    max-width: 800px;
    margin: 0 auto;
}

.hero-title {
    font-size: 3rem;
    font-weight: 800;
    margin-bottom: 20px;
    color: #ffffff;
    line-height: 1.1;
}

.text-gradient {
    background: linear-gradient(135deg, #60a5fa 0%, #a78bfa 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.hero-subtitle {
    font-size: 1.25rem;
    color: #94a3b8; /* Slate 400 */
    line-height: 1.6;
    max-width: 600px;
    margin: 0 auto;
}

/* 3. SEZIONI E TITOLI */
.section-title {
    font-size: 1.5rem;
    font-weight: 700;
    color: #f8fafc;
    margin-top: 60px;
    margin-bottom: 30px;
    display: flex;
    align-items: center;
    gap: 12px;
}

.section-title::after {
    content: "";
    flex: 1;
    height: 1px;
    background: #334155;
    margin-left: 15px;
}

/* 4. GRIGLIA GENERICA (Usata per Labs e Software) */
.grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 24px;
}

/* 5. CARD DESIGN BASE */
.card {
    background: #1e293b; /* Slate 800 */
    padding: 24px; 
    border-radius: 12px;
    border: 1px solid rgba(255, 255, 255, 0.05);
    height: 100%; 
    display: flex;
    flex-direction: column;
    justify-content: center;
    transition: all 0.3s ease;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.card-link {
    text-decoration: none;
    display: block;
    height: 100%;
}

.card-link:hover .card, .card:hover {
    transform: translateY(-4px);
    border-color: #3b82f6;
    box-shadow: 0 10px 30px -10px rgba(59, 130, 246, 0.2);
}

.card h3 {
    margin-top: 0;
    font-size: 1.15rem;
    font-weight: 600;
    color: #ffffff !important;
    margin-bottom: 6px;
}

.card p {
    font-size: 0.95rem;
    color: #cbd5e1 !important;
    margin-bottom: 0;
    line-height: 1.5;
}

/* 6. NUOVO STILE CERTIFICAZIONI (Lista Verticale) */
.cert-list {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.cert-card {
    background: linear-gradient(to right, #1e293b, #0f172a);
    padding: 18px 24px;
    border-radius: 10px;
    border: 1px solid #334155;
    border-left-width: 5px; /* Bordo colorato a sinistra */
    display: flex;
    flex-direction: column; /* Mobile first */
    transition: transform 0.2s ease;
}

.cert-card:hover {
    transform: translateX(5px);
    background: #1e293b;
}

/* Desktop: Layout orizzontale per le cert */
@media (min-width: 600px) {
    .cert-card {
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }
}

.cert-vendor {
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: 700;
    color: #94a3b8;
    margin-bottom: 4px;
    display: block;
}

.cert-name {
    font-size: 1.1rem;
    font-weight: 600;
    color: #ffffff;
    margin: 0;
}

.cert-details {
    font-size: 0.9rem;
    color: #cbd5e1;
}

/* Colori specifici per Vendor (Bordo sinistro) */
.border-cisco { border-left-color: #2563eb; }    /* Blue */
.border-fortinet { border-left-color: #ef4444; } /* Red */
.border-sophos { border-left-color: #3b82f6; }   /* Blue Light */
.border-arduino { border-left-color: #0d9488; }  /* Teal */
.border-yeastar { border-left-color: #f97316; }  /* Orange */
.border-isc2 { border-left-color: #10b981; }     /* Green */
.border-3cx { border-left-color: #0ea5e9; }      /* Sky Blue */

/* Card Speciale (Software) */
.card-featured {
    border-left: 5px solid #3b82f6;
    background: linear-gradient(to right, #1e293b, #0f172a);
}

/* 7. LISTA ARTICOLI BLOG */
.post-list-modern {
    list-style: none;
    padding: 0;
}

.post-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 16px;
    border-bottom: 1px solid #334155;
    transition: background 0.2s;
}

.post-item:hover {
    background: rgba(59, 130, 246, 0.1);
    border-radius: 8px;
    border-bottom-color: transparent;
}

.post-date {
    font-size: 0.85rem;
    color: #64748b;
    font-family: monospace;
    min-width: 100px;
}

.post-link {
    color: #3b82f6 !important;
    text-decoration: none;
    font-weight: 600;
    font-size: 1.05rem;
    flex-grow: 1;
}

.post-link:hover {
    text-decoration: underline;
}

/* 8. BOTTONI */
.btn-group {
    margin-top: 60px;
    text-align: center;
    display: flex;
    justify-content: center;
    gap: 15px;
}

.btn {
    display: inline-block;
    padding: 12px 30px;
    border-radius: 50px;
    text-decoration: none;
    font-weight: 600;
    transition: all 0.2s;
}

.btn-primary {
    background: #2563eb;
    color: #ffffff !important;
    box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
}
.btn-primary:hover {
    background: #1d4ed8;
    transform: translateY(-2px);
}

.btn-secondary {
    background: transparent;
    border: 1px solid #475569;
    color: #cbd5e1 !important;
}
.btn-secondary:hover {
    border-color: #cbd5e1;
    background: rgba(255, 255, 255, 0.05);
}

/* Nasconde elementi Markdown standard non desiderati */
h1, hr { display: none; }
</style>

<div class="hero-section">
    <div class="hero-title">Ciao, sono <span class="text-gradient">David Aulicino</span> 🇮🇹</div>
    <div class="hero-subtitle">
        Benvenuto nel mio spazio personale.<br>
        Sono un <strong>Network & Infrastructure Engineer</strong> appassionato di reti, sicurezza informatica ed elettronica.
    </div>
</div>

<h2 class="section-title">🏅 Certificazioni</h2>
<div class="cert-list">

  <a href="https://www.cisco.com/c/en/us/training-events/training-certifications/certifications/professional/ccnp-enterprise.html" target="_blank" style="text-decoration:none;">
    <div class="cert-card border-cisco">
      <div>
        <span class="cert-vendor">Cisco</span>
        <h3 class="cert-name">CCNP ENARSI 300-410</h3>
      </div>
      <div class="cert-details">Enterprise Advanced Routing</div>
    </div>
  </a>

  <a href="https://www.cisco.com/c/en/us/training-events/training-certifications/certifications/associate/ccna.html" target="_blank" style="text-decoration:none;">
    <div class="cert-card border-cisco">
      <div>
        <span class="cert-vendor">Cisco</span>
        <h3 class="cert-name">CCNA 200-301</h3>
      </div>
      <div class="cert-details">Network Associate</div>
    </div>
  </a>

  <div class="cert-card border-cisco">
      <div>
        <span class="cert-vendor">Cisco</span>
        <h3 class="cert-name">OCSE 500-560</h3>
      </div>
  </div>

  <div class="cert-card border-cisco">
      <div>
        <span class="cert-vendor">Cisco - Black Belt</span>
        <h3 class="cert-name">Switching Deployment</h3>
      </div>
      <div class="cert-details">Stage 1, 2, 3</div>
  </div>

  <div class="cert-card border-cisco">
      <div>
        <span class="cert-vendor">Cisco - Black Belt</span>
        <h3 class="cert-name">Meraki Deployment</h3>
      </div>
      <div class="cert-details">Stage 1, 2</div>
  </div>

  <div class="cert-card border-cisco">
      <div>
        <span class="cert-vendor">Cisco - Black Belt</span>
        <h3 class="cert-name">Wireless Deployment</h3>
      </div>
      <div class="cert-details">Stage 1 (Apr 2025)</div>
  </div>

  <div class="cert-card border-fortinet">
      <div>
        <span class="cert-vendor">Fortinet</span>
        <h3 class="cert-name">Certified Fundamentals Cybersecurity</h3>
      </div>
  </div>

  <div class="cert-card border-sophos">
      <div>
        <span class="cert-vendor">Sophos</span>
        <h3 class="cert-name">Sophos Certified Engineer</h3>
      </div>
  </div>

  <div class="cert-card border-sophos">
      <div>
        <span class="cert-vendor">Sophos</span>
        <h3 class="cert-name">ET80 - XG Firewall v18.0</h3>
      </div>
      <div class="cert-details">Engineer</div>
  </div>

  <div class="cert-card border-sophos">
      <div>
        <span class="cert-vendor">Sophos</span>
        <h3 class="cert-name">ET01 - Central Overview</h3>
      </div>
      <div class="cert-details">Engineer</div>
  </div>

  <div class="cert-card border-yeastar">
      <div>
        <span class="cert-vendor">Yeastar</span>
        <h3 class="cert-name">YSCRS - Routing Specialist</h3>
      </div>
  </div>

  <div class="cert-card border-yeastar">
      <div>
        <span class="cert-vendor">Yeastar</span>
        <h3 class="cert-name">YSCIS - Integration Specialist</h3>
      </div>
  </div>

  <div class="cert-card border-yeastar">
      <div>
        <span class="cert-vendor">Yeastar</span>
        <h3 class="cert-name">YSCT - Certified Technician</h3>
      </div>
  </div>

  <div class="cert-card border-arduino">
      <div>
        <span class="cert-vendor">Arduino</span>
        <h3 class="cert-name">Arduino Certification</h3>
      </div>
      <div class="cert-details">Electronics & Physical Computing</div>
  </div>

  <div class="cert-card border-3cx">
      <div>
        <span class="cert-vendor">3CX</span>
        <h3 class="cert-name">Basic Certified Engineer v16</h3>
      </div>
  </div>

  <div class="cert-card border-isc2">
      <div>
        <span class="cert-vendor">ISC2</span>
        <h3 class="cert-name">ISC2 Candidate</h3>
      </div>
  </div>

</div>

<h2 class="section-title">💻 Software & Tools</h2>
<div class="grid-container" style="grid-template-columns: 1fr;"> 
  <a href="https://github.com/davidaulicino17/EXAM-SIMULATOR-PUBLIC" class="card-link" target="_blank">
    <div class="card card-featured">
      <h3>Exam Simulator - Pro Edition v3.0</h3>
      <p>Simulatore d'esame desktop moderno in Python (CustomTkinter). Supporto JSON/CSV e statistiche avanzate.</p>
      <div style="margin-top: 10px; font-size: 0.85rem; color: #94a3b8;">
        📂 Database: CCNA, CCNP, CCDE
      </div>
    </div>
  </a>
</div>

<h2 class="section-title">🧪 Laboratori PNetLab</h2>
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

<h2 class="section-title">📝 Ultimi Articoli</h2>
<ul class="post-list-modern">
  {% for post in site.posts limit:5 %}
    <li class="post-item">
      <span class="post-date">{{ post.date | date: "%d/%m/%Y" }}</span>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

<div class="btn-group">
    <a href="https://www.linkedin.com/in/david-aulicino-b9371648" target="_blank" class="btn btn-primary">LinkedIn</a>
    <a href="mailto:david.aulicino@tiscali.it" class="btn btn-secondary">Contattami</a>
</div>