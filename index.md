---
layout: default
title: "Home"
---

<div class="page-content">

    <!-- HERO BIO -->
    <div class="hero-card">
        <div class="hero-avatar">DA</div>
        <div class="hero-text">
            <p class="role">Network &amp; Infrastructure Engineer</p>
            <h1>David Aulicino</h1>
            <p>Senior Network Engineer specializzato in infrastrutture critiche, SD-WAN, sicurezza perimetrale e reti distribuite. Scrivo di networking, carriera e tecnologia.</p>
        </div>
    </div>

    <div class="home-layout">

        <!-- COLONNA ARTICOLI -->
        <div>
            <p class="section-title">Articoli recenti</p>

            {% for post in site.posts %}
            <a class="post-card" href="{{ post.url | relative_url }}">
                <div class="card-top">
                    <span class="card-cat">{{ post.categories | join: " · " }}</span>
                    <span class="card-date">{{ post.date | date: "%d %b %Y" }}</span>
                </div>
                <p class="card-title">{{ post.title }}</p>
                <p class="card-excerpt">{{ post.excerpt | strip_html | truncate: 160 }}</p>
                <div class="card-footer">
                    <span class="read-more">Leggi →</span>
                </div>
            </a>
            {% endfor %}
        </div>

        <!-- SIDEBAR -->
        <div>

            <!-- STATISTICHE + SOCIAL -->
            <div class="sidebar-card" style="padding-bottom: 1.25rem;">
                <div class="stats-grid">
                    <div class="stat">
                        <span class="stat-num">{{ site.posts | size }}</span>
                        <span class="stat-label">Articoli</span>
                    </div>
                    <div class="stat">
                        <span class="stat-num">7+</span>
                        <span class="stat-label">Anni exp.</span>
                    </div>
                    <div class="stat">
                        <span class="stat-num">70+</span>
                        <span class="stat-label">Siti gestiti</span>
                    </div>
                    <div class="stat">
                        <span class="stat-num">2</span>
                        <span class="stat-label">Datacenter gestiti</span>
                    </div>
                </div>
                <div class="social-links">
                    <a class="social-link" href="https://www.linkedin.com/in/david-aulicino-b9371648" target="_blank" rel="noopener">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
                        <span>LinkedIn</span>
                    </a>
                    <a class="social-link" href="https://github.com/davidaulicino17" target="_blank" rel="noopener">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                        <span>GitHub</span>
                    </a>
                </div>
            </div>

            <!-- CERTIFICAZIONI -->
            <div class="sidebar-card">
                <h3>Certificazioni</h3>

                <p class="cert-tier-label" style="margin-top:0">⭐ Cisco — Core</p>
                <div class="cert-item tier-top">
                    <div class="cert-dot"></div>
                    <div><span class="cert-name">CCNP ENARSI 300-410</span><span class="cert-issuer">Cisco · Enterprise Advanced Infrastructure</span></div>
                </div>
                <div class="cert-item tier-top">
                    <div class="cert-dot"></div>
                    <div><span class="cert-name">CCNA 200-301</span><span class="cert-issuer">Cisco · Network Associate</span></div>
                </div>

                <p class="cert-tier-label">Cisco — Black Belt</p>
                <div class="cert-item tier-cisco"><div class="cert-dot"></div><div><span class="cert-name">Black Belt Support Stage 1</span><span class="cert-issuer">Cisco · 2025</span></div></div>
                <div class="cert-item tier-cisco"><div class="cert-dot"></div><div><span class="cert-name">Black Belt SD-WAN Deployment S1</span><span class="cert-issuer">Cisco · 2026</span></div></div>
                <div class="cert-item tier-cisco"><div class="cert-dot"></div><div><span class="cert-name">Black Belt Networking Competitive</span><span class="cert-issuer">Cisco · Feb 2026</span></div></div>
                <div class="cert-item tier-cisco"><div class="cert-dot"></div><div><span class="cert-name">Black Belt Wireless Deployment S1 &amp; S2</span><span class="cert-issuer">Cisco · 2025</span></div></div>
                <div class="cert-item tier-cisco"><div class="cert-dot"></div><div><span class="cert-name">Black Belt Meraki Deployment S1 &amp; S2</span><span class="cert-issuer">Cisco · 2026</span></div></div>
                <div class="cert-item tier-cisco"><div class="cert-dot"></div><div><span class="cert-name">Black Belt Switching Deployment S1–S3</span><span class="cert-issuer">Cisco · 2026</span></div></div>
                <div class="cert-item tier-cisco"><div class="cert-dot"></div><div><span class="cert-name">OCSE On Premise and Cloud Solutions</span><span class="cert-issuer">Cisco · 2021</span></div></div>

                <p class="cert-tier-label">Security &amp; Altri Vendor</p>
                <div class="cert-item tier-other"><div class="cert-dot"></div><div><span class="cert-name">Fortinet Certified Fundamentals Cybersecurity</span><span class="cert-issuer">Fortinet · 2024</span></div></div>
                <div class="cert-item tier-other"><div class="cert-dot"></div><div><span class="cert-name">Sophos Certified Engineer</span><span class="cert-issuer">Sophos · XG Firewall + Central</span></div></div>
                <div class="cert-item tier-other"><div class="cert-dot"></div><div><span class="cert-name">ISC2 Candidate</span><span class="cert-issuer">ISC2 · 2025–2026</span></div></div>
                <div class="cert-item tier-other"><div class="cert-dot"></div><div><span class="cert-name">Arduino Certification</span><span class="cert-issuer">Arduino · Electronics &amp; Physical Computing</span></div></div>

                <p class="cert-tier-label">VoIP &amp; Unified Comm.</p>
                <div class="cert-item tier-other"><div class="cert-dot"></div><div><span class="cert-name">YSCIS — Yeastar Integration Specialist</span><span class="cert-issuer">Yeastar · 2020</span></div></div>
                <div class="cert-item tier-other"><div class="cert-dot"></div><div><span class="cert-name">YSCRS — Yeastar Routing Specialist</span><span class="cert-issuer">Yeastar · 2020</span></div></div>
                <div class="cert-item tier-other"><div class="cert-dot"></div><div><span class="cert-name">YSCT — Yeastar Certified Technician</span><span class="cert-issuer">Yeastar · 2019</span></div></div>
                <div class="cert-item tier-other"><div class="cert-dot"></div><div><span class="cert-name">3CX Basic Certified Engineer v16</span><span class="cert-issuer">3CX · 2020</span></div></div>

                <p class="cert-tier-label">IA &amp; Vibe Coding</p>
                <div class="cert-item tier-other"><div class="cert-dot"></div><div><span class="cert-name">Replit Platform Builder</span><span class="cert-issuer">Replit · Level 1 – Beginner Builder · Mar 2026</span></div></div>
                <div class="cert-item tier-other"><div class="cert-dot"></div><div><span class="cert-name">Vibe Coding 101 with Replit</span><span class="cert-issuer">DeepLearning.AI · Mar 2026</span></div></div>
            </div>

        </div>
    </div>
</div>
