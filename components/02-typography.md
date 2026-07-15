# Feihong Design System — Typography
# N°02 · 文字排版
> Type scale, headings, body text, captions, and editorial title variants.
> 字体层级、标题、正文、说明文字，以及编辑风格标题变体。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
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

### 1.7 行内金色下划线强调（Inline Gold Underline Emphasis）

Hero标题中 `<em>` 标签的样式，使用 `::after` 伪元素在文字下方垫一条金色下划线，`z-index:-1` 使下划线不遮挡文字，形成经典编辑风格强调效果。

```html
<h1 class="hero-title">
  不像AI的<br>
  <em>个人品牌</em><br>
  设计系统
</h1>
```
```css
.hero-title em {
  font-style: italic;
  color: var(--royal);
  position: relative;
  display: inline-block;
}
.hero-title em::after {
  content: '';
  position: absolute;
  bottom: 0.08em;
  left: 0;
  width: 100%;
  height: 0.12em;
  background: var(--gold);
  z-index: -1;
  border-radius: 2px;
}
```

### 1.8 酒红斜体点缀（Wine Accent Italic）

`.wine-accent` 类，酒红色斜体文字，用于标题中需要暖色点缀的关键词，与金色下划线强调形成冷暖对比。

```html
<h1 class="hero-title">
  不像AI的<br>
  <em>个人品牌</em><br>
  <span class="wine-accent">设计系统</span>
</h1>
```
```css
.hero-title .wine-accent {
  color: var(--wine);
  font-style: italic;
}
```

### 1.9 双侧金色短线装饰语（Flanked Gold Line Tagline）

Hero副标题标语样式，使用 `::before` / `::after` 伪元素在文字两侧生成金色短线装饰，`display:flex` + `gap` 控制间距，典雅精致。

```html
<p class="hero-tagline">Crafted with devotion, designed for distinction</p>
```
```css
.hero-tagline {
  font-family: var(--font-display);
  font-size: clamp(0.95rem, 1.4vw, 1.1rem);
  font-style: italic;
  color: var(--gold-700);
  letter-spacing: 0.04em;
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  gap: 0.75rem;
}
.hero-tagline::before,
.hero-tagline::after {
  content: '';
  width: 32px;
  height: 1px;
  background: var(--gold);
}
```

---

### 36.3 菱形前缀Eyebrow标签（Diamond Eyebrow Label）

Hero区域的眉标样式，`::before` 伪元素插入 ◆ 菱形符号作为前缀，搭配大写字母间距（`0.22em`），形成品牌识别度极高的开篇标签。

```html
<div class="hero-eyebrow">Feihong Design System</div>
```
```css
.hero-eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 0.6rem;
  font-size: 0.72rem;
  font-weight: 600;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  color: var(--gold-700);
  margin-bottom: 1.5rem;
}
.hero-eyebrow::before {
  content: '◆';
  color: var(--gold);
  font-size: 0.6rem;
  width: auto;
  height: auto;
  background: none;
}
```
