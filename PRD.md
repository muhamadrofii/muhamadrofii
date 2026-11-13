# Technical Specification: GitHub Profile Architecture

- **Project**: Developer Profile Landing Architecture
- **Repository**: `muhamadrofii/muhamadrofii`
- **Owner**: Muhamad Rofi'i (`muhamadrofii911@gmail.com`)
- **Role Positioning**: Software Engineer & Automation
- **Version**: 2.5.0
- **Status**: Production

---

## 1. System Objective & Scope

This specification defines the functional, structural, and integration requirements for the root GitHub Profile README (`muhamadrofii/muhamadrofii`). 

The architecture deploys an ultra-minimalist, high-signal developer portfolio:
1. **Zero Tacky Emojis**: Replaced with canonical Simple Icons and clean typographic hierarchy.
2. **Compact Card Grid Layout**: Projects structured in a responsive 2-column HTML grid with subtle borders, title anchors, and inline stack chips.
3. **Scaled Single-Card Telemetry**: Scaled to 520px width to match the header typewriter width and maintain vertical discipline.

---

## 2. Architecture & Telemetry Pipeline

```mermaid
flowchart TD
    subgraph Client["GitHub Web / Mobile Client"]
        GH[Profile View: github.com/muhamadrofii]
    end

    subgraph CDN["Edge & Service Pipelines"]
        SVG[Typing SVG Engine]
        PVC[Page View Counter]
        SI[Shields.io Badge Gateway]
        GPSC[GitHub Profile Summary Engine]
    end

    subgraph DataSources["GitHub GraphQL / REST APIs"]
        API[api.github.com/users/muhamadrofii]
        EVT[Public Event Streams & Contributions]
    end

    GH --> SVG
    GH --> PVC
    GH --> SI
    GH --> GPSC

    GPSC --> API
    GPSC --> EVT
```

---

## 3. Structural & Component Requirements

### 3.1 Hero Header & Identity
1. **Dynamic Vector Typewriter**:
   - Provider: `readme-typing-svg.demolab.com`
   - Parameters: `font=JetBrains+Mono&weight=500&size=20&pause=1500&color=38BDF8&center=true&vCenter=true&width=560`
   - Key Lines:
     - `Software Engineer & Automation`
     - `Full-Stack Web, Mobile & Data Pipelines`
     - `Nuxt 3 • Laravel • Django • Flutter`
     - `Headless Browser Automation & Scraping`
2. **Metadata & Status Badges**:
   - Page view counter (`komarev.com/ghpvc/`, `color=0284c7`, `style=flat-square`).
   - Specialization badge: `Focus-Software_Engineer_%26_Automation`.
3. **Verified Contact Gateways**:
   - Direct links with flat-square brand badges for Email, LinkedIn, and GitHub.

### 3.2 Technical Taxonomy (Shields.io + Simple Icons)

| Domain | Stack | Canonical Icon Key |
| :--- | :--- | :--- |
| **Languages** | JavaScript, TypeScript, Python, PHP, Dart, HTML5, CSS3, SQL | `javascript`, `typescript`, `python`, `php`, `dart`, `html5`, `css3`, `postgresql` |
| **Automation & Tools** | Playwright, Python Automation, Git, GitHub, Postman, Figma | `playwright`, `python`, `git`, `github`, `postman`, `figma` |
| **Backend & APIs** | Laravel, Django, Node.js, Express, Strapi | `laravel`, `django`, `nodedotjs`, `express`, `strapi` |
| **Frontend & Mobile** | Vue.js, Nuxt 3, Flutter, Tailwind CSS, Bootstrap | `vuedotjs`, `nuxtdotjs`, `flutter`, `tailwindcss`, `bootstrap` |
| **Storage & Databases** | MySQL, PostgreSQL, SQLite | `mysql`, `postgresql`, `sqlite` |

### 3.3 2-Column Project Grid
Structured as a symmetrical 2x3 responsive table tile grid:
- **Col 1 / Row 1**: Scraping & Automation (`Python`, `Playwright`)
- **Col 2 / Row 1**: Bank Sampah Platform (`Flutter`, `Node.js`)
- **Col 1 / Row 2**: Smart City Mobile (`Flutter`, `Dart`)
- **Col 2 / Row 2**: Nuxt 3 Portfolio & CMS (`Nuxt 3`, `Strapi`)
- **Col 1 / Row 3**: SIMKODES (Info Desa) (`Laravel`, `MySQL`)
- **Col 2 / Row 3**: X Social Scraper (`Python`, `Playwright`)

### 3.4 Scaled Telemetry Card
- **Component**: `github-profile-summary-cards.vercel.app/api/cards/profile-details?username=muhamadrofii&theme=tokyonight`
- **Render Width**: `520px` (scaled from 700px native viewBox)
- **Rendered Metrics**: Total annual contributions, repository count, account longevity, and chronological activity wave curve.

---

## 4. Performance & Reliability

1. **Reduced HTTP Footprint**: Eliminating stacked secondary widgets reduces edge requests and eliminates layout shift.
2. **Edge Caching**: Upstream HTTP cache TTL (4 hours) ensures responsive rendering and zero rate-limiting overhead.
