# Papy Oiseaux -- Maquette Ulule Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a single standalone HTML file reproducing a pixel-perfect Ulule 2026 campaign page for the Papy Oiseaux birdhouse kit project.

**Architecture:** One `index.html` file with inline CSS (in `<style>`) and inline JS (in `<script>`). No build step, no dependencies, no framework. Open in browser = done. Structure follows real Ulule 2026 DOM: header → hero with sidebar → sticky nav → 2-column content + reward cards → footer.

**Tech Stack:** HTML5, CSS3 (custom properties, grid, flexbox, sticky, animations), vanilla JS, Google Fonts (Nunito + Lora)

**Reference files:**
- Spec: `docs/superpowers/specs/2026-04-07-papy-oiseaux-ulule-design.md`
- Rédac & ton: `docs/humanization-rules.md`
- Équipe: `docs/team.md`
- Brief: `docs/project-brief.md`

---

### Task 1: Scaffold HTML + CSS Reset + Fonts + Header

**Files:**
- Create: `index.html`

- [ ] **Step 1: Create the HTML scaffold with meta, fonts, CSS reset, and CSS custom properties**

Create `index.html` with:
- DOCTYPE, `<html lang="fr">`, charset utf-8, viewport meta
- Google Fonts link: Nunito (400,600,700,800) + Lora (400,400i,700)
- `<style>` block with CSS reset (box-sizing, margin 0, font-family)
- CSS custom properties on `:root`:
  ```
  --ulule-green: #1dba95;
  --ulule-green-dark: #15956f;
  --ulule-orange: #ff6b35;
  --bg-page: #f7f8fa;
  --bg-header: #ffffff;
  --text-primary: #232221;
  --text-secondary: #6b6b6b;
  --border-color: #e3ddd3;
  --wood-dark: #1a1208;
  --wood-warm: #2a1f0a;
  --papy-green: #2d5016;
  --font-sans: 'Nunito', sans-serif;
  --font-serif: 'Lora', serif;
  --max-width: 1200px;
  --sidebar-width: 380px;
  --header-height: 60px;
  ```
- Body: `background: var(--bg-page); font-family: var(--font-sans); color: var(--text-primary);`

- [ ] **Step 2: Build the sticky header**

Inside `<body>`, add a `<header>` with:
- `position: sticky; top: 0; z-index: 100; height: var(--header-height); background: #fff; border-bottom: 1px solid var(--border-color);`
- Flex container with:
  - Left: Ulule owl SVG logo inline (copy the `<svg>` with `<symbol id="ulule-owl-only-logo">` paths from the Ulule DOM reference) + text "ulule" in bold
  - Center: nav links "Lancer une collecte" | "Formation" | "Communauté" (plain `<a>` tags, `color: var(--text-primary)`)
  - Right: search icon placeholder + "Se connecter" button (outline style with person SVG icon)
- Max-width container inside: `max-width: var(--max-width); margin: 0 auto; padding: 0 24px;`
- Mobile: hide nav links, show only logo + burger placeholder

- [ ] **Step 3: Open in browser and verify header**

Open `index.html` in a browser. Verify:
- Nunito font loaded
- Header is sticky, white background, border bottom
- Logo + nav + login button visible on desktop
- Responsive: nav hidden on mobile

- [ ] **Step 4: Commit**

```bash
cd /home/claude/papy-oiseaux
git init
git add index.html
git commit -m "feat: scaffold HTML + header sticky Ulule"
```

---

### Task 2: Hero Section (background + title + video placeholder)

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add hero background and title block**

After `</header>`, add `<section class="hero">` with:
- Background: `var(--papy-green)` with a subtle radial gradient overlay
- Inner container: `max-width: var(--max-width); margin: 0 auto; padding: 60px 24px 40px;`
- 2-column flex: `.hero-content` (flex, gap 40px)
- Left column `.hero-left` (flex: 1):
  - H1 in white, Nunito 800, font-size 2rem: full title from spec
  - Subtitle `<p>` in rgba(255,255,255,0.85), font-size 1.1rem: subtitle from spec
  - Both show on desktop above video, on mobile below video

- [ ] **Step 2: Add video placeholder**

Inside `.hero-left`, add `.hero-video`:
- `aspect-ratio: 16/9; border-radius: 12px; overflow: hidden;`
- Background: `radial-gradient(ellipse at center, var(--wood-warm) 0%, var(--wood-dark) 100%);`
- Centered content: bird emoji (font-size 4rem) + play button SVG circle + label "VIDEO DE PRESENTATION"
- Label: uppercase, letter-spacing 2px, font-size 0.7rem, rgba(255,255,255,0.6)

- [ ] **Step 3: Add tags row below video**

Below video placeholder, add `.hero-tags`:
- Flex row of pill badges: Ecologie, Famille, Artisanat, France
- Each pill: `background: rgba(255,255,255,0.15); color: #fff; padding: 6px 16px; border-radius: 20px; font-size: 0.8rem;`

- [ ] **Step 4: Add creator info row**

Below tags, `.hero-creator`:
- Flex row: 4 avatar emojis in circles (32px, background rgba(255,255,255,0.2)) + "Papy Oiseaux" name + location "France" with map pin SVG + category "Enfants & famille" with tag SVG
- All in white/semi-transparent

- [ ] **Step 5: Verify hero in browser**

Check: green background, white text, video placeholder with wood texture, tags, creator row. Responsive: stacks vertically on mobile.

- [ ] **Step 6: Commit**

```bash
git add index.html
git commit -m "feat: hero section with video placeholder + tags"
```

---

### Task 3: Hero Sidebar (funding stats + CTA)

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add sidebar column in hero**

Right column `.hero-sidebar` (width: var(--sidebar-width), flex-shrink: 0):
- `background: #fff; border-radius: 16px; padding: 32px; box-shadow: 0 4px 24px rgba(0,0,0,0.1);`
- Position: stays in flow on desktop, not sticky yet (will be sticky in sidebar section below hero)

- [ ] **Step 2: Add funding amount with counter placeholder**

Inside sidebar:
- Green egg SVG icon (simplified version of Ulule's owl-egg icon, filled `var(--ulule-green)`)
- Amount: `<div class="amount" id="amount-counter">0 EUR</div>` -- Nunito 800, font-size 2.2rem, color var(--text-primary)
- Goal: `<p>sur 15 000 EUR</p>` -- font-size 0.9rem, color var(--text-secondary)
- Funded badge: "Finance a 62%" -- small green badge

- [ ] **Step 3: Add progress bar**

- `.progress-bar` container: height 8px, background #e8e8e8, border-radius 4px
- `.progress-fill`: width 0% (animated later), height 100%, background linear-gradient(90deg, var(--ulule-green), #2ee0ab), border-radius 4px, transition width 1s ease-out

- [ ] **Step 4: Add stats row**

Flex row with:
- 187 contributions (with small avatar icon)
- 14 jours restants (with calendar SVG icon)
- Each: number in Nunito 700 + label in small text

- [ ] **Step 5: Add CTA button + share/follow buttons**

- Main CTA: `<button class="cta-contribute">Contribuer</button>` + `<small>A partir de 1 EUR</small>`
  - Full width, padding 16px, background var(--ulule-green), color #fff, border-radius 8px, font-size 1.1rem, font-weight 700, cursor pointer
  - Hover: background var(--ulule-green-dark)
- Below: "Paiement securise et sans engagement" link text
- Share + Follow buttons: outline style, flex row, gap 12px

- [ ] **Step 6: Verify sidebar in browser**

Check: white card on green background, stats visible, CTA button green, hover works. Mobile: sidebar below hero content.

- [ ] **Step 7: Commit**

```bash
git add index.html
git commit -m "feat: hero sidebar with funding stats + CTA"
```

---

### Task 4: Sticky Navigation Menu

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add sticky nav bar below hero**

After `</section>` (hero), add `<nav class="sticky-menu">`:
- `position: sticky; top: var(--header-height); z-index: 90; background: #fff; border-bottom: 1px solid var(--border-color);`
- Inner container max-width, flex row of tab links:
  - Collecte (active by default -- border-bottom 2px solid var(--ulule-green), font-weight 700)
  - Contreparties
  - FAQ
  - Actualites + badge `<span class="badge">2</span>`
  - Contributions + badge `<span class="badge">187</span>`
  - Commentaires
- Badge: background var(--ulule-green), color #fff, border-radius 10px, padding 2px 8px, font-size 0.75rem
- Tab hover: color var(--ulule-green)
- Mobile: horizontal scroll with `-webkit-overflow-scrolling: touch;`

- [ ] **Step 2: Verify sticky behavior**

Scroll the page. Nav should stick below header. Tabs should be clickable (JS comes later).

- [ ] **Step 3: Commit**

```bash
git add index.html
git commit -m "feat: sticky navigation tabs"
```

---

### Task 5: Main Content -- Description Section

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Create 2-column layout**

After sticky nav, `<main class="content">`:
- `max-width: var(--max-width); margin: 0 auto; padding: 40px 24px;`
- `display: grid; grid-template-columns: 1fr var(--sidebar-width); gap: 40px;`
- Mobile: `grid-template-columns: 1fr;`
- Left: `<div class="content-left">`
- Right: `<aside class="content-sidebar">` (will contain reward cards, Task 7)

- [ ] **Step 2: Add "A propos de cette collecte" section header**

In `.content-left`, add section with:
- `<h2>` styled like Ulule (Nunito 800, font-size 1.5rem, margin-bottom 24px)

- [ ] **Step 3: Add citation fondatrice**

Blockquote with wood styling:
- `background: radial-gradient(ellipse at center, var(--wood-warm), var(--wood-dark)); color: rgba(255,255,255,0.9); padding: 32px; border-radius: 12px; border-left: 4px solid var(--ulule-green); font-family: var(--font-serif); font-style: italic; line-height: 1.8; margin: 24px 0;`
- Full citation text from spec (the papy story with sensory details)

- [ ] **Step 4: Add placeholder image after citation**

Placeholder div:
- `aspect-ratio: 16/9; border-radius: 12px; background: radial-gradient(...); margin: 24px 0;`
- Centered emoji + label "PHOTO -- LE PAPY ET SA PETITE-FILLE DANS L'ATELIER"

- [ ] **Step 5: Add "Le produit" section with emoji list**

- Intro paragraph from spec (emotional B2C tone)
- List with emoji bullets (styled with CSS, no `<ul>` bullet):
  - Each item: `display: flex; gap: 12px; margin-bottom: 16px;`
  - Emoji: `font-size: 1.5rem; flex-shrink: 0;`
  - Text: `<strong>` for the title part, normal for description

- [ ] **Step 6: Add 3-image placeholder grid**

`.placeholder-grid`: `display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 24px 0;`
- 3 placeholder divs with house, pencil, mountain emojis

- [ ] **Step 7: Add "La magie" and "Toitures aimantees" sections**

Two more content sections with:
- H3 headings (Nunito 700, 1.2rem)
- Paragraphs from spec (full text, respecting humanization rules)
- One large placeholder image after "La magie"

- [ ] **Step 8: Verify content in browser**

Check: 2-column layout, citation in wood style, placeholder images, emoji list, readable text. Mobile: 1 column.

- [ ] **Step 9: Commit**

```bash
git add index.html
git commit -m "feat: description content with citation + product sections"
```

---

### Task 6: Content Sections -- Funding, Team, FAQ, Actualites

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add "Pourquoi Ulule" section**

Content from spec, followed by a separator `<hr>`.

- [ ] **Step 2: Add "A quoi servira le financement" accordion**

- Container with border, border-radius 12px
- `<label>` as trigger with H2 + chevron SVG
- Hidden `<input type="checkbox" checked>` + adjacent div toggle (CSS-only accordion)
- Content: transparent funding breakdown from spec

- [ ] **Step 3: Add "Qui porte la collecte" accordion**

Same accordion pattern:
- Avatar large (80px circle)
- Name "Papy Oiseaux" as link
- Location "France"
- "1 collecte lancee sur Ulule"
- Team bios: Le Papy, Lucas, Antoine, Valentin (full text from spec)

- [ ] **Step 4: Add FAQ accordion**

3 questions, each a CSS-only accordion:
- "Comment envoyer le dessin de mon enfant ?"
- "Le kit est adapte a quel age ?"
- "Le nichoir tient-il en exterieur ?"
- Answers from spec

- [ ] **Step 5: Add social links section**

"Suivez la collecte ailleurs" with placeholder social buttons (YouTube, Instagram, Website) styled like Ulule's colored circle icons.

- [ ] **Step 6: Add Actualites section (hidden by default, toggled by tab)**

Two news items from spec:
- Each: avatar, date relative, title, content paragraph
- Container: `display: none;` by default (JS tab switching)

- [ ] **Step 7: Verify all sections**

Check: accordions open/close with CSS, FAQ works, team info displays correctly.

- [ ] **Step 8: Commit**

```bash
git add index.html
git commit -m "feat: funding, team, FAQ, actualites sections"
```

---

### Task 7: Sidebar -- Reward Cards + Donation

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add sidebar rewards container**

In `.content-sidebar`:
- `position: sticky; top: calc(var(--header-height) + 60px); align-self: start;`
- H2 "Contreparties" + subtitle
- Container for reward cards

- [ ] **Step 2: Build reward card component (repeat for 5 paliers)**

Each `.reward-card`:
- `border: 1px solid var(--border-color); border-radius: 12px; padding: 20px; margin-bottom: 16px; transition: border-color 0.2s, box-shadow 0.2s; cursor: pointer;`
- Hover: `border-color: var(--ulule-green); box-shadow: 0 4px 12px rgba(0,0,0,0.1);`
- Structure:
  - Price: `<div class="reward-price">Pour 59 EUR</div>` (Nunito 600, small)
  - Title: `<div class="reward-title">Box Essentielle</div>` (Nunito 700, 1.1rem)
  - Subtitle if any (e.g. "POPULAIRE" star badge)
  - Description text (font-size 0.85rem, color var(--text-secondary))
  - CTA: `<button class="reward-cta">Choisir</button>` (ulule-green, outline or filled)
  - Footer: calendar icon + "Avril 2026" | heart icon + "98 contributions"
  - For Collector: badge "limite" + "6/50" count

Build all 5 cards with content from spec:
1. 5 EUR Soutien symbolique
2. 25 EUR Kit Decouverte
3. 59 EUR Box Essentielle (star)
4. 75 EUR Box Decouverte
5. 95 EUR Coffret Collector (limite 50)

- [ ] **Step 3: Add donation box**

After reward cards:
- "Faire un don" heading
- Input field + "Faire un don" button (same style as Ulule)
- Placeholder text: "5, 10, 25, 50, ce que vous voulez !"

- [ ] **Step 4: Add delivery info**

- Estimated delivery: Avril 2026
- Shipping: France, Europe
- Link "En savoir plus sur les contreparties"

- [ ] **Step 5: Verify sidebar**

Check: cards stack, hover effect, sticky on scroll, mobile: full width below content.

- [ ] **Step 6: Commit**

```bash
git add index.html
git commit -m "feat: reward cards sidebar + donation box"
```

---

### Task 8: Footer + "How Crowdfunding Works" Section

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add "Comment fonctionne ce crowdfunding" section**

3-column grid below main content:
- Each column: illustration placeholder (colored circle with simple SVG icon) + H3 + paragraph
  1. "Donnez des ailes a ce projet" -- paper plane icon, `#e3ddd3` bg
  2. "Tout ou rien" -- balance/trophy icon
  3. "Securise et sans engagement" -- lock icon
- Text from Ulule's original (adapted)
- CTA "Contribuer" button centered below

- [ ] **Step 2: Add footer**

`<footer>`:
- Background: #fff, border-top 1px solid var(--border-color)
- 4-column grid: Ulule Crowdfunding | Formation | Camp de base | A propos (link lists from Ulule DOM)
- Social icons row (Facebook, TikTok, Instagram, LinkedIn, YouTube) -- simple SVG circles
- Bottom: Ulule horizontal logo + legal links + language/currency selectors (placeholder)
- **IMPORTANT**: Clear disclaimer text: "Ceci est une maquette de travail non officielle. Aucun paiement reel. Projet Papy Oiseaux."
- `font-size: 0.85rem; color: var(--text-secondary);`

- [ ] **Step 3: Verify footer**

Check: 4 columns desktop, stacked mobile, maquette disclaimer visible.

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: crowdfunding explainer + footer with disclaimer"
```

---

### Task 9: JavaScript -- Animations + Interactions

**Files:**
- Modify: `index.html` (add `<script>` before `</body>`)

- [ ] **Step 1: Animated counter (0 -> 9 240 EUR)**

Implement `animateCounter` function:
- Uses `requestAnimationFrame` loop
- easeOutQuart easing: `1 - Math.pow(1 - t, 4)`
- Duration: 1200ms
- Format: `n.toLocaleString('fr-FR') + ' EUR'` (with euro sign)
- Trigger on DOMContentLoaded targeting `#amount-counter`

- [ ] **Step 2: Progress bar animation**

On DOMContentLoaded, set `.progress-fill` width to 62% with a 300ms delay using setTimeout.

- [ ] **Step 3: CTA button feedback**

Add click handler to all `.cta-contribute` buttons:
- On click: change `textContent` to "Merci !" with bird emoji, darken background
- After 2s timeout: restore original textContent and clear inline background style

- [ ] **Step 4: Tab switching**

Add click handlers to `.sticky-menu a` elements:
- Prevent default
- Toggle `.active` class on tabs
- Show/hide `.tab-content` sections via `style.display`
- Use `data-target` attribute to map tab to section ID

- [ ] **Step 5: Smooth scroll for tab links**

Add `scroll-behavior: smooth;` to `html` in CSS. Tab links use `href="#section-id"` with scroll offset for sticky headers.

- [ ] **Step 6: Test all interactions in browser**

Verify: counter animates on load, progress bar fills, CTA shows feedback, tabs switch content, accordions work.

- [ ] **Step 7: Commit**

```bash
git add index.html
git commit -m "feat: JS animations (counter, progress, CTA, tabs)"
```

---

### Task 10: Responsive Polish + Final Review

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Mobile breakpoint (<768px)**

Add media queries:
- Header: hide nav links, show only logo + burger icon
- Hero: `flex-direction: column;` sidebar full width below
- Sticky menu: `overflow-x: auto; white-space: nowrap;`
- Content grid: `grid-template-columns: 1fr;`
- Sidebar: not sticky on mobile, full width
- Footer: single column
- Font sizes: reduce H1 to 1.5rem, H2 to 1.2rem

- [ ] **Step 2: Tablet breakpoint (768-1024px)**

- Content grid: `grid-template-columns: 1fr 320px;` (narrower sidebar)
- Hero: keep 2 columns but reduce gap

- [ ] **Step 3: Desktop polish**

- Max-width constraint on all containers
- Proper spacing between sections (48-64px)
- Ensure sidebar sticky doesn't overflow viewport height

- [ ] **Step 4: Cross-browser check**

Open in at least Chrome. Check:
- All fonts loaded
- Animations smooth
- Sticky elements work
- Placeholders look good (wood gradient + emoji)
- Footer disclaimer clearly visible
- No horizontal scroll

- [ ] **Step 5: Final commit**

```bash
git add index.html
git commit -m "feat: responsive polish + final review"
```

---

## Post-Implementation

The deliverable is a single file:
```
papy-oiseaux/index.html
```

Open in any browser to see the complete Ulule campaign maquette for Papy Oiseaux.
