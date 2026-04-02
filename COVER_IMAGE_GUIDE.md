# Come usare cover_image nei post

Aggiungi `cover_image` nel front matter **solo** per i post che hanno un'immagine di copertina.
Se non la aggiungi, l'immagine non verrà mostrata.

## Esempio CON immagine:

```yaml
---
layout: post
title: "Come effettuare rollback su Cisco IOS"
date: 2026-01-04
author: "David Aulicino"
categories: [Networking, Cisco]
tags: [Cisco, CCNP, IOS, Networking]
cover_image: /assets/images/rollback_cisco/screenshot_cisco.png
---
```

## Esempio SENZA immagine:

```yaml
---
layout: post
title: "L'arte di essere invisibili"
date: 2025-12-30
author: "David Aulicino"
categories: [Carriera, Riflessioni]
tags: [Network Engineer, Carriera]
---
```

## Post con immagine di copertina disponibile:

| Post | Cover Image |
|------|-------------|
| Come effettuare rollback su Cisco IOS | `/assets/images/rollback_cisco/screenshot_cisco.png` |
| Networking al confine del mondo (SD-WAN) | `/assets/images/eolico/wind_cover.png` |

## Post SENZA immagine di copertina:

- L'arte di essere invisibili
- Dalla Cornetta al Core Network
- Smettere di studiare è l'inizio del downtime
- Oltre la CLI: simulazioni roleplay AI
- Dirigere un team
- Modem, Router e Firewall
