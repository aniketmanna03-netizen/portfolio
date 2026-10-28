# Aniket Manna — Portfolio

> Cinematic 3D developer portfolio. Pure HTML & CSS — no JavaScript, no frameworks.

---

## 🚀 Getting Started

Just open `index.html` in any modern browser:

```
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

No build step, no server, no dependencies. Works offline.

> **Tip:** For the Google Fonts to load (`Space Grotesk` and `JetBrains Mono`), you need an internet connection on first open. The fonts then cache automatically.

---

## 📁 File Structure

```
Portfolio/
├── index.html        ← All page structure, sections, toolkit, and content
├── style.css         ← Midnight Purple theme, 3D sculpture, toolkit, animations
├── README.md         ← This file
└── assets/
    └── skills/       ← 3D vector logo assets (HTML5, CSS3, Python, C++, Git, GitHub)
        ├── html5.svg
        ├── css3.svg
        ├── python.svg
        ├── cpp.svg
        ├── git.svg
        └── github.svg
```

---

## ✏️ How to Edit

### Personal Information

Edit these values directly in **`index.html`**:

| What to change | Where to find it |
|---|---|
| Name, role, bio | Hero section (`#hero`) and About section (`#about`) |
| Email address | Hero buttons, Contact section (`#contact`), `<meta>` tags |
| GitHub URL | Nav, Hero buttons, GitHub section (`#github`), Contact |
| LinkedIn URL | Contact section — replace `[ Add your LinkedIn URL ]` |
| College / Location | About section `.edu-card` |
| Project details | Projects section (`#projects`) — cards 01, 02, 03 |
| Timeline milestones | Journey section (`#journey`) — `.tl-item` blocks |
| GitHub repo cards | GitHub section — `.repo-card` blocks |
| Achievements | GitHub section — `.ach-item` blocks |

---

### Colors (CSS Variables)

All colors are defined at the top of **`style.css`** as CSS custom properties. Edit them in `:root {}`:

```css
:root {
  --bg:            #0B0714;    /* Deep Midnight Purple */
  --bg-secondary:  #171126;    /* Secondary cosmic surface */
  --bg-card:       #171126;    /* Glassmorphic card surface */
  --text:          #F5F3FF;    /* Soft White */
  --muted:         #9D8FC7;    /* Cosmic Lavender */
  --accent-lime:   #A78BFA;    /* Accent Purple */
  --accent-blue:   #67E8F9;    /* Electric Cyan */
  --accent-violet: #C084FC;    /* Electric Violet */
  --border:        #2D1F5E;    /* Deep Purple border */
  --border-light:  #3D2A7A;    /* Lighter Purple border */
}
```

---

### Typography

Fonts are imported via Google Fonts at the top of `style.css`:

```css
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;500;700&display=swap');
```

Font variables:
```css
--font-display: 'Space Grotesk', system-ui, sans-serif;  /* Headings */
--font-mono:    'JetBrains Mono', 'Courier New', monospace; /* Code, labels */
```

---

### Adding a New Project

Copy and paste a project card block inside the `.projects-grid` in `index.html`:

```html
<article class="project-card" role="listitem">
  <div class="proj-num" aria-hidden="true">04</div>
  <div class="proj-badge">STATUS</div>
  <h3 class="proj-title">Your Project Title</h3>
  <p class="proj-desc">Your project description here.</p>
  <div class="proj-tech-stack">
    <span class="tech-pill">HTML</span>
    <span class="tech-pill">CSS</span>
  </div>
  <div class="proj-status">
    <span class="status-dot"></span> Status text
  </div>
  <div class="proj-actions">
    <a href="YOUR_GITHUB_URL" class="proj-link">View on GitHub →</a>
  </div>
</article>
```

> **Note:** The grid is set to `grid-template-columns: 1fr 1fr`. The featured card (`.project-card--featured`) spans 2 columns. New cards auto-flow into the grid.

---

### Adding Timeline Milestones

Inside the `.timeline` div in the journey section:

```html
<div class="tl-item" role="listitem">
  <div class="tl-marker" aria-hidden="true">
    <div class="tl-dot"></div>
  </div>
  <div class="tl-content">
    <span class="tl-year">2026</span>
    <h3 class="tl-title">Milestone Title</h3>
    <p class="tl-desc">Description of what happened.</p>
  </div>
</div>
```

For active items add class `tl-item--active` and `tl-dot--active` / `tl-pulse--active`.  
For future items add `tl-item--future` and `tl-dot--future`.

---

### Modifying the 3D Sculpture

The sculpture is inside `#hero` in `.sculpture-wrapper`. Key things:

- **Size**: Change `.sculpture-wrapper` width/height (default `440px × 440px`)
- **Core cube size**: Change `.core` width/height (default `80px`)
- **Ring sizes**: Change `.orbit-g1`, `.orbit-g2`, `.orbit-g3`, `.orbit-g4` width/height
- **Animation speed**: Find the `animation` property on each element and change duration (e.g., `18s → 30s`)
- **Colors**: Uses `var(--accent-lime)` and `var(--accent-blue)` — change via CSS variables

---

### Animation Speed

All animation durations are in `style.css` under section `17. ANIMATIONS & KEYFRAMES`. To slow everything down, search for each animation name and increase the `s` value. To disable all animations (e.g., for accessibility testing), add:

```css
* { animation: none !important; transition: none !important; }
```

> The site already respects `prefers-reduced-motion` — users who prefer reduced motion see no animations.

---

## 🛠 Technologies Used

| Tech | Usage |
|---|---|
| **HTML5** | Semantic structure, accessibility attributes |
| **CSS3** | All layout, animation, 3D transforms, visual design |
| **Google Fonts** | `Space Grotesk` (display) + `JetBrains Mono` (mono) via CDN |
| **CSS Custom Properties** | Theming, color palette management |
| **CSS Grid & Flexbox** | Layout system |
| **CSS 3D Transforms** | Hero sculpture (`perspective`, `transform-style: preserve-3d`) |
| **CSS Keyframe Animations** | All motion effects |
| **CSS `backdrop-filter`** | Navigation glass effect |

**No JavaScript. No frameworks. No build tools. No dependencies.**

---

## 📐 Design System

| Element | Value |
|---|---|
| Background | `#080909` |
| Accent — Lime | `#C5FF4A` |
| Accent — Blue | `#4AFFED` |
| Accent — Violet | `#B57BFF` |
| Display Font | Space Grotesk |
| Mono Font | JetBrains Mono |
| Border radius | `2–4px` (minimal) |
| Style | Cinematic · Editorial · Minimal |

---

## ♿ Accessibility

- Semantic HTML (`header`, `nav`, `main`, `section`, `article`, `footer`)
- All images and decorative elements have `aria-hidden="true"` or `aria-label`
- Visible `:focus-visible` outlines (2px lime)
- `prefers-reduced-motion` media query disables all animations
- Descriptive link text throughout
- Proper heading hierarchy `h1 → h2 → h3`
- Color contrast meets WCAG AA for body text

---

## 📱 Responsive Breakpoints

| Breakpoint | Layout |
|---|---|
| `1440px+` | Full desktop layout, large sculpture |
| `1200px` | Slightly reduced sculpture size |
| `1024px` | Tablet — stacked hero, single column projects |
| `768px` | Mobile — hamburger nav, single column all |
| `480px` | Small mobile — vertical buttons |
| `360px` | Very small — compact spacing |

---

## 🗂 CSS Architecture

The `style.css` is organized into clearly labelled sections:

```
1.  Google Fonts Import
2.  CSS Variables & Reset
3.  Typography
4.  Navigation
5.  Layout (Container & Section)
6.  Buttons
7.  Hero & 3D Sculpture
8.  Digital Playground
9.  About Section
10. Skills Section
11. Projects Section
12. Journey Timeline
13. GitHub Section
14. Terminal Visual
15. Contact Section
16. Footer
17. Animations & Keyframes
18. Responsive (Media Queries)
19. Prefers Reduced Motion
```

---

*Built with HTML & CSS · No JavaScript · No frameworks · © 2025 Aniket Manna*
