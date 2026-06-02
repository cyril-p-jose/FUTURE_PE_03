# GrowthSpark — AI SEO Blog & Content Cluster Generator

A modern, professional SaaS dashboard for SEO agencies and digital marketers. Built to demonstrate prompt engineering, content cluster strategy, and modern React UI patterns.

**Live Demo:** [GrowthSpark Studio](https://promptspark-seo.lovable.app)

---

## What It Is

GrowthSpark is a portfolio-ready SaaS prototype that helps SEO teams plan, generate, and export content clusters using AI-powered prompt engineering workflows. It simulates a real SEO agency platform with keyword research, pillar blog generation, supporting cluster management, local SEO optimisation, internal linking visualisation, and analytics tracking.

> **Note:** This is a frontend demonstration. All "AI generation" buttons trigger toast notifications — there is no live AI backend connected. It is designed to showcase UI/UX architecture, design systems, and SEO workflow automation concepts.

---

## Features

| Module | Description |
|--------|-------------|
| **Keyword Research** | Intent-grouped keyword discovery with volume, difficulty, and filtering |
| **Pillar Blog Generator** | Full SEO brief with titles, meta, outlines, article preview, FAQ schema, and CTA |
| **Supporting Blog Clusters** | 5+ supporting blogs with difficulty scoring, traffic estimates, and internal link targets |
| **Local SEO** | City-based keyword insertion, GBP optimisation tips, and LocalBusiness schema generation |
| **Internal Linking Visualiser** | SVG node map showing pillar → cluster connections with anchor text recommendations |
| **Prompt Library** | 6 reusable, parameter-driven SEO prompts with copy-to-clipboard |
| **Analytics Dashboard** | Traffic trends, keyword rankings, content scores, and optimisation breakdowns |
| **Export Hub** | PDF, Markdown, and SEO Pack export options |
| **Settings** | Workspace config, AI model toggles, and integration placeholders |

---

## Tech Stack

- **Framework:** React 19 + TypeScript
- **Router:** TanStack Start (file-based routing)
- **State & Data:** TanStack Query
- **Styling:** Tailwind CSS v4
- **UI Components:** shadcn/ui
- **Icons:** Lucide React
- **Notifications:** Sonner (toast)
- **Build Tool:** Vite 7

---

## Design System

Custom glassmorphism design system with violet/indigo gradient theming:

- **Primary gradient:** `oklch(0.55 0.22 268)` → `oklch(0.7 0.2 295)`
- **Glass surfaces:** Backdrop-filter blur with translucent gradients
- **Glow shadows:** Soft violet glows on primary elements
- **Animations:** Fade-up entry, float hover, pulse-glow accents
- **Dark mode:** Full theme inversion with adjusted contrast ratios
- **Responsive:** Collapsible sidebar, stacked grids on mobile

---

## Project Structure

```
src/
├── components/
│   ├── app-sidebar.tsx        # Collapsible nav sidebar (Workspace + Tools groups)
│   ├── dashboard-header.tsx   # Sticky header with title, upgrade, theme toggle
│   ├── theme-provider.tsx     # Light/dark mode context with localStorage persistence
│   └── ui/                    # shadcn/ui components
├── lib/
│   └── seo-data.ts            # Demo data: pillar blog, clusters, keywords, prompts
├── routes/
│   ├── __root.tsx             # Root layout with QueryClient + ThemeProvider
│   ├── index.tsx              # Landing page (marketing site)
│   ├── dashboard.tsx          # Dashboard layout wrapper (Sidebar + Outlet)
│   ├── dashboard.index.tsx    # Dashboard home (stats, cluster progress, activity)
│   ├── dashboard.pillar.tsx   # Pillar blog generator
│   ├── dashboard.supporting.tsx # Supporting blog cluster cards
│   ├── dashboard.keywords.tsx # Keyword research table
│   ├── dashboard.local-seo.tsx # Local SEO tools + schema
│   ├── dashboard.linking.tsx  # Internal linking SVG visualiser
│   ├── dashboard.prompts.tsx  # Prompt library with search
│   ├── dashboard.analytics.tsx # Performance charts + metrics
│   ├── dashboard.export.tsx   # Export options hub
│   └── settings.tsx           # Workspace + AI + integrations settings
├── styles.css                 # Tailwind v4 theme tokens + custom utilities
└── router.tsx                 # TanStack Router bootstrap
```

---

## Getting Started

### Prerequisites

- Node.js 20+
- bun (recommended) or npm

### Installation

```bash
# Clone the repository
git clone <repo-url>
cd growthspark-seo

# Install dependencies
bun install

# Start the development server
bun run dev
```

The app will be available at `http://localhost:3000`.

### Build for Production

```bash
bun run build
```

---

## Demo Content

All demo content is centred around **GrowthSpark Digital**, a fictional SEO agency based in **Kochi, Kerala, India**.

- **Primary keyword:** "digital marketing agency in Kochi" (Vol 4,400, KD 46)
- **Market focus:** Kerala D2C brands, SaaS startups, hospitality groups
- **Pricing:** ₹0 / ₹2,490 / Custom (Indian Rupee, realistic local pricing)
- **Local context:** Malayalam-aware content, Kochi/Ernakulam geo-targeting, India-specific SEO examples

This makes the demo feel authentic for Indian SEO agencies and freelancers while remaining adaptable to any market.

---

## Key Design Decisions

1. **File-based routing** — Every page is a route file under `src/routes/`. TanStack Router auto-generates the route tree.
2. **Semantic design tokens** — All colours use CSS custom properties (`oklch`) for perfect light/dark mode switching.
3. **No real AI backend** — The prompt is for a **portfolio/demo** project. Buttons trigger toasts to simulate AI responses without API costs.
4. **Glassmorphism cards** — Every card uses `.bg-glass` with backdrop blur for a premium SaaS feel.
5. **Staggered animations** — Cards animate in with `animate-fade-up` and incremental delays for a polished load experience.

---

## Screenshots

| Landing Page | Dashboard | Pillar Generator |
|-------------|-----------|------------------|
| Marketing site with hero, features, pricing | Stats cards + cluster progress | SEO brief + outline tabs |

| Keyword Research | Local SEO | Internal Linking |
|------------------|-----------|------------------|
| Intent-grouped keyword table | City selector + GBP tips | SVG node map visualisation |

---

## Roadmap (Future Enhancements)

- [ ] Connect live AI API (OpenAI / Claude) for real generation
- [ ] Add user authentication and workspace persistence
- [ ] Implement actual PDF/Markdown export generation
- [ ] Add content calendar and scheduling
- [ ] Team collaboration and comment threads
- [ ] Integration webhooks for WordPress, Notion, Webflow

---

## Author

**GrowthSpark Digital** — Kochi, Kerala, India

Built as a portfolio showcase for:
- SEO agency demos
- Internship submissions
- Freelance portfolio pieces
- SaaS startup prototypes

---

## License

MIT License — feel free to fork, adapt, and use as a foundation for your own SEO tools.
