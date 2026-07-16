# Feihong Design System — Dividers & Decorations
# N°11 · 分隔与装饰
> Gold dividers, decorative numbers, avatars, IP characters, and hand-drawn pen stroke dividers.
> 金色分隔线、装饰数字、头像、IP形象和手绘钢笔画分隔线。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
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
  <img src="assets/avatar.png" alt="飞鸿">
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

---

### 9.6 Hero Background Watermark Number（首屏巨字水印）

首屏背景装饰巨字，Cormorant Garamond 花体斜体，极低透明度 0.04，绝对定位不干扰内容，营造编辑级层次感。提供右上(dn1)和左下(dn2)两个变体。

```html
<section class="hero" style="position:relative;">
  <span class="hero-decor-num dn1" aria-hidden="true">07</span>
  <span class="hero-decor-num dn2" aria-hidden="true">2026</span>
  <!-- 其余首屏内容 -->
</section>
```
```css
/* 首屏巨字水印 — 基础 */
.hero-decor-num {
  position: absolute;
  font-family: var(--font-display);
  font-style: italic;
  font-weight: 300;
  color: var(--royal);
  opacity: 0.04;
  pointer-events: none;
  user-select: none;
}
/* 右上变体 */
.hero-decor-num.dn1 {
  top: 5%; right: 2%;
  font-size: clamp(3rem, 6vw, 5.5rem);
  line-height: 1;
  letter-spacing: 0.05em;
}
/* 左下变体 */
.hero-decor-num.dn2 {
  bottom: 10%; left: -2%;
  font-size: clamp(4rem, 8vw, 7rem);
  color: var(--royal);
  line-height: 1;
  letter-spacing: 0.05em;
}
```

---

### 9.7 Year Watermark（年份水印装饰）

Cormorant Garamond 花体斜体年份水印，3.5rem 字号、opacity:0.06，用于 IP 形象组合或首屏视觉区左下角作为年代标记。

```html
<div class="ip-composition">
  <span class="ip-year" aria-hidden="true">2026</span>
  <!-- 其他装饰元素 -->
</div>
```
```css
/* 年份水印装饰 */
.ip-year {
  position: absolute;
  bottom: 3%; left: 20%;
  z-index: 2;
  font-family: var(--font-display);
  font-style: italic;
  font-size: 3.5rem;
  font-weight: 300;
  color: var(--royal);
  opacity: 0.06;
  line-height: 1;
  pointer-events: none;
}
```

---

### 9.8 Tricolor Gradient Connector（三色渐变连接线）

工作流步骤之间的水平连接线，使用 `::before` 伪元素绘制，线性渐变依次经过皇家蓝→复古金→酒红→皇家蓝，1px 高度，仅桌面端显示。

```html
<div class="workflow-steps">
  <div class="wf-step"><div class="wf-step-num">N°01</div><h5>Discover</h5><p>洞察需求</p></div>
  <div class="wf-step"><div class="wf-step-num">N°02</div><h5>Define</h5><p>定调定向</p></div>
  <div class="wf-step"><div class="wf-step-num">N°03</div><h5>Inject DNA</h5><p>品牌注入</p></div>
  <div class="wf-step"><div class="wf-step-num">N°04</div><h5>Structure</h5><p>架构搭建</p></div>
</div>
```
```css
/* 工作流步骤容器 */
.workflow-steps {
  margin-top: 3rem;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 0;
  position: relative;
}
/* 三色渐变连接线 */
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
  font-weight: 400;
  font-style: italic;
  font-size: 0.85rem;
  display: flex; align-items: center; justify-content: center;
  margin: 0 auto 1rem;
  position: relative;
  z-index: 1;
  border: 1.5px solid var(--gold);
  box-shadow: 0 0 0 4px var(--ink);
  transition: all 300ms var(--ease);
}
.wf-step:hover .wf-step-num {
  background: var(--gold);
  color: var(--royal);
  transform: scale(1.1);
}
@media (max-width: 768px) {
  .workflow-steps { grid-template-columns: repeat(2, 1fr); gap: 1.5rem; }
  .workflow-steps::before { display: none; }
}
```

---

### 9.9 Concentric Decorative Rings（同心装饰圆环）

三层同心/偏心圆环装饰，r1 为皇家蓝实线大圆、r2 为金色虚线中圆、r3 为酒红半透明小圆，用于 IP 形象组合背景营造层次。

```html
<div class="ip-composition">
  <span class="ip-ring r1" aria-hidden="true"></span>
  <span class="ip-ring r2" aria-hidden="true"></span>
  <span class="ip-ring r3" aria-hidden="true"></span>
  <!-- 主图和其他装饰 -->
</div>
```
```css
/* 装饰圆环基础 */
.ip-ring {
  position: absolute;
  border-radius: 50%;
  border: 1px solid var(--cream-200);
  pointer-events: none;
}
/* r1 — 皇家蓝实线大圆（右上） */
.ip-ring.r1 {
  top: 3%; right: 0;
  width: 68%; aspect-ratio: 1;
  border-color: var(--royal-100);
}
/* r2 — 金色虚线中圆（左下） */
.ip-ring.r2 {
  bottom: 5%; left: 0;
  width: 45%; aspect-ratio: 1;
  border-color: var(--gold-200);
  border-style: dashed;
}
/* r3 — 酒红半透明小圆（右上偏下） */
.ip-ring.r3 {
  top: 15%; right: 8%;
  width: 20%; aspect-ratio: 1;
  border: 2px solid var(--wine);
  opacity: 0.5;
}
```

---

### 9.10 Gold Arc Semi-Circle（金色半圆弧线）

55% 直径的金色圆弧，隐藏左边和底边形成半圆，旋转 -20 度放置于右上角，为 IP 形象组合增加 Art Deco 几何感。

```html
<div class="ip-composition">
  <span class="ip-arc" aria-hidden="true"></span>
</div>
```
```css
/* 金色半圆弧线 */
.ip-arc {
  position: absolute;
  width: 55%; aspect-ratio: 1;
  border: 2px solid var(--gold);
  border-radius: 50%;
  border-left-color: transparent;
  border-bottom-color: transparent;
  transform: rotate(-20deg);
  top: 8%; right: 5%;
  pointer-events: none;
}
```

---

### 9.11 Scattered Color Dot Ornament（散落彩色圆点装饰）

四个散落的彩色圆点（酒红/金/皇家蓝/浅金），尺寸从 6px 到 14px 不等，搭配 `box-shadow` 光晕效果，散布于 IP 形象组合四周增加灵动感。

```html
<div class="ip-composition">
  <span class="ip-dot d1" aria-hidden="true"></span>
  <span class="ip-dot d2" aria-hidden="true"></span>
  <span class="ip-dot d3" aria-hidden="true"></span>
  <span class="ip-dot d4" aria-hidden="true"></span>
</div>
```
```css
/* 散落圆点基础 */
.ip-dot {
  position: absolute;
  border-radius: 50%;
  z-index: 4;
}
/* d1 — 酒红圆点 + 酒红光晕（左侧） */
.ip-dot.d1 {
  width: 10px; height: 10px;
  background: var(--wine);
  top: 20%; left: -2%;
  box-shadow: 0 0 0 3px rgba(216, 49, 91, 0.15);
}
/* d2 — 金色圆点 + 金光晕（右下） */
.ip-dot.d2 {
  width: 14px; height: 14px;
  background: var(--gold);
  bottom: 22%; right: 6%;
  box-shadow: 0 0 0 4px rgba(244, 211, 94, 0.2);
}
/* d3 — 皇家蓝圆点 + 蓝光晕（右中） */
.ip-dot.d3 {
  width: 6px; height: 6px;
  background: var(--royal);
  top: 45%; right: -2%;
  box-shadow: 0 0 0 2px rgba(10, 36, 99, 0.15);
}
/* d4 — 浅金小圆点（左上） */
.ip-dot.d4 {
  width: 8px; height: 8px;
  background: var(--gold-200);
  top: 5%; left: 20%;
}
```

---

### 9.12 Art Deco Diamond & Corner（Art Deco菱形和角框）

金色菱形（旋转45度）和 L 形角框线条，1920 年代装饰艺术风格几何元素，用于 IP 形象组合的角落点缀。菱形提供 3 种尺寸变体(dd1/dd2/dd3)，角框提供左上(tl)和右下(br)两个位置。

```html
<div class="ip-composition">
  <span class="deco-diamond dd1" aria-hidden="true"></span>
  <span class="deco-diamond dd2" aria-hidden="true"></span>
  <span class="deco-diamond dd3" aria-hidden="true"></span>
  <span class="deco-corner tl" aria-hidden="true"></span>
  <span class="deco-corner br" aria-hidden="true"></span>
</div>
```
```css
/* Art Deco 金色菱形基础 */
.deco-diamond {
  position: absolute;
  z-index: 4;
  width: 18px; height: 18px;
  border: 1.5px solid var(--gold);
  transform: rotate(45deg);
  pointer-events: none;
}
.deco-diamond.dd1 { top: 8%; right: 12%; width: 14px; height: 14px; border-color: var(--gold-600); opacity: 0.6; }
.deco-diamond.dd2 { bottom: 18%; left: 4%; width: 10px; height: 10px; border-color: var(--gold); opacity: 0.5; }
.deco-diamond.dd3 { top: 42%; right: -1%; width: 8px; height: 8px; background: var(--gold); border: none; opacity: 0.4; }

/* Art Deco L形角框 */
.deco-corner {
  position: absolute;
  z-index: 4;
  width: 28px; height: 28px;
  pointer-events: none;
}
.deco-corner::before, .deco-corner::after {
  content: '';
  position: absolute;
  background: var(--gold);
  opacity: 0.5;
}
/* 左上角 */
.deco-corner.tl { top: 2%; left: 0%; }
.deco-corner.tl::before { top: 0; left: 0; width: 28px; height: 1px; }
.deco-corner.tl::after { top: 0; left: 0; width: 1px; height: 28px; }
/* 右下角 */
.deco-corner.br { bottom: 2%; right: 0%; }
.deco-corner.br::before { bottom: 0; right: 0; width: 28px; height: 1px; }
.deco-corner.br::after { bottom: 0; right: 0; width: 1px; height: 28px; }
```

---

### 9.13 Gold Gradient Thin Line（金色渐变细线）

两端透明、中间金色的 1px 高渐变细线，倾斜放置于 IP 形象组合边缘，增加精致的几何装饰感。提供两个位置变体(gl1/gl2)。

```html
<div class="ip-composition">
  <span class="deco-gold-line gl1" aria-hidden="true"></span>
  <span class="deco-gold-line gl2" aria-hidden="true"></span>
</div>
```
```css
/* 金色渐变细线基础 */
.deco-gold-line {
  position: absolute;
  z-index: 4;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--gold), transparent);
  pointer-events: none;
  opacity: 0.4;
}
/* 右上倾斜-30度 */
.deco-gold-line.gl1 { width: 80px; top: 22%; right: -8%; transform: rotate(-30deg); }
/* 左下倾斜20度 */
.deco-gold-line.gl2 { width: 50px; bottom: 30%; left: -4%; transform: rotate(20deg); }
```

---

### 9.14 N° Serial Number Decoration（N°编号装饰）

Cormorant Garamond 花体斜体小字编号，0.65rem、gold-700 色、半透明，放置于 IP 形象组合的角落作为限量编号感装饰。提供两个位置(dn-a/dn-b)。

```html
<div class="ip-composition">
  <span class="deco-num dn-a" aria-hidden="true">N° 001</span>
  <span class="deco-num dn-b" aria-hidden="true">N° 2026</span>
</div>
```
```css
/* N°编号装饰 */
.deco-num {
  position: absolute;
  z-index: 4;
  font-family: var(--font-display);
  font-style: italic;
  font-size: 0.65rem;
  color: var(--gold-700);
  letter-spacing: 0.1em;
  pointer-events: none;
  opacity: 0.6;
}
.deco-num.dn-a { top: 0; right: 22%; }
.deco-num.dn-b { bottom: 0; left: 2%; }
```

---

### 9.15 Plus Cross Ornament（十字加号装饰）

轻量 300 weight 的 `+` 号装饰，皇家蓝 200 浅色，两种尺寸(1.2rem/0.9rem)散布于 IP 形象组合中，增加编辑设计的呼吸感。

```html
<div class="ip-composition">
  <span class="ip-plus p1" aria-hidden="true">+</span>
  <span class="ip-plus p2" aria-hidden="true">+</span>
</div>
```
```css
/* 十字加号装饰 */
.ip-plus {
  position: absolute;
  color: var(--royal-200);
  font-size: 1.2rem;
  font-weight: 300;
  z-index: 2;
  pointer-events: none;
}
.ip-plus.p1 { top: 15%; right: 25%; }
.ip-plus.p2 { bottom: 25%; left: 18%; font-size: 0.9rem; }
```

---

## D1. 取景框角标 Viewfinder Frame（飞鸿专属 · 影院母题）

**特征**：四角L形线条标记，模拟相机/电影取景框。可用于深色或浅色背景，角标颜色可调整。营造电影拍摄/取景的视觉暗示。

```html
<div class="viewfinder-wrap" style="position:relative;padding:3rem;min-height:200px;border:1px dashed rgba(10,36,99,0.1);border-radius:var(--r-md);">
  <!-- Viewfinder corner marks -->
  <div class="vf-mark vf-tl" style="position:absolute;top:20px;left:20px;width:36px;height:36px;border-top:2px solid var(--royal);border-left:2px solid var(--royal);"></div>
  <div class="vf-mark vf-tr" style="position:absolute;top:20px;right:20px;width:36px;height:36px;border-top:2px solid var(--royal);border-right:2px solid var(--royal);"></div>
  <div class="vf-mark vf-bl" style="position:absolute;bottom:20px;left:20px;width:36px;height:36px;border-bottom:2px solid var(--royal);border-left:2px solid var(--royal);"></div>
  <div class="vf-mark vf-br" style="position:absolute;bottom:20px;right:20px;width:36px;height:36px;border-bottom:2px solid var(--royal);border-right:2px solid var(--royal);"></div>
  <div style="display:flex;align-items:center;justify-content:center;height:100%;min-height:140px;">
    <p style="font-family:var(--font-serif);font-size:1.5rem;color:var(--ink);text-align:center;">取景框内的内容<br><em style="color:var(--gold-dark);font-size:0.7em;">Viewfinder Frame</em></p>
  </div>
</div>
```
```css
/* For dark backgrounds, use white/gold corner marks */
.vf-mark.gold { border-color: var(--gold); }
.vf-mark.white { border-color: rgba(255,255,255,0.3); }
/* Subtle hover animation */
.viewfinder-wrap:hover .vf-mark { border-color: var(--wine); transition: border-color 0.5s; }
```

**使用场景**：Hero区域装饰、图片展示框、作品集封面、深色CTA区域
**气质传达**：电影感、摄影感、专业取景、仪式感

---

## D2. 胶片噪点纹理层 Film Grain Noise Overlay（飞鸿专属）

**特征**：全局SVG噪点纹理覆盖层，使用feTurbulence生成分形噪声，模拟胶片颗粒质感。透明度0.035-0.08，提供微妙的材质感。

```html
<!-- Add this as the first child of body or a section for grain texture -->
<div class="grain-overlay" style="position:absolute;inset:0;z-index:1;pointer-events:none;opacity:0.04;mix-blend-mode:overlay;background-image:url(\"data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E\");"></div>
```
```css
.grain-overlay {
  animation: grainShift 0.8s steps(6) infinite;
}
@keyframes grainShift {
  0%, 100% { transform: translate(0, 0); }
  10% { transform: translate(-2%, -2%); }
  30% { transform: translate(3%, -1%); }
  50% { transform: translate(-1%, 3%); }
  70% { transform: translate(2%, 1%); }
  90% { transform: translate(-3%, 2%); }
}
```

**使用场景**：整个页面背景、深色区块上方、Hero区域、图片上方叠加
**气质传达**：胶片质感、模拟感、温暖、非数字冰冷感

---

## D3. 斜切区块分隔线 Slash Divider（飞鸿专属）

**特征**：使用clip-path创建的斜切边缘分隔，在深色和浅色区块之间创造非直角的有机过渡。两种方向：从左上到右下、从右上到左下。

```html
<!-- Slash divider: dark to light (slopes down from left to right) -->
<div class="slash" style="height:60px;background:var(--royal-deep);clip-path:polygon(0 0,100% 40%,100% 100%,0 100%);margin-top:-1px;"></div>

<!-- Light section content here -->
<section style="background:var(--cream);padding:4rem 2.5rem;">
  <p style="text-align:center;font-family:var(--font-serif);font-size:1.5rem;color:var(--royal);">斜切分隔后的浅色内容区</p>
</section>

<!-- Slash-alt divider: light to dark (slopes up from left to right) -->
<div class="slash-alt" style="height:70px;background:var(--cream);clip-path:polygon(0 0,100% 0,100% 60%,0 100%);"></div>

<!-- Dark section content here -->
<section style="background:var(--royal-deep);padding:4rem 2.5rem;">
  <p style="text-align:center;font-family:var(--font-serif);font-size:1.5rem;color:#fff;">斜切分隔后的深色内容区</p>
</section>
```
```css
.slash { height: 60px; clip-path: polygon(0 0, 100% 40%, 100% 100%, 0 100%); }
.slash-alt { height: 70px; clip-path: polygon(0 0, 100% 0, 100% 60%, 0 100%); }
```

**使用场景**：深色→浅色区块过渡、章节之间的非水平分隔、营造动感
**气质传达**：动感、非对称、编辑感、打破直角框架
