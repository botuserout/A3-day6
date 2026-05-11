# A3 — Day 6 : CSS Positioning & Layout Assignment

> **Student Assignment** | Web Development  
> Three separate UI projects demonstrating CSS positioning, layout techniques, and NFT/media-themed designs.

---

## 📁 Project Structure

```
A3-day6/
├── SIMPLE/          → Task 1 — Squid Game Landing Page
├── MEDIUM/          → Task 2 — Shinsei Village NFT Hero Page
├── simple2/         → Task 3 — NFT Marketplace "Explore Art Work"
└── README.md        → This file
```

---

## 🟢 Task 1 — SIMPLE: Squid Game Landing Page

**Folder:** `SIMPLE/`

### How to Open
Open `SIMPLE/index.html` directly in any browser — **no server needed**.

### Files
| File | Purpose |
|------|---------|
| `index.html` | Main page markup |
| `style.css` | All styles and layout |
| `src/guard.png` | Hero character image (Squid Game guard) |
| `src/Gemini_Generated_Image_...png` | Custom Squid Game logo |
| `src/one.jpg` | Episode card image 1 |
| `src/two.jpg` | Episode card image 2 |

### Page Sections
1. **Background Text** — Large "SQUID GAME" watermark text behind everything
2. **Navbar** — Logo left, nav links center, hamburger menu for mobile
3. **Hero** — Left: logo + description + CTA buttons (`Play Now`, `Watch Trailer`). Right: guard character + social icons + scroll indicator
4. **Episode Cards** — Three cards with thumbnails and a circular play button overlay

### CSS Concepts Demonstrated
- `position: absolute` / `position: relative` for layering background text behind content
- `position: fixed` for sticky navbar
- Flexbox for nav, hero two-column layout, and card row
- Responsive design with `@media` queries (hamburger menu on mobile)
- JavaScript toggle for mobile hamburger menu

---

## 🟡 Task 2 — MEDIUM: Shinsei Village NFT Hero Page

**Folder:** `MEDIUM/`

### How to Open
Open `MEDIUM/index.html` directly in any browser — **no server needed**.

### Files
| File | Purpose |
|------|---------|
| `index.html` | Main page markup |
| `style.css` | All styles and layout |
| `background.png` | Cherry blossom mountain landscape (hero background) |
| `monkey.png` | Central monkey warrior character (PNG, transparent) |
| `Gemini_Generated_Image_rus3kbrus3kbrus3-removebg-preview.png` | Shinsei Village logo (transparent PNG) |

### Page Sections
1. **Header / Navbar** — `position: absolute` over the hero. Logo left, nav links center (Vision · Collection · Roadmap · Team · Mint ↗ · Wallet Checker ↗), social icons (Instagram, Telegram, Discord) right.
2. **Hero Section** — Full-viewport background image; the title "SHINSEI" and "VILLAGE" are split left/right with the character occupying the center space; "MINT NOW" button floats at the character's waist level; curved dark divider at the bottom blends the hero into the next section.
3. **Vision Section** — Dark background (`#2a1b24`); "VISION" heading with a diamond divider; two-column text grid explaining the project.

### CSS Concepts Demonstrated
- `position: absolute` for header over the hero
- `position: absolute` + `z-index` stacking for: background → text → button → character → curved divider
- `border-radius: 50%` trick for the curved dark shape at the bottom of the hero
- CSS `mask-image` (gradient) to fade the character's legs into the curved shape
- `clamp()` for fluid/responsive font sizes
- CSS custom properties (`--bg-dark`, `--primary-color`, etc.)
- Google Fonts (`Outfit`, `Inter`) + Font Awesome icons

### Key z-index Stack (Hero)
```
z-index 0   → .hero-bg      (background image)
z-index 2   → .hero-text-layer  (SHINSEI / VILLAGE text)
z-index 4   → .curved-divider   (dark curved bottom shape)
z-index 5   → .hero-character   (monkey image, overlaps the curve)
z-index 10  → .cta-container    (MINT NOW button, above everything)
z-index 100 → header            (always on top)
```

---

## 🔵 Task 3 — simple2: NFT Marketplace "Explore Art Work"

**Folder:** `simple2/`

### How to Open
Open `simple2/simple2.html` directly in any browser — **no server needed**.

### Files
| File | Purpose |
|------|---------|
| `simple2.html` | Self-contained page (HTML + CSS + JS inline) |
| `Screenshot 2026-05-11 163228.png` | NFT card image — "Monocular" (cyborg skull) |
| `Screenshot 2026-05-11 163236.png` | NFT card image — "Horns Mask" / "Skull Wire" (skeleton) |
| `Screenshot 2026-05-11 163242.png` | NFT card image — "Spiderman" (hoodie character) |
| `Screenshot 2026-05-11 163249.png` | NFT card image — "DeadPool" (gold chain hoodie) |
| `Screenshot 2026-05-11 163253.png` | NFT card image — "White Eye" (x-ray skull) |
| `Screenshot 2026-05-11 163306.png` | NFT card image — "Plastic Spinal" (x-ray skeleton) |
| `Gemini_Generated_Image_g2qfb9g2qfb9g2qf.png` | NFT card image — "Light Moon" (AI generated eye artwork) |

### Page Sections
1. **Navbar** — "NFTX" logo left, navigation links center (Explore · Collections · Artists · Stats), "Connect Wallet" gradient button right
2. **Header Row** — "Explore Art Work" heading with gradient accent, subtitle, filter tabs (All · Art · Gaming), "See All →" link
3. **Stats Bar** — Four quick-stats: Artworks (482K) · Artists (38.6K) · Auctions (126K) · Volume ($4.2B)
4. **Card Grid** — 8 NFT cards in a 4-column grid (2-col on tablet, 1-col on mobile), each with:
   - Real photo image with zoom-on-hover
   - Badge overlay (⚡ HOT / 🔥 TOP / ✨ NEW)
   - ETH price pill (bottom-right of image)
   - NFT name + like count + heart toggle button
   - "Place Bid" button (white fill on active card)

### CSS Concepts Demonstrated
- CSS Grid (`grid-template-columns: repeat(4, 1fr)`) for the card layout
- `position: absolute` for badge and price pill overlays on card images
- `backdrop-filter: blur()` for glassmorphism overlays
- CSS custom properties for the full design system
- `aspect-ratio: 1/1` to keep card images square
- `radial-gradient` animated blobs in the background (`@keyframes blobPulse`)
- CSS pseudo-elements (`::before`, `::after`) for glow/shimmer effects
- JavaScript heart toggle (`classList.toggle('liked')`) and filter button active state

---

## 🎯 Assignment Learning Objectives

| Concept | Where Used |
|---------|-----------|
| `position: relative` | Card containers (simple2), vision section |
| `position: absolute` | All three projects — overlaid elements |
| `position: fixed` | Sticky header (SIMPLE) |
| `z-index` layering | MEDIUM hero stack (6 layers) |
| CSS Grid | simple2 card grid |
| Flexbox | All three projects — nav, header, card info rows |
| Responsive / Media Queries | All three projects |
| CSS Custom Properties | MEDIUM and simple2 |
| CSS Mask / Gradient fades | MEDIUM (monkey character fade) |
| `clamp()` fluid sizing | MEDIUM title |
| JS DOM interaction | SIMPLE hamburger menu, simple2 heart + filter buttons |

---

## 🚀 Quick Start for Mentor

```
1. Open A3-day6/ in VS Code (or any editor)
2. Right-click any index.html → "Open with Live Server"  
   OR simply double-click the .html file to open in browser
3. No npm / build step / server required — all pages are pure HTML + CSS
```

> **Note:** Internet connection is required for Google Fonts and Font Awesome CDN icons to load in the MEDIUM and simple2 pages.
