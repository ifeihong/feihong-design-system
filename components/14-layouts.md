# Feihong Design System — Layout Patterns
# N°14 · 布局模式
> Hero patterns, asymmetric grids, magazine spreads, masonry, split screens, zigzag narratives, and 16 editorial layout recipes.
> 首屏布局、非对称网格、杂志双页、瀑布流、分屏、Z字叙事和16种编辑级布局方案。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
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
    <div class="avatar avatar-xl"><img src="assets/avatar.png" alt="飞鸿"></div>
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

## 51. Layouts 布局类

### 51.1 Asymmetric Grid 非对称网格

非对称网格布局，主内容区占2/3宽度配侧边1/3栏，区块间有金色分隔线，模块有不同高度比例，编辑设计/杂志页面风格。

```html
<div class="asym-grid">
  <div class="ag-hero"><span class="ag-tag">Feature</span><h2>主视觉区域</h2><p>大幅视觉展示，配衬线标题与简介文字。</p></div>
  <div class="ag-side"><span class="ag-tag-sm">Note</span><p>侧边小栏，放置补充信息、引述或数据。</p></div>
  <div class="ag-sub"><span class="ag-tag-sm">Story</span><h3>次级内容块</h3></div>
  <div class="ag-wide"><span class="ag-tag-sm">Gallery</span><p>全宽横条，用于图片画廊或引用条。</p></div>
</div>
```
```css
.asym-grid { display:grid; grid-template-columns:2fr 1fr; grid-template-rows:auto auto auto; gap:1.5rem; font-family:var(--font-sans); max-width:1000px; }
.ag-hero { grid-column:1/2; grid-row:1/3; background:var(--cream); border-radius:var(--r-lg); padding:3rem 2.5rem; border:1px solid var(--cream-200); position:relative; min-height:300px; display:flex; flex-direction:column; justify-content:flex-end; }
.ag-side { grid-column:2/3; grid-row:1/2; background:var(--royal); border-radius:var(--r-lg); padding:2rem 1.5rem; color:var(--cream); }
.ag-sub { grid-column:2/3; grid-row:2/3; background:var(--gold-50); border-radius:var(--r-lg); padding:1.5rem; border:1px solid var(--gold-200); }
.ag-wide { grid-column:1/3; grid-row:3/4; background:var(--wine); border-radius:var(--r-lg); padding:2rem; color:var(--cream); text-align:center; }
.ag-tag { font-family:var(--font-mono); font-size:0.65rem; text-transform:uppercase; letter-spacing:0.2em; color:var(--gold); background:var(--royal); display:inline-block; padding:0.3rem 0.7rem; border-radius:var(--r-sm); margin-bottom:1rem; }
.ag-tag-sm { font-family:var(--font-mono); font-size:0.6rem; text-transform:uppercase; letter-spacing:0.15em; color:var(--gold-700); display:block; margin-bottom:0.75rem; }
.ag-hero h2 { font-family:var(--font-serif); font-size:2rem; color:var(--royal); margin:0 0 0.75rem; }
.ag-hero p { font-size:0.9rem; color:var(--ink-300); line-height:1.6; margin:0; }
.ag-side p, .ag-wide p { font-family:var(--font-display); font-style:italic; font-size:1rem; line-height:1.6; margin:0; opacity:0.9; }
.ag-sub h3 { font-family:var(--font-serif); font-size:1.1rem; color:var(--royal); margin:0; }
@media(max-width:768px){ .asym-grid{grid-template-columns:1fr;} .ag-hero,.ag-side,.ag-sub,.ag-wide{grid-column:1;grid-row:auto;min-height:auto;} }
```

---

### 51.2 Magazine Spread 杂志排版

经典杂志双页排版，左页大标题+引言+首字下沉，右页多列正文配侧边图注，中间有金色装订线模拟，出版物风格。

```html
<div class="mag-spread">
  <div class="ms-page ms-left">
    <span class="ms-kicker">Volume XII · Autumn</span>
    <h1 class="ms-headline">The Art of<br/><em>Quiet Luxury</em></h1>
    <p class="ms-deck">A meditation on restraint, material, and the new language of understated elegance.</p>
    <div class="ms-rule"></div>
    <p class="ms-lede"><span class="ms-drop">I</span>n an age of excess, the most radical statement is often the one you do not make. The maisons of Paris and Milan have long understood this truth — that true luxury whispers rather than shouts.</p>
  </div>
  <div class="ms-spine"></div>
  <div class="ms-page ms-right">
    <p class="ms-body">The new vocabulary of luxury is written in texture rather than logos. It is the weight of a cashmere coat, the depth of a hand-dyed indigo, the precision of a seam that lies perfectly flat against the body.</p>
    <div class="ms-pull"><span class="ms-pull-mark">"</span>Restraint is the ultimate form of confidence.<span class="ms-pull-mark">"</span></div>
    <p class="ms-body">These are not details that announce themselves. They are details that reveal themselves — slowly, intimately, only to those who know how to look.</p>
    <span class="ms-page-num">— 42 —</span>
  </div>
</div>
```
```css
.mag-spread { display:grid; grid-template-columns:1fr 2px 1fr; gap:0; background:var(--cream); max-width:1000px; border-radius:var(--r-sm); box-shadow:var(--shadow-lg); overflow:hidden; font-family:var(--font-serif); }
.ms-page { padding:3rem 2.5rem; }
.ms-spine { background:linear-gradient(to bottom,transparent,var(--gold-300) 20%,var(--gold-300) 80%,transparent); }
.ms-kicker { font-family:var(--font-mono); font-size:0.65rem; text-transform:uppercase; letter-spacing:0.25em; color:var(--wine); display:block; margin-bottom:1.5rem; }
.ms-headline { font-size:clamp(2rem,4vw,3rem); color:var(--ink); line-height:1.1; margin:0 0 1rem; font-weight:700; }
.ms-headline em { font-family:var(--font-display); font-weight:400; color:var(--royal); }
.ms-deck { font-family:var(--font-display); font-style:italic; font-size:1.1rem; color:var(--ink-200); line-height:1.5; margin:0 0 1.5rem; }
.ms-rule { width:60px; height:2px; background:var(--gold); margin-bottom:1.5rem; }
.ms-lede { font-size:0.95rem; color:var(--ink); line-height:1.8; margin:0; }
.ms-drop { float:left; font-family:var(--font-serif); font-size:3.5rem; line-height:0.8; padding-right:0.1em; padding-top:0.1em; color:var(--royal); font-weight:700; }
.ms-body { font-size:0.88rem; color:var(--ink-200); line-height:1.8; margin:0 0 1rem; text-align:justify; }
.ms-pull { font-family:var(--font-display); font-style:italic; font-size:1.1rem; color:var(--royal); text-align:center; padding:1.5rem 1rem; margin:1.5rem 0; position:relative; border-top:1px solid var(--gold-200); border-bottom:1px solid var(--gold-200); }
.ms-pull-mark { font-size:2rem; color:var(--gold); opacity:0.5; line-height:0; vertical-align:-0.2em; }
.ms-page-num { font-family:var(--font-mono); font-size:0.7rem; color:var(--ink-400); display:block; text-align:center; margin-top:2rem; letter-spacing:0.3em; }
@media(max-width:768px){ .mag-spread{grid-template-columns:1fr;} .ms-spine{display:none;} }
```

---

### 51.3 Masonry Flow 瀑布流

瀑布流布局，使用CSS columns实现，卡片有不同高度，hover时卡片微微上浮并显示金色边框，画廊/作品集风格。

```html
<div class="masonry">
  <div class="mf-item" style="height:180px;background:var(--royal);"><span>A</span></div>
  <div class="mf-item" style="height:240px;background:var(--wine);"><span>B</span></div>
  <div class="mf-item" style="height:160px;background:var(--gold);color:var(--ink);"><span>C</span></div>
  <div class="mf-item" style="height:200px;background:var(--royal-700);"><span>D</span></div>
  <div class="mf-item" style="height:220px;background:var(--cream);border:1px solid var(--cream-200);color:var(--royal);"><span>E</span></div>
  <div class="mf-item" style="height:170px;background:var(--wine-700);"><span>F</span></div>
</div>
```
```css
.masonry { column-count:3; column-gap:1.25rem; max-width:900px; font-family:var(--font-display); font-style:italic; }
.mf-item { break-inside:avoid; margin-bottom:1.25rem; border-radius:var(--r-md); display:flex; align-items:center; justify-content:center; font-size:2rem; color:var(--gold); transition:all var(--t-base); cursor:pointer; position:relative; overflow:hidden; }
.mf-item::after { content:''; position:absolute; inset:0; border:2px solid var(--gold); opacity:0; border-radius:var(--r-md); transition:opacity var(--t-base); }
.mf-item:hover { transform:scale(1.02); box-shadow:var(--shadow-gold); }
.mf-item:hover::after { opacity:1; }
@media(max-width:768px){ .masonry{column-count:2;} }
@media(max-width:480px){ .masonry{column-count:1;} }
```

---

### 51.4 Split Screen 分屏布局

左右分屏布局，两侧各占50%，中间有金色垂直分割线，hover时一侧展开到55%另一侧收缩到45%，产品/服务对比展示风格。

```html
<div class="split-screen">
  <div class="ss-left"><span class="ss-label">Collection</span><h2>Haute<br/>Couture</h2><a href="#" class="ss-cta">Explore →</a></div>
  <div class="ss-divider"></div>
  <div class="ss-right"><span class="ss-label">Maison</span><h2>Prêt-à-<br/>Porter</h2><a href="#" class="ss-cta">Discover →</a></div>
</div>
```
```css
.split-screen { display:flex; height:500px; border-radius:var(--r-lg); overflow:hidden; font-family:var(--font-sans); }
.ss-left, .ss-right { flex:1; display:flex; flex-direction:column; justify-content:center; align-items:flex-start; padding:3rem; transition:flex var(--t-slow); position:relative; cursor:pointer; }
.ss-left { background:linear-gradient(135deg,var(--royal-800),var(--royal)); color:var(--cream); }
.ss-right { background:linear-gradient(135deg,var(--wine-700),var(--wine)); color:var(--cream); }
.ss-divider { width:2px; background:var(--gold); position:relative; z-index:1; }
.split-screen:hover .ss-left { flex:0.55; }
.split-screen:hover .ss-right { flex:0.45; }
.ss-label { font-family:var(--font-mono); font-size:0.7rem; text-transform:uppercase; letter-spacing:0.25em; color:var(--gold); margin-bottom:1rem; display:block; }
.ss-left h2, .ss-right h2 { font-family:var(--font-serif); font-size:clamp(2rem,4vw,3.5rem); margin:0 0 1.5rem; line-height:1.1; font-weight:700; }
.ss-cta { font-family:var(--font-display); font-style:italic; color:var(--gold); text-decoration:none; font-size:1rem; border-bottom:1px solid var(--gold); padding-bottom:2px; transition:all var(--t-fast); }
.ss-cta:hover { letter-spacing:0.1em; }
@media(max-width:768px){ .split-screen{flex-direction:column;height:auto;} .ss-divider{height:2px;width:100%;} .split-screen:hover .ss-left,.split-screen:hover .ss-right{flex:1;} }
```

---

### 51.5 Zigzag Narrative Z字布局

Z字形叙事布局，图文交替左右排列，金色连接线穿过各节点，适合时间线/故事/流程展示，品牌故事页面风格。

```html
<div class="zigzag">
  <div class="zz-item zz-left"><div class="zz-img" style="background:var(--royal)">01</div><div class="zz-text"><span class="zz-step">Step One</span><h3>Discovery</h3><p>We begin with deep listening — understanding your vision, values, and audience.</p></div></div>
  <div class="zz-item zz-right"><div class="zz-text"><span class="zz-step">Step Two</span><h3>Design</h3><p>Crafting visual language that speaks with clarity, elegance, and intention.</p></div><div class="zz-img" style="background:var(--wine)">02</div></div>
  <div class="zz-item zz-left"><div class="zz-img" style="background:var(--gold);color:var(--ink)">03</div><div class="zz-text"><span class="zz-step">Step Three</span><h3>Refinement</h3><p>Iterative polish — every pixel, every spacing, every word considered.</p></div></div>
  <div class="zz-item zz-right"><div class="zz-text"><span class="zz-step">Step Four</span><h3>Delivery</h3><p>Handing over a system built to last, documented with care.</p></div><div class="zz-img" style="background:var(--royal-700)">04</div></div>
</div>
```
```css
.zigzag { max-width:800px; font-family:var(--font-sans); position:relative; }
.zigzag::before { content:''; position:absolute; left:50%; top:60px; bottom:60px; width:1px; background:linear-gradient(to bottom,var(--gold-200),var(--gold),var(--gold-200)); transform:translateX(-50%); }
.zz-item { display:flex; align-items:center; gap:2.5rem; margin-bottom:3rem; position:relative; }
.zz-item.zz-right { flex-direction:row-reverse; }
.zz-img { width:120px; height:120px; border-radius:50%; display:flex; align-items:center; justify-content:center; font-family:var(--font-display); font-style:italic; font-size:2rem; color:var(--gold); flex-shrink:0; border:3px solid var(--gold); box-shadow:0 0 0 8px var(--cream); position:relative; z-index:1; }
.zz-text { flex:1; }
.zz-step { font-family:var(--font-mono); font-size:0.65rem; text-transform:uppercase; letter-spacing:0.2em; color:var(--gold-700); display:block; margin-bottom:0.4rem; }
.zz-text h3 { font-family:var(--font-serif); font-size:1.4rem; color:var(--royal); margin:0 0 0.5rem; }
.zz-text p { font-size:0.9rem; color:var(--ink-300); line-height:1.7; margin:0; }
@media(max-width:640px){ .zigzag::before{left:60px;} .zz-item,.zz-item.zz-right{flex-direction:column;text-align:center;} .zz-img{width:80px;height:80px;font-size:1.3rem;} }
```

---

## Supplement: 16 Layout Patterns · 补充布局模式

> 来自 layouts.md 的完整16种布局模式，提供页面级别的编排方案。

---

## 布局分类索引

| 类别 | 布局 | 适用位置 | 密度 |
|------|------|---------|------|
| **Hero 首屏** | L1 非对称图文Hero | 第一屏 | 高冲击 |
| | L2 居中大字Hero | 第一屏 | 高冲击 |
| | L3 分屏Hero | 第一屏 | 高冲击 |
| | L4 全屏视觉Hero | 第一屏 | 高冲击 |
| **内容叙述** | L5 左图右文 | 中段 | 中等 |
| | L6 左文右图 | 中段 | 中等 |
| | L7 单栏长文 | 教程/博客 | 疏 |
| | L8 引文全屏 | 节奏打破 | 疏 |
| **网格展示** | L9 三列卡片网格 | 中段 | 密 |
| | L10 非对称网格 | 作品展示 | 中密 |
| | L11 交错瀑布流 | 作品/博客 | 中 |
| | L12 时间线 | 经历/过程 | 中 |
| **特殊布局** | L13 深色面板CTA | 2/3处或结尾 | 强 |
| | L14 数据统计条 | 信任建立 | 密 |
| | L15 双栏对比 | 对比/前后 | 中 |
| | L16 画册溢出式 | 视觉惊喜 | 疏 |

---

## L1. 非对称图文 Hero

**特征**：左侧大标题+文案+CTA，右侧头像/视觉，文字视觉比约 1.2:1，视觉略小但有装饰元素（大数字、圆形背景）。

**适用**：个人主页、作品集首页、Landing首屏。

**视觉效果**：现代、个人化、有温度。首屏有焦点但不单调。

```html
<section class="L1-hero">
  <div class="L1-content">
    <span class="eyebrow">设计师 · 品牌顾问</span>
    <h1 class="hero-title">创造<span class="gold-accent">有温度</span>的设计</h1>
    <p class="body-text">我是飞鸿，专注于个人品牌和数字体验设计。</p>
    <div class="flex gap-4 flex-wrap">
      <a href="#work" class="btn btn-cta">查看作品</a>
      <a href="#contact" class="btn btn-outline">联系我</a>
    </div>
  </div>
  <div class="L1-visual">
    <div class="avatar avatar-xl"><img src="assets/avatar.png" alt="飞鸿"></div>
    <div class="decor-number" style="top:-2rem;right:-1rem;">07</div>
  </div>
</section>
```
```css
.L1-hero {
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: clamp(3rem, 8vw, 6rem);
  align-items: center;
  min-height: 85vh;
  padding: clamp(4rem, 12vw, 8rem) 1.5rem;
  max-width: var(--container);
  margin: 0 auto;
  position: relative;
}
.L1-visual { position: relative; display: flex; justify-content: center; }
@media (max-width: 768px) {
  .L1-hero { grid-template-columns: 1fr; text-align: center; min-height: auto; padding-top: 6rem; }
  .L1-visual { order: -1; }
  .L1-content .flex { justify-content: center; }
}
```

---

## L2. 居中大字 Hero

**特征**：所有内容居中对齐，超大衬线标题是绝对焦点，金色装饰线或装饰文字衬托，底部有CTA。

**适用**：活动页Landing、演示文稿封面、个人品牌Slogan页。

**视觉效果**：大气、权威、聚焦。适合一句话讲清楚核心价值。

```html
<section class="L2-hero">
  <div class="decor-text" style="top:20%;left:50%;transform:translateX(-50%);">DESIGN</div>
  <span class="eyebrow">2024 设计分享会</span>
  <h1 class="L2-title">设计的温度</h1>
  <p class="L2-subtitle">当AI可以生成一切，<br>人的审美判断才是最稀缺的能力。</p>
  <div class="flex gap-4 flex-wrap justify-center">
    <a href="#" class="btn btn-cta btn-lg">立即报名</a>
    <a href="#" class="btn btn-ghost btn-lg">了解详情 →</a>
  </div>
  <div class="L2-scroll-hint">向下滚动 ↓</div>
</section>
```
```css
.L2-hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 6rem 1.5rem;
  position: relative;
}
.L2-title {
  font-family: var(--font-serif);
  font-size: clamp(3rem, 10vw, 7rem);
  font-weight: 700;
  line-height: 1.05;
  color: var(--ink);
  margin: 1.5rem 0;
  letter-spacing: -0.02em;
}
.L2-subtitle {
  font-family: var(--font-display);
  font-size: clamp(1.125rem, 2vw, 1.5rem);
  font-style: italic;
  color: var(--ink-200);
  line-height: 1.6;
  max-width: 500px;
  margin: 0 0 2.5rem;
}
.L2-scroll-hint {
  position: absolute;
  bottom: 2rem;
  font-family: var(--font-sans);
  font-size: 0.75rem;
  color: var(--ink-400);
  letter-spacing: 0.15em;
  text-transform: uppercase;
  animation: bounce 2s ease infinite;
}
@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(8px); }
}
@media (prefers-reduced-motion: reduce) {
  .L2-scroll-hint { animation: none; }
}
```

---

## L3. 分屏 Hero（Split Screen）

**特征**：50:50 左右分屏，一侧纯色（皇家蓝/酒红深色），一侧图片或浅色内容。强烈对比。

**适用**：App展示、产品介绍、作品集封面。

**视觉效果**：戏剧化、现代、有冲击力。

```html
<section class="L3-split">
  <div class="L3-left">
    <span class="eyebrow" style="background:rgba(244,211,94,0.15);color:var(--gold);">New</span>
    <h1 class="L3-title">Feihong<br>Design<br>System</h1>
    <p style="color:rgba(255,255,255,0.7);max-width:380px;line-height:1.7;">一套完整的个人品牌设计系统，让每一次创作都保持一致的温度与品质。</p>
    <a href="#" class="btn btn-gold">开始使用 →</a>
  </div>
  <div class="L3-right">
    <img src="hero-visual.jpg" alt="产品预览">
  </div>
</section>
```
```css
.L3-split {
  display: grid;
  grid-template-columns: 1fr 1fr;
  min-height: 100vh;
}
.L3-left {
  background: radial-gradient(ellipse at bottom right, var(--royal-700), var(--ink));
  padding: clamp(3rem, 8vw, 6rem);
  display: flex;
  flex-direction: column;
  justify-content: center;
  color: #fff;
  position: relative;
  overflow: hidden;
}
.L3-left::before {
  content: '';
  position: absolute;
  width: 400px; height: 400px;
  background: radial-gradient(circle, rgba(244,211,94,0.06), transparent);
  border-radius: 50%;
  bottom: -100px; left: -100px;
}
.L3-title {
  font-family: var(--font-serif);
  font-size: clamp(2.5rem, 5vw, 4.5rem);
  font-weight: 700;
  line-height: 1.05;
  color: #fff;
  margin: 1rem 0 1.5rem;
}
.L3-right {
  background: var(--cream-100);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}
.L3-right img { width: 100%; height: 100%; object-fit: cover; }
@media (max-width: 768px) {
  .L3-split { grid-template-columns: 1fr; }
  .L3-right { min-height: 50vh; }
}
```

---

## L4. 全屏视觉 Hero（Full Bleed）

**特征**：全幅背景图/渐变+叠加文字，标题在图上，金色线条装饰。图片占满视口宽度。

**适用**：活动页、案例研究封面、品牌视觉页。

**视觉效果**：沉浸式、画册感、艺术感。

```html
<section class="L4-fullbleed">
  <div class="L4-bg"></div>
  <div class="L4-overlay"></div>
  <div class="L4-content">
    <span class="caption-text" style="color:var(--gold);letter-spacing:0.2em;">CASE STUDY · 2024</span>
    <h1 class="L4-title">某某科技<br>品牌升级</h1>
    <div class="title-gold-line" style="margin:1.5rem 0;"></div>
    <p style="color:rgba(255,255,255,0.8);max-width:450px;">从传统B2B到现代科技品牌的视觉重塑，包含Logo、色彩系统、设计规范全流程。</p>
  </div>
</section>
```
```css
.L4-fullbleed {
  position: relative;
  min-height: 80vh;
  display: flex;
  align-items: flex-end;
  padding: clamp(3rem, 8vw, 6rem);
  overflow: hidden;
}
.L4-bg {
  position: absolute;
  inset: 0;
  background: url('case-hero.jpg') center/cover;
  /* 无图时用渐变替代 */
  background: linear-gradient(135deg, var(--royal-700) 0%, var(--royal) 40%, var(--wine-700) 100%);
}
.L4-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(0deg, rgba(13,18,37,0.8) 0%, rgba(13,18,37,0.2) 50%, transparent 100%);
}
.L4-content {
  position: relative;
  z-index: 1;
  max-width: var(--container);
  margin: 0 auto;
  width: 100%;
}
.L4-title {
  font-family: var(--font-serif);
  font-size: clamp(2rem, 5vw, 4rem);
  font-weight: 700;
  color: #fff;
  line-height: 1.1;
  margin: 0.75rem 0 0;
}
```

---

## L5. 左图右文

**特征**：左侧图片/视觉，右侧标题+正文+列表/CTA。图文各占约一半。

**适用**：关于我、服务介绍、功能说明。

**视觉效果**：经典、平衡、清晰。

```html
<section class="L5-img-text section">
  <div class="container L5-grid">
    <div class="L5-image">
      <img src="about.jpg" alt="关于飞鸿">
    </div>
    <div class="L5-text">
      <div class="section-title" style="margin-bottom:2rem;">
        <span class="section-number">02</span>
        <h2>关于我</h2>
      </div>
      <p class="body-text">我是一名有8年经验的设计师，专注于个人品牌和数字产品设计。</p>
      <p class="body-text">我相信好的设计不是炫技，而是让人感到被理解。</p>
      <ul class="list list-gold-dot" style="margin-top:1.5rem;">
        <li>8年品牌与产品设计经验</li>
        <li>服务过50+个人品牌客户</li>
        <li>前某科技公司设计负责人</li>
      </ul>
    </div>
  </div>
</section>
```
```css
.L5-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: clamp(2rem, 6vw, 5rem);
  align-items: center;
}
.L5-image {
  border-radius: var(--r-xl);
  overflow: hidden;
  aspect-ratio: 4/5;
  box-shadow: var(--shadow-lg);
}
.L5-image img { width: 100%; height: 100%; object-fit: cover; }
@media (max-width: 768px) {
  .L5-grid { grid-template-columns: 1fr; }
}
```

---

## L6. 左文右图（镜像L5）

```css
/* 与L5相同，交换顺序 */
.L6-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: clamp(2rem, 6vw, 5rem);
  align-items: center;
}
@media (max-width: 768px) {
  .L6-grid { grid-template-columns: 1fr; }
  .L6-image { order: -1; }
}
```
```html
<section class="section">
  <div class="container L6-grid">
    <div class="L6-text"><!-- 文案在左 --></div>
    <div class="L5-image L6-image"><!-- 图片在右 --></div>
  </div>
</section>
```

> L5和L6交替使用，避免连续两个"图左文右"。

---

## L7. 单栏长文（Reading Layout）

**特征**：单栏居中，窄列（65ch），大行距，舒适阅读。衬线标题+无衬线正文，可含金色装饰线和引用块。

**适用**：教程、博客文章、案例研究正文、关于长文。

**视觉效果**：专注、安静、阅读友好。

```html
<article class="L7-reading">
  <div class="L7-container">
    <span class="eyebrow">教程</span>
    <h1 class="L7-title">如何建立有辨识度的个人品牌</h1>
    <div class="L7-meta">
      <span>2024年7月</span><span>·</span><span>阅读 8 分钟</span>
    </div>
    <div class="divider-gold" style="margin:2rem 0;"></div>
    <p class="body-text">正文内容...</p>
    <h2 class="subsection-title">第一个要点</h2>
    <p class="body-text">...</p>
    <blockquote class="pull-quote"><p>品牌不是logo，是别人提到你时的第一印象。</p></blockquote>
    <h2 class="subsection-title">第二个要点</h2>
    <p class="body-text">...</p>
  </div>
</article>
```
```css
.L7-reading {
  padding: clamp(4rem, 8vw, 7rem) 1.5rem;
}
.L7-container {
  max-width: 680px;
  margin: 0 auto;
}
.L7-title {
  font-family: var(--font-serif);
  font-size: clamp(1.75rem, 4vw, 2.75rem);
  font-weight: 700;
  line-height: 1.2;
  color: var(--ink);
  margin: 1rem 0 0.75rem;
}
.L7-meta {
  font-family: var(--font-sans);
  font-size: 0.875rem;
  color: var(--ink-300);
  display: flex;
  gap: 0.5rem;
}
```

---

## L8. 引文全屏（Pull Quote Break）

**特征**：整屏/整section只有一句大引言，衬线斜体，金色大号引号，极简。作为节奏打破点。

**适用**：section之间的过渡、价值主张强调、金句页（演示文稿/卡片）。

**视觉效果**：呼吸感、艺术感、停顿。

```html
<section class="L8-quote-section">
  <div class="decor-text" style="top:10%;left:5%;">QUOTE</div>
  <blockquote class="L8-quote">
    <span class="quote-mark">&ldquo;</span>
    <p>设计不是让东西看起来好看，<br>而是让人感到被理解。</p>
    <cite>— 飞鸿</cite>
  </blockquote>
</section>
```
```css
.L8-quote-section {
  min-height: 70vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 4rem 1.5rem;
  position: relative;
  background: var(--cream);
}
.L8-quote {
  text-align: center;
  max-width: 800px;
  position: relative;
}
.L8-quote .quote-mark {
  font-family: var(--font-serif);
  font-size: 6rem;
  color: var(--gold);
  line-height: 1;
  display: block;
  margin-bottom: -1rem;
}
.L8-quote p {
  font-family: var(--font-display);
  font-size: clamp(1.5rem, 3.5vw, 2.75rem);
  font-style: italic;
  font-weight: 300;
  line-height: 1.4;
  color: var(--royal);
  margin: 1rem 0 1.5rem;
}
.L8-quote cite {
  font-family: var(--font-sans);
  font-size: 0.875rem;
  font-style: normal;
  color: var(--ink-300);
  letter-spacing: 0.12em;
  text-transform: uppercase;
}
```

---

## L9. 三列卡片网格

**特征**：标题+描述，下方等宽三列（或多列）卡片，卡片有悬停效果。

**适用**：服务介绍、功能特色、文章列表、客户展示。

**视觉效果**：整齐、专业、信息密度高。注意：这是AI最爱用的布局，**必须搭配其他非网格布局**使用，不能连续两个section都是网格。

```html
<section class="section">
  <div class="container">
    <div class="section-title">
      <span class="section-number">03</span>
      <h2>我的服务</h2>
      <div class="title-gold-line"></div>
    </div>
    <p class="body-text" style="max-width:550px;margin-bottom:3rem;">从品牌策略到视觉落地，提供完整的设计服务。</p>
    <div class="L9-grid">
      <div class="card card-feature reveal">
        <div class="card-icon">✦</div>
        <h3 class="card-title">品牌设计</h3>
        <p class="card-desc">从logo到完整视觉体系，打造有记忆点的品牌。</p>
        <a href="#" class="card-link">了解更多 →</a>
      </div>
      <div class="card card-feature reveal reveal-delay-1">
        <div class="card-icon">◆</div>
        <h3 class="card-title">设计系统</h3>
        <p class="card-desc">可扩展的组件库和规范，让团队高效协作。</p>
        <a href="#" class="card-link">了解更多 →</a>
      </div>
      <div class="card card-feature reveal reveal-delay-2">
        <div class="card-icon">●</div>
        <h3 class="card-title">落地页设计</h3>
        <p class="card-desc">高转化的Landing Page设计与开发。</p>
        <a href="#" class="card-link">了解更多 →</a>
      </div>
    </div>
  </div>
</section>
```
```css
.L9-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
}
@media (max-width: 900px) {
  .L9-grid { grid-template-columns: repeat(2, 1fr); }
}
@media (max-width: 600px) {
  .L9-grid { grid-template-columns: 1fr; }
}
```

---

## L10. 非对称网格（Asymmetric Grid）

**特征**：不等宽网格，一个大卡片+两个小卡片，或有主有次的bento布局。比等宽网格更有设计感。

**适用**：作品集展示、功能展示、首页内容编排。

**视觉效果**：有主次、现代、非模板感。

```html
<section class="section">
  <div class="container">
    <div class="section-title">
      <span class="section-number">04</span>
      <h2>精选作品</h2>
      <div class="title-gold-line"></div>
    </div>
    <div class="L10-bento">
      <div class="L10-item L10-large">
        <img src="work1.jpg" alt="项目1">
        <div class="L10-info"><span class="badge badge-gold">品牌设计</span><h3>科技品牌升级</h3></div>
      </div>
      <div class="L10-item">
        <img src="work2.jpg" alt="项目2">
        <div class="L10-info"><span class="badge badge-royal">落地页</span><h3>教育平台</h3></div>
      </div>
      <div class="L10-item">
        <img src="work3.jpg" alt="项目3">
        <div class="L10-info"><span class="badge badge-wine">设计系统</span><h3>组件库</h3></div>
      </div>
    </div>
  </div>
</section>
```
```css
.L10-bento {
  display: grid;
  grid-template-columns: 2fr 1fr;
  grid-template-rows: 1fr 1fr;
  gap: 1rem;
  min-height: 500px;
}
.L10-large { grid-row: 1 / 3; }
.L10-item {
  border-radius: var(--r-lg);
  overflow: hidden;
  position: relative;
  cursor: pointer;
}
.L10-item img { width: 100%; height: 100%; object-fit: cover; transition: transform var(--t-slow); }
.L10-item:hover img { transform: scale(1.05); }
.L10-info {
  position: absolute;
  bottom: 0; left: 0; right: 0;
  padding: 1.5rem;
  background: linear-gradient(transparent, rgba(13,18,37,0.8));
  color: #fff;
}
.L10-info h3 { font-family: var(--font-serif); font-size: 1.25rem; margin-top: 0.5rem; }
@media (max-width: 768px) {
  .L10-bento { grid-template-columns: 1fr; grid-template-rows: auto; min-height: auto; }
  .L10-large { grid-row: auto; }
  .L10-item { aspect-ratio: 4/3; }
}
```

---

## L11. 交错瀑布流（Staggered List）

**特征**：内容项左右交错排列，图文交替，类似杂志排版。每个item有图片+标题+简介，偶数项左右翻转。

**适用**：博客文章列表、作品列表、项目流程。

**视觉效果**：画册感、有节奏、不呆板。

```html
<section class="section">
  <div class="container">
    <div class="L11-item">
      <div class="L11-img"><img src="post1.jpg" alt=""></div>
      <div class="L11-content">
        <span class="caption-text">2024.07</span>
        <h3 class="card-title">设计系统的十个常见错误</h3>
        <p class="card-desc">从实践中总结的设计系统建设经验...</p>
        <a href="#" class="card-link">阅读全文 →</a>
      </div>
    </div>
    <div class="L11-item L11-reverse">
      <div class="L11-img"><img src="post2.jpg" alt=""></div>
      <div class="L11-content">
        <span class="caption-text">2024.06</span>
        <h3 class="card-title">如何让设计不像AI</h3>
        <p class="card-desc">反AI审美的具体策略和手法...</p>
        <a href="#" class="card-link">阅读全文 →</a>
      </div>
    </div>
  </div>
</section>
```
```css
.L11-item {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: clamp(2rem, 5vw, 4rem);
  align-items: center;
  margin-bottom: 4rem;
}
.L11-reverse .L11-img { order: 2; }
.L11-img {
  border-radius: var(--r-lg);
  overflow: hidden;
  aspect-ratio: 4/3;
  box-shadow: var(--shadow-md);
}
.L11-img img { width: 100%; height: 100%; object-fit: cover; }
@media (max-width: 768px) {
  .L11-item, .L11-item.L11-reverse {
    grid-template-columns: 1fr;
  }
  .L11-reverse .L11-img { order: 0; }
}
```

---

## L12. 时间线（Timeline）

**特征**：垂直时间线，金色圆点+连线，每个时间点有年份+标题+描述。

**适用**：个人经历、项目流程、公司发展历程、案例研究过程。

**视觉效果**：叙事感、清晰、有历程感。

```html
<section class="section" style="background:var(--cream-100);">
  <div class="container">
    <div class="section-title">
      <span class="section-number">05</span>
      <h2>我的历程</h2>
      <div class="title-gold-line"></div>
    </div>
    <div class="timeline" style="max-width:600px;margin:0 auto;padding-left:2rem;">
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-content">
          <span class="caption-text">2024 — 至今</span>
          <h4>创立个人工作室</h4>
          <p>专注个人品牌设计，服务50+客户。</p>
        </div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-content">
          <span class="caption-text">2020 — 2024</span>
          <h4>某科技公司 · 设计负责人</h4>
          <p>主导设计系统搭建，管理8人设计团队。</p>
        </div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-content">
          <span class="caption-text">2016 — 2020</span>
          <h4>某互联网公司 · 高级设计师</h4>
          <p>从UI设计师成长为产品设计核心成员。</p>
        </div>
      </div>
    </div>
  </div>
</section>
```
（CSS 见 components.md 中的 `.timeline` 组件）

---

## L13. 深色面板 CTA

**特征**：深蓝/深色背景，金色点缀，白色文字，大CTA按钮。打断浅色页面节奏。

**适用**：转化CTA区、联系方式区、价格区、2/3处的节奏打破。

**视觉效果**：聚焦、高级、转化导向。

```html
<section class="section">
  <div class="container">
    <div class="dark-panel">
      <span class="eyebrow" style="background:rgba(244,211,94,0.15);color:var(--gold);">开始合作</span>
      <h2>准备好创造<br>有温度的设计了吗？</h2>
      <p>告诉我你的项目想法，我们一起把它变成现实。</p>
      <div class="flex gap-4 flex-wrap" style="margin-top:2rem;">
        <a href="mailto:hello@Feihong.art" class="btn btn-gold btn-lg">发送邮件</a>
        <a href="#" class="btn btn-outline btn-lg" style="border-color:rgba(255,255,255,0.3);color:#fff;">预约咨询</a>
      </div>
    </div>
  </div>
</section>
```
（CSS 见 components.md 中的 `.dark-panel` 组件）

---

## L14. 数据统计条

**特征**：横向排列的大数字+标签，4个以内，衬线大数字，金色/皇家蓝。

**适用**：Hero下方社会证明、关于页数据展示、案例研究结果。

**视觉效果**：建立信任、权威感、简洁有力。

```html
<section class="L14-stats">
  <div class="container">
    <div class="L14-grid">
      <div class="stat-card"><span class="stat-number">8+</span><span class="stat-label">年经验</span></div>
      <div class="stat-card"><span class="stat-number">50+</span><span class="stat-label">品牌项目</span></div>
      <div class="stat-card"><span class="stat-number">100%</span><span class="stat-label">客户满意</span></div>
      <div class="stat-card"><span class="stat-number">12</span><span class="stat-label">设计奖项</span></div>
    </div>
  </div>
</section>
```
```css
.L14-stats {
  padding: 3rem 1.5rem;
  background: #fff;
  border-top: 1px solid var(--cream-200);
  border-bottom: 1px solid var(--cream-200);
}
.L14-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  max-width: var(--container);
  margin: 0 auto;
}
@media (max-width: 600px) {
  .L14-grid { grid-template-columns: repeat(2, 1fr); gap: 2rem; }
  .stat-card::after { display: none; }
}
```
（stat-card CSS 见 components.md）

---

## L15. 双栏对比

**特征**：左右两栏对比展示，中间可有分隔线。Before/After、服务对比、优势对比。

**适用**：服务套餐对比、前后对比、方案对比。

**视觉效果**：清晰、决策辅助。

```html
<section class="section">
  <div class="container">
    <div class="section-title">
      <span class="section-number">06</span>
      <h2>合作方式</h2>
      <div class="title-gold-line"></div>
    </div>
    <div class="L15-compare">
      <div class="L15-col">
        <span class="badge badge-outline">单次项目</span>
        <h3 style="font-family:var(--font-serif);font-size:1.5rem;margin:1rem 0;">品牌设计</h3>
        <p class="caption-text">适合有明确需求的项目</p>
        <div class="divider-gold" style="margin:1.5rem 0;max-width:60px;"></div>
        <ul class="list list-check">
          <li>完整品牌视觉体系</li>
          <li>4-6周交付</li>
          <li>3次修改</li>
          <li>源文件交付</li>
        </ul>
        <a href="#" class="btn btn-outline" style="margin-top:1.5rem;">了解详情</a>
      </div>
      <div class="L15-col L15-featured">
        <span class="badge badge-gold">推荐</span>
        <h3 style="font-family:var(--font-serif);font-size:1.5rem;margin:1rem 0;">设计顾问</h3>
        <p class="caption-text">长期合作，持续迭代</p>
        <div class="divider-gold" style="margin:1.5rem 0;max-width:60px;"></div>
        <ul class="list list-check">
          <li>月度设计支持</li>
          <li>优先响应</li>
          <li>不限修改次数</li>
          <li>策略咨询</li>
        </ul>
        <a href="#" class="btn btn-cta" style="margin-top:1.5rem;">预约咨询</a>
      </div>
    </div>
  </div>
</section>
```
```css
.L15-compare {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  max-width: 800px;
  margin: 0 auto;
}
.L15-col {
  padding: 2.5rem;
  border-radius: var(--r-lg);
  border: 1px solid var(--cream-200);
  background: #fff;
}
.L15-featured {
  border-color: var(--gold);
  box-shadow: var(--shadow-gold);
  transform: scale(1.03);
  position: relative;
}
@media (max-width: 600px) {
  .L15-compare { grid-template-columns: 1fr; }
  .L15-featured { transform: none; }
}
```

---

## L16. 画册溢出式（Editorial Bleed）

**特征**：图片有意突破容器边界（溢出卡片、跨栏、出血到边缘），文字叠加在图片上或图片旁边，大留白。

**适用**：视觉惊喜section、画册式排版、作品集细节展示、案例研究亮点。

**视觉效果**：艺术感、画册感、专业设计水准。这是"反AI"的重要手法。

```html
<section class="section L16-editorial" style="overflow:hidden;">
  <div class="container L16-grid">
    <div class="L16-text">
      <span class="eyebrow">设计理念</span>
      <h2 style="font-family:var(--font-serif);font-size:clamp(1.75rem,3vw,2.5rem);margin:1rem 0;">细节构成品质</h2>
      <p class="body-text">每一个像素、每一个间距、每一处金色装饰线的长度，都是经过反复斟酌的决定。好设计的质感来自于这些看不见的细节。</p>
      <blockquote style="border-left:3px solid var(--gold);padding-left:1.5rem;margin:2rem 0;font-family:var(--font-display);font-style:italic;font-size:1.25rem;color:var(--royal);line-height:1.6;">
        "God is in the details."
      </blockquote>
    </div>
    <div class="L16-images">
      <div class="L16-img-main">
        <img src="detail1.jpg" alt="设计细节">
      </div>
      <div class="L16-img-accent">
        <img src="detail2.jpg" alt="金色装饰">
      </div>
    </div>
  </div>
</section>
```
```css
.L16-grid {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 4rem;
  align-items: center;
  position: relative;
}
.L16-images { position: relative; }
.L16-img-main {
  border-radius: var(--r-xl);
  overflow: hidden;
  aspect-ratio: 4/3;
  box-shadow: var(--shadow-xl);
}
.L16-img-main img { width: 100%; height: 100%; object-fit: cover; }
.L16-img-accent {
  position: absolute;
  width: 50%;
  bottom: -2rem;
  right: -2rem;
  border-radius: var(--r-lg);
  overflow: hidden;
  border: 4px solid var(--cream);
  box-shadow: var(--shadow-lg);
}
.L16-img-accent img { width: 100%; aspect-ratio: 1; object-fit: cover; }
@media (max-width: 768px) {
  .L16-grid { grid-template-columns: 1fr; }
  .L16-img-accent { display: none; }
}
```

---

## 布局搭配推荐

### 典型个人主页（6屏节奏）
1. **L1 非对称图文Hero**（强，建立第一印象）
2. **L14 数据统计条**（密，信任建立）
3. **L10 非对称网格作品**（中密，视觉展示）
4. **L8 引文全屏**（疏，节奏打破）
5. **L9 三列卡片服务**（密，信息展示）
6. **L13 深色面板CTA**（强，转化）

### 典型Landing（7屏节奏）
1. **L2 居中大字Hero**（强，冲击力）
2. **L5 左图右文介绍**（中，产品说明）
3. **L9 三列特色卡片**（密，功能展示）
4. **L6 左文右图社会证明**（中，信任）
5. **L16 画册溢出式**（疏，视觉惊喜）
6. **L15 双栏价格对比**（中，决策）
7. **L13 深色CTA**（强，行动）

### 典型教程文章（阅读导向）
1. **L7 单栏长文**（全篇，阅读体验为主）
2. 其中穿插 **L8 引文全屏** 做节奏打破
3. 代码块使用components.md中的 `.code-block`

---

*Layout Patterns v8.0 · Feihong Design System*

---

## L17. 深色居中CTA区块（Centered CTA Dark Block）

**特征**：radial-gradient 深色皇家蓝背景，居中 max-width:600px 内容区，金色眉标+衬线大标题+双按钮（金色实心+白色描边），下方4列金色统计数字，再下方3步 Fork 指南半透明卡片。

**适用**：页面底部行动号召、注册/下载/获取CTA、开源项目引导。

**视觉效果**：强对比、聚焦感、金色在深色底上格外醒目，径向渐变营造舞台聚光灯效果。

```html
<section class="cta-section">
  <div class="cta-inner">
    <div class="cta-eyebrow">Get Started</div>
    <h2>开始创造<em>有温度</em>的<br>个人品牌</h2>
    <p>将 Feihong Design System 放入你的 AI 助手 Skills 目录，用自然语言描述需求，剩下的交给设计系统。</p>
    <div class="cta-btns">
      <a href="#" class="btn btn-gold btn-lg">在 GitHub 上获取</a>
      <a href="#" class="btn btn-outline-light">浏览模板 →</a>
    </div>
    <!-- 4列金色统计数字 -->
    <div class="cta-stats">
      <div class="cta-stat">
        <div class="stat-num">148</div>
        <div class="stat-label">品牌组件</div>
      </div>
      <div class="cta-stat">
        <div class="stat-num">19</div>
        <div class="stat-label">科学分类</div>
      </div>
      <div class="cta-stat">
        <div class="stat-num">250+</div>
        <div class="stat-label">样式变体</div>
      </div>
      <div class="cta-stat">
        <div class="stat-num">MIT</div>
        <div class="stat-label">开源免费</div>
      </div>
    </div>
    <!-- 3步Fork指南 -->
    <div class="fork-guide">
      <div class="fork-title">Fork & Customize · 克隆并定制</div>
      <p class="fork-desc">Fork 后只需几步，即可将其改为属于你自己的品牌设计系统。</p>
      <div class="fork-steps">
        <div class="fork-step">
          <div class="fork-step-num">1. Fork</div>
          <p>点击 GitHub 右上角 Fork 按钮，将项目复制到自己的仓库。</p>
        </div>
        <div class="fork-step">
          <div class="fork-step-num">2. Rebrand</div>
          <p>修改 DNA.md 中的品牌名、颜色、字体；替换头像和形象图。</p>
        </div>
        <div class="fork-step">
          <div class="fork-step-num">3. Deploy</div>
          <p>开启 GitHub Pages，你的个人品牌设计系统即刻上线。</p>
        </div>
      </div>
    </div>
  </div>
</section>
```
```css
/* CTA深色区块 */
.cta-section {
  text-align: center;
  padding: 5rem 2.5rem;
  background: radial-gradient(ellipse at center, var(--royal-700) 0%, var(--ink) 70%);
  position: relative;
  overflow: hidden;
}
/* 装饰光晕 */
.cta-section::before {
  content: '';
  position: absolute;
  width: 500px; height: 500px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(244,211,94,0.08) 0%, transparent 65%);
  top: -200px; right: -100px;
}
.cta-section::after {
  content: '';
  position: absolute;
  width: 400px; height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(216,49,91,0.08) 0%, transparent 65%);
  bottom: -150px; left: -100px;
}
/* 居中内容容器 */
.cta-inner {
  max-width: 600px;
  margin: 0 auto;
  position: relative;
  z-index: 1;
}
/* 金色眉标 */
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
.cta-section h2 {
  font-family: var(--font-serif);
  font-size: clamp(1.8rem, 4vw, 2.8rem);
  font-weight: 700;
  color: #fff;
  line-height: 1.15;
  margin-bottom: 1rem;
}
.cta-section h2 em {
  font-style: italic;
  color: var(--gold);
}
.cta-section p {
  font-size: 1rem;
  color: rgba(255,255,255,0.6);
  line-height: 1.7;
  margin-bottom: 2rem;
}
/* 双按钮 */
.cta-btns {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}
.btn-gold {
  background: var(--gold);
  color: var(--royal);
  font-weight: 600;
  padding: 0.75rem 1.5rem;
  border-radius: 8px;
  text-decoration: none;
  box-shadow: 0 4px 20px rgba(244,211,94,0.3);
  transition: all 300ms var(--ease);
}
.btn-gold:hover { background: var(--gold-600); color: #fff; transform: translateY(-2px); }
.btn-outline-light {
  background: transparent;
  color: #fff;
  border: 1.5px solid rgba(255,255,255,0.25);
  padding: 0.75rem 1.5rem;
  border-radius: 8px;
  text-decoration: none;
  transition: all 300ms var(--ease);
}
.btn-outline-light:hover { border-color: var(--gold); color: var(--gold); }
/* 4列金色统计数字 */
.cta-stats {
  margin-top: 40px;
  padding-top: 28px;
  border-top: 1px solid rgba(255,255,255,0.1);
  max-width: 560px;
  margin-left: auto;
  margin-right: auto;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  text-align: center;
}
.stat-num {
  font-family: var(--font-serif);
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--gold);
  line-height: 1;
}
.stat-label {
  font-size: 0.7rem;
  color: rgba(255,255,255,0.4);
  margin-top: 6px;
  letter-spacing: 0.05em;
}
/* 3步Fork指南 */
.fork-guide {
  margin-top: 48px;
  padding-top: 32px;
  border-top: 1px solid rgba(255,255,255,0.1);
  max-width: 640px;
  margin-left: auto;
  margin-right: auto;
  text-align: left;
}
.fork-title {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 16px;
  text-align: center;
}
.fork-desc {
  font-size: 0.9rem;
  color: rgba(255,255,255,0.7);
  line-height: 1.7;
  text-align: center;
  margin-bottom: 20px;
}
.fork-steps {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 16px;
}
.fork-step {
  background: rgba(255,255,255,0.05);
  border-radius: 10px;
  padding: 16px;
  border: 1px solid rgba(255,255,255,0.08);
}
.fork-step-num {
  font-family: var(--font-serif);
  font-size: 1.1rem;
  font-weight: 700;
  color: var(--gold);
  margin-bottom: 6px;
}
.fork-step p {
  font-size: 0.8rem;
  color: rgba(255,255,255,0.6);
  line-height: 1.5;
  margin: 0;
}
@media (max-width: 600px) {
  .cta-section { padding: 3.5rem 1.25rem; }
  .cta-stats { grid-template-columns: repeat(2, 1fr); }
}
```

---

## L18. 双栏Token展示（Two-Column Token Showcase）

**特征**：1fr 1fr 网格布局，左侧色彩卡片包含 flex 比例条（55/30/15 品牌三色）+ 三色图例，右侧字体卡片包含逐行字体样例（衬线/斜体/无衬线/等宽），双卡片白底圆角20px+米色边框。

**适用**：设计语言展示、品牌规范说明、Design Token可视化、设计系统首页。

**视觉效果**：信息密度适中，左右对比清晰，色彩条直观表达配色比例，字体行直接展示字体风貌。

```html
<section class="tokens-section">
  <div class="section-label">Design Language</div>
  <h2 class="section-h">品牌<em>基因</em>，精确到像素</h2>
  <div class="tokens-grid">
    <!-- 左栏：色彩比例 -->
    <div class="color-palette-card">
      <h4>品牌三色 · 55/30/15</h4>
      <div class="color-bar">
        <span style="flex:5.5;background:var(--royal);">#0A2463 皇家蓝 55%</span>
        <span style="flex:3;background:var(--gold);color:var(--royal);">#F4D35E 复古金 30%</span>
        <span style="flex:1.5;background:var(--wine);">#D8315B 酒红 15%</span>
      </div>
      <div class="color-legend">
        <div class="cl-item">
          <span class="cl-dot" style="background:var(--royal)"></span>
          <div>
            <div class="cl-name">皇家蓝</div>
            <div class="cl-hex">#0A2463 · 主色</div>
          </div>
        </div>
        <div class="cl-item">
          <span class="cl-dot" style="background:var(--gold)"></span>
          <div>
            <div class="cl-name">复古金</div>
            <div class="cl-hex">#F4D35E · 强调</div>
          </div>
        </div>
        <div class="cl-item">
          <span class="cl-dot" style="background:var(--wine)"></span>
          <div>
            <div class="cl-name">酒红</div>
            <div class="cl-hex">#D8315B · 点缀</div>
          </div>
        </div>
      </div>
    </div>
    <!-- 右栏：字体样例 -->
    <div class="typography-card">
      <h4>字体系统 · 衬线+无衬线混搭</h4>
      <div class="type-row">
        <span class="type-sample-serif">Display 衬线</span>
        <span class="type-label">Playfair Display</span>
      </div>
      <div class="type-row">
        <span class="type-sample-display">Italic 斜体</span>
        <span class="type-label">Cormorant Garamond</span>
      </div>
      <div class="type-row">
        <span class="type-sample-sans">Body 正文无衬线</span>
        <span class="type-label">Inter</span>
      </div>
      <div class="type-row">
        <span class="type-sample-mono">Mono 等宽</span>
        <span class="type-label">JetBrains Mono</span>
      </div>
    </div>
  </div>
</section>
```
```css
/* Token双栏网格 */
.tokens-grid {
  margin-top: 3rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
}
/* 色彩卡片 */
.color-palette-card,
.typography-card {
  background: #fff;
  border-radius: 20px;
  border: 1px solid var(--cream-200);
  padding: 2rem;
}
.color-palette-card h4,
.typography-card h4 {
  font-family: var(--font-serif);
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 1.25rem;
  color: var(--ink);
}
/* 色彩比例条 */
.color-bar {
  display: flex;
  height: 80px;
  border-radius: 12px;
  overflow: hidden;
  margin-bottom: 1rem;
  box-shadow: 0 2px 12px rgba(10,36,99,0.08);
}
.color-bar span {
  display: flex;
  align-items: flex-end;
  padding: 0.75rem;
  font-family: var(--font-mono);
  font-size: 0.7rem;
  font-weight: 500;
  color: #fff;
}
/* 色彩图例 */
.color-legend {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 0.75rem;
}
.cl-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.78rem;
}
.cl-dot {
  width: 12px; height: 12px;
  border-radius: 4px;
  flex-shrink: 0;
}
.cl-name { font-weight: 600; color: var(--ink); }
.cl-hex { font-family: var(--font-mono); font-size: 0.7rem; color: var(--ink-300); }
/* 字体样例行 */
.type-row {
  padding: 0.75rem 0;
  border-bottom: 1px solid var(--cream-100);
  display: flex;
  justify-content: space-between;
  align-items: baseline;
}
.type-row:last-child { border-bottom: none; }
.type-sample-serif {
  font-family: var(--font-serif);
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--royal);
}
.type-sample-display {
  font-family: var(--font-display);
  font-size: 1.3rem;
  font-style: italic;
  color: var(--royal);
}
.type-sample-sans {
  font-family: var(--font-sans);
  font-size: 1rem;
  font-weight: 400;
  color: var(--ink);
}
.type-sample-mono {
  font-family: var(--font-mono);
  font-size: 0.9rem;
  color: var(--ink-100);
  background: var(--royal-50);
  padding: 0.2rem 0.5rem;
  border-radius: 4px;
}
.type-label {
  font-size: 0.72rem;
  color: var(--ink-300);
  font-family: var(--font-mono);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}
@media (max-width: 768px) {
  .tokens-grid { grid-template-columns: 1fr; }
}
```

---

## L19. 架构堆叠图（Architecture Stack Diagram）

**特征**：纵向 flex 布局，三层卡片纵向堆叠（场景层/模板层/组件层），每层不同背景色（深蓝/白底/米金渐变），层间用金色 ↓ 箭头连接，hover 时整层右移6px。

**适用**：产品架构说明、工作流展示、分层概念解释、How It Works板块。

**视觉效果**：层次分明、信息递进、箭头引导视线自上而下流动，hover 交互增加探索感。

```html
<div class="arch-diagram">
  <!-- 第一层：场景 -->
  <div class="arch-layer arch-scene">
    <div class="arch-num">N°01</div>
    <div class="arch-content">
      <div class="arch-label">Scene · 场景</div>
      <h4>决定"做什么菜"</h4>
      <p>10种场景，每种有完整的结构规范、颜色比例、阅读节奏、技术约束。AI根据你的关键词自动匹配。</p>
      <div class="arch-tags">
        <span>Portfolio</span><span>Landing</span><span>Tutorial</span><span>Deck</span>
      </div>
    </div>
  </div>
  <!-- 连接箭头 -->
  <div class="arch-arrow">↓</div>
  <!-- 第二层：模板 -->
  <div class="arch-layer arch-template">
    <div class="arch-num">N°02</div>
    <div class="arch-content">
      <div class="arch-label">Template · 模板</div>
      <h4>提供"半成品骨架"</h4>
      <p>10个生产级HTML模板，CSS变量、字体、响应式都已配好。从模板开始改，不是从零写。</p>
      <div class="arch-tags">
        <span>字体引入</span><span>CSS变量</span><span>响应式</span><span>基础布局</span>
      </div>
    </div>
  </div>
  <!-- 连接箭头 -->
  <div class="arch-arrow">↓</div>
  <!-- 第三层：组件 -->
  <div class="arch-layer arch-component">
    <div class="arch-num">N°03</div>
    <div class="arch-content">
      <div class="arch-label">Component · 组件</div>
      <h4>填充"精致零件"</h4>
      <p>200+品牌组件分19类，按钮/卡片/引用/标题/动效/签名元素。按需挑选搭配，零默认样式。</p>
      <div class="arch-tags">
        <span>按钮</span><span>卡片</span><span>引用</span><span>动画标题</span><span>花饰❦</span>
      </div>
    </div>
  </div>
</div>
```
```css
/* 架构堆叠图容器 */
.arch-diagram {
  margin: 60px 0 70px;
  display: flex;
  flex-direction: column;
  gap: 0;
}
/* 架构层基础 */
.arch-layer {
  display: flex;
  gap: 28px;
  align-items: flex-start;
  padding: 32px 36px;
  border-radius: 20px;
  position: relative;
  transition: transform 400ms var(--ease);
}
.arch-layer:hover { transform: translateX(6px); }
/* 场景层：深蓝底 */
.arch-scene {
  background: linear-gradient(135deg, var(--royal), var(--royal-700));
  color: #fff;
}
/* 模板层：白底 */
.arch-template {
  background: #fff;
  border: 1px solid var(--cream-200);
  box-shadow: 0 4px 24px rgba(10,36,99,0.06);
}
/* 组件层：米金渐变 */
.arch-component {
  background: linear-gradient(135deg, var(--royal-50), var(--gold-50));
  border: 1px solid var(--cream-200);
}
/* 层编号 */
.arch-num {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 2.4rem;
  font-weight: 600;
  color: var(--gold);
  line-height: 1;
  min-width: 70px;
  padding-top: 4px;
}
.arch-template .arch-num { color: var(--royal); }
.arch-component .arch-num { color: var(--wine); }
/* 层内容 */
.arch-content { flex: 1; }
.arch-label {
  font-family: var(--font-mono);
  font-size: 0.7rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 6px;
  opacity: 0.8;
}
.arch-template .arch-label { color: var(--royal-400); }
.arch-component .arch-label { color: var(--wine); opacity: 0.7; }
.arch-content h4 {
  font-family: var(--font-serif);
  font-size: 1.5rem;
  font-weight: 700;
  margin: 0 0 10px;
  line-height: 1.3;
}
.arch-scene h4 { color: var(--gold); }
.arch-template h4 { color: var(--ink); }
.arch-component h4 { color: var(--royal); }
.arch-content p {
  font-size: 0.95rem;
  line-height: 1.7;
  margin: 0 0 16px;
  opacity: 0.85;
}
.arch-template p { color: var(--ink-400); opacity: 1; }
.arch-component p { color: var(--ink-500); opacity: 1; }
/* 标签组 */
.arch-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.arch-tags span {
  font-size: 0.75rem;
  padding: 4px 12px;
  border-radius: 100px;
  font-weight: 500;
}
.arch-scene .arch-tags span {
  background: rgba(244,211,94,0.15);
  color: var(--gold);
  border: 1px solid rgba(244,211,94,0.25);
}
.arch-template .arch-tags span {
  background: var(--cream);
  color: var(--royal);
  border: 1px solid var(--cream-200);
}
.arch-component .arch-tags span {
  background: #fff;
  color: var(--ink-500);
  border: 1px solid var(--cream-200);
}
/* 连接箭头 */
.arch-arrow {
  text-align: center;
  font-size: 1.4rem;
  color: var(--gold);
  padding: 8px 0;
  line-height: 1;
  font-family: var(--font-display);
}
```

---

## L20. 引语+原则双栏（Quote-Plus-Principles Two Column）

**特征**：1fr 1fr 网格，左侧大引用卡片（白底圆角+大号金色引号装饰+Cormorant斜体正文+署名），右侧N°编号原则列表（纵向flex，每条N°01-04编号+衬线标题+正文，hover变米白底）。

**适用**：设计理念阐述、品牌宣言、关于页面、价值观展示。

**视觉效果**：左疏右密、左静右动，引用卡片有编辑品质感，原则列表hover交互增加触感。

```html
<section class="philosophy-section">
  <div class="philosophy-inner">
    <div class="section-label">Design Philosophy</div>
    <h2 class="section-h">设计不是装饰，<br>是<em>有立场</em>的表达</h2>
    <div class="philosophy-grid">
      <!-- 左栏：大引用卡片 -->
      <div class="philosophy-quote">
        <p>好的设计让人感到被理解，而不是被炫技。每一个间距、每一处金色装饰线的长度，都是经过反复斟酌的决定。</p>
        <cite>— Feihong Design System</cite>
      </div>
      <!-- 右栏：编号原则列表 -->
      <div class="principles-list">
        <div class="principle-item">
          <span class="principle-num">N°01</span>
          <div>
            <h4>克制即高级</h4>
            <p>拒绝花哨渐变、冷灰配色、无灵魂模板感。每个元素都要有明确的设计意图，宁缺毋滥。</p>
          </div>
        </div>
        <div class="principle-item">
          <span class="principle-num">N°02</span>
          <div>
            <h4>艺术且有品质</h4>
            <p>高对比度衬线大字、金色下划线强调、微妙径向渐变制造深度，不做纯平色。</p>
          </div>
        </div>
        <div class="principle-item">
          <span class="principle-num">N°03</span>
          <div>
            <h4>有温度、有人味</h4>
            <p>暖米白底色、手写感衬线斜体、不完美的间距节奏，像设计师亲手做的。</p>
          </div>
        </div>
        <div class="principle-item">
          <span class="principle-num">N°04</span>
          <div>
            <h4>精确到像素</h4>
            <p>间距精确到8px网格、色彩克制不滥用、层级清晰有呼吸感，Crafted with Precision。</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
```
```css
/* 双栏容器 */
.philosophy-inner {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}
.philosophy-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  margin-top: 3rem;
  align-items: start;
}
/* 左栏：大引用卡片 */
.philosophy-quote {
  position: relative;
  padding: 2.5rem;
  background: #fff;
  border-radius: 20px;
  border: 1px solid var(--cream-200);
  box-shadow: 0 4px 24px rgba(10,36,99,0.05);
}
.philosophy-quote::before {
  content: '"';
  position: absolute;
  top: 0.5rem; left: 1.5rem;
  font-family: var(--font-serif);
  font-size: 5rem;
  font-weight: 700;
  color: var(--gold);
  line-height: 1;
  opacity: 0.5;
}
.philosophy-quote p {
  font-family: var(--font-display);
  font-size: 1.35rem;
  font-style: italic;
  font-weight: 400;
  line-height: 1.6;
  color: var(--royal);
  margin-bottom: 1rem;
  padding-top: 1.5rem;
}
.philosophy-quote cite {
  font-size: 0.8rem;
  font-style: normal;
  color: var(--ink-300);
  letter-spacing: 0.1em;
  text-transform: uppercase;
}
/* 右栏：原则列表 */
.principles-list {
  display: flex;
  flex-direction: column;
  gap: 0;
}
.principle-item {
  display: flex;
  gap: 1.25rem;
  padding: 1.5rem;
  border-radius: 16px;
  transition: all 250ms var(--ease);
  border: 1px solid transparent;
}
.principle-item:hover {
  background: var(--cream);
  border-color: var(--cream-200);
}
.principle-num {
  font-family: var(--font-display);
  font-size: 1.1rem;
  font-style: italic;
  font-weight: 400;
  color: var(--gold-700);
  line-height: 1.2;
  flex-shrink: 0;
  width: 50px;
  letter-spacing: 0.05em;
  padding-top: 0.15rem;
}
.principle-item h4 {
  font-family: var(--font-serif);
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--ink);
  margin-bottom: 0.35rem;
}
.principle-item p {
  font-size: 0.875rem;
  color: var(--ink-200);
  line-height: 1.65;
}
@media (max-width: 768px) {
  .philosophy-grid { grid-template-columns: 1fr; gap: 2rem; }
}
```

---

## L21. 连线步骤时间线（Connected Step Timeline）

**特征**：两行4列grid布局，三色渐变连接线（royal→gold→wine→royal），64px圆形金边编号（hover变金底蓝字放大），深色背景适配。

**适用**：工作流程、方法论展示、服务流程、产品使用步骤。

**视觉效果**：仪式感、精工品质、品牌基因三色贯穿。

```html
<section class="section-dark" style="padding:5rem 2.5rem;">
  <div class="section-inner" style="max-width:1100px;margin:0 auto;">
    <div class="section-label">◆ 八步精工流程</div>
    <h2 class="section-title">从一张白纸到<br><em>可交付的品牌页面</em></h2>
    <div class="workflow-steps">
      <div class="wf-step"><div class="wf-step-num"><em>N°01</em></div><h5>需求解读</h5><p>理解你的品牌、受众和目标</p></div>
      <div class="wf-step"><div class="wf-step-num"><em>N°02</em></div><h5>品牌定位</h5><p>提炼核心差异化与视觉方向</p></div>
      <div class="wf-step"><div class="wf-step-num"><em>N°03</em></div><h5>色彩体系</h5><p>构建三色基因与比例分配</p></div>
      <div class="wf-step"><div class="wf-step-num"><em>N°04</em></div><h5>字体选型</h5><p>衬线+display+无衬线组合</p></div>
      <div class="wf-step wf-step-row2"><div class="wf-step-num"><em>N°05</em></div><h5>布局编排</h5><p>非对称网格与编辑级排版</p></div>
      <div class="wf-step wf-step-row2"><div class="wf-step-num"><em>N°06</em></div><h5>组件填充</h5><p>从组件库选取匹配元素</p></div>
      <div class="wf-step wf-step-row2"><div class="wf-step-num"><em>N°07</em></div><h5>动效注入</h5><p>Feihong缓动与微动效</p></div>
      <div class="wf-step wf-step-row2"><div class="wf-step-num"><em>N°08</em></div><h5>质量校验</h5><p>P0/P1/P2三级门槛检查</p></div>
    </div>
  </div>
</section>
```
```css
.workflow-steps {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 0;
  position: relative;
  margin-top: 3rem;
}
.workflow-steps::before {
  content: '';
  position: absolute;
  top: 28px; left: 6%; right: 6%;
  height: 1px;
  background: linear-gradient(90deg, var(--royal-200), var(--gold), var(--wine), var(--royal-200));
  opacity: 0.4;
}
.wf-step {
  text-align: center;
  padding: 1rem 0.75rem;
  position: relative;
}
.wf-step-num {
  width: 64px; height: 64px;
  border-radius: 50%;
  background: var(--ink);
  color: var(--gold);
  font-family: var(--font-display);
  font-style: italic;
  font-size: 0.85rem;
  display: flex; align-items: center; justify-content: center;
  margin: 0 auto 1rem;
  position: relative; z-index: 1;
  border: 1.5px solid var(--gold);
  box-shadow: 0 0 0 4px var(--ink);
  transition: all 300ms var(--ease);
  letter-spacing: 0.03em;
}
.wf-step:hover .wf-step-num {
  background: var(--gold);
  color: var(--royal);
  transform: scale(1.1);
}
.wf-step h5 {
  font-family: var(--font-serif);
  font-size: 0.95rem;
  font-weight: 600;
  color: #fff;
  margin-bottom: 0.3rem;
}
.wf-step p {
  font-size: 0.75rem;
  color: rgba(255,255,255,0.5);
  line-height: 1.5;
}
.wf-step-row2 { margin-top: 2rem; }
@media (max-width: 768px) {
  .workflow-steps { grid-template-columns: repeat(2, 1fr); }
  .workflow-steps::before { display: none; }
}
```

---

## L22. 品牌色彩比例条（Color Proportion Bar）

**特征**：flex比例分配的多色横条（55%皇家蓝 / 30%复古金 / 15%酒红），80px高圆角12px，内嵌hex色值文字，配合3列图例展示。

**适用**：设计系统展示、品牌规范页、色彩规则说明。

**视觉效果**：直观展示品牌色彩占比，科学感与专业感。

```html
<div class="color-palette">
  <h4>品牌三色 · Brand Palette</h4>
  <div class="color-bar">
    <span>#0A2463</span>
    <span>#F4D35E</span>
    <span>#D8315B</span>
  </div>
  <div class="color-legend">
    <div class="cl-item"><div class="cl-dot" style="background:var(--royal);"></div><div><div class="cl-name">皇家蓝</div><div class="cl-hex">#0A2463 · 55%</div></div></div>
    <div class="cl-item"><div class="cl-dot" style="background:var(--gold);"></div><div><div class="cl-name">复古金</div><div class="cl-hex">#F4D35E · 30%</div></div></div>
    <div class="cl-item"><div class="cl-dot" style="background:var(--wine);"></div><div><div class="cl-name">酒红</div><div class="cl-hex">#D8315B · 15%</div></div></div>
  </div>
</div>
```
```css
.color-palette {
  background: #fff;
  border-radius: 20px;
  border: 1px solid var(--cream-200);
  padding: 2rem;
}
.color-palette h4 {
  font-family: var(--font-serif);
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 1.25rem;
  color: var(--ink);
}
.color-bar {
  display: flex;
  height: 80px;
  border-radius: 12px;
  overflow: hidden;
  margin-bottom: 1rem;
  box-shadow: 0 2px 12px rgba(10,36,99,0.08);
}
.color-bar span {
  display: flex;
  align-items: flex-end;
  padding: 0.75rem;
  font-family: var(--font-mono);
  font-size: 0.7rem;
  font-weight: 500;
  color: #fff;
}
.color-bar span:nth-child(1) { flex: 5.5; background: var(--royal); }
.color-bar span:nth-child(2) { flex: 3; background: var(--gold); color: var(--royal); }
.color-bar span:nth-child(3) { flex: 1.5; background: var(--wine); }
.color-legend {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 0.75rem;
}
.cl-item { display: flex; align-items: center; gap: 0.5rem; font-size: 0.78rem; }
.cl-dot { width: 12px; height: 12px; border-radius: 4px; flex-shrink: 0; }
.cl-name { font-weight: 600; color: var(--ink); }
.cl-hex { font-family: var(--font-mono); font-size: 0.7rem; color: var(--ink-300); }
```

---

## L23. 字体样例行展示（Typography Specimen Row）

**特征**：左右对齐flex布局，左侧字体样例（衬线/Display斜体/无衬线/等宽四种风格），右侧mono标签说明。

**适用**：设计系统展示、字体规范页、品牌视觉介绍。

**视觉效果**：编辑级字体展示，专业感与美感并存。

```html
<div class="typography-showcase">
  <h4>字体体系 · Type System</h4>
  <div class="type-row"><span class="type-sample-serif">Feihong Design</span><span class="type-label">Serif · 标题</span></div>
  <div class="type-row"><span class="type-sample-display">Timeless Vision</span><span class="type-label">Display Italic · 装饰</span></div>
  <div class="type-row"><span class="type-sample-sans">正文与说明文字</span><span class="type-label">Sans · 正文</span></div>
  <div class="type-row"><span class="type-sample-mono">font-mono</span><span class="type-label">Mono · 代码</span></div>
</div>
```
```css
.typography-showcase {
  background: #fff;
  border-radius: 20px;
  border: 1px solid var(--cream-200);
  padding: 2rem;
}
.typography-showcase h4 {
  font-family: var(--font-serif);
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 1.25rem;
  color: var(--ink);
}
.type-row {
  padding: 0.75rem 0;
  border-bottom: 1px solid var(--cream-100);
  display: flex;
  justify-content: space-between;
  align-items: baseline;
}
.type-row:last-child { border-bottom: none; }
.type-sample-serif { font-family: var(--font-serif); font-size: 1.3rem; font-weight: 700; color: var(--royal); }
.type-sample-display { font-family: var(--font-display); font-size: 1.3rem; font-style: italic; color: var(--royal); }
.type-sample-sans { font-family: var(--font-sans); font-size: 1rem; font-weight: 400; color: var(--ink); }
.type-sample-mono { font-family: var(--font-mono); font-size: 0.9rem; color: var(--ink-100); background: var(--royal-50); padding: 0.2rem 0.5rem; border-radius: 4px; }
.type-label { font-size: 0.72rem; color: var(--ink-300); font-family: var(--font-mono); text-transform: uppercase; letter-spacing: 0.05em; flex-shrink: 0; }
```
