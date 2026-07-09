# Feihong Design System — Luxe Art Components
# N°13 · 高奢艺术组件
> 25 high-luxury artistic components: art dividers, luxury badges, marquees, galleries, stamps, ribbons, and editorial ornaments.
> 25种高奢艺术组件：艺术分隔线、奢华徽章、跑马灯、画廊、邮票、丝带、展览标签等。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 44. 高奢艺术组件 Luxe Art Components（25种新组件/变体）

> 以下组件专为高奢/艺术/时尚/个人品牌场景设计。统一使用品牌三色变量（皇家蓝、复古金、酒红），
> 内置微妙的 hover 与入场动画，风格统一、形态各异。每个组件均可独立复制使用。

---

### 44.1 Art Divider 艺术分隔线

五种奢华分隔样式：金线+菱形、双金夹花饰、虚线+圆点、手画波浪线、Art Deco 几何分隔。

```html
<!-- 1. 金线+菱形 -->
<div class="art-divider">
  <div class="ad-line"></div>
  <div class="ad-diamond"></div>
  <div class="ad-line"></div>
</div>

<!-- 2. 双金夹花饰 -->
<div class="art-divider double-gold">
  <div class="ad-line"></div>
  <span class="ad-ornament">&#10086;</span>
  <div class="ad-line"></div>
</div>

<!-- 3. 虚线+圆点 -->
<div class="art-divider dotted">
  <span class="ad-dot"></span>
  <span class="ad-dot large"></span>
  <span class="ad-dot"></span>
  <span class="ad-dot large"></span>
  <span class="ad-dot"></span>
</div>

<!-- 4. 手画波浪线 -->
<div class="art-divider wave">
  <svg viewBox="0 0 320 28" preserveAspectRatio="none">
    <path d="M0,14 Q20,2 40,14 T80,14 T120,14 T160,14 T200,14 T240,14 T280,14 T320,14" />
  </svg>
</div>

<!-- 5. Art Deco 几何分隔 -->
<div class="art-divider deco">
  <div class="deco-bar"></div>
  <div class="deco-sun"></div>
  <div class="deco-bar"></div>
</div>
```
```css
.art-divider { display:flex; align-items:center; justify-content:center; gap:1rem; margin:2rem 0; color:var(--gold); }
.art-divider .ad-line { flex:1; height:1px; max-width:120px; background:linear-gradient(90deg,transparent,var(--gold-600),transparent); }
.art-divider .ad-diamond { width:10px; height:10px; background:var(--gold); transform:rotate(45deg); box-shadow:0 0 0 2px var(--gold-50),0 2px 8px rgba(244,211,94,0.4); }
.art-divider.double-gold .ad-line { height:3px; max-width:140px; background:linear-gradient(90deg,transparent,var(--gold) 20%,var(--gold-600) 50%,var(--gold) 80%,transparent); position:relative; }
.art-divider.double-gold .ad-line::before, .art-divider.double-gold .ad-line::after { content:''; position:absolute; left:0; right:0; height:1px; background:var(--gold-300); }
.art-divider.double-gold .ad-line::before { top:-3px; } .art-divider.double-gold .ad-line::after { bottom:-3px; }
.art-divider.double-gold .ad-ornament { font-family:var(--font-display); font-size:1.4rem; color:var(--gold-700); }
.art-divider.dotted .ad-dot { width:5px; height:5px; border-radius:50%; background:var(--gold-600); margin:0 6px; }
.art-divider.dotted .ad-dot.large { width:8px; height:8px; background:var(--gold); box-shadow:0 0 6px rgba(244,211,94,0.5); }
.art-divider.wave svg { width:100%; max-width:320px; height:28px; }
.art-divider.wave path { stroke:var(--gold-600); stroke-width:1.5; fill:none; stroke-linecap:round; }
.art-divider.deco .deco-sun { width:28px; height:28px; position:relative; }
.art-divider.deco .deco-sun::before { content:''; position:absolute; top:50%; left:50%; width:10px; height:10px; border-radius:50%; background:var(--gold); transform:translate(-50%,-50%); }
.art-divider.deco .deco-sun::after { content:''; position:absolute; inset:0; background:linear-gradient(var(--gold-500),var(--gold-500)) center/100% 1.5px no-repeat,linear-gradient(90deg,var(--gold-500),var(--gold-500)) center/1.5px 100% no-repeat,linear-gradient(45deg,var(--gold-500),var(--gold-500)) center/70% 1.5px no-repeat,linear-gradient(-45deg,var(--gold-500),var(--gold-500)) center/70% 1.5px no-repeat; }
.art-divider.deco .deco-bar { flex:1; max-width:100px; height:2px; background:var(--gold); position:relative; }
.art-divider.deco .deco-bar::before, .art-divider.deco .deco-bar::after { content:''; position:absolute; top:50%; width:8px; height:8px; border:2px solid var(--gold); transform:translateY(-50%) rotate(45deg); background:var(--cream); }
.art-divider.deco .deco-bar::before { left:-4px; } .art-divider.deco .deco-bar::after { right:-4px; }
```

---

### 44.2 Luxury Badge 高奢徽章

金边徽章、火漆圆形徽章、编号限量徽章、蜡封圆形标签四种变体。

```html
<span class="luxe-badge gold-border">Exclusive</span>

<div class="luxe-badge wax">
  <span class="wax-init">F</span>
  <span>Seal</span>
</div>

<span class="luxe-badge limited">Edition <span class="ltd-num">N° 007</span> / 100</span>

<div class="luxe-badge seal">
  <span>Est.</span>
  <span class="seal-year">MMXXV</span>
</div>
```
```css
.luxe-badge { display:inline-flex; align-items:center; gap:6px; padding:6px 14px; font-family:var(--font-display); font-size:0.85rem; font-weight:500; letter-spacing:0.08em; text-transform:uppercase; border-radius:2px; transition:all 250ms var(--ease); }
.luxe-badge.gold-border { color:var(--gold-800); border:1px solid var(--gold); background:linear-gradient(135deg,var(--gold-50),#fff); }
.luxe-badge.gold-border::before,.luxe-badge.gold-border::after { content:'❋'; font-size:0.6rem; color:var(--gold-600); }
.luxe-badge.wax { background:var(--wine); color:#fff; border-radius:50%; width:64px; height:64px; padding:0; flex-direction:column; justify-content:center; font-family:var(--font-serif); font-size:0.65rem; font-weight:700; box-shadow:inset -3px -3px 8px rgba(0,0,0,0.3),inset 2px 2px 6px rgba(255,255,255,0.15),0 4px 12px rgba(216,49,91,0.4); }
.luxe-badge.wax .wax-init { font-family:var(--font-display); font-size:1.3rem; font-style:italic; }
.luxe-badge.wax:hover { transform:scale(1.06) rotate(-3deg); }
.luxe-badge.limited { background:var(--ink); color:var(--gold); border:1px solid var(--gold-700); padding:8px 18px; font-family:var(--font-mono); font-size:0.7rem; letter-spacing:0.15em; }
.luxe-badge.limited .ltd-num { font-family:var(--font-display); font-size:1rem; font-style:italic; color:#fff; margin:0 2px; }
.luxe-badge.seal { background:linear-gradient(135deg,var(--royal-700),var(--royal)); color:var(--gold); width:72px; height:72px; border-radius:50%; flex-direction:column; justify-content:center; font-size:0.6rem; border:2px double var(--gold); box-shadow:0 4px 16px rgba(10,36,99,0.3); }
.luxe-badge.seal .seal-year { font-family:var(--font-display); font-size:0.9rem; font-style:italic; color:#fff; margin-top:2px; }
```

---

### 44.3 Editorial Quote 杂志风金句

时尚杂志风格：Cormorant Garamond 大引号 + 衬线斜体大字 + 金色作者署名线。

```html
<div class="editorial-quote">
  <span class="eq-open">&ldquo;</span>
  <blockquote>好的设计是让人感到被尊重的，<br>它安静地存在，却让一切变得更美好。</blockquote>
  <span class="eq-close">&rdquo;</span>
  <div class="eq-author">
    <span class="eq-author-line"></span>
    <span class="eq-author-text">Feihong · Designer</span>
    <span class="eq-author-line"></span>
  </div>
</div>
```
```css
.editorial-quote { position:relative; padding:3rem 2.5rem; max-width:720px; margin:0 auto; }
.editorial-quote .eq-open,.editorial-quote .eq-close { font-family:var(--font-display); font-size:6rem; font-style:italic; font-weight:300; color:var(--gold); line-height:0.7; position:absolute; }
.editorial-quote .eq-open { top:1rem; left:0; } .editorial-quote .eq-close { bottom:0.5rem; right:0; }
.editorial-quote blockquote { font-family:var(--font-serif); font-size:clamp(1.4rem,2.8vw,2rem); font-weight:500; line-height:1.45; color:var(--ink); text-align:center; font-style:italic; position:relative; z-index:1; }
.editorial-quote .eq-author { margin-top:1.5rem; display:flex; align-items:center; justify-content:center; gap:0.75rem; }
.editorial-quote .eq-author-line { width:40px; height:1px; background:var(--gold); }
.editorial-quote .eq-author-text { font-family:var(--font-sans); font-size:0.8rem; font-weight:500; letter-spacing:0.18em; text-transform:uppercase; color:var(--ink-300); }
```

---

### 44.4 Marquee 滚动跑马灯

皇家蓝底 + 金色 Cormorant 斜体文字 + 酒红圆点分隔的无缝滚动。

```html
<div class="luxe-marquee">
  <div class="luxe-marquee-track">
    <!-- 内容重复两遍实现无缝滚动 -->
    <span class="luxe-marquee-item">Atelier Feihong <span class="mq-dot"></span></span>
    <span class="luxe-marquee-item">Est. MMXXV <span class="mq-dot"></span></span>
    <span class="luxe-marquee-item">Crafted with Care <span class="mq-dot"></span></span>
    <span class="luxe-marquee-item">Limited Edition <span class="mq-dot"></span></span>
    <span class="luxe-marquee-item">Atelier Feihong <span class="mq-dot"></span></span>
    <span class="luxe-marquee-item">Est. MMXXV <span class="mq-dot"></span></span>
    <span class="luxe-marquee-item">Crafted with Care <span class="mq-dot"></span></span>
    <span class="luxe-marquee-item">Limited Edition <span class="mq-dot"></span></span>
  </div>
</div>
```
```css
@keyframes luxeMarquee { from{transform:translateX(0);} to{transform:translateX(-50%);} }
.luxe-marquee { overflow:hidden; background:var(--royal); padding:1rem 0; position:relative; border-top:1px solid var(--gold-700); border-bottom:1px solid var(--gold-700); }
.luxe-marquee::before,.luxe-marquee::after { content:''; position:absolute; top:0; bottom:0; width:80px; z-index:2; pointer-events:none; }
.luxe-marquee::before { left:0; background:linear-gradient(90deg,var(--royal),transparent); }
.luxe-marquee::after { right:0; background:linear-gradient(-90deg,var(--royal),transparent); }
.luxe-marquee-track { display:flex; width:max-content; animation:luxeMarquee 30s linear infinite; }
.luxe-marquee-item { font-family:var(--font-display); font-size:1.5rem; font-style:italic; color:var(--gold); white-space:nowrap; padding:0 1.5rem; display:flex; align-items:center; gap:1.5rem; }
.luxe-marquee-item .mq-dot { width:6px; height:6px; border-radius:50%; background:var(--wine); }
```

---

### 44.5 Asymmetric Gallery 非对称画廊

12 列 grid 错落布局，6 张大小不一的色块占位，配金色三角角贴，hover 浮起显示标题。

```html
<div class="asym-gallery">
  <div class="ag-item">
    <div class="ag-corner tl"></div><div class="ag-corner br"></div>
    <div class="ag-ph">I</div>
    <div class="ag-caption">Portrait No.1</div>
  </div>
  <div class="ag-item">
    <div class="ag-corner tr"></div>
    <div class="ag-ph">II</div>
    <div class="ag-caption">Still Life</div>
  </div>
  <!-- ... 共 6 个 .ag-item ... -->
</div>
```
```css
.asym-gallery { display:grid; grid-template-columns:repeat(12,1fr); grid-auto-rows:70px; gap:12px; max-width:900px; margin:0 auto; }
.ag-item { position:relative; overflow:hidden; border-radius:4px; background:linear-gradient(135deg,var(--cream-100),var(--cream-200)); transition:all 400ms var(--ease); cursor:pointer; }
.ag-item:hover { transform:translateY(-4px) scale(1.01); box-shadow:var(--shadow-lg); z-index:2; }
.ag-item:nth-child(1){grid-column:span 5;grid-row:span 4;background:linear-gradient(135deg,var(--royal-100),var(--royal-200));}
.ag-item:nth-child(2){grid-column:span 4;grid-row:span 3;background:linear-gradient(135deg,var(--gold-100),var(--gold-200));}
.ag-item:nth-child(3){grid-column:span 3;grid-row:span 3;background:linear-gradient(135deg,var(--wine-100),var(--wine-200));}
.ag-item:nth-child(4){grid-column:span 4;grid-row:span 3;background:linear-gradient(135deg,var(--royal-50),var(--gold-100));}
.ag-item:nth-child(5){grid-column:span 3;grid-row:span 4;background:linear-gradient(135deg,var(--cream-100),var(--royal-100));}
.ag-item:nth-child(6){grid-column:span 5;grid-row:span 2;background:linear-gradient(135deg,var(--gold-50),var(--wine-50));}
.ag-corner { position:absolute; width:24px; height:24px; background:var(--gold); z-index:3; box-shadow:0 2px 6px rgba(0,0,0,0.15); }
.ag-corner.tl{top:6px;left:6px;clip-path:polygon(0 0,100% 0,0 100%);}
.ag-corner.tr{top:6px;right:6px;clip-path:polygon(100% 0,100% 100%,0 0);}
.ag-corner.bl{bottom:6px;left:6px;clip-path:polygon(0 0,0 100%,100% 100%);}
.ag-corner.br{bottom:6px;right:6px;clip-path:polygon(100% 100%,0 100%,100% 0);}
.ag-item .ag-caption { position:absolute; bottom:0; left:0; right:0; padding:0.5rem 0.75rem; background:linear-gradient(transparent,rgba(13,18,37,0.75)); color:#fff; font-size:0.7rem; letter-spacing:0.1em; text-transform:uppercase; opacity:0; transition:opacity 250ms; }
.ag-item:hover .ag-caption { opacity:1; }
```

---

### 44.6 Number Counter 艺术数字

Cormorant Garamond 超大金色斜体数字 + 金色渐变文字 + 左侧金色竖线。

```html
<div class="art-number-group">
  <div class="art-number">
    <span class="an-num">12</span>
    <span class="an-label">Years of Craft</span>
  </div>
  <div class="art-number"><span class="an-num">248</span><span class="an-label">Projects</span></div>
  <div class="art-number"><span class="an-num">97%</span><span class="an-label">Satisfaction</span></div>
  <div class="art-number"><span class="an-num">∞</span><span class="an-label">Possibilities</span></div>
</div>
```
```css
.art-number { display:inline-flex; flex-direction:column; align-items:flex-start; position:relative; padding-left:1.25rem; }
.art-number::before { content:''; position:absolute; left:0; top:0.3em; bottom:0.3em; width:2px; background:linear-gradient(180deg,var(--gold),transparent); }
.art-number .an-num { font-family:var(--font-display); font-size:clamp(3rem,6vw,5rem); font-weight:300; font-style:italic; line-height:1; background:linear-gradient(180deg,var(--gold-400),var(--gold-600) 60%,var(--gold-800)); -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent; }
.art-number .an-label { font-family:var(--font-sans); font-size:0.8rem; font-weight:500; letter-spacing:0.12em; text-transform:uppercase; color:var(--ink-200); margin-top:0.5rem; }
.art-number-group { display:grid; grid-template-columns:repeat(auto-fit,minmax(160px,1fr)); gap:2rem; }
```

---

### 44.7 Signature Block 签名区

手写签名（斜体）+ 花饰分隔线 + 酒红日期印章 + 右上角圆形印章。

```html
<div class="signature-block">
  <div class="sig-stamp">Original<br>2025</div>
  <div class="sig-name">Feihong</div>
  <div class="sig-ornament">
    <span class="sig-line"></span><span>&#10086;</span><span class="sig-line"></span>
  </div>
  <span class="sig-date">2025 · 07 · 08</span>
</div>
```
```css
.signature-block { display:inline-flex; flex-direction:column; align-items:center; gap:0.5rem; padding:1.5rem; position:relative; }
.signature-block .sig-name { font-family:var(--font-display); font-size:2.2rem; font-style:italic; color:var(--ink); transform:rotate(-2deg); }
.signature-block .sig-ornament { display:flex; align-items:center; gap:8px; color:var(--gold-600); font-size:0.9rem; }
.signature-block .sig-ornament .sig-line { width:40px; height:1px; background:var(--gold-400); }
.signature-block .sig-date { font-family:var(--font-mono); font-size:0.7rem; color:var(--wine); letter-spacing:0.1em; padding:3px 10px; border:1px solid var(--wine); border-radius:2px; transform:rotate(-1deg); }
.signature-block .sig-stamp { position:absolute; top:0.5rem; right:0; width:56px; height:56px; border:2px solid var(--wine); border-radius:50%; display:flex; align-items:center; justify-content:center; font-family:var(--font-serif); font-size:0.55rem; font-weight:700; color:var(--wine); text-transform:uppercase; text-align:center; transform:rotate(12deg); opacity:0.75; }
```

---

### 44.8 Sticker Tag 贴纸标签

倾斜贴纸 + 顶部胶带伪元素 + 多层阴影，hover 回正放大。

```html
<span class="sticker-tag">New Arrival</span>
<span class="sticker-tag wine">Sold Out</span>
<span class="sticker-tag royal">Bestseller</span>
<span class="sticker-tag cream">Handmade with Love</span>
```
```css
.sticker-tag { display:inline-flex; align-items:center; padding:8px 18px; font-family:var(--font-sans); font-size:0.85rem; font-weight:600; background:var(--gold); color:var(--royal); border-radius:3px; box-shadow:2px 3px 8px rgba(0,0,0,0.15); transform:rotate(-3deg); position:relative; transition:transform 250ms var(--ease); }
.sticker-tag:hover { transform:rotate(0deg) scale(1.05); }
.sticker-tag::before { content:''; position:absolute; top:-8px; left:50%; transform:translateX(-50%) rotate(-4deg); width:48px; height:14px; background:rgba(255,240,200,0.7); border:1px dashed rgba(0,0,0,0.08); box-shadow:0 1px 2px rgba(0,0,0,0.08); }
.sticker-tag.wine{background:var(--wine);color:#fff;}
.sticker-tag.royal{background:var(--royal);color:var(--gold);}
.sticker-tag.cream{background:var(--cream-100);color:var(--ink);border:1px dashed var(--ink-300);box-shadow:2px 3px 8px rgba(10,36,99,0.08);}
```

---

### 44.9 Accordion 奢华手风琴

花饰前缀（❋）+ 金色圆形 + 号按钮，展开时 + 号旋转 45° 变 ×，面板平滑展开。

```html
<div class="luxe-accordion">
  <div class="luxe-acc-item open">
    <button class="luxe-acc-trigger" onclick="this.parentElement.classList.toggle('open')">
      <span class="acc-fleur">&#10086;</span>
      <span class="acc-title">关于飞鸿设计系统的理念</span>
      <span class="acc-plus">+</span>
    </button>
    <div class="luxe-acc-panel"><div class="luxe-acc-panel-inner">内容……</div></div>
  </div>
  <!-- 更多 .luxe-acc-item -->
</div>
```
```css
.luxe-acc-item { border-bottom:1px solid var(--cream-200); }
.luxe-acc-item:first-child { border-top:1px solid var(--cream-200); }
.luxe-acc-trigger { display:flex; align-items:center; gap:0.75rem; width:100%; padding:1rem 0; background:transparent; border:none; cursor:pointer; text-align:left; font-family:var(--font-serif); font-size:1.05rem; font-weight:600; color:var(--ink); }
.luxe-acc-trigger:hover { color:var(--royal); }
.luxe-acc-trigger .acc-fleur { font-family:var(--font-display); font-size:1rem; color:var(--gold-600); transition:transform 250ms; }
.luxe-acc-trigger .acc-plus { width:24px; height:24px; border:1px solid var(--gold); border-radius:50%; display:flex; align-items:center; justify-content:center; font-family:var(--font-display); font-size:1rem; color:var(--gold-700); transition:all 250ms; }
.luxe-acc-item.open .acc-plus { background:var(--gold); color:var(--royal); transform:rotate(45deg); }
.luxe-acc-item.open .acc-fleur { transform:rotate(15deg); color:var(--wine); }
.luxe-acc-panel { max-height:0; overflow:hidden; transition:max-height 400ms var(--ease); }
.luxe-acc-panel-inner { padding:0 0 1rem 1.75rem; font-size:0.9375rem; line-height:1.75; color:var(--ink-200); }
.luxe-acc-item.open .luxe-acc-panel { max-height:300px; }
```

---

### 44.10 Art Deco Frame 装饰艺术边框

双层金边（实线+虚线）+ 四角 SVG 几何角花，1920 年代装饰艺术风格邀请框。

```html
<div class="deco-frame">
  <div class="deco-corner tl"><svg viewBox="0 0 32 32"><path d="M0 0 L32 0 L32 2 L2 2 L2 32 L0 32 Z" fill="#DDB52E"/><path d="M6 6 L20 6 L20 8 L8 8 L8 20 L6 20 Z" fill="#DDB52E"/><circle cx="6" cy="6" r="2" fill="#F4D35E"/></svg></div>
  <div class="deco-corner tr"><!-- 同上 SVG + scaleX(-1) --></div>
  <div class="deco-corner bl"><!-- 同上 SVG + scaleY(-1) --></div>
  <div class="deco-corner br"><!-- 同上 SVG + scale(-1,-1) --></div>
  <div class="deco-frame-content">
    <h3>Invitation</h3>
    <p>诚邀您出席<br>飞鸿设计作品私享会<br>MMXXV · 秋</p>
  </div>
</div>
```
```css
.deco-frame { position:relative; padding:2rem; background:var(--cream); max-width:500px; margin:0 auto; }
.deco-frame::before { content:''; position:absolute; top:8px; left:8px; right:8px; bottom:8px; border:1px solid var(--gold); }
.deco-frame::after { content:''; position:absolute; top:14px; left:14px; right:14px; bottom:14px; border:1px dashed var(--gold); opacity:0.5; }
.deco-corner { position:absolute; width:32px; height:32px; z-index:2; }
.deco-corner.tl{top:0;left:0;} .deco-corner.tr{top:0;right:0;transform:scaleX(-1);} .deco-corner.bl{bottom:0;left:0;transform:scaleY(-1);} .deco-corner.br{bottom:0;right:0;transform:scale(-1,-1);}
.deco-frame-content { position:relative; z-index:1; text-align:center; }
.deco-frame-content h3 { font-family:var(--font-display); font-size:2rem; font-weight:500; color:var(--royal); letter-spacing:0.15em; text-transform:uppercase; margin-bottom:0.75rem; }
.deco-frame-content p { font-family:var(--font-serif); font-size:0.95rem; font-style:italic; color:var(--ink-200); line-height:1.7; }
```

---

### 44.11 Vintage Stamp 复古邮票

CSS mask 实现齿孔边缘、内部图案区 + 邮戳伪元素（斜盖在右侧）。

```html
<div class="vintage-stamp">
  <div class="stamp-postmark">POSTED<br>JUL 2025</div>
  <div class="stamp-art">F</div>
  <div class="stamp-title">Feihong Atelier</div>
  <div class="stamp-value">1<small>st</small> Class</div>
</div>
```
```css
.vintage-stamp { display:inline-flex; flex-direction:column; width:180px; padding:14px; background:var(--cream-100); position:relative; -webkit-mask:radial-gradient(circle at 10px 10px,transparent 5px,#000 5.5px) -10px -10px; mask:radial-gradient(circle at 10px 10px,transparent 5px,#000 5.5px) -10px -10px; -webkit-mask-size:20px 20px; mask-size:20px 20px; box-shadow:0 4px 14px rgba(0,0,0,0.12); transition:transform 250ms; }
.vintage-stamp:hover { transform:rotate(-2deg) translateY(-3px); }
.vintage-stamp .stamp-art { height:120px; background:linear-gradient(135deg,var(--royal),var(--royal-700)); display:flex; align-items:center; justify-content:center; font-family:var(--font-display); font-size:2.5rem; font-style:italic; color:var(--gold); border:1px solid var(--gold-400); margin-bottom:8px; }
.vintage-stamp .stamp-title { font-family:var(--font-serif); font-size:0.7rem; font-weight:600; color:var(--ink); text-align:center; letter-spacing:0.05em; text-transform:uppercase; }
.vintage-stamp .stamp-value { font-family:var(--font-display); font-size:1.1rem; font-style:italic; color:var(--royal); text-align:center; margin-top:2px; }
.vintage-stamp .stamp-postmark { position:absolute; top:20px; right:-10px; width:72px; height:72px; border:2px solid var(--wine); border-radius:50%; color:var(--wine); font-family:var(--font-mono); font-size:0.5rem; font-weight:700; text-transform:uppercase; display:flex; align-items:center; justify-content:center; text-align:center; transform:rotate(-18deg); opacity:0.6; z-index:3; }
```

---

### 44.12 Magazine Headline 杂志标题

酒红 mono eyebrow + 衬线大字 + Cormorant 斜体 + 金词 + 侧边旋转小字 + 金色署名线。

```html
<div class="mag-headline">
  <span class="mh-eyebrow">Feature Story · 专题</span>
  <span class="mh-rotated">Issue N°07 — Summer</span>
  <h2>The Art of<br><em>Quiet</em> <span class="mh-gold">Luxury</span></h2>
  <p class="mh-dek">探索当代设计中"静奢"美学的回归……</p>
  <div class="mh-byline">文字 / 飞鸿 · 摄影 / 佚名</div>
</div>
```
```css
.mag-headline { position:relative; max-width:700px; }
.mag-headline .mh-eyebrow { font-family:var(--font-mono); font-size:0.7rem; font-weight:500; letter-spacing:0.3em; text-transform:uppercase; color:var(--wine); margin-bottom:0.75rem; display:inline-block; padding-bottom:4px; border-bottom:1px solid var(--wine); }
.mag-headline h2 { font-family:var(--font-serif); font-size:clamp(2.5rem,5.5vw,4.5rem); font-weight:700; line-height:1; color:var(--ink); letter-spacing:-0.02em; }
.mag-headline h2 em { font-family:var(--font-display); font-style:italic; font-weight:300; color:var(--royal); }
.mag-headline h2 .mh-gold { color:var(--gold-700); }
.mag-headline .mh-dek { font-size:1rem; line-height:1.7; color:var(--ink-200); max-width:480px; margin-top:1rem; }
.mag-headline .mh-rotated { position:absolute; right:-60px; top:30%; font-family:var(--font-mono); font-size:0.65rem; letter-spacing:0.3em; text-transform:uppercase; color:var(--gold-700); transform:rotate(90deg); transform-origin:left top; white-space:nowrap; }
.mag-headline .mh-byline { margin-top:1.5rem; display:flex; align-items:center; gap:0.75rem; font-family:var(--font-display); font-style:italic; font-size:0.95rem; color:var(--ink-300); }
.mag-headline .mh-byline::before { content:''; width:30px; height:1px; background:var(--gold); }
```

---

### 44.13 Ornamental Initial 装饰首字母

中世纪手抄本花式首字下沉（float 实现），含 `.illuminated` 泥金装饰变体（蓝底金字+金色偏移阴影）。

```html
<p class="ornamental-initial">
  <span class="oi-letter">I</span>n the beginning, there was the word...
</p>
<p class="ornamental-initial illuminated">
  <span class="oi-letter">A</span>rt is not what you see but what you make others see...
</p>
```
```css
.ornamental-initial { font-size:1rem; line-height:1.8; color:var(--ink-100); max-width:560px; }
.ornamental-initial .oi-letter { float:left; font-family:var(--font-display); font-size:4.5rem; font-weight:400; font-style:italic; line-height:0.85; color:var(--royal); padding:6px 12px 4px 0; margin-right:4px; position:relative; }
.ornamental-initial .oi-letter::after { content:''; position:absolute; right:4px; bottom:2px; width:30px; height:30px; background:radial-gradient(circle at 30% 30%,var(--gold) 2px,transparent 2.5px),radial-gradient(circle at 70% 70%,var(--gold) 1.5px,transparent 2px); opacity:0.5; }
.ornamental-initial::first-line { font-variant:small-caps; letter-spacing:0.05em; color:var(--ink); font-weight:500; }
.ornamental-initial.illuminated .oi-letter { background:var(--royal); color:var(--gold); padding:8px 14px; margin:4px 10px 4px 0; border-radius:2px; box-shadow:3px 3px 0 var(--gold); }
```

---

### 44.14 Polaroid Frame 宝丽来相框

白色宽边（padding 12px 12px 44px）+ 底部手写 caption（轻微旋转）+ 整体轻微旋转，hover 回正浮起。

```html
<div class="polaroid">
  <div class="pol-photo">I</div>
  <div class="pol-caption">Paris, 2024</div>
</div>
<div class="polaroid pol-wine"><div class="pol-photo">&#10086;</div><div class="pol-caption">Atelier</div></div>
<div class="polaroid pol-royal"><div class="pol-photo">F</div><div class="pol-caption">Signature</div></div>
```
```css
.polaroid { display:inline-block; background:#fff; padding:12px 12px 44px; box-shadow:0 8px 24px rgba(10,36,99,0.15),0 2px 6px rgba(0,0,0,0.08); position:relative; transform:rotate(-3deg); transition:all 400ms var(--ease); width:220px; }
.polaroid:hover { transform:rotate(0deg) translateY(-6px); box-shadow:0 16px 40px rgba(10,36,99,0.2); }
.polaroid:nth-child(even){transform:rotate(2deg);} .polaroid:nth-child(even):hover{transform:rotate(0deg) translateY(-6px);}
.polaroid .pol-photo { width:100%; height:196px; background:linear-gradient(135deg,var(--royal-100),var(--gold-100)); display:flex; align-items:center; justify-content:center; font-family:var(--font-display); font-size:2.5rem; font-style:italic; color:var(--royal); }
.polaroid .pol-caption { position:absolute; bottom:10px; left:12px; right:12px; font-family:var(--font-display); font-style:italic; font-size:1rem; color:var(--ink-300); text-align:center; transform:rotate(-1deg); }
.polaroid.pol-wine .pol-photo{background:linear-gradient(135deg,var(--wine-100),var(--gold-100));color:var(--wine);}
.polaroid.pol-royal .pol-photo{background:linear-gradient(135deg,var(--royal-200),var(--royal));color:var(--gold);}
```

---

### 44.15 Gold Foil Text 烫金文字

多段金色渐变 + background-size:200% + shimmer 动画扫光 + drop-shadow 立体边缘。

```html
<div class="gold-foil">Feihong</div>
<span class="gold-foil italic">Atelier</span>
```
```css
@keyframes luxeShimmer { 0%{background-position:-200% center;} 100%{background-position:200% center;} }
.gold-foil { font-family:var(--font-serif); font-size:clamp(2.5rem,6vw,4.5rem); font-weight:700; background:linear-gradient(110deg,var(--gold-800) 0%,var(--gold-600) 20%,var(--gold-300) 35%,var(--gold-50) 45%,var(--gold-300) 55%,var(--gold-600) 70%,var(--gold-800) 100%); background-size:200% auto; -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent; animation:luxeShimmer 4s linear infinite; display:inline-block; line-height:1.1; filter:drop-shadow(0 1px 0 var(--gold-800)); }
.gold-foil.italic { font-family:var(--font-display); font-style:italic; font-weight:400; }
```

---

### 44.16 Washi Tape 和纸胶带

半透明胶带（absolute 定位贴角），自带锯齿/条纹纹理伪元素，4 种颜色变体。

```html
<div class="washi-demo-box">
  <div class="washi gold washi-tl"></div>
  珍藏手稿 · 卷一
</div>
<div class="washi-demo-box">
  <div class="washi wine washi-tl" style="width:120px;"></div>
  Private Collection
</div>
```
```css
.washi { position:absolute; width:100px; height:28px; background:var(--tape-color,var(--gold)); opacity:0.75; box-shadow:0 2px 4px rgba(0,0,0,0.1); z-index:5; }
.washi::before,.washi::after { content:''; position:absolute; top:0; bottom:0; width:4px; background:repeating-linear-gradient(45deg,transparent,transparent 2px,rgba(255,255,255,0.3) 2px,rgba(255,255,255,0.3) 4px); }
.washi::before { left:0; border-left:2px dashed rgba(0,0,0,0.08); } .washi::after { right:0; border-right:2px dashed rgba(0,0,0,0.08); }
.washi.gold{--tape-color:linear-gradient(90deg,var(--gold-300),var(--gold),var(--gold-300));}
.washi.wine{--tape-color:linear-gradient(90deg,var(--wine-300),var(--wine),var(--wine-300));opacity:0.65;}
.washi.royal{--tape-color:linear-gradient(90deg,var(--royal-300),var(--royal),var(--royal-300));opacity:0.7;}
.washi.stripe{--tape-color:repeating-linear-gradient(-45deg,var(--cream-100),var(--cream-100) 6px,var(--gold-200) 6px,var(--gold-200) 12px);opacity:0.85;}
.washi-demo-box { position:relative; display:inline-block; padding:1.5rem 2rem; background:#fff; border:1px solid var(--cream-200); border-radius:var(--r-md); font-family:var(--font-serif); font-size:1.1rem; color:var(--ink); }
.washi-demo-box .washi-tl{top:-10px;left:20px;transform:rotate(-6deg);}
.washi-demo-box .washi-tr{top:-8px;right:20px;transform:rotate(5deg);width:80px;}
```

---

### 44.17 Exhibition Label 展览标签

博物馆画廊风格：左侧粗色条 + mono 编号 + 斜体作品名 + 艺术家年份 + 材质行，含 `.wall` 墙面变体。

```html
<div class="exhibition-label">
  <div class="el-num">No. 001</div>
  <div class="el-title">Composition in Royal Blue</div>
  <div class="el-artist">Feihong<span class="el-year">2025</span></div>
  <div class="el-medium">Digital print on archival paper · 42 × 59 cm</div>
</div>
<div class="exhibition-label wall"><!-- 墙面米黄版本 --></div>
```
```css
.exhibition-label { display:inline-block; background:#fff; border-left:3px solid var(--royal); padding:1rem 1.25rem; max-width:280px; box-shadow:var(--shadow-sm); }
.exhibition-label .el-num { font-family:var(--font-mono); font-size:0.65rem; color:var(--gold-700); letter-spacing:0.15em; margin-bottom:0.25rem; }
.exhibition-label .el-title { font-family:var(--font-serif); font-size:1.1rem; font-weight:600; font-style:italic; color:var(--ink); line-height:1.3; margin-bottom:0.5rem; }
.exhibition-label .el-artist { font-family:var(--font-sans); font-size:0.75rem; color:var(--ink-200); letter-spacing:0.05em; }
.exhibition-label .el-year { font-family:var(--font-display); font-style:italic; color:var(--wine); margin-left:6px; }
.exhibition-label .el-medium { font-family:var(--font-mono); font-size:0.65rem; color:var(--ink-400); margin-top:0.5rem; padding-top:0.5rem; border-top:1px dotted var(--cream-200); letter-spacing:0.05em; }
.exhibition-label.wall { background:var(--cream-200); border-left-color:var(--wine); }
```

---

### 44.18 Constellation Link 星座链接

SVG 虚线连接 + 金色圆点节点（带光晕）+ mono 标签，hover 节点变酒红放大；`.active` 态为皇家蓝+脉冲动画。

```html
<div class="constellation">
  <svg viewBox="0 0 500 200" preserveAspectRatio="none">
    <line class="const-line" x1="60" y1="60" x2="180" y2="130"/>
    <!-- 更多 line -->
  </svg>
  <div class="const-dot active" style="top:60px;left:60px;"><span class="const-label">Home</span></div>
  <div class="const-dot" style="top:130px;left:180px;"><span class="const-label">Works</span></div>
  <!-- ... -->
</div>
```
```css
@keyframes luxePulse { 0%,100%{opacity:1;transform:scale(1);} 50%{opacity:0.7;transform:scale(1.05);} }
.constellation { position:relative; width:100%; max-width:500px; height:200px; }
.constellation svg { position:absolute; inset:0; width:100%; height:100%; pointer-events:none; }
.constellation .const-line { stroke:var(--gold-300); stroke-width:1; stroke-dasharray:3 3; opacity:0.6; }
.constellation .const-dot { position:absolute; width:12px; height:12px; border-radius:50%; background:var(--gold); transform:translate(-50%,-50%); box-shadow:0 0 0 4px var(--gold-50),0 0 12px rgba(244,211,94,0.5); cursor:pointer; transition:all 250ms var(--ease); z-index:2; }
.constellation .const-dot:hover { transform:translate(-50%,-50%) scale(1.4); background:var(--wine); box-shadow:0 0 0 4px var(--wine-100),0 0 16px rgba(216,49,91,0.5); }
.constellation .const-label { position:absolute; font-family:var(--font-mono); font-size:0.65rem; color:var(--ink-300); letter-spacing:0.1em; text-transform:uppercase; transform:translate(-50%,12px); white-space:nowrap; pointer-events:none; }
.constellation .const-dot.active { background:var(--royal); box-shadow:0 0 0 4px var(--royal-100),0 0 12px rgba(10,36,99,0.4); animation:luxePulse 2s ease-in-out infinite; }
```

---

### 44.19 Embossed Card 浮雕卡片

新古典主义浮雕名片：双向阴影模拟凸/凹效果，文字用双 text-shadow 做浮雕感，含 `.dark-emb` 深色版本。

```html
<div class="embossed-card">
  <div class="emb-monogram">F</div>
  <div class="emb-name">Feihong</div>
  <div class="emb-title">Designer &amp; Artisan</div>
  <div class="emb-rule"></div>
  <div class="emb-contact">hello@Feihong.design<br>Feihong.design</div>
</div>
```
```css
.embossed-card { background:linear-gradient(145deg,var(--cream-100),#fff); border-radius:var(--r-lg); padding:2rem 1.5rem; max-width:320px; box-shadow:8px 8px 20px rgba(10,36,99,0.08),-4px -4px 12px rgba(255,255,255,0.9),inset 1px 1px 1px rgba(255,255,255,0.8); transition:transform 250ms; }
.embossed-card:hover{transform:translateY(-3px);}
.embossed-card .emb-monogram { font-family:var(--font-display); font-size:3rem; font-style:italic; color:var(--royal); text-align:center; line-height:1; margin-bottom:0.75rem; text-shadow:1px 1px 1px rgba(255,255,255,0.9),-1px -1px 1px rgba(10,36,99,0.15); }
.embossed-card .emb-name { font-family:var(--font-serif); font-size:1.05rem; font-weight:600; color:var(--ink); text-align:center; letter-spacing:0.1em; text-transform:uppercase; }
.embossed-card .emb-title { font-family:var(--font-display); font-style:italic; font-size:0.85rem; color:var(--ink-300); text-align:center; margin-top:0.25rem; }
.embossed-card .emb-rule { width:40px; height:1px; background:var(--gold); margin:0.75rem auto; }
.embossed-card .emb-contact { font-family:var(--font-mono); font-size:0.65rem; color:var(--ink-300); text-align:center; letter-spacing:0.08em; line-height:1.8; }
.embossed-card.dark-emb { background:linear-gradient(145deg,var(--royal-700),var(--royal-900)); box-shadow:6px 6px 18px rgba(0,0,0,0.3),-2px -2px 8px rgba(255,255,255,0.04),inset 1px 1px 1px rgba(255,255,255,0.05); }
.embossed-card.dark-emb .emb-monogram{color:var(--gold);text-shadow:1px 1px 1px rgba(0,0,0,0.5),-1px -1px 1px rgba(244,211,94,0.2);}
.embossed-card.dark-emb .emb-name{color:var(--gold);} .embossed-card.dark-emb .emb-title,.embossed-card.dark-emb .emb-contact{color:rgba(255,255,255,0.5);}
```

---

### 44.20 Ribbon Banner 丝带横幅

折叠三角尾部 + 深色阴影折角，3 种配色：皇家蓝/金色/酒红。

```html
<div class="ribbon-banner">
  <span class="rb-fold-l"></span>Featured<span class="rb-fold-r"></span>
</div>
<div class="ribbon-banner gold-rb">Premium</div>
<div class="ribbon-banner wine-rb">Exclusive</div>
```
```css
.ribbon-banner { display:inline-block; position:relative; padding:10px 36px; background:var(--royal); color:var(--gold); font-family:var(--font-serif); font-size:1.1rem; font-weight:600; letter-spacing:0.1em; text-transform:uppercase; box-shadow:0 4px 12px rgba(10,36,99,0.25); }
.ribbon-banner::before{content:'';position:absolute;top:100%;left:0;border-width:14px 0 0 12px;border-style:solid;border-color:transparent transparent transparent var(--royal-800);}
.ribbon-banner::after{content:'';position:absolute;top:100%;right:0;border-width:14px 12px 0 0;border-style:solid;border-color:var(--royal-800) transparent transparent transparent;}
.ribbon-banner .rb-fold-l,.ribbon-banner .rb-fold-r{position:absolute;top:100%;width:12px;height:14px;background:var(--royal-900);}
.ribbon-banner .rb-fold-l{left:0;clip-path:polygon(0 0,100% 0,0 100%);} .ribbon-banner .rb-fold-r{right:0;clip-path:polygon(0 0,100% 0,100% 100%);}
.ribbon-banner.gold-rb{background:var(--gold);color:var(--royal);box-shadow:0 4px 12px rgba(244,211,94,0.3);}
.ribbon-banner.gold-rb::before{border-color:transparent transparent transparent var(--gold-700);} .ribbon-banner.gold-rb::after{border-color:var(--gold-700) transparent transparent transparent;} .ribbon-banner.gold-rb .rb-fold-l,.ribbon-banner.gold-rb .rb-fold-r{background:var(--gold-800);}
.ribbon-banner.wine-rb{background:var(--wine);color:#fff;box-shadow:0 4px 12px rgba(216,49,91,0.3);}
.ribbon-banner.wine-rb::before{border-color:transparent transparent transparent var(--wine-700);} .ribbon-banner.wine-rb::after{border-color:var(--wine-700) transparent transparent transparent;} .ribbon-banner.wine-rb .rb-fold-l,.ribbon-banner.wine-rb .rb-fold-r{background:var(--wine-800);}
```

---

### 44.21 Handwritten Note 手写便签

米黄横线纸（linear-gradient 做横线）+ 红色左边距线 + 图钉（pin 类）+ Cormorant 斜体正文。

```html
<div class="hw-note">
  <span class="hw-date">2025.07.08</span>
  记得整理新作品，<br>给老客户发一封手写邮件，<br>保持温度。
  <span class="hw-sign">— F</span>
</div>
<div class="hw-note pin"><!-- 带图钉版本 --></div>
```
```css
.hw-note { display:inline-block; background:linear-gradient(180deg,#FFFEF7,#FFF8E1); padding:1.25rem 1.5rem; width:240px; min-height:180px; box-shadow:2px 3px 10px rgba(0,0,0,0.12),inset 0 0 0 1px rgba(0,0,0,0.03); transform:rotate(-2deg); position:relative; font-family:var(--font-display); font-style:italic; font-size:1rem; line-height:1.7; color:var(--ink); background-image:linear-gradient(180deg,transparent 30px,rgba(10,36,99,0.06) 30px,rgba(10,36,99,0.06) 31px,transparent 31px); background-size:100% 32px; transition:transform 400ms var(--ease); }
.hw-note:hover{transform:rotate(0deg);}
.hw-note::before { content:''; position:absolute; top:0; left:30px; bottom:0; width:1px; background:rgba(216,49,91,0.2); }
.hw-note .hw-date { font-family:var(--font-mono); font-size:0.7rem; font-style:normal; color:var(--wine); letter-spacing:0.05em; margin-bottom:0.75rem; display:block; }
.hw-note .hw-sign { display:block; text-align:right; font-family:var(--font-display); font-style:italic; font-size:1.2rem; color:var(--royal); margin-top:0.75rem; }
.hw-note.pin::after { content:''; position:absolute; top:-8px; left:50%; transform:translateX(-50%); width:14px; height:14px; border-radius:50%; background:radial-gradient(circle at 35% 35%,var(--wine-200),var(--wine)); box-shadow:0 2px 4px rgba(0,0,0,0.3); }
```

---

### 44.22 Serial Number 限量编号

"N° 001 / 100" 风格：Cormorant 斜体大号数字 + 上下金边，含 `.dark-sn` 深色版本。

```html
<div class="serial-num">
  <span class="sn-prefix">N&deg;</span>
  <span class="sn-num">001</span>
  <span class="sn-total">/ 100</span>
</div>
<div class="serial-num dark-sn"><span class="sn-prefix">No.</span><span class="sn-num">VII</span><span class="sn-total">/ XII</span></div>
```
```css
.serial-num { display:inline-flex; align-items:baseline; gap:4px; font-family:var(--font-display); color:var(--ink); padding:4px 0; border-top:1px solid var(--gold); border-bottom:1px solid var(--gold); }
.serial-num .sn-prefix { font-size:0.85rem; font-style:italic; color:var(--gold-700); letter-spacing:0.1em; text-transform:uppercase; }
.serial-num .sn-num { font-family:var(--font-display); font-size:1.6rem; font-weight:400; font-style:italic; color:var(--royal); letter-spacing:0.05em; }
.serial-num .sn-total { font-family:var(--font-mono); font-size:0.7rem; color:var(--ink-400); letter-spacing:0.05em; }
.serial-num.dark-sn { background:var(--ink); color:var(--gold); padding:8px 18px; border-color:var(--gold-700); }
.serial-num.dark-sn .sn-prefix{color:var(--gold);} .serial-num.dark-sn .sn-num{color:#fff;} .serial-num.dark-sn .sn-total{color:var(--ink-400);}
```

---

### 44.23 Vertical Text 竖排文字

CSS `writing-mode: vertical-rl` 实现中文竖排，衬线正文 + 金色边线 + `.vt-display` 花体标题变体。

```html
<div class="vt-stack">
  <div class="vertical-text">设<span class="vt-gold">计</span>有温度</div>
  <div class="vertical-text vt-display">Atelier</div>
  <div class="vt-content"><p>竖排文字是中文排版最古老也最典雅的形式……</p></div>
</div>
```
```css
.vertical-text { writing-mode:vertical-rl; text-orientation:mixed; font-family:var(--font-serif); font-size:1.1rem; font-weight:500; letter-spacing:0.3em; color:var(--ink); line-height:1.8; padding:0.75rem; border-right:2px solid var(--gold); display:inline-block; }
.vertical-text .vt-gold { color:var(--gold-700); }
.vertical-text.vt-display { font-family:var(--font-display); font-size:1.8rem; font-weight:400; font-style:italic; color:var(--royal); letter-spacing:0.2em; border-right-color:var(--wine); border-right-width:1px; }
.vt-stack { display:flex; gap:1.5rem; align-items:flex-start; }
.vt-stack .vt-content { flex:1; font-size:0.95rem; line-height:1.85; color:var(--ink-100); }
```

---

### 44.24 Ink Bleed 墨迹晕染

radial-gradient 椭圆晕染 + 中心墨点，入场 scale 动画；3 色（黑墨/蓝墨/酒红）+ `.ink-splash` 飞溅效果。

```html
<div class="ink-bleed"><div class="ink-blob"></div><div class="ink-core"></div></div>
<div class="ink-bleed royal-ink">...</div>
<div class="ink-bleed wine-ink">...</div>
<div class="ink-splash"></div>
```
```css
@keyframes luxeInkBleed { 0%{transform:scale(0.3);opacity:0;} 60%{opacity:0.9;} 100%{transform:scale(1);opacity:0.75;} }
.ink-bleed { position:relative; display:inline-block; width:60px; height:60px; }
.ink-bleed .ink-core { position:absolute; top:50%; left:50%; transform:translate(-50%,-50%); width:14px; height:14px; border-radius:50%; background:var(--ink); }
.ink-bleed .ink-blob { position:absolute; inset:0; background:radial-gradient(ellipse at center,var(--ink) 0%,rgba(13,18,37,0.7) 30%,rgba(13,18,37,0.3) 55%,transparent 75%); border-radius:48% 52% 60% 40%/45% 55% 45% 55%; filter:blur(1px); opacity:0.7; animation:luxeInkBleed 1.5s var(--ease) both; }
.ink-bleed.royal-ink .ink-core{background:var(--royal);} .ink-bleed.royal-ink .ink-blob{background:radial-gradient(ellipse at center,var(--royal) 0%,rgba(10,36,99,0.6) 35%,rgba(10,36,99,0.2) 60%,transparent 78%);}
.ink-bleed.wine-ink .ink-core{background:var(--wine);} .ink-bleed.wine-ink .ink-blob{background:radial-gradient(ellipse at center,var(--wine) 0%,rgba(216,49,91,0.6) 35%,rgba(216,49,91,0.2) 60%,transparent 78%);}
.ink-splash { position:relative; width:80px; height:80px; }
.ink-splash::before { content:''; position:absolute; inset:10%; background:var(--ink); border-radius:50% 40% 55% 45%/45% 55% 40% 55%; filter:blur(0.5px); opacity:0.85; }
.ink-splash::after { content:''; position:absolute; top:15%; left:20%; width:8px; height:8px; background:var(--ink); border-radius:50%; box-shadow:30px 10px 0 -1px var(--ink),50px 30px 0 -2px var(--ink),15px 45px 0 -1.5px var(--ink),-5px 25px 0 -2px var(--ink); }
```

---

### 44.25 Luxe Pagination 奢华分页

Cormorant 斜体页码 + 金色/皇家蓝激活态，含 `.roman` 罗马数字+金色下划线变体。

```html
<div class="luxe-pagination">
  <button class="page-link nav-arrow">&larr;</button>
  <button class="page-link current">1</button>
  <button class="page-link">2</button>
  <button class="page-link">3</button>
  <span class="page-sep">&middot;</span>
  <button class="page-link">42</button>
  <button class="page-link nav-arrow">&rarr;</button>
</div>

<div class="luxe-pagination roman">
  <button class="page-link nav-arrow">&laquo;</button>
  <button class="page-link">i</button>
  <button class="page-link current">ii</button>
  <button class="page-link">iii</button>
  ...
</div>
```
```css
.luxe-pagination { display:inline-flex; align-items:center; gap:0.5rem; }
.luxe-pagination .page-link { display:inline-flex; align-items:center; justify-content:center; min-width:40px; height:40px; font-family:var(--font-display); font-size:1rem; font-style:italic; color:var(--ink-300); border:1px solid transparent; border-radius:2px; padding:0 0.75rem; transition:all 150ms var(--ease); cursor:pointer; background:transparent; }
.luxe-pagination .page-link:hover { color:var(--royal); border-color:var(--gold-200); background:var(--gold-50); }
.luxe-pagination .page-link.current { color:var(--gold); background:var(--royal); border-color:var(--royal); font-weight:500; box-shadow:var(--shadow-gold); }
.luxe-pagination .page-link.nav-arrow { font-family:var(--font-serif); font-style:normal; font-weight:600; color:var(--gold-700); }
.luxe-pagination .page-sep { color:var(--cream-200); font-size:1rem; }
.luxe-pagination.roman .page-link { font-size:0.9rem; letter-spacing:0.08em; text-transform:uppercase; }
.luxe-pagination.roman .page-link.current { background:transparent; color:var(--royal); border-bottom:2px solid var(--gold); box-shadow:none; border-radius:0; border-top-color:transparent; border-left-color:transparent; border-right-color:transparent; }
```

---

### 共用入场动画（推荐配合使用）

```css
@keyframes luxeFadeUp { from{opacity:0;transform:translateY(18px);} to{opacity:1;transform:translateY(0);} }
.luxe-enter { opacity:0; animation:luxeFadeUp 0.8s var(--ease) forwards; }
.luxe-enter-delay-1{animation-delay:0.1s;} .luxe-enter-delay-2{animation-delay:0.2s;}
.luxe-enter-delay-3{animation-delay:0.3s;} .luxe-enter-delay-4{animation-delay:0.4s;}
```
