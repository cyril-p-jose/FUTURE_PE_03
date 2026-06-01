# AI SEO Blog & Content Cluster Generator — Complete Build Prompt

## Project Overview

Build a modern, professional, responsive web application called **"GrowthSpark — AI SEO Studio"**. It is a SaaS dashboard used by SEO agencies and digital marketers. The platform helps users plan pillar blogs, generate supporting content clusters, research keywords, optimise local SEO, visualise internal linking, manage reusable AI prompts, track analytics, and export content packs.

The brand identity is **GrowthSpark Digital**, an agency based in Kochi, Kerala, India.

## Tech Stack

- React 19 + TypeScript
- TanStack Start (file-based routing, `src/routes/`)
- TanStack Router + TanStack Query
- Tailwind CSS v4 (`src/styles.css` with `@theme inline` tokens)
- shadcn/ui components (Button, Card, Badge, Input, Textarea, Tabs, Select, Progress, Switch, Label, Separator, Sidebar, Sonner toast)
- Lucide React icons
- No actual AI backend — all "Generate" buttons trigger `toast.success()` and/or `console.log()`

## Design System (EXACT TOKENS — copy verbatim)

Define ALL of these in `src/styles.css` using Tailwind CSS v4 syntax:

### Theme Variables
- `--radius: 0.875rem`
- Light mode background: `oklch(0.99 0.005 250)`
- Light mode foreground: `oklch(0.18 0.04 265)`
- Primary: `oklch(0.55 0.22 268)` with foreground `oklch(0.99 0 0)`
- Primary glow: `oklch(0.7 0.2 295)`
- Muted: `oklch(0.96 0.01 260)` with foreground `oklch(0.5 0.03 260)`
- Accent: `oklch(0.94 0.04 280)` with foreground `oklch(0.3 0.1 280)`
- Success: `oklch(0.65 0.16 155)`
- Warning: `oklch(0.78 0.16 75)`
- Dark mode background: `oklch(0.14 0.025 265)`
- Dark mode primary: `oklch(0.72 0.2 285)`

### CSS Custom Properties (both modes)
- `--gradient-primary: linear-gradient(135deg, oklch(0.55 0.22 268), oklch(0.7 0.2 295))`
- `--gradient-hero: radial-gradient(ellipse at top, oklch(0.7 0.2 295 / 0.25), transparent 60%), radial-gradient(ellipse at bottom left, oklch(0.55 0.22 268 / 0.18), transparent 50%)`
- `--gradient-glass: linear-gradient(135deg, oklch(1 0 0 / 0.7), oklch(1 0 0 / 0.4))` (dark: `/0.06` and `/0.02`)
- `--shadow-glow: 0 20px 60px -20px oklch(0.55 0.22 268 / 0.4)` (dark: `/0.45`)
- `--shadow-soft: 0 10px 30px -10px oklch(0.3 0.1 265 / 0.15)` (dark: `oklch(0 0 0 / 0.5)`)

### Utility Classes
Register these in `@layer utilities`:
- `.bg-gradient-primary` → uses `--gradient-primary`
- `.bg-gradient-hero` → uses `--gradient-hero`
- `.bg-glass` → uses `--gradient-glass` + `backdrop-filter: blur(16px)`
- `.shadow-glow` → uses `--shadow-glow`
- `.shadow-soft` → uses `--shadow-soft`
- `.text-gradient` → `--gradient-primary` with `-webkit-background-clip: text`
- `.grid-bg` → subtle grid pattern using `oklch(0.55 0.22 268 / 0.07)` lines at `48px` spacing
- `.animate-float` → `float` keyframe (6s, translateY 0 to -12px)
- `.animate-fade-up` → `fade-up` keyframe (0.6s, opacity 0→1, translateY 16px→0)
- `.animate-pulse-glow` → `pulse-glow` keyframe (3s, box-shadow pulse)

## Data File (`src/lib/seo-data.ts`)

Create this file with EXACT data:

```ts
export const pillarBlog = {
  title: "Best Digital Marketing Agency in Kochi: The 2026 Definitive Guide",
  metaTitle: "Best Digital Marketing Agency in Kochi (2026) — GrowthSpark",
  metaDescription: "Looking for the best digital marketing agency in Kochi? Compare strategy, SEO, and ROI from Kerala's top performance agencies in our 2026 guide.",
  slug: "best-digital-marketing-agency-in-kochi",
  primaryKeyword: "digital marketing agency in Kochi",
  intent: "Commercial",
  score: 92,
  wordCount: 2840,
  outline: [
    { tag: "H1", text: "Best Digital Marketing Agency in Kochi: The 2026 Definitive Guide" },
    { tag: "H2", text: "Why Kochi Businesses Need a Specialised Digital Partner" },
    { tag: "H3", text: "The Kerala digital landscape in 2026" },
    { tag: "H3", text: "What separates Kochi's top agencies" },
    { tag: "H2", text: "Core Services to Expect From a Top Agency" },
    { tag: "H3", text: "SEO & local search dominance" },
    { tag: "H3", text: "Performance marketing & paid media" },
    { tag: "H3", text: "Content strategy & brand storytelling" },
    { tag: "H2", text: "How to Evaluate an Agency Before You Sign" },
    { tag: "H2", text: "Pricing, Contracts & ROI Benchmarks in Kerala" },
    { tag: "H2", text: "Frequently Asked Questions" },
  ],
  preview: `Choosing a digital marketing agency in Kochi in 2026 is no longer about flashy decks...`, // (truncated in output, use full text from source)
  faqs: [
    { q: "How much does a digital marketing agency in Kochi typically cost?", a: "Retainers in Kochi range from ₹35,000 for boutique SEO engagements to ₹3,50,000+ per month..." },
    { q: "How long before I see SEO results in Kerala's market?", a: "Most Kochi SMBs see meaningful keyword movement within 90 days..." },
    { q: "Should I hire a Kochi agency or a remote one?", a: "Local agencies win on cultural nuance, Malayalam-friendly content..." },
  ],
};

export const supportingBlogs = [
  { title: "Why Local SEO Matters for Small Businesses in Kerala", keyword: "local SEO Kerala", intent: "Informational", difficulty: 32, traffic: "1.4K / mo", link: "/best-digital-marketing-agency-in-kochi#local-seo" },
  { title: "SEO Services in Kochi Explained: What You Actually Pay For", keyword: "SEO services in Kochi", intent: "Commercial", difficulty: 41, traffic: "2.1K / mo", link: "/best-digital-marketing-agency-in-kochi#services" },
  { title: "Social Media Marketing for Kerala Businesses in 2026", keyword: "social media marketing Kerala", intent: "Informational", difficulty: 28, traffic: "980 / mo", link: "/best-digital-marketing-agency-in-kochi#channels" },
  { title: "7 Common SEO Mistakes That Cost Kochi Brands Rankings", keyword: "SEO mistakes Kochi", intent: "Informational", difficulty: 24, traffic: "620 / mo", link: "/best-digital-marketing-agency-in-kochi#checklist" },
  { title: "How to Choose the Right Digital Marketing Agency", keyword: "choose digital marketing agency", intent: "Transactional", difficulty: 47, traffic: "3.3K / mo", link: "/best-digital-marketing-agency-in-kochi#evaluate" },
];

export const keywords = [
  { kw: "digital marketing agency in Kochi", vol: 4400, kd: 46, intent: "Commercial" },
  { kw: "SEO services in Kochi", vol: 2900, kd: 41, intent: "Commercial" },
  { kw: "local SEO Kerala", vol: 1300, kd: 32, intent: "Informational" },
  { kw: "best SEO company Ernakulam", vol: 880, kd: 38, intent: "Transactional" },
  { kw: "content marketing agency Kochi", vol: 720, kd: 29, intent: "Commercial" },
  { kw: "Google Ads agency Kerala", vol: 1600, kd: 44, intent: "Transactional" },
  { kw: "AI content writing services India", vol: 5300, kd: 52, intent: "Commercial" },
  { kw: "how to rank on Google in Kerala", vol: 410, kd: 18, intent: "Informational" },
];

export const prompts = [
  { title: "SEO Pillar Blog Generator", category: "Content", body: "Act as a senior SEO content strategist. Write a 2,500-word pillar blog targeting the keyword '{KEYWORD}' for a {INDUSTRY} audience in {LOCATION}. Include an SEO title under 60 chars, meta description under 155 chars, H2/H3 outline, internal link anchors, and an FAQ section with schema-ready Q&As." },
  { title: "Local SEO Optimisation", category: "Local", body: "You are a local SEO specialist. Produce a Google Business Profile optimisation plan for a {BUSINESS_TYPE} in {CITY}. Include 10 location-specific keyword variations, 5 GBP post ideas, NAP consistency checklist, and a LocalBusiness schema snippet." },
  { title: "Keyword Cluster Builder", category: "Research", body: "Generate a topical cluster for the seed keyword '{KEYWORD}'. Group keywords by search intent (informational, commercial, transactional). Output a table with keyword, intent, monthly volume estimate, and the cluster page it should live on." },
  { title: "FAQ Schema Generator", category: "Technical", body: "From the article below, extract 6 high-intent questions and write concise, 40–60 word answers optimised for Google's FAQ rich result. Output as valid FAQPage JSON-LD.\n\nARTICLE:\n{ARTICLE}" },
  { title: "Meta Description Rewriter", category: "On-Page", body: "Rewrite the meta description below to be under 155 characters, include the primary keyword '{KEYWORD}', a benefit, and a soft CTA. Provide 3 variants ranked by predicted CTR.\n\nCURRENT:\n{META}" },
  { title: "Internal Linking Strategist", category: "Architecture", body: "Given this list of published URLs and their target keywords, propose an internal linking map. For each URL recommend 3–5 contextual anchor texts and the destination pages, prioritising pages with commercial intent.\n\nPAGES:\n{LIST}" },
];
```

## Shared Components

### `src/components/theme-provider.tsx`
Create a React context that:
- Reads `localStorage.getItem("theme")` on mount (defaults to system preference)
- Toggles `"light" | "dark"` class on `document.documentElement`
- Persists choice to `localStorage`
- Exports `useTheme()` hook returning `{ theme, toggle }`

### `src/components/app-sidebar.tsx`
Use shadcn `<Sidebar>` with groups "Workspace" and "Tools". Navigation items:

**Workspace:**
- Dashboard → `/dashboard`
- Keyword Research → `/dashboard/keywords`
- Pillar Blog Generator → `/dashboard/pillar`
- Supporting Blogs → `/dashboard/supporting`
- Local SEO → `/dashboard/local-seo`

**Tools:**
- Prompt Library → `/dashboard/prompts`
- Internal Linking → `/dashboard/linking`
- Analytics → `/dashboard/analytics`
- Export Content → `/dashboard/export`

**Footer:** Settings → `/settings`

Sidebar header shows a Zap icon in a gradient rounded square + "GrowthSpark / AI SEO Studio". Each item uses `isActive` matching current route.

### `src/components/dashboard-header.tsx`
Sticky header with:
- `<SidebarTrigger />`
- Title + optional subtitle
- "Upgrade" button with Sparkles icon
- Theme toggle button (Moon/Sun based on current theme)

## Routes (create ALL of these in `src/routes/`)

### `/` — Landing Page (`index.tsx`)
Full marketing page with:
1. **Header:** Sticky nav with logo, links to `#features`, `#workflow`, `#pricing`, Analytics, Sign in + "Open Studio" CTA buttons
2. **Hero:** Dual radial gradient background + `.grid-bg` overlay. Badge "Powered by Prompt Engineering · GPT-class models". H1 with `.text-gradient` on "SEO Content Clusters". Subheadline about planning pillar blogs and clusters in minutes. Two CTAs: "Launch the Studio" (primary) and "See sample output" (outline). Trust badges: "No credit card", "GPT-class prompts", "Export to Markdown / PDF". Below: a glassmorphism mockup card showing a browser chrome with 3 preview cards (Primary keyword, Pillar draft, Cluster) and meta/outline preview.
3. **Logos strip:** "Trusted by content teams across Kerala & India" with 6 fictional brand names.
4. **Features (`#features`):** 6 feature cards in a 3-column grid with gradient icon circles: Keyword Research, Pillar Blog Generator, Supporting Clusters, Local SEO, Internal Linking Map, Prompt Library. Each with hover lift + shadow-soft + fade-up animation.
5. **Workflow (`#workflow`):** 4 steps (01–04) in a 4-column grid: Seed a keyword → Generate cluster → Refine with prompts → Export & ship.
6. **Pricing (`#pricing`):** 3 tiers — Starter (₹0/mo), Studio (₹2,490/mo, featured with glow border + "Most popular" badge), Agency (Custom). Each lists features with checkmarks.
7. **CTA section:** Gradient background card "Ready to ship your first SEO cluster?" with secondary button.
8. **Footer:** "GrowthSpark Digital · Kochi, Kerala" + nav links + copyright.

### `/dashboard` — Dashboard Home (`dashboard.index.tsx`)
- 4 stat cards: Organic traffic (48,210, +24.6%), Tracked keywords (1,284), Content score (92/100), Pillar coverage (76%)
- Active content cluster card (2/3 width): 5 cluster rows with progress bars and status labels (Pillar 92% Ready, others Draft/Outline/Queued)
- Quick actions card (1/3): Links to Pillar, Keywords, Prompts, Local SEO
- Recent activity list: 4 items with tags (Pillar, Cluster, Local, Prompt) and timestamps

### `/dashboard/pillar` — Pillar Blog Generator (`dashboard.pillar.tsx`)
Two-column layout (sidebar 340px sticky + main):

**Sidebar:**
- "Generation brief" form: Primary keyword, Target location, Audience, Tone, Notes
- "Regenerate pillar" gradient button
- 3 mini stats: Score 92, Words 2840, H2s 12

**Main area:**
- Badge row: "Pillar", "Commercial", "Ready to publish"
- H1 title
- Grid: SEO title, URL slug, Meta description fields with Copy buttons
- `<Tabs>` with 4 panels:
  - **Outline:** Numbered list with H1/H2/H3 badges
  - **Article preview:** Prose-styled rendered text of `pillarBlog.preview`
  - **FAQ schema:** 3 Q&A cards
  - **CTA:** Gradient card "Book your free SEO audit with GrowthSpark" + button
- Supporting cluster teaser card with link to `/dashboard/supporting`

### `/dashboard/supporting` — Supporting Blogs (`dashboard.supporting.tsx`)
- Header showing active pillar title
- "Generate more" gradient button
- 5 blog cards in a responsive grid (2-3 columns). Each card shows:
  - Intent badge (Informational/Commercial/Transactional with color variants)
  - Traffic estimate
  - Title, target keyword
  - Difficulty progress bar (KD value)
  - Internal link destination (monospace, truncated)
  - "+18% est." trending indicator + "Open" button

### `/dashboard/keywords` — Keyword Research (`dashboard.keywords.tsx`)
- Search card: seed keyword input, Intent select (All/Informational/Commercial/Transactional), Location input, "Research" gradient button
- 3 summary cards: Total keywords (248), Avg difficulty (37), Est. traffic (16.4K)
- Keyword table card: 8 rows from `seo-data.ts`. Each row: keyword, volume, KD progress bar, intent badge

### `/dashboard/local-seo` — Local SEO (`dashboard.local-seo.tsx`)
Two-column layout:

**Left (wide):**
- City selector badges: Kochi (selected), Ernakulam, Thiruvananthapuram, Kozhikode, Thrissur, Kollam
- Suggested local keywords list (6 items with checkmarks)
- Map placeholder: gradient hero background with grid, centered pulse-glow MapPin icon, location label "GrowthSpark Digital · MG Road, Kochi 682016"

**Right (360px):**
- GBP optimisation card: 87% score, 5 stars, 5 checklist tips
- LocalBusiness schema JSON-LD card (preformatted code block) + "Regenerate schema" button
- "Add another location" input + "Generate local pack" button

### `/dashboard/linking` — Internal Linking (`dashboard.linking.tsx`)
- SVG node map in a Card: center = gradient pillared box (title + keyword) with `animate-pulse-glow`. Right side = 5 supporting blog cards stacked vertically. Between them = SVG `<path>` curved dashed lines (`strokeDasharray="4 4"`) from center to each blog.
- Anchor text recommendations card below: 4 items showing "From → anchor text" pairs

### `/dashboard/prompts` — Prompt Library (`dashboard.prompts.tsx`)
- Search bar + "New prompt" button
- 6 prompt cards in a responsive grid (2-3 columns). Each card:
  - Category badge (top right)
  - Copy icon button (copies to clipboard + toast)
  - Title
  - Body text in muted bordered box
  - "Copy prompt" full-width outline button
- Filter by search query matching title or category

### `/dashboard/analytics` — Analytics (`dashboard.analytics.tsx`)
- 4 stat cards: Organic traffic (48,210), Keywords top 10 (184), Content score (92), SEO optimisation (87%)
- Traffic bar chart card: 16 gradient bars representing weekly traffic trend (+38% badge)
- Two bottom cards side by side:
  - Top performing pages: 4 rows (slug, monthly visits, KD badge)
  - Content optimisation breakdown: 5 progress bars (On-page 94%, Internal linking 88%, Readability 91%, Schema 76%, Local relevance 83%)

### `/dashboard/export` — Export Content (`dashboard.export.tsx`)
- Active export bundle card: "1 pillar + 5 supporting blogs · 12,480 words · Local SEO pack for Kochi" — Ready badge
- 4 export option cards in a 2-column grid:
  - Export as PDF (tag: "Most used")
  - Export Markdown
  - Copy Content
  - Download SEO Pack
Each with gradient icon circle, description, and action button that triggers a toast.

### `/settings` — Settings (`settings.tsx`)
Wrapped in its own SidebarProvider + AppSidebar + SidebarInset.
- Workspace card: Agency name, Primary location, Domain, Default language (4 inputs in 2-column grid)
- AI model card: 4 toggle switches (GPT-class reasoning, Local SEO context injection, Auto-generate FAQ schema, Aggressive keyword expansion)
- Integrations card: 6 rows (Google Search Console, GA4, WordPress, Notion, Webflow, Ahrefs) each with "Connect" button
- Save changes gradient button at bottom right

### `/dashboard` layout (`dashboard.tsx`)
Wraps all `/dashboard/*` child routes. Renders `<SidebarProvider><AppSidebar /><SidebarInset><Outlet /></SidebarInset></SidebarProvider>`.

### `__root.tsx`
Root layout with:
- `<html>` shell with `<HeadContent />` and `<Scripts />`
- `<QueryClientProvider>` → `<ThemeProvider>` → `<Outlet>` → `<Toaster />`
- SEO meta: title "GrowthSpark — AI SEO Blog & Content Cluster Generator", description about AI-powered prompt engineering for SEO
- `notFoundComponent`: 404 page with "Go home" link
- `errorComponent`: Error boundary with "Try again" (calls `router.invalidate()` + `reset()`) and "Go home" buttons

## Important Implementation Notes

1. **No AI backend:** Every "Generate", "Regenerate", "Research", "Export" button should call `toast.success("...")` from sonner. No real API calls.
2. **Copy to clipboard:** Use `navigator.clipboard.writeText()` + toast confirmation.
3. **Dark mode:** The `.dark` class on `html` must toggle ALL theme-aware CSS variables. Every card, border, and background must use semantic tokens.
4. **Responsive:** Sidebar collapses to icon mode. Grids stack to 1 column on mobile. Dashboard header stays sticky.
5. **Animations:** Use `animate-fade-up` on page content with staggered `animationDelay` (e.g., `60ms * index`). Use `hover:-translate-y-0.5 hover:shadow-soft` on cards.
6. **Route metadata:** Every route should set `head: () => ({ meta: [{ title: "Page Name · GrowthSpark Studio" }] })`.
7. **File routing:** Use TanStack Start flat file naming: `dashboard.index.tsx`, `dashboard.pillar.tsx`, etc. Do NOT use nested folders.
8. **Pricing currency:** Use Indian Rupee (₹) with realistic local pricing: ₹0, ₹2,490, Custom.
9. **Demo content:** All content should reference the Kochi/Kerala SEO market with Malayalam-aware, India-specific context.

## Final Quality Checklist

- [ ] All 11+ routes render without errors
- [ ] Dark mode toggle works across every page
- [ ] Sidebar navigation highlights active route
- [ ] Landing page has all 8 sections (Header, Hero, Logos, Features, Workflow, Pricing, CTA, Footer)
- [ ] Dashboard pages use consistent DashboardHeader + Card pattern
- [ ] All buttons have appropriate hover states and shadows
- [ ] No hardcoded colors — everything uses CSS variables or Tailwind semantic tokens
- [ ] Toast notifications appear on all "action" buttons
- [ ] Mobile responsive: sidebar collapsible, grids stack
