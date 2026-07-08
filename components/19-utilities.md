# FEIHONG Design System — Utilities
# N°19 · 工具类
> Helper classes: selection, focus, scrollbar, print styles, accessibility, spacing, flex/grid utilities, and truncation.
> 辅助工具类：选中样式、焦点态、滚动条、打印样式、无障碍、间距、Flex/Grid工具和文本截断。
> Part of FEIHONG Design System v7.0 · 所有组件遵循 DNA.md 色彩字体规范
---

### Selection · 文本选中样式

```css
::selection {
  background: var(--gold);
  color: var(--royal);
}

::-moz-selection {
  background: var(--gold);
  color: var(--royal);
}
```

### Focus Visible · 键盘焦点样式

```css
:focus-visible {
  outline: 2px solid var(--gold);
  outline-offset: 2px;
  border-radius: var(--r-sm);
}
```

### Smooth Scroll · 平滑滚动

```css
html {
  scroll-behavior: smooth;
}

@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }
}
```

### Reduced Motion · 无障碍动画降级

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

### Scrollbar Styling · 滚动条样式

```css
/* Webkit browsers */
::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

::-webkit-scrollbar-track {
  background: var(--cream-100);
}

::-webkit-scrollbar-thumb {
  background: var(--cream-200);
  border-radius: var(--r-full);
}

::-webkit-scrollbar-thumb:hover {
  background: var(--gold);
}

/* Firefox */
* {
  scrollbar-width: thin;
  scrollbar-color: var(--cream-200) var(--cream-100);
}
```

### Print Styles · 打印样式

```css
@media print {
  *,
  *::before,
  *::after {
    background: transparent !important;
    color: #000 !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }

  body {
    font-family: var(--font-serif);
    font-size: 12pt;
    line-height: 1.5;
  }

  a {
    text-decoration: underline;
  }

  a[href]::after {
    content: " (" attr(href) ")";
    font-size: 10pt;
    color: #666;
  }

  a[href^="#"]::after,
  a[href^="javascript:"]::after {
    content: "";
  }

  pre, blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }

  thead {
    display: table-header-group;
  }

  tr, img {
    page-break-inside: avoid;
  }

  img {
    max-width: 100% !important;
  }

  p, h2, h3 {
    orphans: 3;
    widows: 3;
  }

  h2, h3 {
    page-break-after: avoid;
  }

  .navbar, .footer, .social-links, .btn, .modal,
  .anchor-nav, .scrollspy-nav, .bookmark-ribbon {
    display: none !important;
  }
}
```

### Container Helpers · 容器辅助类

```css
.container {
  max-width: var(--container);
  margin: 0 auto;
  padding: 0 var(--sp-4);
}

.container-narrow {
  max-width: var(--container-narrow);
  margin: 0 auto;
  padding: 0 var(--sp-4);
}
```

### Section Spacing · 区块间距

```css
.section {
  padding: clamp(var(--sp-8), 8vw, var(--sp-12)) var(--sp-4);
}

.section-sm {
  padding: var(--sp-6) var(--sp-4);
}
```

### Text Alignment · 文本对齐

```css
.text-center { text-align: center; }
.text-left { text-align: left; }
.text-right { text-align: right; }
```

### Flex Utilities · Flex 工具类

```css
.flex { display: flex; }
.flex-col { flex-direction: column; }
.items-center { align-items: center; }
.justify-center { justify-content: center; }
.justify-between { justify-content: space-between; }
.gap-2 { gap: var(--sp-2); }
.gap-4 { gap: var(--sp-4); }
.gap-6 { gap: var(--sp-6); }
.flex-wrap { flex-wrap: wrap; }
```

### Grid Utilities · Grid 工具类

```css
.grid-2 { display: grid; grid-template-columns: repeat(2, 1fr); gap: var(--sp-6); }
.grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: var(--sp-5); }
.grid-4 { display: grid; grid-template-columns: repeat(4, 1fr); gap: var(--sp-4); }

@media (max-width: 900px) {
  .grid-3, .grid-4 { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 600px) {
  .grid-2, .grid-3, .grid-4 { grid-template-columns: 1fr; }
}
```

### Text Colors · 文字颜色

```css
.text-royal { color: var(--royal); }
.text-gold { color: var(--gold); }
.text-wine { color: var(--wine); }
.text-muted { color: var(--ink-300); }
```

### Visibility & Accessibility · 可见性与无障碍

```css
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

.hidden { display: none !important; }

@media (max-width: 768px) {
  .hide-mobile { display: none !important; }
}

@media (min-width: 769px) {
  .hide-desktop { display: none !important; }
}
```

### Image Helpers · 图片辅助

```css
.img-responsive {
  max-width: 100%;
  height: auto;
  display: block;
}

.img-rounded {
  border-radius: var(--r-lg);
}

.img-circle {
  border-radius: 50%;
}
```

### Truncation · 文本截断

```css
.truncate {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.line-clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
```

### Z-Index Scale · 层级管理

```css
.z-dropdown { z-index: 50; }
.z-sticky { z-index: 100; }
.z-fixed { z-index: 200; }
.z-modal-backdrop { z-index: 900; }
.z-modal { z-index: 1000; }
.z-toast { z-index: 1100; }
```
