# ☕ El Galáctico Cafe — Website

A fully responsive, luxury coffee shop website themed around Real Madrid's legacy. Built as a **learning project** to practice light-theme design, CSS Grid product layouts, and advanced scroll-driven animations — all in pure HTML and CSS, no JavaScript.

---

## 🌐 Live Preview

> Open `index.html` in any modern browser to view locally.
> https://madridista-cafe.vercel.app/

---

## 🎯 What This Project Was Built to Learn

This was the third project in a self-directed HTML + CSS learning path, focused on pushing into new territory:

- ✅ **Light theme design** — moving away from dark backgrounds to a warm, luxury aesthetic
- ✅ **Business/product page layout** — not a biography, a real-world web format
- ✅ **CSS Grid `grid-template-areas`** for a complex multi-card product section
- ✅ **Scroll exit animations** — using both `entry` and `exit` in `animation-range`
- ✅ **Serif + sans-serif font pairing** for editorial warmth
- ✅ **CSS `p:has(time)` selector** — modern relational CSS
- ✅ **Overlapping elements** with `position: relative` for a badge effect

---

## 📁 Project Structure

```
El-Galactico-Cafe/
├── index.html      # Main HTML file
├── style.css       # Desktop styles & animations
├── tablet.css      # Tablet responsive styles (≤ 1110px)
├── mobile.css      # Mobile responsive styles (≤ 699px / ≤ 350px)
└── images/         # All local image assets
    ├── coffe-shop-inside.jpg
    ├── Coffe-image.png
    ├── bernabeu-blend.png
    ├── latte.png
    ├── PC-Background-image.jpg
    ├── Tropihes.png
    ├── Seat1.png
    ├── Cups-image.avif
    └── icon-.png
```

---

## 📌 Sections

| Section | Description |
|---|---|
| **Hero** | Full-screen coffee shop interior, headline, animated location CTA |
| **Our Story** | Brand narrative, coffee image with overlapping stat badge, legacy link |
| **The Menu** | 4-item product grid — Bernabéu Blend, Zidane Espresso, Décima Latte, Reserve CTA |
| **Gallery** | Interior atmosphere photos in an asymmetric grid |
| **Match Day** | Full-width CTA section to place an order |
| **Footer** | Brand name, navigation links, GitHub, copyright |

---

## 🎨 Design System

### Color Palette

```css
:root {
  --gold:        #FEBE10;   /* Primary accent — buttons, highlights */
  --gold-hover:  #E5A800;   /* Gold hover state */
  --light-gold:  #fdda8b;   /* Hero headline span */
  --dark-yellow: #745b16;   /* Labels, links, secondary accent */
  --blue:        #001E4E;   /* Primary dark — headings, buttons, navbar */
  --blue-hover:  #003080;   /* Blue hover state */
  --brown:       #401100;   /* Reserved accent */
  --white:       #FFFFFF;   /* Text on dark surfaces */
  --gray:        #5a6074;   /* Body text, muted content */
}
```

**Page background:** `#f5f3ef` — warm off-white cream, intentionally not pure white.

### Typography

```css
/* Headings — editorial warmth */
font-family: "Noto Serif", sans-serif;

/* Body — clean and modern */
font-family: "Manrope", sans-serif;
```

Both loaded via Google Fonts `@import` in `style.css`. The serif/sans-serif contrast gives the site a luxury editorial feel — different from the all-sans-serif approach in the previous two projects.

---

## 🎞️ Animations

### Keyframes

```css
@keyframes slide-in    /* Sections enter from the left on scroll */
@keyframes hide-in     /* Sections exit to the left on scroll out */
@keyframes mov-left    /* Location CTA nudges right in a loop */
```

### Scroll-Driven Entry + Exit

The standout animation technique in this project — sections animate both **in and out** as you scroll:

```css
animation: slide-in 1.4s ease, hide-in 2s ease;
animation-timeline: view();
animation-range: entry, exit 70%;
```

This means each section slides in when entering the viewport and fades out as you scroll past it — creating a cinematic flow through the page.

> ⚠️ Scroll-driven animations require Chromium 115+ (Chrome, Edge). Firefox support is limited.

### Usage Per Section

| Section | Animation |
|---|---|
| Story | `slide-in` + `hide-in` |
| Menu | `slide-in` + `hide-in` |
| Gallery | `slide-in` + `hide-in` |
| Location CTA | `mov-left` infinite alternate |

---

## 🧱 Menu Grid Layout

The most complex layout in the project — a 3-column CSS Grid with named areas:

```css
.menu {
  display: grid;
  grid-template-areas:
    "header   header   header"
    "product1 product1 product2"
    "product3 reserve  reserve"
    "product3 reserve  reserve";
  gap: 2rem;
}
```

Each card has a distinct visual identity:
- **Product 1 (Bernabéu Blend)** — flex row, full image, cream background
- **Product 2 (Zidane Espresso)** — dark navy `#000827`, breaks the light theme intentionally
- **Product 3 (Décima Latte)** — column-reverse, image on top, stacked layout
- **Reserve** — full background image, centered CTA, deep padding

---

## ✨ Special Details

**`p:has(time)` selector** — the launch date label uses modern relational CSS to style any paragraph containing a `<time>` element, without adding an extra class:
```css
p:has(time) {
  background-color: var(--blue);
  transform: skew(-10deg);
  letter-spacing: 3px;
}
```

**Blends badge overlay** — the "15+ Champions Blends" stat card overlaps the coffee image using `position: relative` with `left` and `bottom` offsets, creating a depth effect without absolute positioning tricks.

**Navbar depth** — `box-shadow: 10px 0px 10px black` gives the sticky navbar a floating card feel over the hero background.

---

## 📱 Responsive Design

| File | Breakpoint | Key Changes |
|---|---|---|
| `style.css` | > 1110px (desktop) | Full grid menu, side-by-side story, gallery grid |
| `tablet.css` | ≤ 1110px | Menu becomes flex column, story stacks, gallery linearizes |
| `mobile.css` | ≤ 699px | Nav links hidden, hero text reduced, products stack fully |
| `mobile.css` | ≤ 350px | Extra small adjustments for very narrow screens |

---

## 🛠️ Built With

- **HTML5** — Semantic elements (`<header>`, `<section>`, `<article>`, `<nav>`, `<footer>`, `<time>`)
- **CSS3** — Grid, Flexbox, custom properties, scroll-driven animations, `p:has()`, `@keyframes`
- **Google Fonts** — Noto Serif & Manrope
- **No JavaScript** — Entirely static

---

## 📈 Learning Progress

| Project | Theme | Key Concept Learned |
|---|---|---|
| Federico Valverde Biography | Dark sports | CSS Grid, scroll entry animations |
| Apollo 11 Mission | Dark sci-fi | `backdrop-filter`, scroll flip animation |
| **El Galáctico Cafe** | **Light luxury product** | **Exit animations, grid-template-areas, `has()` selector** |

---

## 🚀 Getting Started

1. Clone or download the repository:
   ```bash
   git clone https://github.com/iiwpkabderrahime/El-Galactico-Cafe.git
   ```
2. Open `index.html` in any modern browser.
3. No build step, no dependencies to install.

---

## ✍️ Author

**iiwpkabderrahime**
[GitHub](https://github.com/iiwpkabderrahime)

---

## 📄 License

Built for learning and portfolio purposes only. All Real Madrid references are fan-made and not affiliated with Real Madrid C.F.
