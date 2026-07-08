# Feihong Design System · Component Library
# 飞鸿品牌设计系统 · 组件库

> 所有组件的完整 HTML + CSS 代码。使用时直接复制代码，不使用浏览器默认样式。
> 每个组件都遵循 brand-dna.md 的色彩、字体、间距规范。

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

## 1. Typography 排版组件

### 1.1 Hero Heading（首屏大标题）

```html
<h1 class="hero-title">
  设计有温度的<br>
  <span class="gold-accent">数字体验</span>
</h1>
```
```css
.hero-title {
  font-family: var(--font-serif);
  font-size: clamp(2.5rem, 6vw, 5rem);
  font-weight: 700;
  line-height: 1.05;
  letter-spacing: -0.02em;
  color: var(--ink);
  margin: 0;
}
.hero-title .gold-accent {
  color: var(--royal);
  font-style: italic;
  position: relative;
}
.hero-title .gold-accent::after {
  content: '';
  position: absolute;
  bottom: 0.05em;
  left: 0;
  width: 100%;
  height: 0.12em;
  background: var(--gold);
  z-index: -1;
  border-radius: 2px;
}
```

### 1.2 Section Title（章节标题）

```html
<div class="section-title">
  <span class="section-number">01</span>
  <h2>精选作品</h2>
  <div class="title-gold-line"></div>
</div>
```
```css
.section-title {
  display: flex;
  align-items: center;
  gap: var(--sp-4);
  margin-bottom: var(--sp-8);
}
.section-title .section-number {
  font-family: var(--font-display);
  font-size: clamp(2rem, 4vw, 3.5rem);
  font-style: italic;
  font-weight: 300;
  color: var(--gold);
  line-height: 1;
}
.section-title h2 {
  font-family: var(--font-serif);
  font-size: clamp(1.5rem, 3vw, 2.5rem);
  font-weight: 700;
  color: var(--ink);
  margin: 0;
}
.title-gold-line {
  flex: 1;
  height: 2px;
  max-width: 80px;
  background: linear-gradient(90deg, var(--gold) 0%, transparent 100%);
}
```

### 1.3 Subsection Title（子标题）

```html
<h3 class="subsection-title">设计原则</h3>
```
```css
.subsection-title {
  font-family: var(--font-serif);
  font-size: clamp(1.25rem, 2vw, 1.75rem);
  font-weight: 600;
  color: var(--ink);
  margin: 0 0 var(--sp-4);
}
```

### 1.4 Body Paragraph（正文段落）

```html
<p class="body-text">这是一段正文内容。设计不是装饰，而是解决问题的方式。好的设计让人感到被理解，而不是被炫技。</p>
```
```css
.body-text {
  font-family: var(--font-sans);
  font-size: clamp(1rem, 1.2vw, 1.125rem);
  line-height: 1.75;
  color: var(--ink-100);
  margin: 0 0 var(--sp-4);
  max-width: 65ch;
}
```

### 1.5 Small Text / Caption（小字说明）

```html
<p class="caption-text">2024 · 品牌设计项目</p>
```
```css
.caption-text {
  font-family: var(--font-sans);
  font-size: 0.8125rem;
  line-height: 1.6;
  color: var(--ink-300);
  letter-spacing: 0.02em;
  text-transform: uppercase;
  margin: 0;
}
```

### 1.6 Eyebrow Label（标签式小标题）

```html
<span class="eyebrow">个人品牌</span>
```
```css
.eyebrow {
  display: inline-block;
  font-family: var(--font-sans);
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--royal);
  background: var(--royal-50);
  padding: var(--sp-1) var(--sp-3);
  border-radius: var(--r-sm);
  margin-bottom: var(--sp-3);
}
```

---

## 2. Quote / Pull Quote（引用块）

### 2.1 Gold Serif Pull Quote（金色衬线大引用 — 签名式组件）

```html
<blockquote class="pull-quote">
  <span class="quote-mark">&ldquo;</span>
  <p>好的设计是隐形的。它不喧哗，却让人感到被理解。</p>
  <span class="quote-mark quote-mark-end">&rdquo;</span>
  <cite>— 飞鸿</cite>
</blockquote>
```
```css
.pull-quote {
  position: relative;
  padding: var(--sp-8) var(--sp-6);
  margin: var(--sp-8) 0;
  text-align: center;
}
.pull-quote .quote-mark {
  font-family: var(--font-serif);
  font-size: 5rem;
  line-height: 1;
  color: var(--gold);
  display: block;
}
.pull-quote .quote-mark-end {
  text-align: right;
  margin-top: -2rem;
}
.pull-quote p {
  font-family: var(--font-display);
  font-size: clamp(1.25rem, 2.5vw, 2rem);
  font-style: italic;
  font-weight: 400;
  line-height: 1.5;
  color: var(--royal);
  margin: var(--sp-4) auto;
  max-width: 700px;
}
.pull-quote cite {
  font-family: var(--font-sans);
  font-size: 0.875rem;
  font-style: normal;
  color: var(--ink-300);
  letter-spacing: 0.1em;
  text-transform: uppercase;
}
```

### 2.2 Inline Quote（行内引用/斜体强调）

```html
<p>正如设计师所说，<em class="inline-quote">细节不是细节，它们构成了设计</em>。</p>
```
```css
.inline-quote {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 1.1em;
  color: var(--royal);
  font-weight: 500;
}
```

---

## 3. Buttons 按钮

### 3.1 Primary Button（主按钮 — 皇家蓝）

```html
<a href="#" class="btn btn-primary">了解更多</a>
<button class="btn btn-primary">开始使用</button>
```
```css
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--sp-2);
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  font-weight: 500;
  padding: var(--sp-3) var(--sp-5);
  border-radius: var(--r-md);
  border: none;
  cursor: pointer;
  text-decoration: none;
  transition: all var(--t-fast);
  white-space: nowrap;
}
.btn-primary {
  background: var(--royal);
  color: #fff;
  box-shadow: var(--shadow-md);
}
.btn-primary:hover {
  background: var(--royal-700);
  transform: translateY(-1px);
  box-shadow: var(--shadow-lg);
}
```

### 3.2 CTA Button（酒红CTA — 最高行动优先级）

```html
<a href="#" class="btn btn-cta">立即预约</a>
```
```css
.btn-cta {
  background: var(--wine);
  color: #fff;
  box-shadow: var(--shadow-wine);
}
.btn-cta:hover {
  background: var(--wine-600);
  transform: translateY(-1px);
  box-shadow: 0 6px 24px rgba(216,49,91,0.35);
}
```

### 3.3 Gold Button（金色按钮 — 次要/高亮）

```html
<a href="#" class="btn btn-gold">查看作品</a>
```
```css
.btn-gold {
  background: var(--gold);
  color: var(--royal);
  font-weight: 600;
}
.btn-gold:hover {
  background: var(--gold-600);
  color: #fff;
  transform: translateY(-1px);
}
```

### 3.4 Outline Button（描边按钮 — 低调）

```html
<a href="#" class="btn btn-outline">下载简历</a>
```
```css
.btn-outline {
  background: transparent;
  color: var(--royal);
  border: 1.5px solid var(--royal);
}
.btn-outline:hover {
  background: var(--royal);
  color: #fff;
}
```

### 3.5 Ghost Button（幽灵按钮 — 最次要）

```html
<a href="#" class="btn btn-ghost">了解详情 →</a>
```
```css
.btn-ghost {
  background: transparent;
  color: var(--royal);
  padding: var(--sp-2) var(--sp-3);
}
.btn-ghost:hover {
  color: var(--wine);
  background: transparent;
}
.btn-ghost::after {
  content: ' →';
  transition: transform var(--t-fast);
  display: inline-block;
}
.btn-ghost:hover::after {
  transform: translateX(4px);
}
```

### 3.6 Button Sizes

```css
.btn-sm { padding: var(--sp-2) var(--sp-4); font-size: 0.8125rem; }
.btn-lg { padding: var(--sp-4) var(--sp-6); font-size: 1.0625rem; }
.btn-xl { padding: var(--sp-5) var(--sp-8); font-size: 1.125rem; }
```

---

## 4. Badges & Tags（徽章/标签）

### 4.1 Gold Badge（金色标签 — 类别/标识）

```html
<span class="badge badge-gold">设计系统</span>
<span class="badge badge-royal">品牌</span>
<span class="badge badge-wine">精选</span>
<span class="badge badge-outline">UI/UX</span>
```
```css
.badge {
  display: inline-flex;
  align-items: center;
  font-family: var(--font-sans);
  font-size: 0.75rem;
  font-weight: 500;
  padding: 0.2rem var(--sp-3);
  border-radius: var(--r-sm);
  letter-spacing: 0.04em;
}
.badge-gold { background: var(--gold); color: var(--royal); }
.badge-royal { background: var(--royal); color: #fff; }
.badge-wine { background: var(--wine); color: #fff; }
.badge-outline { background: transparent; color: var(--ink-200); border: 1px solid var(--cream-200); }
.badge-soft-royal { background: var(--royal-50); color: var(--royal); }
```

### 4.2 Dot Indicator（圆点指示器）

```html
<span class="dot dot-gold"></span> 设计
<span class="dot dot-royal"></span> 开发
<span class="dot dot-wine"></span> 品牌
```
```css
.dot {
  display: inline-block;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin-right: var(--sp-2);
}
.dot-gold { background: var(--gold); }
.dot-royal { background: var(--royal); }
.dot-wine { background: var(--wine); }
```

---

## 5. Cards 卡片

### 5.1 Feature Card（功能/特色卡片）

```html
<div class="card card-feature">
  <div class="card-icon">✦</div>
  <h3 class="card-title">品牌设计</h3>
  <p class="card-desc">从logo到完整视觉体系，打造有记忆点的个人品牌。</p>
  <a href="#" class="card-link">了解更多 →</a>
</div>
```
```css
.card {
  background: #fff;
  border-radius: var(--r-lg);
  padding: var(--sp-6);
  transition: all var(--t-base);
  position: relative;
  overflow: hidden;
}
.card-feature {
  border: 1px solid var(--cream-200);
}
.card-feature::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--royal), var(--gold), var(--wine));
  opacity: 0;
  transition: opacity var(--t-base);
}
.card-feature:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-lg);
  border-color: var(--gold-200);
}
.card-feature:hover::before { opacity: 1; }
.card-icon {
  font-size: 1.75rem;
  color: var(--gold);
  margin-bottom: var(--sp-4);
  display: inline-flex;
  width: 48px;
  height: 48px;
  align-items: center;
  justify-content: center;
  background: var(--gold-50);
  border-radius: var(--r-md);
}
.card-title {
  font-family: var(--font-serif);
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--ink);
  margin: 0 0 var(--sp-2);
}
.card-desc {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  line-height: 1.65;
  color: var(--ink-200);
  margin: 0 0 var(--sp-4);
}
.card-link {
  font-family: var(--font-sans);
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--royal);
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: 4px;
  transition: gap var(--t-fast);
}
.card-link:hover {
  gap: 8px;
  color: var(--wine);
}
```

### 5.2 Project Card（项目/作品集卡片）

```html
<div class="card card-project">
  <div class="card-project-image">
    <img src="project.jpg" alt="项目封面">
    <div class="card-project-overlay">
      <span class="badge badge-gold">查看案例</span>
    </div>
  </div>
  <div class="card-project-body">
    <span class="caption-text">2024 · 品牌视觉</span>
    <h3 class="card-title">某某科技品牌升级</h3>
    <p class="card-desc">从传统到现代的品牌视觉重塑</p>
  </div>
</div>
```
```css
.card-project {
  padding: 0;
  border: none;
  background: #fff;
  overflow: hidden;
  cursor: pointer;
}
.card-project-image {
  position: relative;
  aspect-ratio: 4/3;
  overflow: hidden;
  background: var(--royal-50);
}
.card-project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform var(--t-slow);
}
.card-project:hover .card-project-image img {
  transform: scale(1.05);
}
.card-project-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(10,36,99,0.7), rgba(10,36,99,0.3));
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity var(--t-base);
}
.card-project:hover .card-project-overlay { opacity: 1; }
.card-project-body { padding: var(--sp-5); }
```

### 5.3 Stat Card（数据/统计卡片）

```html
<div class="stat-card">
  <span class="stat-number">8+</span>
  <span class="stat-label">年设计经验</span>
</div>
```
```css
.stat-card {
  text-align: center;
  padding: var(--sp-6) var(--sp-4);
  position: relative;
}
.stat-card::after {
  content: '';
  position: absolute;
  right: 0;
  top: 20%;
  height: 60%;
  width: 1px;
  background: var(--cream-200);
}
.stat-card:last-child::after { display: none; }
.stat-number {
  font-family: var(--font-serif);
  font-size: clamp(2rem, 4vw, 3.5rem);
  font-weight: 700;
  color: var(--royal);
  line-height: 1;
  display: block;
}
.stat-label {
  font-family: var(--font-sans);
  font-size: 0.875rem;
  color: var(--ink-300);
  margin-top: var(--sp-2);
  display: block;
}
```

### 5.4 Testimonial Card（推荐/口碑卡片）

```html
<div class="card card-testimonial">
  <div class="testimonial-stars">★★★★★</div>
  <p class="testimonial-text">飞鸿的设计有一种独特的温度，既专业又有艺术感。</p>
  <div class="testimonial-author">
    <div class="author-avatar">张</div>
    <div>
      <div class="author-name">张先生</div>
      <div class="author-title">创业公司CEO</div>
    </div>
  </div>
</div>
```
```css
.card-testimonial {
  background: var(--cream);
  border: 1px solid var(--cream-200);
}
.testimonial-stars { color: var(--gold); font-size: 1rem; letter-spacing: 2px; margin-bottom: var(--sp-3); }
.testimonial-text {
  font-family: var(--font-display);
  font-size: 1.0625rem;
  font-style: italic;
  line-height: 1.7;
  color: var(--ink-100);
  margin: 0 0 var(--sp-5);
}
.testimonial-author { display: flex; align-items: center; gap: var(--sp-3); }
.author-avatar {
  width: 40px; height: 40px; border-radius: 50%;
  background: var(--royal); color: #fff;
  display: flex; align-items: center; justify-content: center;
  font-family: var(--font-serif); font-weight: 600;
}
.author-name { font-family: var(--font-sans); font-weight: 600; font-size: 0.9375rem; color: var(--ink); }
.author-title { font-family: var(--font-sans); font-size: 0.8125rem; color: var(--ink-300); }
```

### 5.5 Dark Panel Card（深色面板 — 节奏打破）

```html
<div class="dark-panel">
  <span class="eyebrow" style="background:rgba(244,211,94,0.15);color:var(--gold);">深度合作</span>
  <h2 style="color:#fff;">准备好开始你的项目了吗？</h2>
  <p style="color:rgba(255,255,255,0.7);">让我们一起创造有温度的设计。</p>
  <a href="#" class="btn btn-gold">立即联系</a>
</div>
```
```css
.dark-panel {
  background: radial-gradient(ellipse at top left, var(--royal-700) 0%, var(--ink) 70%);
  border-radius: var(--r-xl);
  padding: clamp(var(--sp-8), 8vw, var(--sp-12));
  color: #fff;
  position: relative;
  overflow: hidden;
}
.dark-panel::before {
  content: '';
  position: absolute;
  width: 400px; height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(244,211,94,0.08) 0%, transparent 70%);
  top: -100px; right: -100px;
}
.dark-panel h2 {
  font-family: var(--font-serif);
  font-size: clamp(1.75rem, 3.5vw, 2.75rem);
  color: #fff;
  margin: var(--sp-3) 0 var(--sp-4);
}
.dark-panel p {
  font-family: var(--font-sans);
  font-size: 1.0625rem;
  color: rgba(255,255,255,0.7);
  line-height: 1.7;
  margin: 0 0 var(--sp-6);
  max-width: 500px;
}
```

---

## 6. Lists 列表

### 6.1 Gold Dot List（金色圆点列表 — 品牌签名式）

```html
<ul class="list list-gold-dot">
  <li>品牌视觉体系设计</li>
  <li>设计系统搭建与维护</li>
  <li>落地页与活动页设计</li>
  <li>用户体验优化</li>
</ul>
```
```css
.list { margin: 0; padding: 0; list-style: none; }
.list-gold-dot li {
  font-family: var(--font-sans);
  font-size: 1rem;
  line-height: 1.7;
  color: var(--ink-100);
  padding-left: var(--sp-5);
  position: relative;
  margin-bottom: var(--sp-3);
}
.list-gold-dot li::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0.7em;
  width: 8px;
  height: 8px;
  background: var(--gold);
  border-radius: 50%;
}
```

### 6.2 Serif Number List（衬线数字列表 — 教程/步骤）

```html
<ol class="list list-serif-number">
  <li>
    <strong>理解需求</strong>
    <p>深入了解项目背景和目标用户。</p>
  </li>
  <li>
    <strong>研究与草图</strong>
    <p>收集灵感，绘制大量草图。</p>
  </li>
  <li>
    <strong>视觉设计</strong>
    <p>将概念转化为精确的视觉语言。</p>
  </li>
</ol>
```
```css
.list-serif-number {
  list-style: none;
  padding: 0;
  margin: 0;
  counter-reset: serif-counter;
}
.list-serif-number li {
  counter-increment: serif-counter;
  padding-left: var(--sp-10);
  position: relative;
  margin-bottom: var(--sp-6);
}
.list-serif-number li::before {
  content: counter(serif-counter, decimal-leading-zero);
  position: absolute;
  left: 0;
  top: 0;
  font-family: var(--font-serif);
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--gold);
  font-style: italic;
  line-height: 1;
}
.list-serif-number li strong {
  font-family: var(--font-serif);
  font-size: 1.125rem;
  color: var(--ink);
  display: block;
  margin-bottom: var(--sp-1);
}
.list-serif-number li p {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  line-height: 1.7;
  color: var(--ink-200);
  margin: 0;
}
```

### 6.3 Check List（金色勾选列表）

```html
<ul class="list list-check">
  <li>包含完整源文件</li>
  <li>3次免费修改</li>
  <li>终身使用授权</li>
</ul>
```
```css
.list-check li {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  line-height: 1.7;
  color: var(--ink-100);
  padding-left: var(--sp-6);
  position: relative;
  margin-bottom: var(--sp-2);
}
.list-check li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--royal);
  font-weight: 700;
  background: var(--gold);
  width: 20px;
  height: 20px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.75rem;
  top: 0.3em;
}
```

---

## 7. Form Elements 表单

### 7.1 Input（输入框）

```html
<div class="form-group">
  <label class="form-label">姓名</label>
  <input type="text" class="form-input" placeholder="请输入您的姓名">
</div>
```
```css
.form-group { margin-bottom: var(--sp-5); }
.form-label {
  display: block;
  font-family: var(--font-sans);
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--ink);
  margin-bottom: var(--sp-2);
}
.form-input {
  width: 100%;
  font-family: var(--font-sans);
  font-size: 1rem;
  padding: var(--sp-3) var(--sp-4);
  border: 1.5px solid var(--cream-200);
  border-radius: var(--r-md);
  background: #fff;
  color: var(--ink);
  transition: all var(--t-fast);
  outline: none;
}
.form-input:focus {
  border-color: var(--royal);
  box-shadow: 0 0 0 3px var(--royal-50);
}
.form-input::placeholder { color: var(--ink-400); }
```

### 7.2 Textarea

```html
<div class="form-group">
  <label class="form-label">项目描述</label>
  <textarea class="form-input form-textarea" rows="4" placeholder="简单描述您的项目..."></textarea>
</div>
```
```css
.form-textarea { resize: vertical; min-height: 120px; line-height: 1.6; }
```

### 7.3 Select

```html
<div class="form-group">
  <label class="form-label">项目类型</label>
  <select class="form-input form-select">
    <option>品牌设计</option>
    <option>落地页设计</option>
    <option>设计系统</option>
  </select>
</div>
```
```css
.form-select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='8' viewBox='0 0 12 8'%3E%3Cpath d='M1 1l5 5 5-5' stroke='%230A2463' stroke-width='1.5' fill='none' stroke-linecap='round'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right var(--sp-4) center;
  padding-right: var(--sp-8);
}
```

---

## 8. Navigation 导航

### 8.1 Navbar（顶部导航栏）

```html
<nav class="navbar">
  <a href="#" class="nav-logo">Feihong<span style="color:var(--gold)">.</span></a>
  <div class="nav-links">
    <a href="#work" class="nav-link">作品</a>
    <a href="#about" class="nav-link">关于</a>
    <a href="#services" class="nav-link">服务</a>
    <a href="#contact" class="btn btn-primary btn-sm">联系我</a>
  </div>
</nav>
```
```css
.navbar {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: var(--sp-4) clamp(var(--sp-4), 4vw, var(--sp-8));
  background: rgba(253,251,246,0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid transparent;
  transition: all var(--t-base);
}
.navbar.scrolled {
  border-bottom-color: var(--cream-200);
  box-shadow: var(--shadow-sm);
}
.nav-logo {
  font-family: var(--font-serif);
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--royal);
  text-decoration: none;
}
.nav-links { display: flex; align-items: center; gap: var(--sp-6); }
.nav-link {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  color: var(--ink-100);
  text-decoration: none;
  position: relative;
  transition: color var(--t-fast);
}
.nav-link::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--gold);
  transition: width var(--t-base);
}
.nav-link:hover { color: var(--royal); }
.nav-link:hover::after { width: 100%; }
```

### 8.2 Footer（页脚）

```html
<footer class="footer">
  <div class="footer-inner">
    <div class="footer-brand">
      <a href="#" class="nav-logo">Feihong<span style="color:var(--gold)">.</span></a>
      <p class="body-text" style="font-size:0.9375rem;color:var(--ink-300);margin-top:var(--sp-3);">
        设计有温度的数字体验。
      </p>
    </div>
    <div class="footer-links">
      <div class="footer-col">
        <h4>导航</h4>
        <a href="#">作品</a><a href="#">关于</a><a href="#">服务</a>
      </div>
      <div class="footer-col">
        <h4>联系</h4>
        <a href="#">hello@feihong.design</a><a href="#">微信</a><a href="#">小红书</a>
      </div>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2024 Feihong. Designed with ♥</p>
  </div>
</footer>
```
```css
.footer {
  background: var(--ink);
  color: #fff;
  padding: var(--sp-12) var(--sp-6) var(--sp-6);
  margin-top: var(--sp-16);
}
.footer-inner {
  max-width: var(--container);
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--sp-8);
}
.footer-col h4 {
  font-family: var(--font-sans);
  font-size: 0.8125rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.12em;
  color: var(--gold);
  margin: 0 0 var(--sp-4);
}
.footer-col a {
  display: block;
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  color: rgba(255,255,255,0.6);
  text-decoration: none;
  margin-bottom: var(--sp-2);
  transition: color var(--t-fast);
}
.footer-col a:hover { color: var(--gold); }
.footer-bottom {
  max-width: var(--container);
  margin: var(--sp-8) auto 0;
  padding-top: var(--sp-4);
  border-top: 1px solid rgba(255,255,255,0.1);
  font-family: var(--font-sans);
  font-size: 0.8125rem;
  color: rgba(255,255,255,0.4);
}
@media (max-width: 600px) {
  .footer-inner { grid-template-columns: 1fr; }
}
```

---

## 9. Dividers & Decorative Elements（分隔与装饰）

### 9.1 Gold Line Divider（金色装饰分隔线）

```html
<div class="divider-gold"></div>
<div class="divider-dots"></div>
```
```css
.divider-gold {
  height: 1px;
  background: linear-gradient(90deg, transparent 0%, var(--gold) 30%, var(--gold) 70%, transparent 100%);
  margin: var(--sp-8) 0;
}
.divider-dots {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--sp-3);
  margin: var(--sp-8) 0;
}
.divider-dots span {
  width: 6px; height: 6px; border-radius: 50%;
  background: var(--gold);
}
.divider-dots span:nth-child(2) { background: var(--royal); width: 8px; height: 8px; }
.divider-dots span:nth-child(3) { background: var(--wine); }
```

### 9.2 Decorative Section Number（装饰性大数字）

```html
<div class="decor-number" aria-hidden="true">01</div>
```
```css
.decor-number {
  position: absolute;
  font-family: var(--font-serif);
  font-size: clamp(6rem, 15vw, 12rem);
  font-weight: 700;
  font-style: italic;
  color: var(--royal);
  opacity: 0.04;
  line-height: 1;
  z-index: 0;
  pointer-events: none;
  user-select: none;
}
```

### 9.3 Decorative English Text（装饰性英文）

```html
<div class="decor-text" aria-hidden="true">PORTFOLIO</div>
```
```css
.decor-text {
  position: absolute;
  font-family: var(--font-serif);
  font-size: clamp(4rem, 10vw, 8rem);
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--royal);
  opacity: 0.04;
  white-space: nowrap;
  z-index: 0;
  pointer-events: none;
  user-select: none;
}
```

### 9.4 Avatar（头像）

```html
<div class="avatar avatar-lg">
  <img src="assets/avatar.jpg" alt="飞鸿">
</div>
```
```css
.avatar {
  border-radius: 50%;
  overflow: hidden;
  border: 3px solid var(--gold);
  box-shadow: var(--shadow-gold);
}
.avatar img { width: 100%; height: 100%; object-fit: cover; }
.avatar-sm { width: 40px; height: 40px; }
.avatar-md { width: 64px; height: 64px; }
.avatar-lg { width: 120px; height: 120px; }
.avatar-xl {
  width: clamp(200px, 25vw, 320px);
  height: clamp(200px, 25vw, 320px);
  border-width: 4px;
}
```

### 9.5 IP Character（IP形象展示）

```html
<div class="character-wrap">
  <img src="assets/character.png" alt="飞鸿IP形象" class="character-img">
</div>
```
```css
.character-wrap {
  position: relative;
}
.character-img {
  max-width: 100%;
  height: auto;
  filter: drop-shadow(0 20px 40px rgba(10,36,99,0.15));
  transition: transform var(--t-slow);
}
.character-img:hover { transform: translateY(-8px) rotate(-2deg); }
```

---

## 10. Code Block（代码块）

```html
<pre class="code-block"><code>const design = "有温度的设计";
console.log(design);</code></pre>
```
```css
.code-block {
  background: var(--ink);
  color: #E2E8F0;
  font-family: var(--font-mono);
  font-size: 0.875rem;
  line-height: 1.7;
  padding: var(--sp-5);
  border-radius: var(--r-lg);
  overflow-x: auto;
  border-left: 3px solid var(--gold);
  margin: var(--sp-5) 0;
}
.code-block code { font-family: inherit; }
/* Inline code */
code.inline-code {
  font-family: var(--font-mono);
  font-size: 0.875em;
  background: var(--royal-50);
  color: var(--royal);
  padding: 0.15em 0.4em;
  border-radius: var(--r-sm);
}
```

---

## 11. Table（表格）

```html
<div class="table-wrap">
  <table class="brand-table">
    <thead>
      <tr><th>服务</th><th>周期</th><th>价格</th></tr>
    </thead>
    <tbody>
      <tr><td>品牌设计</td><td>4-6周</td><td>¥15,000起</td></tr>
      <tr><td>落地页设计</td><td>2-3周</td><td>¥8,000起</td></tr>
    </tbody>
  </table>
</div>
```
```css
.table-wrap { overflow-x: auto; margin: var(--sp-5) 0; }
.brand-table {
  width: 100%;
  border-collapse: collapse;
  font-family: var(--font-sans);
  font-size: 0.9375rem;
}
.brand-table th {
  text-align: left;
  padding: var(--sp-3) var(--sp-4);
  font-weight: 600;
  color: var(--royal);
  background: var(--royal-50);
  font-size: 0.8125rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}
.brand-table th:first-child { border-radius: var(--r-md) 0 0 0; }
.brand-table th:last-child { border-radius: 0 var(--r-md) 0 0; }
.brand-table td {
  padding: var(--sp-4);
  color: var(--ink-100);
  border-bottom: 1px solid var(--cream-200);
}
.brand-table tr:hover td { background: var(--cream); }
```

---

## 12. Alert / Notification（提示框）

```html
<div class="alert alert-info">ℹ️ 这是一条提示信息</div>
<div class="alert alert-success">✓ 操作成功</div>
<div class="alert alert-warning">⚠️ 请注意</div>
<div class="alert alert-wine">重要提醒</div>
```
```css
.alert {
  padding: var(--sp-3) var(--sp-4);
  border-radius: var(--r-md);
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  line-height: 1.6;
  margin: var(--sp-4) 0;
  border-left: 3px solid;
}
.alert-info { background: var(--royal-50); color: var(--royal); border-color: var(--royal); }
.alert-success { background: #ECFDF5; color: #065F46; border-color: var(--success); }
.alert-warning { background: var(--gold-50); color: var(--gold-800); border-color: var(--gold); }
.alert-wine { background: var(--wine-50); color: var(--wine-700); border-color: var(--wine); }
```

---

## 13. Progress / Bar（进度条）

```html
<div class="progress">
  <div class="progress-label">设计能力</div>
  <div class="progress-bar"><div class="progress-fill" style="width:95%"></div></div>
</div>
```
```css
.progress { margin-bottom: var(--sp-4); }
.progress-label {
  font-family: var(--font-sans);
  font-size: 0.875rem;
  color: var(--ink-100);
  margin-bottom: var(--sp-2);
  display: flex;
  justify-content: space-between;
}
.progress-bar {
  height: 6px;
  background: var(--cream-200);
  border-radius: var(--r-full);
  overflow: hidden;
}
.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, var(--royal), var(--gold));
  border-radius: var(--r-full);
  transition: width var(--t-slow);
}
```

---

## 14. Social Links（社交链接）

```html
<div class="social-links">
  <a href="#" class="social-link" aria-label="GitHub">GH</a>
  <a href="#" class="social-link" aria-label="微信">WX</a>
  <a href="#" class="social-link" aria-label="小红书">RED</a>
  <a href="#" class="social-link" aria-label="邮箱">@</a>
</div>
```
```css
.social-links { display: flex; gap: var(--sp-3); }
.social-link {
  width: 40px; height: 40px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-family: var(--font-sans);
  font-size: 0.75rem;
  font-weight: 600;
  background: var(--royal-50);
  color: var(--royal);
  text-decoration: none;
  transition: all var(--t-fast);
}
.social-link:hover {
  background: var(--royal);
  color: var(--gold);
  transform: translateY(-2px);
}
```

---

## 15. Tag Group（标签组）

```html
<div class="tag-group">
  <span class="tag">品牌设计</span>
  <span class="tag">视觉系统</span>
  <span class="tag">UI/UX</span>
  <span class="tag">前端开发</span>
  <span class="tag">动效设计</span>
</div>
```
```css
.tag-group { display: flex; flex-wrap: wrap; gap: var(--sp-2); }
.tag {
  font-family: var(--font-sans);
  font-size: 0.8125rem;
  color: var(--ink-200);
  padding: var(--sp-1) var(--sp-3);
  border: 1px solid var(--cream-200);
  border-radius: var(--r-full);
  transition: all var(--t-fast);
}
.tag:hover {
  border-color: var(--gold);
  color: var(--royal);
  background: var(--gold-50);
}
```

---

## 16. Timeline（时间线）

```html
<div class="timeline">
  <div class="timeline-item">
    <div class="timeline-dot"></div>
    <div class="timeline-content">
      <span class="caption-text">2024</span>
      <h4>创立个人工作室</h4>
      <p>专注于为个人品牌和初创公司提供设计服务。</p>
    </div>
  </div>
  <div class="timeline-item">
    <div class="timeline-dot"></div>
    <div class="timeline-content">
      <span class="caption-text">2022</span>
      <h4>加入某科技公司</h4>
      <p>担任高级设计师，主导设计系统搭建。</p>
    </div>
  </div>
</div>
```
```css
.timeline { position: relative; padding-left: var(--sp-8); }
.timeline::before {
  content: '';
  position: absolute;
  left: 7px;
  top: 8px;
  bottom: 8px;
  width: 2px;
  background: linear-gradient(180deg, var(--gold), var(--cream-200));
}
.timeline-item { position: relative; margin-bottom: var(--sp-6); }
.timeline-dot {
  position: absolute;
  left: -25px;
  top: 6px;
  width: 16px; height: 16px;
  border-radius: 50%;
  background: var(--gold);
  border: 3px solid var(--cream);
  box-shadow: 0 0 0 2px var(--gold);
}
.timeline-content h4 {
  font-family: var(--font-serif);
  font-size: 1.0625rem;
  font-weight: 600;
  color: var(--ink);
  margin: var(--sp-1) 0 var(--sp-1);
}
.timeline-content p {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  color: var(--ink-200);
  line-height: 1.6;
  margin: 0;
}
```

---

## 17. Hero Patterns（首屏布局组件）

### 17.1 Asymmetric Hero（非对称Hero）

```html
<section class="hero-asymmetric">
  <div class="hero-content">
    <span class="eyebrow">设计师 · 品牌顾问</span>
    <h1 class="hero-title">创造<span class="gold-accent">有温度</span>的设计</h1>
    <p class="body-text">我是飞鸿，一名专注于个人品牌和数字体验的设计师。相信好的设计不仅美观，更能传递真实的情感与价值。</p>
    <div style="display:flex;gap:var(--sp-3);flex-wrap:wrap;">
      <a href="#work" class="btn btn-cta">查看作品</a>
      <a href="#contact" class="btn btn-outline">联系我</a>
    </div>
  </div>
  <div class="hero-visual">
    <div class="avatar avatar-xl"><img src="assets/avatar.jpg" alt="飞鸿"></div>
    <div class="decor-number" style="top:-2rem;right:-2rem;">07</div>
  </div>
</section>
```
```css
.hero-asymmetric {
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: clamp(var(--sp-8), 8vw, var(--sp-12));
  align-items: center;
  min-height: 85vh;
  padding: clamp(var(--sp-8), 12vw, var(--sp-16)) var(--sp-6);
  max-width: var(--container);
  margin: 0 auto;
  position: relative;
}
.hero-visual {
  position: relative;
  display: flex;
  justify-content: center;
}
@media (max-width: 768px) {
  .hero-asymmetric { grid-template-columns: 1fr; text-align: center; min-height: auto; padding-top: var(--sp-12); }
  .hero-visual { order: -1; }
}
```

---

## 18. Scroll Reveal Animation（滚动入场动画）

```css
/* 在 <style> 中加入 */
.reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 700ms var(--ease), transform 700ms var(--ease);
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}
.reveal-delay-1 { transition-delay: 100ms; }
.reveal-delay-2 { transition-delay: 200ms; }
.reveal-delay-3 { transition-delay: 300ms; }

@media (prefers-reduced-motion: reduce) {
  .reveal { opacity: 1; transform: none; }
}
```

```javascript
// 在 <script> 中加入
const revealEls = document.querySelectorAll('.reveal');
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); }});
}, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });
revealEls.forEach(el => observer.observe(el));
```

使用方式：给需要入场动画的元素加 `class="reveal"`。

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

---

## 21. 首字下沉 Drop Cap（书卷气签名组件）

段落首字母放大下沉，模拟古典印刷书籍的开篇效果。适用于文章开头、章节引言的第一段。

```html
<p class="drop-cap">文字内容，第一个字会自动放大下沉。这里可以写一段文章开头，讲述设计的故事与品牌的精神，让阅读从第一眼就沉浸于书卷气息之中。</p>

<p class="drop-cap gold">金色首字变体，适用于更隆重、更典雅的章节开篇。</p>

<p class="drop-cap wine">酒红首字变体，带有温厚的人文气息，适合散文、手记类内容。</p>
```

```css
/* 首字下沉 — 默认皇家蓝 */
.drop-cap::first-letter {
  float: left;
  font-family: var(--font-serif);
  font-size: 4.5rem;
  line-height: 0.85;
  font-weight: 700;
  color: var(--royal);
  padding: 0.25rem 0.6rem 0 0;
  text-shadow: 1px 1px 0 rgba(10, 36, 99, 0.08);
}

/* 金色首字 */
.drop-cap.gold::first-letter {
  color: var(--gold-600);
  text-shadow: 1px 1px 0 rgba(221, 181, 46, 0.15);
}

/* 酒红首字 */
.drop-cap.wine::first-letter {
  color: var(--wine);
  text-shadow: 1px 1px 0 rgba(216, 49, 91, 0.12);
}
```

---

## 22. 边注/旁注 Marginalia（学术风）

古典学术著作中常见的旁注排版，正文旁配有斜体小字注释。桌面端双栏布局，移动端自动转为 blockquote 样式置于正文前。

```html
<div class="marginalia-wrap">
  <aside class="marginalia">这是一段旁注文字，用以补充正文的背景或引用出处，呈现学术书卷气质。</aside>
  <p>正文内容，承载主要的论述与叙事。旁注在宽屏下呈现于右侧，窄屏下自动以引用样式置于段落之前，保持阅读的流畅性。</p>
</div>

<div class="marginalia-wrap">
  <aside class="marginalia wine">酒红旁注变体，上边框与文字均为酒红色，适合标记重点注释。</aside>
  <p>不同颜色的旁注可用于区分注释类型，如原文引用、译者注、编者按等。</p>
</div>
```

```css
/* 旁注容器 — 桌面端双栏 */
.marginalia-wrap {
  display: grid;
  grid-template-columns: 4fr 1fr;
  gap: 2rem;
  align-items: start;
  margin: var(--sp-5) 0;
}

.marginalia-wrap p {
  margin: 0;
  line-height: 1.8;
  color: var(--ink);
}

/* 旁注本体 */
.marginalia {
  font-family: var(--font-display);
  font-style: italic;
  font-size: clamp(0.85rem, 1.2vw, 1rem);
  color: var(--ink-200);
  border-top: 1px solid var(--gold);
  padding-top: 0.5rem;
  line-height: 1.6;
  margin: 0;
}

/* 酒红旁注变体 */
.marginalia.wine {
  border-top-color: var(--wine);
  color: var(--wine-600);
}

/* 移动端：单列，旁注以 blockquote 样式置于正文前 */
@media (max-width: 768px) {
  .marginalia-wrap {
    grid-template-columns: 1fr;
    gap: var(--sp-3);
  }
  .marginalia {
    border-top: none;
    border-left: 3px solid var(--gold);
    padding: var(--sp-2) 0 var(--sp-2) var(--sp-4);
    font-size: 0.95rem;
  }
  .marginalia.wine {
    border-left-color: var(--wine);
  }
}
```

---

## 23. 花饰分隔符 Fleuron（古典书籍装饰）

传统印刷中用于章节之间的花饰标记，使用经典的 ❦ (U+2766) 花卉符号或 ⁂ (U+2042) 三星号，两侧以横线装饰。

```html
<div class="fleuron"><span>❦</span></div>

<div class="fleuron royal"><span>❦</span></div>

<div class="fleuron wine"><span>❦</span></div>

<div class="fleuron asterism"><span>⁂</span></div>
```

```css
/* 花饰分隔符 — 默认金色 */
.fleuron {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--sp-4);
  margin: var(--sp-10) 0;
  color: var(--gold);
  font-size: 1.5rem;
  line-height: 1;
}

.fleuron::before,
.fleuron::after {
  content: '';
  flex: 1;
  max-width: 120px;
  height: 1px;
  background: var(--gold);
  opacity: 0.6;
}

.fleuron span {
  display: inline-block;
  line-height: 1;
}

/* 皇家蓝变体 */
.fleuron.royal {
  color: var(--royal);
}
.fleuron.royal::before,
.fleuron.royal::after {
  background: var(--royal);
}

/* 酒红变体 */
.fleuron.wine {
  color: var(--wine);
}
.fleuron.wine::before,
.fleuron.wine::after {
  background: var(--wine);
}

/* 三星号（Asterism）更古典 */
.fleuron.asterism {
  font-size: 1.2rem;
  letter-spacing: 0.3em;
}
```

---

## 24. 火漆印章徽章 Wax Seal（签名式组件）

模拟火漆封印的圆形徽章，具有立体高光与阴影，适用于品牌签名、认证标记、精选推荐等场景。支持三档尺寸。

```html
<div class="wax-seal">飞鸿之印</div>

<div class="wax-seal gold">飞鸿之印</div>

<div class="wax-seal" style="--size: 60px; font-size: 0.7rem;">小印</div>

<div class="wax-seal" style="--size: 100px; font-size: 1rem;">珍藏</div>
```

```css
/* 火漆印章 — 默认酒红 */
.wax-seal {
  --size: 80px;
  width: var(--size);
  height: var(--size);
  border-radius: 50%;
  background: radial-gradient(circle at 35% 35%, #E8445A, var(--wine) 50%, #9e1f3e);
  box-shadow:
    inset -3px -3px 8px rgba(0, 0, 0, 0.25),
    inset 3px 3px 6px rgba(255, 255, 255, 0.15),
    2px 4px 12px rgba(216, 49, 91, 0.35),
    0 0 0 1px rgba(158, 31, 62, 0.4);
  color: #fff;
  font-family: var(--font-serif);
  font-weight: 700;
  font-size: 0.85rem;
  line-height: 1.1;
  letter-spacing: 0.05em;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
  flex-shrink: 0;
}

/* 金色火漆 */
.wax-seal.gold {
  background: radial-gradient(circle at 35% 35%, #F8E175, var(--gold) 50%, #A88A23);
  color: var(--royal);
  box-shadow:
    inset -3px -3px 8px rgba(0, 0, 0, 0.12),
    inset 3px 3px 6px rgba(255, 255, 255, 0.3),
    2px 4px 12px rgba(244, 211, 94, 0.4),
    0 0 0 1px rgba(168, 138, 35, 0.3);
  text-shadow: none;
}
```

---

## 25. 照片角贴 Photo Corner（相册装饰）

模拟老相册的照片角贴效果，白底衬边配金色三角形角饰，底部预留手写体说明空间。提供宝丽来和复古两种变体。

```html
<figure class="photo-frame">
  <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=600&h=400&fit=crop" alt="古典书房">
  <figcaption>古典书房，墨香如故</figcaption>
</figure>

<figure class="photo-frame polaroid">
  <img src="https://images.unsplash.com/photo-1512820790803-83ca734da794?w=600&h=400&fit=crop" alt="藏书">
  <figcaption>午后阅读时光</figcaption>
</figure>

<figure class="photo-frame vintage">
  <img src="https://images.unsplash.com/photo-1457369804613-52c61a468e7d?w=600&h=400&fit=crop" alt="旧书">
  <figcaption>泛黄的书页</figcaption>
</figure>
```

```css
/* 照片角贴 — 默认 */
.photo-frame {
  position: relative;
  background: #fff;
  padding: 1.5rem 1.5rem 3rem;
  box-shadow: var(--shadow-lg);
  max-width: 420px;
  margin: var(--sp-6) auto;
  transform: rotate(-0.5deg);
}

.photo-frame img {
  width: 100%;
  height: auto;
  display: block;
}

.photo-frame figcaption {
  position: absolute;
  bottom: 1rem;
  left: 0;
  right: 0;
  text-align: center;
  font-family: var(--font-display);
  font-style: italic;
  color: var(--ink-200);
  font-size: 0.95rem;
  margin: 0;
}

/* 两个角贴（左上+右下）使用 border 三角实现 */
.photo-frame::before {
  content: '';
  position: absolute;
  top: 8px;
  left: 8px;
  width: 0;
  height: 0;
  border-top: 20px solid var(--gold);
  border-right: 20px solid transparent;
}

.photo-frame::after {
  content: '';
  position: absolute;
  bottom: 3.5rem;
  right: 8px;
  width: 0;
  height: 0;
  border-bottom: 20px solid var(--gold);
  border-left: 20px solid transparent;
}

/* 宝丽来变体：更宽白底、轻微旋转 */
.photo-frame.polaroid {
  padding: 1.5rem 1.5rem 4rem;
  max-width: 380px;
  transform: rotate(1.5deg);
  box-shadow: var(--shadow-xl);
}
.photo-frame.polaroid figcaption {
  bottom: 1.25rem;
  font-size: 1rem;
}

/* 复古变体：深褐色调 */
.photo-frame.vintage {
  background: var(--cream-100);
  transform: rotate(-1deg);
}
.photo-frame.vintage img {
  filter: sepia(0.4) contrast(0.95) brightness(0.95);
}
.photo-frame.vintage figcaption {
  color: var(--ink-300);
}
```

---

## 26. 书签丝带 Bookmark Ribbon

左上角斜插的丝带书签，常用于卡片或推荐内容的标记。使用 `clip-path` 实现燕尾切口。

```html
<div style="position: relative; padding: var(--sp-8); background: #fff; box-shadow: var(--shadow-md); overflow: hidden;">
  <div class="bookmark-ribbon">精选推荐</div>
  <h3 style="font-family: var(--font-serif); margin-top: 0;">被标记的内容</h3>
  <p style="color: var(--ink-200);">丝带来自书签组件，贴边显示于左上角。</p>
</div>

<div style="position: relative; padding: var(--sp-8); background: #fff; box-shadow: var(--shadow-md); overflow: hidden; margin-top: var(--sp-4);">
  <div class="bookmark-ribbon gold">经典收藏</div>
  <h3 style="font-family: var(--font-serif); margin-top: 0;">金色丝带</h3>
</div>

<div style="position: relative; padding: var(--sp-8); background: var(--royal); color: #fff; box-shadow: var(--shadow-md); overflow: hidden; margin-top: var(--sp-4);">
  <div class="bookmark-ribbon royal">皇家特选</div>
  <h3 style="font-family: var(--font-serif); margin-top: 0;">皇家蓝丝带</h3>
</div>
```

```css
/* 书签丝带 — 默认酒红 */
.bookmark-ribbon {
  position: absolute;
  top: 1rem;
  left: -4px;
  background: var(--wine);
  color: #fff;
  font-size: 0.7rem;
  font-weight: 600;
  font-family: var(--font-sans);
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 0.4rem 1.2rem 0.4rem 0.8rem;
  clip-path: polygon(0 0, 100% 0, 100% 70%, 85% 100%, 70% 70%, 0 70%);
  box-shadow: 0 2px 8px rgba(216, 49, 91, 0.3);
  z-index: 2;
  line-height: 1.4;
}

/* 金色丝带 */
.bookmark-ribbon.gold {
  background: var(--gold);
  color: var(--royal);
  box-shadow: 0 2px 8px rgba(244, 211, 94, 0.4);
}

/* 皇家蓝丝带 */
.bookmark-ribbon.royal {
  background: var(--royal);
  color: var(--gold);
  box-shadow: 0 2px 8px rgba(10, 36, 99, 0.3);
}
```

---

## 27. 目录排版 Table of Contents

古典书籍风格的目录页，罗马数字编号、点状引导线、页码右对齐，金色装饰线衬于标题之下。

```html
<nav class="toc">
  <h3 class="toc-title">目 录</h3>
  <ol class="toc-list">
    <li><a href="#s1"><span class="toc-num">i</span><span class="toc-text">第一章 设计的温度</span><span class="toc-dots"></span><span class="toc-page">01</span></a></li>
    <li><a href="#s2"><span class="toc-num">ii</span><span class="toc-text">第二章 笔墨之间</span><span class="toc-dots"></span><span class="toc-page">12</span></a></li>
    <li><a href="#s3"><span class="toc-num">iii</span><span class="toc-text">第三章 色彩的呼吸</span><span class="toc-dots"></span><span class="toc-page">28</span></a></li>
    <li><a href="#s4"><span class="toc-num">iv</span><span class="toc-text">第四章 留白的哲学</span><span class="toc-dots"></span><span class="toc-page">45</span></a></li>
    <li><a href="#s5"><span class="toc-num">v</span><span class="toc-text">第五章 时间的印记</span><span class="toc-dots"></span><span class="toc-page">67</span></a></li>
  </ol>
</nav>
```

```css
/* 目录容器 */
.toc {
  max-width: 640px;
  margin: var(--sp-10) auto;
  padding: var(--sp-8);
  background: var(--cream);
  border: 1px solid var(--cream-200);
}

/* 目录标题 */
.toc-title {
  font-family: var(--font-serif);
  font-size: 2rem;
  font-weight: 700;
  letter-spacing: 0.3em;
  text-transform: uppercase;
  text-align: center;
  color: var(--royal);
  margin: 0 0 var(--sp-6);
  position: relative;
  padding-bottom: var(--sp-4);
}

.toc-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 2px;
  background: var(--gold);
}

/* 目录列表 */
.toc-list {
  list-style: none;
  padding: 0;
  margin: 0;
  counter-reset: toc-counter;
}

.toc-list li {
  counter-increment: toc-counter;
  margin-bottom: var(--sp-3);
}

.toc-list a {
  display: flex;
  align-items: baseline;
  gap: var(--sp-2);
  text-decoration: none;
  color: var(--ink);
  font-family: var(--font-serif);
  font-size: 1rem;
  line-height: 1.6;
  transition: color var(--t-fast);
}

.toc-list a:hover {
  color: var(--royal);
}

/* 罗马数字编号 */
.toc-num {
  font-family: var(--font-display);
  font-style: italic;
  color: var(--gold-700);
  font-size: 0.9rem;
  min-width: 2rem;
  flex-shrink: 0;
}

/* 章节标题 */
.toc-text {
  flex-shrink: 0;
}

/* 点状引导线 */
.toc-dots {
  flex-grow: 1;
  border-bottom: 1px dotted var(--cream-200);
  margin: 0 var(--sp-2);
  min-width: 2rem;
  position: relative;
  top: -3px;
}

/* 页码 */
.toc-page {
  font-family: var(--font-serif);
  font-weight: 600;
  color: var(--royal);
  flex-shrink: 0;
  min-width: 2rem;
  text-align: right;
}
```

---

## 28. 金色手写签名 Signature

作者签名式组件，使用 Cormorant Garamond 斜体模拟手写感，配以微微倾斜的金色下划线。

```html
<div class="signature">飞鸿</div>

<div class="signature gold">Feihong</div>
```

```css
/* 签名 — 默认墨色 */
.signature {
  font-family: var(--font-display);
  font-style: italic;
  font-size: clamp(2rem, 4vw, 3.5rem);
  font-weight: 500;
  color: var(--ink);
  position: relative;
  display: inline-block;
  line-height: 1.2;
  padding-bottom: 0.3em;
}

/* 倾斜的金色下划线 */
.signature::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 5%;
  width: 90%;
  height: 2px;
  background: var(--gold);
  transform: rotate(-3deg);
  transform-origin: left center;
}

/* 金色签名变体 */
.signature.gold {
  color: var(--gold-600);
}
.signature.gold::after {
  background: var(--gold);
  height: 1.5px;
}
```

---

## 29. 章节扉页 Chapter Opening

新章节开篇的扉页排版，包含章节编号、大标题、引言段落，中央对齐，金色装饰贯穿其间。

```html
<section class="chapter-opening">
  <div class="chapter-num">Chapter I</div>
  <h2 class="chapter-title">笔墨的起源</h2>
  <div class="chapter-epigraph">
    <p>文字是思想的载体，笔墨是时间的痕迹。在数字时代，我们依然需要那份沉下心来书写与阅读的庄重感。</p>
    <cite>— 飞鸿手记</cite>
  </div>
  <div class="fleuron"><span>❦</span></div>
</section>
```

```css
/* 章节扉页容器 */
.chapter-opening {
  text-align: center;
  padding: var(--sp-12) var(--sp-6);
  max-width: 760px;
  margin: 0 auto;
}

/* 章节编号 */
.chapter-num {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 1rem;
  letter-spacing: 0.3em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: var(--sp-4);
}

/* 章节标题 */
.chapter-title {
  font-family: var(--font-serif);
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 700;
  line-height: 1.05;
  color: var(--ink);
  margin: 0 0 var(--sp-6);
}

/* 引言区域 */
.chapter-epigraph {
  position: relative;
  max-width: 600px;
  margin: 0 auto var(--sp-8);
  padding-top: var(--sp-5);
}

/* 引言大引号装饰 */
.chapter-epigraph::before {
  content: '\201C';
  font-family: var(--font-serif);
  font-size: 4rem;
  color: var(--gold);
  line-height: 0.8;
  display: block;
  margin-bottom: -0.3em;
}

.chapter-epigraph p {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 1.15rem;
  line-height: 1.8;
  color: var(--ink-200);
  margin: 0 0 var(--sp-3);
}

.chapter-epigraph cite {
  font-family: var(--font-sans);
  font-style: normal;
  font-size: 0.85rem;
  color: var(--ink-300);
  letter-spacing: 0.05em;
}
```

---

## 30. 装饰引文框 Decorative Quote Frame

三种风格的引文框：角缺金边（默认）、古典首字线（old-style）、杂志大字（magazine）。默认款使用四条不相连的金色边线围成角部有缺口的边框。

```html
<blockquote class="quote-frame">
  <p>设计的本质不是装饰，而是让事物的意义得以显现。</p>
  <cite>— 原研哉</cite>
</blockquote>

<blockquote class="quote-frame old-style">
  <p>书籍是人类进步的阶梯，每一页都承载着文明的重量与思想的光芒。</p>
  <cite>— 高尔基</cite>
</blockquote>

<blockquote class="quote-frame magazine">
  <p>Simplicity is the ultimate sophistication.</p>
  <cite>— Leonardo da Vinci</cite>
</blockquote>
```

```css
/* === 装饰引文框 · 默认：角缺金边 === */
.quote-frame {
  position: relative;
  padding: var(--sp-8) var(--sp-10);
  margin: var(--sp-8) auto;
  max-width: 680px;
  text-align: center;
}

/* 四条装饰线（上下左右各一条，角部留缺口） */
.quote-frame::before,
.quote-frame::after {
  content: '';
  position: absolute;
  background: var(--gold);
}
/* 上线 */
.quote-frame::before {
  top: 0;
  left: 15%;
  right: 15%;
  height: 1px;
}
/* 下线 */
.quote-frame::after {
  bottom: 0;
  left: 15%;
  right: 15%;
  height: 1px;
}

/* 左右线使用额外伪元素技巧 — 包装在内部元素实现 */
/* 使用背景渐变实现左右两条短线 */
.quote-frame {
  background-image:
    linear-gradient(var(--gold), var(--gold)),
    linear-gradient(var(--gold), var(--gold));
  background-size: 1px 40%, 1px 40%;
  background-position: left top 30%, right top 30%;
  background-repeat: no-repeat;
}

.quote-frame p {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 1.25rem;
  line-height: 1.7;
  color: var(--ink);
  margin: 0 0 var(--sp-4);
}

.quote-frame cite {
  font-family: var(--font-sans);
  font-style: normal;
  font-size: 0.85rem;
  color: var(--ink-300);
  letter-spacing: 0.08em;
}

/* === 古典变体：左侧金色粗线 + 首字放大 === */
.quote-frame.old-style {
  text-align: left;
  padding: var(--sp-5) var(--sp-6);
  border-left: 4px solid var(--gold);
  background-image: none;
}
.quote-frame.old-style::before,
.quote-frame.old-style::after {
  display: none;
}
.quote-frame.old-style p {
  font-family: var(--font-serif);
  font-style: italic;
  font-size: 1.1rem;
  line-height: 1.8;
  color: var(--ink);
}
.quote-frame.old-style p::first-letter {
  font-family: var(--font-serif);
  font-size: 2.8rem;
  font-weight: 700;
  float: left;
  line-height: 0.85;
  padding: 0.2rem 0.5rem 0 0;
  color: var(--gold-600);
}
.quote-frame.old-style cite {
  display: block;
  text-align: right;
  margin-top: var(--sp-3);
  color: var(--ink-200);
}

/* === 杂志变体：全宽大字 + 引号超出文本框 === */
.quote-frame.magazine {
  position: relative;
  max-width: none;
  padding: var(--sp-8) var(--sp-6);
  background-image: none;
  text-align: left;
}
.quote-frame.magazine::before,
.quote-frame.magazine::after {
  display: none;
}
.quote-frame.magazine p {
  font-family: var(--font-serif);
  font-style: italic;
  font-weight: 700;
  font-size: clamp(1.5rem, 3vw, 2.5rem);
  line-height: 1.3;
  color: var(--royal);
  position: relative;
  padding-left: 3.5rem;
}
.quote-frame.magazine p::before {
  content: '\201C';
  font-family: var(--font-serif);
  font-size: 6rem;
  color: var(--gold);
  position: absolute;
  left: -0.5rem;
  top: -1.5rem;
  line-height: 1;
}
.quote-frame.magazine cite {
  display: block;
  margin-top: var(--sp-4);
  padding-left: 3.5rem;
  color: var(--ink-300);
  font-family: var(--font-display);
  font-style: italic;
  font-size: 1rem;
}
```

---

## 31. 脚注 Footnote（学术风）

学术文章常用的脚注系统，正文用上标编号，底部有脚注列表，支持双向跳转链接。

```html
<p>设计不仅仅是视觉的呈现，更是一种思维方式<span class="footnote-ref" id="fn1"><a href="#fn1-def">1</a></span>。好的设计能让复杂的信息变得清晰易懂，让使用的过程变得自然流畅<span class="footnote-ref" id="fn2"><a href="#fn2-def">2</a></span>。</p>

<p>正如某位设计师所言："简约不是少，而是刚刚好。"<span class="footnote-ref" id="fn3"><a href="#fn3-def">3</a></span></p>

<hr style="border: none; border-top: 1px solid var(--gold); margin: var(--sp-10) 0 var(--sp-6);">

<ol class="footnotes">
  <li id="fn1-def">赫伯特·西蒙在《The Sciences of the Artificial》中提出设计思维的核心概念。<a href="#fn1">&#8617;</a></li>
  <li id="fn2-def">关于设计与认知负荷的关系，参见 Don Norman《设计心理学》。<a href="#fn2">&#8617;</a></li>
  <li id="fn3-def">这句话常被归于 Antoine de Saint-Exupery，但原始出处存有争议。<a href="#fn3">&#8617;</a></li>
</ol>
```

```css
/* 脚注上标引用 */
.footnote-ref {
  vertical-align: super;
  font-size: 0.7em;
  line-height: 0;
  font-weight: 600;
}

.footnote-ref a {
  color: var(--royal);
  text-decoration: none;
  padding: 0 1px;
  border-bottom: 1px solid var(--gold);
  transition: color var(--t-fast);
}

.footnote-ref a:hover {
  color: var(--wine);
}

/* 脚注列表区域 */
.footnotes {
  list-style: decimal;
  padding-left: var(--sp-6);
  margin: 0;
  border-top: 1px solid var(--gold);
  padding-top: var(--sp-4);
}

.footnotes li {
  font-size: 0.8rem;
  color: var(--ink-200);
  line-height: 1.7;
  margin-bottom: var(--sp-2);
  font-family: var(--font-sans);
}

.footnotes li a {
  color: var(--royal);
  text-decoration: none;
  margin-left: var(--sp-1);
}

.footnotes li a:hover {
  color: var(--wine);
}
```

---

## 32. 衬线编号徽章 Serif Number Badge

圆形编号徽章，使用衬线斜体数字，适用于步骤引导、排行榜、序号标注等场景。提供线框、实心、酒红三种风格。

```html
<div class="number-badge"><span>01</span></div>

<div class="number-badge solid"><span>02</span></div>

<div class="number-badge wine"><span>03</span></div>
```

```css
/* 编号徽章 — 默认金线皇家蓝字 */
.number-badge {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  border: 2px solid var(--gold);
  background: transparent;
  font-family: var(--font-display);
  font-style: italic;
  font-size: 1.2rem;
  font-weight: 600;
  color: var(--royal);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  line-height: 1;
}

/* 实心皇家蓝 */
.number-badge.solid {
  background: var(--royal);
  border-color: var(--royal);
  color: var(--gold);
}

/* 酒红实心 */
.number-badge.wine {
  background: var(--wine);
  border-color: var(--wine);
  color: #fff;
}
```

---

## 33. 钢笔画分隔线 Pen Stroke Divider

手绘质感的分隔线，模拟钢笔在纸上划过的痕迹，比直线更有人文温度。提供单线、双线中点、波浪线三种变体。

```html
<hr class="pen-divider">

<hr class="pen-divider double">

<hr class="pen-divider wave">
```

```css
/* 钢笔画分隔线 — 默认：手绘感金色单线 */
hr.pen-divider {
  border: none;
  margin: var(--sp-8) 0;
  position: relative;
  height: 6px;
  background: none;
  overflow: visible;
}

hr.pen-divider::before {
  content: '';
  position: absolute;
  top: 0;
  left: 5%;
  right: 5%;
  height: 2px;
  background: var(--gold);
  opacity: 0.7;
  transform: rotate(-0.3deg);
  border-radius: 1px;
}

hr.pen-divider::after {
  content: '';
  position: absolute;
  top: 3px;
  left: 10%;
  right: 15%;
  height: 1px;
  background: var(--gold);
  opacity: 0.4;
  transform: rotate(0.2deg);
}

/* 双线 + 中间小点变体 */
hr.pen-divider.double {
  height: 14px;
}

hr.pen-divider.double::before {
  top: 0;
  left: 10%;
  right: 10%;
  height: 1px;
  opacity: 0.6;
  transform: rotate(-0.2deg);
}

hr.pen-divider.double::after {
  content: '';
  top: 50%;
  left: 50%;
  width: 5px;
  height: 5px;
  background: var(--gold);
  border-radius: 50%;
  opacity: 0.7;
  transform: translate(-50%, -50%);
}

/* 上线用包装伪元素实现双线 */
hr.pen-divider.double {
  background-image: linear-gradient(var(--gold), var(--gold));
  background-size: 80% 1px;
  background-position: center bottom;
  background-repeat: no-repeat;
}

/* 波浪线变体（SVG data URI） */
hr.pen-divider.wave {
  height: 14px;
  background: none;
}

hr.pen-divider.wave::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  height: 12px;
  transform: translateY(-50%);
  background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 200 12'%3E%3Cpath d='M0 6 Q 12 0, 25 6 T 50 6 T 75 6 T 100 6 T 125 6 T 150 6 T 175 6 T 200 6' stroke='%23F4D35E' stroke-width='1.5' fill='none' stroke-linecap='round' opacity='0.7'/%3E%3C/svg%3E") repeat-x center;
  background-size: 200px 12px;
  opacity: 1;
}

hr.pen-divider.wave::after {
  display: none;
}
```

---

## 34. 卡片组件扩展变体（3种新变体）

在原有 5 种卡片基础上，新增杂志编辑风、编号主导风、引用风三种变体。

### 34.1 杂志编辑风 .feature-card.editorial

大号编号作为底层装饰，图片溢出卡片边界，衬线大标题配金色边线。

```html
<article class="feature-card editorial">
  <span class="card-number">01</span>
  <div class="card-image-wrap">
    <img src="https://images.unsplash.com/photo-1544947950-fa07a98d237f?w=500&h=300&fit=crop" alt="书籍">
  </div>
  <div class="card-body">
    <span class="card-tag">随笔</span>
    <h3>关于阅读这件事</h3>
    <p>翻开一本旧书，就像推开一扇通往另一个时代的门。纸张的气味、排版的节奏、批注的痕迹……</p>
    <a href="#" class="card-link">阅读全文</a>
  </div>
</article>
```

```css
.feature-card.editorial {
  position: relative;
  background: #fff;
  padding: var(--sp-8);
  box-shadow: var(--shadow-lg);
  border-top: 3px solid var(--gold);
  overflow: visible;
  max-width: 480px;
}

.feature-card.editorial .card-number {
  position: absolute;
  top: var(--sp-4);
  right: var(--sp-5);
  font-family: var(--font-serif);
  font-size: 6rem;
  font-weight: 700;
  color: var(--cream-100);
  line-height: 1;
  z-index: 0;
  user-select: none;
}

.feature-card.editorial .card-image-wrap {
  margin: calc(-1 * var(--sp-8)) calc(-1 * var(--sp-8)) var(--sp-5);
  height: 220px;
  overflow: hidden;
}

.feature-card.editorial .card-image-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform var(--t-slow);
}

.feature-card.editorial:hover .card-image-wrap img {
  transform: scale(1.05);
}

.feature-card.editorial .card-body {
  position: relative;
  z-index: 1;
}

.feature-card.editorial .card-tag {
  display: inline-block;
  font-family: var(--font-sans);
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--gold-700);
  margin-bottom: var(--sp-2);
}

.feature-card.editorial h3 {
  font-family: var(--font-serif);
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--royal);
  margin: 0 0 var(--sp-3);
  line-height: 1.2;
}

.feature-card.editorial p {
  font-family: var(--font-sans);
  font-size: 0.95rem;
  line-height: 1.7;
  color: var(--ink-200);
  margin: 0 0 var(--sp-4);
}

.feature-card.editorial .card-link {
  font-family: var(--font-serif);
  font-style: italic;
  color: var(--royal);
  text-decoration: none;
  border-bottom: 1px solid var(--gold);
  padding-bottom: 2px;
  transition: color var(--t-fast);
}

.feature-card.editorial .card-link:hover {
  color: var(--wine);
}
```

### 34.2 编号主导 .feature-card.numbered

左侧巨大半透明衬线数字，右侧为文字内容，数字形成强烈视觉锚点。

```html
<article class="feature-card numbered">
  <span class="card-big-num">01</span>
  <div class="card-content">
    <h3>品牌理念</h3>
    <p>以东方美学为根基，融合古典印刷的庄重与当代设计的克制，每一个细节都经得起时间的审视。</p>
  </div>
</article>

<article class="feature-card numbered">
  <span class="card-big-num">02</span>
  <div class="card-content">
    <h3>工艺精神</h3>
    <p>字体间距的微调、色彩饱和度的反复校准、阴影层次的耐心堆叠，追求的是像素级的完美。</p>
  </div>
</article>
```

```css
.feature-card.numbered {
  display: flex;
  align-items: flex-start;
  gap: var(--sp-6);
  padding: var(--sp-6) 0;
  border-bottom: 1px solid var(--cream-200);
  max-width: 600px;
}

.feature-card.numbered .card-big-num {
  font-family: var(--font-serif);
  font-size: 3.5rem;
  font-weight: 700;
  color: var(--cream-200);
  line-height: 1;
  flex-shrink: 0;
  min-width: 4.5rem;
  transition: color var(--t-base);
}

.feature-card.numbered:hover .card-big-num {
  color: var(--gold);
}

.feature-card.numbered .card-content h3 {
  font-family: var(--font-serif);
  font-size: 1.35rem;
  font-weight: 700;
  color: var(--royal);
  margin: 0 0 var(--sp-2);
}

.feature-card.numbered .card-content p {
  font-family: var(--font-sans);
  font-size: 0.95rem;
  line-height: 1.7;
  color: var(--ink-200);
  margin: 0;
}
```

### 34.3 引用风 .feature-card.quote-style

上方大金色引号，中间衬线斜体文字，底部手写签名式落款。

```html
<article class="feature-card quote-style">
  <span class="card-quote-mark">&ldquo;</span>
  <blockquote>
    设计是一种从容的表达，它不喧哗，不张扬，却在每一个细节处诉说着对品质的坚持与对使用者的尊重。
  </blockquote>
  <div class="card-signature">飞鸿</div>
</article>
```

```css
.feature-card.quote-style {
  position: relative;
  background: var(--cream);
  padding: var(--sp-8) var(--sp-8) var(--sp-6);
  max-width: 520px;
  text-align: center;
  border: 1px solid var(--cream-200);
}

.feature-card.quote-style .card-quote-mark {
  font-family: var(--font-serif);
  font-size: 5rem;
  line-height: 0.6;
  color: var(--gold);
  display: block;
  margin-bottom: var(--sp-2);
}

.feature-card.quote-style blockquote {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 1.2rem;
  line-height: 1.8;
  color: var(--ink);
  margin: 0 0 var(--sp-5);
  padding: 0;
}

.feature-card.quote-style .card-signature {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 1.5rem;
  color: var(--ink-200);
  position: relative;
  display: inline-block;
}

.feature-card.quote-style .card-signature::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 10%;
  width: 80%;
  height: 1px;
  background: var(--gold);
  transform: rotate(-2deg);
}
```

---

## 35. 引用块扩展变体（2种新变体）

在原有 pull-quote 基础上新增居中大字款与侧边栏款。

### 35.1 居中大字 .pull-quote.centered

全宽居中，衬线斜体大字，金色引号装饰于两侧。

```html
<blockquote class="pull-quote centered">
  <p>真正的优雅，是在繁华落尽之后依然留存的那份从容。</p>
</blockquote>
```

```css
.pull-quote.centered {
  max-width: 700px;
  margin: var(--sp-10) auto;
  padding: var(--sp-6) var(--sp-8);
  text-align: center;
  position: relative;
}

.pull-quote.centered::before,
.pull-quote.centered::after {
  content: '\201C';
  font-family: var(--font-serif);
  font-size: 4rem;
  color: var(--gold);
  line-height: 1;
  position: absolute;
  top: 0.5rem;
  opacity: 0.5;
}

.pull-quote.centered::before {
  left: 0;
}

.pull-quote.centered::after {
  content: '\201D';
  right: 0;
  left: auto;
}

.pull-quote.centered p {
  font-family: var(--font-serif);
  font-style: italic;
  font-size: clamp(1.5rem, 3vw, 2.5rem);
  font-weight: 500;
  line-height: 1.4;
  color: var(--royal);
  margin: 0;
}
```

### 35.2 侧边栏款 .pull-quote.sidebar

左侧金色粗竖线，衬线斜体，适合嵌入正文流中作为强调段落。

```html
<blockquote class="pull-quote sidebar">
  <p>阅读不是逃避，而是更深地走进这个世界。每一本书都是一次旅行，每一页都是新的风景。</p>
</blockquote>
```

```css
.pull-quote.sidebar {
  border-left: 4px solid var(--gold);
  padding-left: var(--sp-6);
  margin: var(--sp-6) 0;
  max-width: 560px;
}

.pull-quote.sidebar p {
  font-family: var(--font-serif);
  font-style: italic;
  font-size: 1.1rem;
  line-height: 1.8;
  color: var(--ink);
  margin: 0;
}
```

---

## 36. 章节标题扩展变体（2种新变体）

### 36.1 花饰装饰 .section-header.with-fleuron

标题下方加 fleuron 花饰作为装饰性分隔。

```html
<header class="section-header with-fleuron">
  <h2>设计哲学</h2>
  <p>探索设计背后的思考与原则</p>
</header>
```

```css
.section-header.with-fleuron {
  text-align: center;
  margin: var(--sp-10) 0 var(--sp-8);
}

.section-header.with-fleuron h2 {
  font-family: var(--font-serif);
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 700;
  color: var(--royal);
  margin: 0 0 var(--sp-3);
  line-height: 1.15;
}

.section-header.with-fleuron p {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 1.1rem;
  color: var(--ink-200);
  margin: 0 0 var(--sp-4);
}

.section-header.with-fleuron::after {
  content: '❦';
  display: block;
  color: var(--gold);
  font-size: 1.2rem;
  line-height: 1;
  margin-top: var(--sp-4);
}
```

### 36.2 罗马数字编号 .section-header.numbered

左侧大罗马数字编号 + 右侧标题 + 金色底线，适合长文分章。

```html
<header class="section-header numbered">
  <span class="sec-num">I</span>
  <div class="sec-text">
    <h2>初见</h2>
    <p>一切美好始于一次不经意的相遇</p>
  </div>
</header>
```

```css
.section-header.numbered {
  display: flex;
  align-items: flex-start;
  gap: var(--sp-5);
  padding-bottom: var(--sp-5);
  border-bottom: 1px solid var(--gold);
  margin: var(--sp-10) 0 var(--sp-6);
  max-width: 720px;
}

.section-header.numbered .sec-num {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 3.5rem;
  font-weight: 600;
  color: var(--gold);
  line-height: 0.9;
  flex-shrink: 0;
  min-width: 3.5rem;
}

.section-header.numbered .sec-text h2 {
  font-family: var(--font-serif);
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--royal);
  margin: 0 0 var(--sp-1);
  line-height: 1.2;
}

.section-header.numbered .sec-text p {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 0.95rem;
  color: var(--ink-200);
  margin: 0;
}
```

---

## 37. 交互组件：Modal 模态框

点击按钮弹出居中模态框，带半透明遮罩、右上角关闭按钮（hover 旋转 90 度），入场有 scale + opacity 动画。

```html
<button class="btn btn-primary" onclick="document.getElementById('modal1').classList.add('open')">打开模态框</button>

<div class="modal" id="modal1">
  <div class="modal-backdrop" onclick="this.parentElement.classList.remove('open')"></div>
  <div class="modal-content">
    <button class="modal-close" onclick="this.closest('.modal').classList.remove('open')">&times;</button>
    <h3>关于飞鸿</h3>
    <p>飞鸿设计系统致力于将古典印刷美学带入数字界面。我们相信好的设计应当经得起时间的审视，如同一本好书，常读常新。</p>
    <p>每一个组件都经过精心打磨，从字体的选择、色彩的搭配到间距的呼吸，都追求那份恰到好处的从容。</p>
  </div>
</div>
```

```css
/* 模态框遮罩 */
.modal {
  display: none;
  position: fixed;
  inset: 0;
  z-index: 1000;
  align-items: center;
  justify-content: center;
  padding: var(--sp-4);
}

.modal.open {
  display: flex;
}

.modal-backdrop {
  position: absolute;
  inset: 0;
  background: rgba(13, 18, 37, 0.6);
  animation: modalFadeIn 0.3s var(--ease);
}

.modal-content {
  position: relative;
  background: #fff;
  border-radius: var(--r-lg);
  padding: 2.5rem;
  max-width: 560px;
  width: 100%;
  max-height: 85vh;
  overflow-y: auto;
  box-shadow: 0 25px 60px rgba(10, 36, 99, 0.3);
  animation: modalScaleIn 0.4s var(--ease);
  z-index: 1;
}

.modal-content h3 {
  font-family: var(--font-serif);
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--royal);
  margin: 0 0 var(--sp-4);
  padding-right: var(--sp-8);
}

.modal-content p {
  font-family: var(--font-sans);
  font-size: 1rem;
  line-height: 1.8;
  color: var(--ink-200);
  margin: 0 0 var(--sp-4);
}

/* 关闭按钮 */
.modal-close {
  position: absolute;
  top: var(--sp-4);
  right: var(--sp-4);
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: none;
  background: var(--cream);
  color: var(--ink);
  font-family: var(--font-serif);
  font-size: 1.5rem;
  line-height: 1;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform var(--t-base), background var(--t-fast);
}

.modal-close:hover {
  transform: rotate(90deg);
  background: var(--wine);
  color: #fff;
}

/* 入场动画 */
@keyframes modalFadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes modalScaleIn {
  from {
    opacity: 0;
    transform: scale(0.95) translateY(10px);
  }
  to {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
}
```

---

## 38. 交互组件：Accordion 手风琴

使用原生 `<details>/<summary>` 实现的手风琴组件，summary 右侧 +/− 号切换，衬线字体标题，适合 FAQ 场景。

```html
<div class="accordion">
  <details class="accordion-item" open>
    <summary>飞鸿设计系统的核心理念是什么？</summary>
    <div class="accordion-body">
      核心理念是"书卷气"——将古典印刷美学与当代界面设计相结合，追求沉稳、典雅、经得住时间审视的视觉语言。我们相信好的设计不是追随时尚，而是建立自己的节奏与气质。
    </div>
  </details>
  <details class="accordion-item">
    <summary>如何在项目中引入设计系统？</summary>
    <div class="accordion-body">
      直接复制所需组件的 HTML + CSS 代码即可使用。所有组件均不依赖 JavaScript 框架，仅使用原生 CSS 变量，你可以在任何技术栈中引入。建议先引入 Brand Tokens，再按需引入组件。
    </div>
  </details>
  <details class="accordion-item">
    <summary>字体和色彩可以自定义吗？</summary>
    <div class="accordion-body">
      可以。所有设计决策都通过 CSS 变量暴露，你只需要修改 :root 中对应的变量值，即可全局调整色彩、字体、间距等系统属性。我们建议在保持品牌气质的前提下进行微调。
    </div>
  </details>
</div>
```

```css
/* 手风琴容器 */
.accordion {
  max-width: 680px;
  margin: var(--sp-6) 0;
}

/* 单个手风琴项 */
.accordion-item {
  border-bottom: 1px solid var(--cream-200);
}

/* summary 标题 */
.accordion-item summary {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.25rem 0;
  font-family: var(--font-serif);
  font-weight: 600;
  font-size: 1.05rem;
  color: var(--ink);
  cursor: pointer;
  list-style: none;
  transition: color var(--t-fast);
  user-select: none;
}

/* 移除 WebKit 默认 marker */
.accordion-item summary::-webkit-details-marker {
  display: none;
}

.accordion-item summary::after {
  content: '+';
  font-family: var(--font-serif);
  font-size: 1.5rem;
  font-weight: 300;
  color: var(--gold);
  line-height: 1;
  transition: transform var(--t-base);
  flex-shrink: 0;
  margin-left: var(--sp-4);
}

.accordion-item[open] summary::after {
  content: '\2212'; /* − 减号 */
  transform: rotate(180deg);
}

.accordion-item summary:hover {
  color: var(--royal);
}

/* 展开内容区 */
.accordion-body {
  padding: 0 0 1.25rem;
  color: var(--ink-200);
  line-height: 1.7;
  font-family: var(--font-sans);
  font-size: 0.95rem;
}
```

---

## 39. 交互组件：Tabs 标签切换

衬线字体的标签切换组件，底部金色指示线，支持多标签内容切换。附 JS 事件委托脚本。

```html
<div class="tabs">
  <div class="tabs-nav">
    <button class="tab-btn active" data-tab="t1">品牌理念</button>
    <button class="tab-btn" data-tab="t2">设计原则</button>
    <button class="tab-btn" data-tab="t3">使用指南</button>
  </div>
  <div class="tab-panel active" id="t1">
    <p>飞鸿设计系统以"书卷气"为核心，将古典印刷美学融入数字界面。我们追求的不是视觉的冲击，而是阅读的从容。每一个字号的选择、每一处间距的确定，都有其内在的节奏与理由。</p>
  </div>
  <div class="tab-panel" id="t2">
    <p>克制、典雅、留白、呼吸。我们相信少即是多，但"少"不是贫瘠，而是恰到好处。色彩使用克制而有力——皇家蓝奠定基调，金色点缀精神，酒红注入温度。</p>
  </div>
  <div class="tab-panel" id="t3">
    <p>从 Brand Tokens 开始引入，再按需取用组件。所有组件无框架依赖，原生 HTML + CSS 即可运行。交互组件附有简洁的 JS 脚本，可直接复制使用。</p>
  </div>
</div>
```

```css
/* Tabs 导航 */
.tabs {
  max-width: 680px;
  margin: var(--sp-6) 0;
}

.tabs-nav {
  display: flex;
  border-bottom: 2px solid var(--cream-200);
  gap: 0;
}

.tab-btn {
  background: none;
  border: none;
  padding: 0.75rem 1.25rem;
  font-family: var(--font-serif);
  font-weight: 600;
  font-size: 1rem;
  color: var(--ink-300);
  cursor: pointer;
  border-bottom: 2px solid transparent;
  margin-bottom: -2px;
  transition: color var(--t-fast), border-color var(--t-fast);
}

.tab-btn:hover {
  color: var(--ink);
}

.tab-btn.active {
  color: var(--royal);
  border-bottom-color: var(--gold);
}

/* Tab 面板 */
.tab-panel {
  display: none;
  padding: 1.5rem 0;
}

.tab-panel.active {
  display: block;
  animation: tabFadeIn 0.4s var(--ease);
}

.tab-panel p {
  font-family: var(--font-sans);
  font-size: 1rem;
  line-height: 1.8;
  color: var(--ink-200);
  margin: 0;
}

@keyframes tabFadeIn {
  from { opacity: 0; transform: translateY(4px); }
  to { opacity: 1; transform: translateY(0); }
}
```

```html
<script>
// Tabs 切换 — 事件委托
document.addEventListener('click', function (e) {
  var btn = e.target.closest('.tab-btn');
  if (!btn) return;
  var tabs = btn.closest('.tabs');
  if (!tabs) return;
  var target = btn.dataset.tab;
  tabs.querySelectorAll('.tab-btn').forEach(function (b) { b.classList.remove('active'); });
  tabs.querySelectorAll('.tab-panel').forEach(function (p) { p.classList.remove('active'); });
  btn.classList.add('active');
  var panel = tabs.querySelector('#' + target);
  if (panel) panel.classList.add('active');
});
</script>
```

---

## 40. 交互组件：数字递增动画 Count-Up

进入视口时数字从 0 递增到目标值，衬线大字呈现，适合数据展示场景。支持前后缀自定义。

```html
<div style="display: flex; gap: var(--sp-10); flex-wrap: wrap; justify-content: center; padding: var(--sp-8);">
  <div style="text-align: center;">
    <span class="count-up" data-target="1200" data-suffix="+">0</span>
    <p style="font-family: var(--font-sans); font-size: 0.9rem; color: var(--ink-300); margin: var(--sp-2) 0 0;">设计案例</p>
  </div>
  <div style="text-align: center;">
    <span class="count-up" data-target="15" data-suffix="年">0</span>
    <p style="font-family: var(--font-sans); font-size: 0.9rem; color: var(--ink-300); margin: var(--sp-2) 0 0;">品牌沉淀</p>
  </div>
  <div style="text-align: center;">
    <span class="count-up" data-target="98" data-suffix="%">0</span>
    <p style="font-family: var(--font-sans); font-size: 0.9rem; color: var(--ink-300); margin: var(--sp-2) 0 0;">客户满意度</p>
  </div>
</div>
```

```css
.count-up {
  font-family: var(--font-serif);
  font-weight: 700;
  font-size: clamp(2rem, 4vw, 3.5rem);
  color: var(--royal);
  line-height: 1;
  display: inline-block;
}
```

```html
<script>
// Count-Up 数字递增动画
(function () {
  function animateCount(el) {
    var target = parseInt(el.dataset.target, 10) || 0;
    var suffix = el.dataset.suffix || '';
    var prefix = el.dataset.prefix || '';
    var duration = parseInt(el.dataset.duration, 10) || 2000;
    var start = 0;
    var startTime = null;
    function step(timestamp) {
      if (!startTime) startTime = timestamp;
      var progress = Math.min((timestamp - startTime) / duration, 1);
      var eased = 1 - Math.pow(1 - progress, 3); // easeOutCubic
      var current = Math.floor(eased * (target - start) + start);
      el.textContent = prefix + current.toLocaleString() + suffix;
      if (progress < 1) requestAnimationFrame(step);
      else el.textContent = prefix + target.toLocaleString() + suffix;
    }
    requestAnimationFrame(step);
  }

  var observer = new IntersectionObserver(function (entries) {
    entries.forEach(function (entry) {
      if (entry.isIntersecting) {
        animateCount(entry.target);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.3 });

  document.querySelectorAll('.count-up').forEach(function (el) { observer.observe(el); });
})();
</script>
```

---

## 41. 交互组件：衬线打字机效果 Typewriter

进入视口后逐字显示文字，配有金色闪烁光标，使用 Cormorant Garamond 斜体，营造手稿书写感。

```html
<span class="typewriter" data-text="设计不是装饰，是表达。" data-speed="60"></span>
```

```css
.typewriter {
  font-family: var(--font-display);
  font-style: italic;
  font-size: clamp(1.5rem, 3vw, 2.5rem);
  color: var(--ink);
  line-height: 1.4;
  display: inline;
  position: relative;
}

/* 闪烁光标 */
.typewriter::after {
  content: '';
  display: inline-block;
  width: 2px;
  height: 1em;
  background: var(--gold);
  margin-left: 2px;
  vertical-align: text-bottom;
  animation: cursorBlink 0.8s step-end infinite;
}

.typewriter.typing-done::after {
  display: none;
}

@keyframes cursorBlink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}
```

```html
<script>
// Typewriter 打字机效果
(function () {
  function typeWriter(el) {
    var text = el.dataset.text || '';
    var speed = parseInt(el.dataset.speed, 10) || 60;
    var i = 0;
    el.textContent = '';
    function type() {
      if (i < text.length) {
        el.textContent += text.charAt(i);
        i++;
        setTimeout(type, speed);
      } else {
        el.classList.add('typing-done');
      }
    }
    type();
  }

  var observer = new IntersectionObserver(function (entries) {
    entries.forEach(function (entry) {
      if (entry.isIntersecting) {
        typeWriter(entry.target);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.5 });

  document.querySelectorAll('.typewriter').forEach(function (el) { observer.observe(el); });
})();
</script>
```

---

## 42. 交互组件：滚动高亮导航 Scroll-Spy

侧边或顶部导航，自动监听页面内各 section 的滚动位置，当前章节对应的导航项自动高亮（金边+粗体）。

```html
<nav class="scrollspy-nav">
  <a href="#section1" class="spy-link active">初见</a>
  <a href="#section2" class="spy-link">笔墨</a>
  <a href="#section3" class="spy-link">留白</a>
  <a href="#section4" class="spy-link">印记</a>
</nav>

<!-- 对应的页面区块 -->
<section id="section1" style="padding: var(--sp-8); min-height: 60vh;"><h2 style="font-family:var(--font-serif); color:var(--royal);">初见</h2></section>
<section id="section2" style="padding: var(--sp-8); min-height: 60vh;"><h2 style="font-family:var(--font-serif); color:var(--royal);">笔墨</h2></section>
<section id="section3" style="padding: var(--sp-8); min-height: 60vh;"><h2 style="font-family:var(--font-serif); color:var(--royal);">留白</h2></section>
<section id="section4" style="padding: var(--sp-8); min-height: 60vh;"><h2 style="font-family:var(--font-serif); color:var(--royal);">印记</h2></section>
```

```css
/* 滚动监听导航 */
.scrollspy-nav {
  position: sticky;
  top: var(--sp-4);
  display: flex;
  flex-direction: column;
  gap: 0;
  padding: var(--sp-3) 0;
}

.spy-link {
  display: block;
  padding: 0.5rem 0 0.5rem 1rem;
  font-size: 0.85rem;
  font-family: var(--font-sans);
  color: var(--ink-300);
  text-decoration: none;
  border-left: 2px solid transparent;
  transition: color var(--t-fast), border-color var(--t-fast), font-weight var(--t-fast);
  line-height: 1.4;
}

.spy-link:hover {
  color: var(--ink);
}

.spy-link.active {
  color: var(--royal);
  border-left-color: var(--gold);
  font-weight: 600;
}
```

```html
<script>
// Scroll-Spy 滚动高亮
(function () {
  var links = document.querySelectorAll('.spy-link');
  if (links.length === 0) return;
  var sectionIds = Array.from(links).map(function (l) { return l.getAttribute('href').substring(1); });
  var sections = sectionIds.map(function (id) { return document.getElementById(id); }).filter(Boolean);

  var observer = new IntersectionObserver(function (entries) {
    entries.forEach(function (entry) {
      if (entry.isIntersecting) {
        var id = entry.target.id;
        links.forEach(function (l) {
          l.classList.toggle('active', l.getAttribute('href') === '#' + id);
        });
      }
    });
  }, { rootMargin: '-20% 0px -60% 0px', threshold: 0 });

  sections.forEach(function (s) { observer.observe(s); });
})();
</script>
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

*Component Library v2.0 · Feihong Design System · 43个组件分类含变体共80+种样式*
