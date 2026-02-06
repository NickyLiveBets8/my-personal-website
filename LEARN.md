# LEARN.md — What I Learned Building My Personal Website

## What This Project Is

A cyberpunk-themed personal website inspired by Tron, The Matrix, and 8-bit aesthetics. It features a glowing neon design, a photo gallery with click-to-zoom, and a retro pixel font — all built from scratch with no frameworks.

---

## How the Site is Structured (Architecture)

Think of a website like a person:

- **HTML** (`index.html`) = The **skeleton**. It defines *what's on the page* — headings, paragraphs, images, buttons. Without CSS, it's just plain text on a white background.
- **CSS** (`css/style.css`) = The **outfit and appearance**. It defines *how things look* — colors, fonts, glow effects, layout, animations.
- **JavaScript** (inside `index.html`) = The **brain/behavior**. It defines *what happens when you interact* — like clicking a photo to zoom in.

### Folder Structure
```
Project-3/
├── index.html          ← The main (and only) page
├── css/
│   └── style.css       ← All the styling/design
├── images/             ← Where your photos will go
├── CLAUDE.md           ← Instructions for the AI assistant
├── LEARN.md            ← This file! Your learning journal
└── .gitignore          ← Tells Git which files to ignore
```

---

## Technologies Used & Why

| Technology | What It Does | Why We Chose It |
|-----------|-------------|-----------------|
| **HTML** | Page structure | It's the foundation of every website. No way around it! |
| **CSS** | Visual design | Handles all the Tron glow effects, grid backgrounds, and animations without needing any extra tools |
| **JavaScript** | Interactivity | Just a tiny bit — for the photo lightbox. Keeps things simple |
| **Google Fonts** | Custom fonts | Gives us "Press Start 2P" (pixel font) and "Share Tech Mono" (hacker font) for free |
| **Git** | Version control | Like "save checkpoints" for your code. Industry standard for all developers |

**Why no frameworks?** Frameworks like React or Vue are powerful, but they're overkill for a simple personal site. Starting with raw HTML/CSS teaches you the fundamentals — like learning to cook before using a microwave.

---

## Key Concepts I Learned

### CSS Variables (Custom Properties)
Instead of typing `#00ffff` every time we want that Tron cyan color, we gave it a name: `--neon-cyan`. Now we type `var(--neon-cyan)` everywhere. Want to change the color? Update it in ONE place and the whole site changes. It's like a "find and replace" but smarter.

### CSS Grid
The photo gallery uses CSS Grid. Imagine a spreadsheet — Grid lets you arrange items into rows and columns that automatically adjust based on screen size. We used `auto-fill` so the browser figures out how many columns fit.

### The Box Model
Every element on a web page is an invisible box. That box has:
- **Content** (the stuff inside)
- **Padding** (space between content and border — like the foam inside a shipping box)
- **Border** (the edge of the box)
- **Margin** (space between this box and other boxes)

### Pseudo-elements (::before and ::after)
These are "ghost elements" — invisible extras that CSS creates without you adding anything to the HTML. We used them for the glitch effect (creating two ghost copies of your name) and the glowing line under the header.

### Responsive Design
We used `@media (max-width: 768px)` to change the layout on smaller screens. It's like having two outfits — one for a big stage (desktop) and one for a small room (mobile).

### Lightbox Pattern
A "lightbox" is a common web pattern: click a small image, and a big version appears on a dark overlay. The dark overlay is just a full-screen `div` that's normally hidden. JavaScript toggles it visible/invisible.

---

## Lessons Learned & Pitfalls

### 1. "Why isn't my CSS working?"
**Most common reason:** You forgot to link the CSS file in the HTML `<head>`. Always check that `<link rel="stylesheet" href="css/style.css">` is there and the path is correct.

### 2. Glow effects can get heavy
Stacking too many `box-shadow` and `text-shadow` effects can slow down older devices. We kept it tasteful — just enough glow to sell the Tron vibe without melting anyone's laptop.

### 3. `overflow-x: hidden` is your friend
Glow effects sometimes bleed past the edge of the screen, creating an ugly horizontal scrollbar. Adding `overflow-x: hidden` to the body hides that.

### 4. Always use `object-fit: cover` on images
Without it, images stretch and squish to fill their container (looks terrible). With `cover`, they crop intelligently to fill the space while keeping their proportions.

---

## How Good Engineers Think

1. **Start simple, then add complexity.** We built a plain skeleton first, then added the fancy stuff. Don't try to do everything at once.

2. **Name things clearly.** We used names like `--neon-cyan` and `.gallery-item` instead of `.box1` or `.thing`. Future-you will thank present-you.

3. **Don't repeat yourself (DRY).** CSS variables let us define a color once and reuse it everywhere. Repetition = more chances for mistakes.

4. **Test on different screen sizes.** What looks great on your monitor might be broken on a phone. Always check.

5. **Version control everything.** Git lets you experiment freely because you can always go back to a previous version. It's your safety net.
