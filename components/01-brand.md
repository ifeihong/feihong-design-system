# Feihong Design System — Brand Foundation
# N°01 · 品牌基础
> Brand tokens, CSS reset, and utility classes — the foundation every page needs.
> 品牌变量、基础重置和工具类——每个页面必备的基础层。
> Part of Feihong Design System v7.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 0. Brand Tokens（CSS 变量）

所有组件依赖以下 token，放在 `<style>` 的 `:root` 中：

```css
:root {
  /* === Brand Colors === */
  --royal: #0A2463;
  --royal-50: #EEF1FA;
  --royal-100: #D6DDF0;
  --royal-200: #AEBBE1;
  --royal-300: #8599D2;
  --royal-400: #5D77C3;
  --royal-500: #3455B4;
  --royal-600: #0A2463;
  --royal-700: #081C4F;
  --royal-800: #06153B;
  --royal-900: #040E28;

  --gold: #F4D35E;
  --gold-50: #FEFCF0;
  --gold-100: #FDF5D1;
  --gold-200: #FAEBA3;
  --gold-300: #F8E175;
  --gold-400: #F6D747;
  --gold-500: #F4D35E;
  --gold-600: #DDB52E;
  --gold-700: #A88A23;
  --gold-800: #735E18;
  --gold-900: #3E330D;

  --wine: #D8315B;
  --wine-50: #FBEDF1;
  --wine-100: #F5D0DA;
  --wine-200: #ECA1B5;
  --wine-300: #E37290;
  --wine-400: #DA436B;
  --wine-500: #D8315B;
  --wine-600: #AD2749;
  --wine-700: #821D37;
  --wine-800: #561424;
  --wine-900: #2B0A12;

  /* === Neutrals (warm) === */
  --cream: #FDFBF6;
  --cream-100: #F8F4EB;
  --cream-200: #F0EAD9;
  --ink: #0D1225;
  --ink-100: #2C3347;
  --ink-200: #4C546A;
  --ink-300: #6D7487;
  --ink-400: #9197A6;
  --ink-50: #F5F6F8;

  /* === Semantic === */
  --success: #2E9E5A;
  --terminal: #4ADE80;
  --error: var(--wine);
  --warning: #D4960A;

  /* === Typography === */
  --font-serif: 'Playfair Display', 'Noto Serif SC', Georgia, serif;
  --font-sans: 'Inter', 'Noto Sans SC', -apple-system, sans-serif;
  --font-display: 'Cormorant Garamond', 'Noto Serif SC', Georgia, serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', Consolas, monospace;

  /* === Spacing (8px base) === */
  --sp-1: 0.25rem;  /* 4px */
  --sp-2: 0.5rem;   /* 8px */
  --sp-3: 0.75rem;  /* 12px */
  --sp-4: 1rem;     /* 16px */
  --sp-5: 1.5rem;   /* 24px */
  --sp-6: 2rem;     /* 32px */
  --sp-8: 3rem;     /* 48px */
  --sp-10: 4rem;    /* 64px */
  --sp-12: 6rem;    /* 96px */
  --sp-16: 8rem;    /* 128px */

  /* === Radius === */
  --r-sm: 4px;
  --r-md: 8px;
  --r-lg: 12px;
  --r-xl: 20px;
  --r-full: 9999px;

  /* === Shadows (blue-tinted) === */
  --shadow-sm: 0 1px 3px rgba(10,36,99,0.08);
  --shadow-md: 0 4px 16px rgba(10,36,99,0.10);
  --shadow-lg: 0 8px 32px rgba(10,36,99,0.12);
  --shadow-xl: 0 16px 48px rgba(10,36,99,0.16);
  --shadow-gold: 0 4px 20px rgba(244,211,94,0.3);
  --shadow-wine: 0 4px 20px rgba(216,49,91,0.25);

  /* === Transitions === */
  --ease: cubic-bezier(0.16, 1, 0.3, 1);
  --t-fast: 200ms var(--ease);
  --t-base: 350ms var(--ease);
  --t-slow: 600ms var(--ease);

  /* === Layout === */
  --container: min(1200px, 92vw);
  --container-narrow: min(720px, 92vw);
}
```

---

## 43. Base Reset（基础重置 — 每个模板必备）

```css
*, *::before, *::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
html {
  -webkit-text-size-adjust: 100%;
  scroll-behavior: smooth;
}
body {
  font-family: var(--font-sans);
  background: var(--cream);
  color: var(--ink);
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
img, picture, video, canvas, svg {
  display: block;
  max-width: 100%;
  height: auto;
}
input, button, textarea, select {
  font: inherit;
  color: inherit;
}
a { color: inherit; }
ul, ol { list-style: none; }
```

---

## Google Fonts 引入（每个模板必备）

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;1,400;1,500;1,600;1,700&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400;1,500&family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

---

## 19. Utility Classes（工具类）

```css
/* Containers */
.container { max-width: var(--container); margin: 0 auto; padding: 0 var(--sp-4); }
.container-narrow { max-width: var(--container-narrow); margin: 0 auto; padding: 0 var(--sp-4); }

/* Section spacing */
.section { padding: clamp(var(--sp-8), 8vw, var(--sp-12)) var(--sp-4); }
.section-sm { padding: var(--sp-6) var(--sp-4); }

/* Text alignment */
.text-center { text-align: center; }
.text-left { text-align: left; }
.text-right { text-align: right; }

/* Flex utilities */
.flex { display: flex; }
.flex-col { flex-direction: column; }
.items-center { align-items: center; }
.justify-center { justify-content: center; }
.justify-between { justify-content: space-between; }
.gap-2 { gap: var(--sp-2); }
.gap-4 { gap: var(--sp-4); }
.gap-6 { gap: var(--sp-6); }
.flex-wrap { flex-wrap: wrap; }

/* Grid */
.grid-2 { display: grid; grid-template-columns: repeat(2, 1fr); gap: var(--sp-6); }
.grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: var(--sp-5); }
.grid-4 { display: grid; grid-template-columns: repeat(4, 1fr); gap: var(--sp-4); }
@media (max-width: 900px) {
  .grid-3, .grid-4 { grid-template-columns: repeat(2, 1fr); }
}
@media (max-width: 600px) {
  .grid-2, .grid-3, .grid-4 { grid-template-columns: 1fr; }
}

/* Text colors */
.text-royal { color: var(--royal); }
.text-gold { color: var(--gold); }
.text-wine { color: var(--wine); }
.text-muted { color: var(--ink-300); }

/* Selection */
::selection { background: var(--gold); color: var(--royal); }

/* Smooth scroll */
html { scroll-behavior: smooth; }

/* Body base */
body {
  font-family: var(--font-sans);
  background: var(--cream);
  color: var(--ink);
  margin: 0;
  -webkit-font-smoothing: antialiased;
}
```
