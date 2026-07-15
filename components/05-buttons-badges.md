# Feihong Design System — Buttons & Badges
# N°05 · 按钮与徽章
> CTA buttons, outline buttons, gold badges, tags, dot indicators, and numbered badges.
> 行动按钮、描边按钮、金色徽章、标签、圆点指示器和编号徽章。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
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

### 3.8 幽灵描边按钮（Ghost Outline Button for Light）

浅色背景上的幽灵描边按钮，透明底色 + 1.5px 浅灰描边，hover 时描边和文字变为皇家蓝，低调克制不抢主按钮视觉权重。

```html
<a href="#philosophy" class="btn btn-ghost">了解设计哲学</a>
```
```css
.btn-ghost {
  background: transparent;
  color: var(--ink);
  border: 1.5px solid var(--cream-200);
}
.btn-ghost:hover {
  border-color: var(--royal);
  color: var(--royal);
}
```

---

### 3.10 深色底白色描边按钮（Light Outline Button for Dark）

深色背景上使用的白色半透明描边按钮，透明底色 + 1.5px 白色半透明描边，hover 时描边和文字变为金色，与深色CTA区域搭配使用。

```html
<a href="#templates" class="btn btn-ghost-light">浏览模板 →</a>
```
```css
.btn-ghost-light {
  background: transparent;
  color: #fff;
  border: 1.5px solid rgba(255,255,255,0.25);
}
.btn-ghost-light:hover {
  border-color: var(--gold);
  color: var(--gold);
}
```

---

### 4.3 胶囊式眉标（Pill Eyebrow Badge）

CTA区域的胶囊形眉标，`border-radius:999px` 全圆角，半透明金色底 + 金色大写字母间距文字，用于深色CTA区块顶部的引导标签。

```html
<div class="cta-eyebrow">Get Started</div>
```
```css
.cta-eyebrow {
  display: inline-block;
  font-size: 0.72rem;
  font-weight: 600;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--gold);
  background: rgba(244,211,94,0.1);
  padding: 0.3rem 0.8rem;
  border-radius: 999px;
  margin-bottom: 1.5rem;
}
```

### 4.4 迷你彩色标签组（Mini Color Badge Set）

超迷你圆角胶囊标签，字号 0.6rem，提供 5 种配色变体：royal（皇家蓝浅底深字）、gold（金色实心）、wine（酒红实心白字）、blue（皇家蓝实心金字）、green（终端绿实心），适合卡片角标/模板分类标注。

```html
<span class="mini-badge royal">长文阅读</span>
<span class="mini-badge gold">Landing</span>
<span class="mini-badge wine">深色风格</span>
<span class="mini-badge blue">个人主页</span>
<span class="mini-badge green">终端绿</span>
```
```css
.mini-badge {
  font-size: 0.6rem;
  font-weight: 600;
  padding: 0.12rem 0.45rem;
  border-radius: 999px;
  letter-spacing: 0.02em;
}
.mini-badge.royal { background: var(--royal-50); color: var(--royal); }
.mini-badge.gold { background: var(--gold); color: var(--royal); }
.mini-badge.wine { background: var(--wine); color: #fff; }
.mini-badge.blue { background: var(--royal); color: var(--gold); }
.mini-badge.green { background: var(--terminal); color: var(--ink); font-weight: 700; }
```

### 4.5 半透明描边标签（Translucent Bordered Tag Pill）

半透明底 + 描边三色系标签组，提供金色半透明（Scene/场景）、米白皇家蓝（Template/模板）、白色深灰（Component/组件）三种风格，圆角胶囊形，适合架构说明/层级分类标签。

```html
<div class="arch-tag-group">
  <span class="arch-tag arch-tag-gold">Portfolio</span>
  <span class="arch-tag arch-tag-royal">字体引入</span>
  <span class="arch-tag arch-tag-ink">按钮</span>
</div>
```
```css
.arch-tag-group {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.arch-tag {
  font-size: 0.75rem;
  padding: 4px 12px;
  border-radius: 100px;
  font-weight: 500;
}
/* 金色半透明 — 场景标签 */
.arch-tag-gold {
  background: rgba(244,211,94,0.15);
  color: var(--gold);
  border: 1px solid rgba(244,211,94,0.25);
}
/* 米白皇家蓝 — 模板标签 */
.arch-tag-royal {
  background: var(--cream);
  color: var(--royal);
  border: 1px solid var(--cream-200);
}
/* 白色深灰 — 组件标签 */
.arch-tag-ink {
  background: #fff;
  color: var(--ink-500);
  border: 1px solid var(--cream-200);
}
```

### 4.6 模式标识Pill（Mode Badge）

三色实心胶囊标识，酒红（Full/精准模式）、皇家蓝（Smart/智能模式）、金色（Demo/演示模式），加粗小字 + 宽字距，用于功能卡片顶部标注模式类型。

```html
<div class="mode-badge mode-full">精准模式</div>
<div class="mode-badge mode-smart">智能模式</div>
<div class="mode-badge mode-demo">演示模式</div>
```
```css
.mode-badge {
  display: inline-block;
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  padding: 4px 14px;
  border-radius: 100px;
  margin-bottom: 16px;
}
/* 酒红实心 — 精准模式 */
.mode-full {
  background: var(--wine);
  color: #fff;
}
/* 皇家蓝实心 — 智能模式 */
.mode-smart {
  background: var(--royal);
  color: var(--gold);
}
/* 金色实心 — 演示模式 */
.mode-demo {
  background: var(--gold);
  color: var(--royal);
}
```
