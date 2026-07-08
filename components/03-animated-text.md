# FEIHONG Design System — Animated Text & Titles
# N°03 · 动态文字标题
> 22+ CSS text animation components: reveals, glitches, gradients, typewriters, and editorial effects.
> 22种以上CSS文字动画组件：逐字揭示、故障艺术、渐变流动、打字机及编辑风格效果。
> Part of FEIHONG Design System v7.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 45. 动态文字标题组件 Animated Text & Title Components（22种新组件/变体）

精致的CSS文字动画组件，所有动画均使用 cubic-bezier 缓动，支持 `prefers-reduced-motion` 无障碍媒体查询。

---

### 45.1 Split Text Reveal 逐字揭示

文字拆分为独立 span，逐字从下方滑入+淡入，配合 stagger 延迟。提供 IntersectionObserver 触发版本（`.io-split`）。

```html
<div class="split-reveal">
  <span class="char" style="animation-delay:0.05s;">飞</span>
  <span class="char" style="animation-delay:0.12s;">鸿</span>
  <span class="char" style="animation-delay:0.19s;">印</span>
  <span class="char" style="animation-delay:0.26s;">月</span>
</div>
```
```css
.split-reveal { font-family:var(--font-serif); font-size:clamp(2rem,5vw,3.5rem); font-weight:700; display:inline-block; color:var(--ink); }
.split-reveal .char { display:inline-block; opacity:0; transform:translateY(1.2em) rotateX(-40deg); animation:splitCharIn 0.7s cubic-bezier(0.16,1,0.3,1) forwards; }
.split-reveal .char.space { width:0.3em; }
@keyframes splitCharIn { to{opacity:1;transform:translateY(0) rotateX(0);} }
.split-reveal-gold .char:nth-child(odd) { color:var(--gold); }
```

---

### 45.2 Glitch Text 故障艺术

金色文字红蓝错位+偶尔抖动的赛博朋克/时尚杂志效果，使用 `::before`/`::after` 伪元素叠加。

```html
<div class="glitch-text" data-text="FUTURE">FUTURE</div>
```
```css
.glitch-text { font-family:var(--font-display); font-size:clamp(2.2rem,5vw,3.8rem); font-weight:600; font-style:italic; color:var(--gold); position:relative; display:inline-block; }
.glitch-text::before, .glitch-text::after { content:attr(data-text); position:absolute; top:0;left:0; width:100%;height:100%; pointer-events:none; }
.glitch-text::before { color:var(--wine); animation:glitchShift1 3s cubic-bezier(0.25,0.46,0.45,0.94) infinite; clip-path:polygon(0 0,100% 0,100% 45%,0 45%); }
.glitch-text::after { color:var(--royal-300); animation:glitchShift2 3s cubic-bezier(0.55,0.085,0.68,0.53) infinite; clip-path:polygon(0 55%,100% 55%,100% 100%,0 100%); }
@keyframes glitchShift1 { 0%,92%,100%{transform:translate(0);} 93%{transform:translate(-3px,1px);} 94%{transform:translate(3px,-1px);} 95%{transform:translate(-2px,-2px);} 96%{transform:translate(2px,2px);} 97%{transform:translate(-1px,0);} }
@keyframes glitchShift2 { 0%,90%,100%{transform:translate(0);} 91%{transform:translate(2px,-1px);} 92%{transform:translate(-3px,2px);} 93%{transform:translate(2px,1px);} 94%{transform:translate(-1px,-2px);} }
```

---

### 45.3 Gradient Flow 渐变流动

文字填充线性渐变（皇家蓝→复古金→酒红循环），`background-position` 动画让颜色持续流动。

```html
<div class="gradient-flow">Chronicle of Elegance</div>
```
```css
.gradient-flow { font-family:var(--font-serif); font-size:clamp(2rem,5vw,3.5rem); font-weight:700; background:linear-gradient(90deg,var(--royal) 0%,var(--gold) 25%,var(--wine) 50%,var(--gold) 75%,var(--royal) 100%); background-size:200% auto; -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent; animation:gradientFlow 6s cubic-bezier(0.4,0,0.2,1) infinite; }
@keyframes gradientFlow { 0%{background-position:0% center;} 50%{background-position:100% center;} 100%{background-position:0% center;} }
```

---

### 45.4 Shine Sweep 光泽扫过

金色/白色高光从左到右扫过文字，模拟金属光泽质感。

```html
<div class="shine-sweep">Premium Quality</div>
```
```css
.shine-sweep { font-family:var(--font-serif); font-size:clamp(2rem,5vw,3.5rem); font-weight:700; color:var(--royal); position:relative; display:inline-block; overflow:hidden; }
.shine-sweep::after { content:''; position:absolute; top:0;left:-100%; width:60%;height:100%; background:linear-gradient(105deg,transparent 30%,rgba(244,211,94,0.5) 45%,rgba(255,255,255,0.8) 50%,rgba(244,211,94,0.5) 55%,transparent 70%); animation:shineSweep 3.5s cubic-bezier(0.4,0,0.2,1) infinite; }
@keyframes shineSweep { 0%{left:-100%;} 60%{left:150%;} 100%{left:150%;} }
```

---

### 45.5 Stroke Reveal 描边揭示

文字从空心描边状态（`-webkit-text-stroke`）填充为实心。

```html
<div class="stroke-reveal">Atelier</div>
```
```css
.stroke-reveal { font-family:var(--font-display); font-size:clamp(2.5rem,6vw,4.5rem); font-weight:500; font-style:italic; color:transparent; -webkit-text-stroke:1.5px var(--royal); display:inline-block; animation:strokeFill 2s cubic-bezier(0.16,1,0.3,1) forwards; }
@keyframes strokeFill { 0%,50%{-webkit-text-stroke:1.5px var(--royal);color:transparent;} 100%{-webkit-text-stroke:0;color:var(--royal);} }
```

---

### 45.6 Text Mask Image 图片蒙版

文字作为 `background-clip:text` 蒙版，内嵌 SVG 渐变图案在文字内平移流动。

```html
<div class="text-mask">FEIHONG</div>
```
```css
.text-mask { font-family:var(--font-serif); font-size:clamp(3rem,7vw,5.5rem); font-weight:800; line-height:1; background-image:url("data:image/svg+xml,..."); background-size:200% 200%; -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent; animation:maskPan 8s ease-in-out infinite alternate; }
@keyframes maskPan { 0%{background-position:0% 0%;} 100%{background-position:100% 100%;} }
```

---

### 45.7 Rotating Words 轮播词

一句话中关键词自动向上轮播切换（酒红/蓝/金三色循环），如"让设计更[有温度/有品质/有灵魂]"。

```html
<div class="rotating-words">
  <span class="static-text">让设计更</span>
  <span class="word-wrapper">
    <span class="rotating-list">
      <span>有温度</span><span>有品质</span><span>有灵魂</span><span>有温度</span>
    </span>
  </span>
</div>
```
```css
.rotating-words { font-family:var(--font-serif); font-size:clamp(1.5rem,3.5vw,2.5rem); font-weight:600; display:inline-flex; align-items:baseline; gap:0.3em; }
.rotating-words .word-wrapper { display:inline-block; position:relative; height:1.2em; overflow:hidden; vertical-align:bottom; }
.rotating-words .rotating-list { display:flex; flex-direction:column; animation:rotateWords 8s cubic-bezier(0.4,0,0.2,1) infinite; }
.rotating-words .rotating-list span { height:1.2em; display:flex; align-items:center; color:var(--wine); font-style:italic; font-family:var(--font-display); }
@keyframes rotateWords { 0%,25%{transform:translateY(0);} 33%,58%{transform:translateY(-1.2em);} 66%,91%{transform:translateY(-2.4em);} 100%{transform:translateY(-3.6em);} }
```

---

### 45.8 Underline Draw 下划线绘制

金色下划线从中心向两侧展开（默认）或从左向右绘制（`.left` 变体）。

```html
<div class="underline-draw">飞鸿设计<span class="underline-line"></span></div>
<div class="underline-draw left">Crafted with Care<span class="underline-line"></span></div>
```
```css
.underline-draw { font-family:var(--font-serif); font-size:clamp(1.8rem,4vw,3rem); font-weight:700; display:inline-block; position:relative; }
.underline-draw .underline-line { position:absolute; bottom:-4px; left:50%; width:0; height:3px; background:var(--gold); border-radius:2px; transform:translateX(-50%); animation:underlineDraw 2s cubic-bezier(0.16,1,0.3,1) forwards; }
.underline-draw.left .underline-line { left:0; transform:none; animation-name:underlineDrawLeft; }
@keyframes underlineDraw { to{width:100%;} }
@keyframes underlineDrawLeft { 0%{width:0;left:0;} 100%{width:100%;left:0;} }
```

---

### 45.9 Neon Pulse 霓虹脉冲

文字发光呼吸效果，提供金色（默认）、蓝色（`.blue`）、酒红色（`.wine`）三种霓虹。

```html
<div class="neon-pulse">MIDNIGHT</div>
<div class="neon-pulse blue">OCEAN</div>
<div class="neon-pulse wine">ROUGE</div>
```
```css
.neon-pulse { font-family:var(--font-display); font-size:clamp(2.2rem,5vw,3.8rem); font-weight:500; font-style:italic; color:var(--gold); text-shadow:0 0 4px var(--gold),0 0 11px var(--gold),0 0 19px var(--gold),0 0 40px var(--gold-600); animation:neonPulse 2.5s ease-in-out infinite alternate; }
.neon-pulse.blue { color:#7EB5E8; text-shadow:0 0 4px #7EB5E8,0 0 11px #4A90D9,0 0 19px #4A90D9,0 0 40px var(--royal); }
.neon-pulse.wine { color:#F06292; text-shadow:0 0 4px #F06292,0 0 11px var(--wine),0 0 19px var(--wine),0 0 40px var(--wine-700); }
@keyframes neonPulse { 0%{opacity:0.85;filter:brightness(0.9);} 100%{opacity:1;filter:brightness(1.15);} }
```

---

### 45.10 Ornamental Title 花饰标题

Art Deco风格，标题两侧有金色装饰线+菱形端点，入场时花饰从中心展开、文字随后淡入。

```html
<div class="ornamental-title">
  <span class="ornament left"></span>
  <span class="title-text">飞鸿印月</span>
  <span class="ornament right"></span>
</div>
```
```css
.ornamental-title { display:flex; align-items:center; gap:1.2rem; font-family:var(--font-serif); font-size:clamp(1.5rem,3.5vw,2.4rem); font-weight:700; color:var(--royal); white-space:nowrap; }
.ornamental-title .ornament { flex:1; height:1px; background:var(--gold); position:relative; transform:scaleX(0); animation:ornamentGrow 1.2s cubic-bezier(0.16,1,0.3,1) 0.3s forwards; }
.ornamental-title .ornament::before { content:''; position:absolute; top:50%; width:8px;height:8px; background:var(--gold); transform:translateY(-50%) rotate(45deg); }
.ornamental-title .ornament.left::before { right:-4px; } .ornamental-title .ornament.right::before { left:-4px; }
.ornamental-title .title-text { opacity:0; transform:translateY(8px); animation:ornamentTitleIn 0.8s cubic-bezier(0.16,1,0.3,1) 0.6s forwards; }
.ornamental-title .ornament.left { transform-origin:right; } .ornamental-title .ornament.right { transform-origin:left; }
@keyframes ornamentGrow { to{transform:scaleX(1);} }
@keyframes ornamentTitleIn { to{opacity:1;transform:translateY(0);} }
```

---

### 45.11 Marquee Bidirectional 双向跑马灯

两行文字反向无限滚动，奢侈品秀场风格（金色花体正方向 + 米白等宽反方向）。

```html
<div class="bi-marquee">
  <div class="marquee-row top">
    <span>FEIHONG</span><span class="sep">&#10022;</span><span>ATELIER</span>...
  </div>
  <div class="marquee-row bottom">
    <span>SPRING / SUMMER 2026</span><span class="sep">&#8226;</span>...
  </div>
</div>
```
```css
.bi-marquee { overflow:hidden; background:var(--ink); padding:1.5rem 0; }
.bi-marquee .marquee-row { display:flex; white-space:nowrap; font-family:var(--font-display); font-size:clamp(1.5rem,3vw,2.2rem); font-style:italic; font-weight:500; }
.bi-marquee .marquee-row.top { animation:marqueeLeft 25s linear infinite; color:var(--gold); }
.bi-marquee .marquee-row.bottom { animation:marqueeRight 30s linear infinite; color:var(--cream); margin-top:0.5rem; opacity:0.5; font-size:clamp(1rem,2vw,1.4rem); font-family:var(--font-mono); font-style:normal; text-transform:uppercase; letter-spacing:0.2em; }
@keyframes marqueeLeft { 0%{transform:translateX(0);} 100%{transform:translateX(-50%);} }
@keyframes marqueeRight { 0%{transform:translateX(-50%);} 100%{transform:translateX(0);} }
```

---

### 45.12 Blur Fade In 模糊淡入

文字从 `filter:blur(20px)` 大模糊状态逐渐清晰，配合字距收紧。

```html
<div class="blur-fade">雾散见山</div>
```
```css
.blur-fade { font-family:var(--font-serif); font-size:clamp(2rem,5vw,3.5rem); font-weight:700; color:var(--ink); filter:blur(20px); opacity:0; animation:blurFadeIn 1.8s cubic-bezier(0.16,1,0.3,1) forwards; }
@keyframes blurFadeIn { 0%{filter:blur(20px);opacity:0;letter-spacing:0.1em;} 100%{filter:blur(0);opacity:1;letter-spacing:0;} }
```

---

### 45.13 Clip Path Reveal 裁剪揭示

文字从一个窄条通过 `clip-path:inset()` 动画逐渐展开显示，支持水平（默认）和垂直（`.clip-reveal-v`）两种方向。

```html
<div class="clip-reveal">Reveal the Truth</div>
<div class="clip-reveal clip-reveal-v">层层递进</div>
```
```css
.clip-reveal { font-family:var(--font-serif); font-size:clamp(2rem,5vw,3.5rem); font-weight:700; color:var(--royal); display:inline-block; clip-path:inset(0 100% 0 0); animation:clipReveal 1.6s cubic-bezier(0.77,0,0.175,1) forwards; }
.clip-reveal-v { clip-path:inset(100% 0 0 0); animation-name:clipRevealV; }
@keyframes clipReveal { 0%{clip-path:inset(0 100% 0 0);} 100%{clip-path:inset(0 0 0 0);} }
@keyframes clipRevealV { 0%{clip-path:inset(100% 0 0 0);} 100%{clip-path:inset(0 0 0 0);} }
```

---

### 45.14 Vintage Letterpress 活版印刷

文字有压印凹陷效果（`text-shadow` + `inset box-shadow`），入场动画模拟印章盖下（弹性cubic-bezier缓动）。

```html
<div class="letterpress">LETTERPRESS</div>
<div class="letterpress" style="background:var(--wine);">印 · 飞鸿</div>
```
```css
.letterpress { font-family:var(--font-serif); font-size:clamp(2rem,5vw,3.5rem); font-weight:800; color:var(--cream); background:var(--royal); display:inline-block; padding:0.3em 0.6em; text-shadow:0 -1px 0 rgba(0,0,0,0.3),0 1px 0 rgba(255,255,255,0.15); box-shadow:inset 0 2px 4px rgba(0,0,0,0.3),inset 0 -1px 0 rgba(255,255,255,0.1),0 4px 12px rgba(10,36,99,0.3); opacity:0; transform:scale(1.15) translateY(-8px); animation:letterpressStamp 0.8s cubic-bezier(0.34,1.56,0.64,1) forwards; border-radius:2px; }
@keyframes letterpressStamp { 0%{opacity:0;transform:scale(1.15) translateY(-8px);} 50%{opacity:1;transform:scale(0.97) translateY(2px);} 100%{opacity:1;transform:scale(1) translateY(0);} }
```

---

### 45.15 Letterspacing Expand 字距展开

文字从紧凑字距（`letter-spacing:-0.15em`）展开到正常间距，使用 Cormorant Garamond 花体。

```html
<div class="ls-expand">Breathe</div>
```
```css
.ls-expand { font-family:var(--font-display); font-size:clamp(2rem,5vw,3.5rem); font-weight:500; font-style:italic; color:var(--royal); letter-spacing:-0.15em; opacity:0; animation:lsExpand 1.4s cubic-bezier(0.16,1,0.3,1) forwards; }
@keyframes lsExpand { 0%{letter-spacing:-0.15em;opacity:0;} 60%{opacity:1;} 100%{letter-spacing:0.04em;opacity:1;} }
```

---

### 45.16 Gold Foil Shimmer 烫金闪烁

金色文字+多段高光渐变流动，模拟金箔反光闪烁效果。

```html
<div class="gold-shimmer">PREMIUM</div>
```
```css
.gold-shimmer { font-family:var(--font-serif); font-size:clamp(2.2rem,5vw,3.8rem); font-weight:700; background:linear-gradient(110deg,var(--gold-800) 0%,var(--gold-600) 20%,var(--gold-300) 40%,#FFF8DC 50%,var(--gold-300) 60%,var(--gold-600) 80%,var(--gold-800) 100%); background-size:300% 100%; -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent; animation:goldShimmer 4s ease-in-out infinite; filter:drop-shadow(0 2px 4px rgba(244,211,94,0.3)); }
@keyframes goldShimmer { 0%,100%{background-position:0% 50%;} 50%{background-position:100% 50%;} }
```

---

### 45.17 3D Flip Stack 3D翻转堆叠

多行文字 3D 透视（`perspective:800px`）依次绕X轴翻转入场，不同行不同颜色。

```html
<div class="flip-stack">
  <span class="flip-line">Design is</span>
  <span class="flip-line">intelligence</span>
  <span class="flip-line">made visible.</span>
</div>
```
```css
.flip-stack { perspective:800px; font-family:var(--font-serif); font-size:clamp(1.8rem,4vw,3rem); font-weight:700; line-height:1.3; }
.flip-stack .flip-line { display:block; opacity:0; transform-origin:left center; transform:rotateX(-90deg); animation:flipIn 0.9s cubic-bezier(0.16,1,0.3,1) forwards; }
.flip-stack .flip-line:nth-child(1){color:var(--ink);animation-delay:0.1s;}
.flip-stack .flip-line:nth-child(2){color:var(--royal);animation-delay:0.35s;}
.flip-stack .flip-line:nth-child(3){color:var(--wine);font-style:italic;font-family:var(--font-display);font-weight:500;animation-delay:0.6s;}
@keyframes flipIn { to{opacity:1;transform:rotateX(0);} }
```

---

### 45.18 Crosshair Title 十字准线标题

水平金色细线从中心延伸到标题两侧，配合中心圆点+竖排等宽标签，类似展览标签。

```html
<div class="crosshair-title">
  <span class="ch-label">N°01</span>
  <span class="ch-dot"></span>
  <span class="ch-text">飞鸿印月</span>
</div>
```
```css
.crosshair-title { display:inline-flex; align-items:center; gap:1rem; position:relative; padding:1rem 0; }
.crosshair-title::before, .crosshair-title::after { content:''; width:0; height:1px; background:var(--gold); animation:crosshairLine 1s cubic-bezier(0.16,1,0.3,1) 0.4s forwards; }
.crosshair-title::after { animation-delay:0.6s; }
.crosshair-title .ch-dot { width:6px;height:6px; background:var(--gold); border-radius:50%; opacity:0; transform:scale(0); animation:crosshairDot 0.4s cubic-bezier(0.34,1.56,0.64,1) 0.2s forwards; }
.crosshair-title .ch-text { font-family:var(--font-serif); font-size:clamp(1.4rem,3vw,2rem); font-weight:700; color:var(--royal); opacity:0; transform:translateY(4px); animation:crosshairText 0.6s var(--ease) 0.8s forwards; }
.crosshair-title .ch-label { font-family:var(--font-mono); font-size:0.7rem; color:var(--gold-700); text-transform:uppercase; letter-spacing:0.15em; writing-mode:vertical-rl; opacity:0; animation:crosshairText 0.6s var(--ease) 1s forwards; }
@keyframes crosshairLine { to{width:60px;} }
@keyframes crosshairDot { to{opacity:1;transform:scale(1);} }
@keyframes crosshairText { to{opacity:1;transform:translateY(0);} }
```

---

### 45.19 Ink Drop Text 墨滴文字

文字像墨水滴入水中一样晕开显现（blur从大到小 + scale从0.3到1 + 透明度），逐字stagger。

```html
<div class="ink-drop">
  <span class="ink-char" style="animation-delay:0.1s;">墨</span>
  <span class="ink-char" style="animation-delay:0.35s;">韵</span>
</div>
```
```css
.ink-drop { font-family:var(--font-serif); font-size:clamp(2rem,5vw,3.5rem); font-weight:700; color:var(--ink); position:relative; display:inline-block; }
.ink-drop .ink-char { display:inline-block; opacity:0; filter:blur(12px); transform:scale(0.3); animation:inkDropIn 1s cubic-bezier(0.25,0.46,0.45,0.94) forwards; }
@keyframes inkDropIn { 0%{opacity:0;filter:blur(12px);transform:scale(0.3);} 40%{opacity:0.7;filter:blur(4px);transform:scale(1.1);} 70%{filter:blur(1px);transform:scale(0.97);} 100%{opacity:1;filter:blur(0);transform:scale(1);} }
```

---

### 45.20 Serif Swash 花体装饰

Cormorant Garamond 花体字，首字母金色放大，hover 时首字母下划线+竖线装饰元素生长，尾部花饰横线展开。

```html
<div class="serif-swash">
  <span class="swash-initial">F</span>eihong<span class="swash-flourish"></span>
</div>
```
```css
.serif-swash { font-family:var(--font-display); font-size:clamp(2.2rem,5vw,4rem); font-weight:400; font-style:italic; color:var(--royal); display:inline-block; position:relative; }
.serif-swash .swash-initial { font-size:1.4em; color:var(--gold); position:relative; display:inline-block; transition:all 0.5s var(--ease); }
.serif-swash .swash-initial::before { content:''; position:absolute; bottom:0.05em;left:-0.1em;right:-0.1em; height:2px; background:var(--gold); transform:scaleX(0); transform-origin:left; transition:transform 0.6s cubic-bezier(0.16,1,0.3,1); }
.serif-swash .swash-initial::after { content:''; position:absolute; top:-0.1em;left:50%; width:2px;height:0; background:var(--gold); transition:height 0.6s cubic-bezier(0.16,1,0.3,1) 0.2s; }
.serif-swash:hover .swash-initial::before { transform:scaleX(1); }
.serif-swash:hover .swash-initial::after { height:0.4em; }
.serif-swash .swash-flourish { display:inline-block; width:0; height:1px; background:var(--gold); vertical-align:middle; margin-left:0.2em; transition:width 0.7s cubic-bezier(0.16,1,0.3,1); }
.serif-swash:hover .swash-flourish { width:2em; }
```

---

### 45.21 Count Up Number 滚动数字

数字从0滚动到目标值，IntersectionObserver 触发，Cormorant 斜体大字，支持前缀/后缀。

```html
<div class="count-up-row">
  <div class="count-up-item">
    <div class="count-up-anim" data-count-target="128" data-count-suffix="+">0</div>
    <div class="cu-label">Components</div>
  </div>
</div>
```
```css
.count-up-anim { font-family:var(--font-display); font-size:clamp(2.5rem,6vw,4.5rem); font-weight:500; font-style:italic; color:var(--royal); display:inline-block; }
.count-up-anim .cu-prefix, .count-up-anim .cu-suffix { font-family:var(--font-serif); font-style:normal; font-weight:600; color:var(--gold); font-size:0.6em; vertical-align:super; }
.count-up-row { display:flex; gap:2.5rem; flex-wrap:wrap; align-items:baseline; }
.count-up-item { text-align:center; }
.count-up-item .cu-label { font-family:var(--font-mono); font-size:0.75rem; color:var(--ink-300); text-transform:uppercase; letter-spacing:0.12em; margin-top:0.3rem; }
```

JS 实现（原生 IntersectionObserver）：
```javascript
(function () {
  function animateCountAnim(el) {
    var target = parseInt(el.dataset.countTarget, 10) || 0;
    var suffix = el.dataset.countSuffix || '';
    var prefix = el.dataset.countPrefix || '';
    var duration = parseInt(el.dataset.countDuration, 10) || 2000;
    var startTime = null;
    function step(ts) {
      if (!startTime) startTime = ts;
      var p = Math.min((ts - startTime) / duration, 1);
      var eased = 1 - Math.pow(1 - p, 3);
      el.textContent = prefix + Math.floor(eased * target).toLocaleString() + suffix;
      if (p < 1) requestAnimationFrame(step);
      else el.textContent = prefix + target.toLocaleString() + suffix;
    }
    requestAnimationFrame(step);
  }
  var obs = new IntersectionObserver(function (entries) {
    entries.forEach(function (e) { if (e.isIntersecting) { animateCountAnim(e.target); obs.unobserve(e.target); } });
  }, { threshold: 0.5 });
  document.querySelectorAll('.count-up-anim').forEach(function (el) { obs.observe(el); });
})();
```

---

### 45.22 Mixed Script 中英混排装饰

中文（Noto Serif SC 粗体）+英文（Cormorant Garamond 细斜体）+装饰符号（金线+菱形+等宽标签）的杂志风标题混排，各自独立入场动画。

```html
<div class="mixed-script">
  <span class="ms-en">The Art of</span>
  <span class="ms-zh">留白<span class="ms-accent">之美</span></span>
  <div class="ms-deco">
    <span class="deco-line"></span>
    <span class="deco-symbol">&#10086;</span>
    <span class="deco-tag">Editorial Design</span>
    <span class="deco-line"></span>
  </div>
</div>
```
```css
.mixed-script { font-family:var(--font-serif); color:var(--ink); line-height:1.2; }
.mixed-script .ms-en { font-family:var(--font-display); font-style:italic; font-size:clamp(2.5rem,6vw,4.5rem); font-weight:300; color:var(--royal); display:block; opacity:0; transform:translateX(-20px); animation:msEnIn 1s cubic-bezier(0.16,1,0.3,1) forwards; }
.mixed-script .ms-zh { font-size:clamp(1.8rem,4vw,3rem); font-weight:700; color:var(--ink); display:block; margin-top:0.2em; opacity:0; transform:translateX(20px); animation:msZhIn 1s cubic-bezier(0.16,1,0.3,1) 0.3s forwards; }
.mixed-script .ms-accent { color:var(--wine); font-style:italic; font-family:var(--font-display); }
.mixed-script .ms-deco { display:flex; align-items:center; gap:0.8rem; margin-top:0.8em; opacity:0; animation:msEnIn 0.8s var(--ease) 0.6s forwards; }
.mixed-script .ms-deco .deco-line { flex:1; max-width:80px; height:1px; background:var(--gold); }
.mixed-script .ms-deco .deco-symbol { font-family:var(--font-display); font-style:italic; color:var(--gold); font-size:1.2rem; }
.mixed-script .ms-deco .deco-tag { font-family:var(--font-mono); font-size:0.7rem; color:var(--ink-300); text-transform:uppercase; letter-spacing:0.15em; }
@keyframes msEnIn { to{opacity:1;transform:translateX(0);} }
@keyframes msZhIn { to{opacity:1;transform:translateX(0);} }
```

---

### 45.23 Velvet Drip 丝绒滴落

酒红色丝绒质感文字，入场后有金色液滴从笔画末端缓缓滴落，高定时装秀场风格。

```html
<div class="velvet-drip">Velvet</div>
```
```css
.velvet-drip { font-family:var(--font-display); font-size:clamp(2.5rem,6vw,4.5rem); font-weight:500; font-style:italic; color:var(--wine); position:relative; display:inline-block; opacity:0; transform:translateY(10px); animation:velvetIn 1s cubic-bezier(0.16,1,0.3,1) forwards; filter:drop-shadow(0 2px 8px rgba(216,49,91,0.3)); }
.velvet-drip::after { content:''; position:absolute; bottom:-4px; left:0.3em; width:3px; height:0; background:linear-gradient(to bottom,var(--gold-500),var(--gold-700)); border-radius:0 0 2px 2px; animation:dripFall 2.5s cubic-bezier(0.25,0.46,0.45,0.94) 1.2s infinite; }
@keyframes velvetIn { to{opacity:1;transform:translateY(0);} }
@keyframes dripFall { 0%{height:0;opacity:1;} 60%{height:20px;opacity:1;} 100%{height:30px;opacity:0;transform:translateY(8px);} }
```

---

### 45.24 Diamond Sparkle 钻石星闪

文字表面有随机闪烁的钻石光点，模拟珠宝反光，光点使用多组伪元素和CSS动画延迟。

```html
<div class="diamond-sparkle">DIAMOND</div>
```
```css
.diamond-sparkle { font-family:var(--font-serif); font-size:clamp(2.2rem,5vw,4rem); font-weight:700; color:var(--royal); position:relative; display:inline-block; background:linear-gradient(135deg,var(--royal) 0%,var(--royal-700) 50%,var(--royal) 100%); -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent; }
.diamond-sparkle::before, .diamond-sparkle::after { content:'✦'; position:absolute; color:var(--gold); font-size:0.4em; opacity:0; animation:sparkle 2s ease-in-out infinite; }
.diamond-sparkle::before { top:0.1em; left:0.2em; animation-delay:0s; }
.diamond-sparkle::after { top:0.3em; right:0.3em; animation-delay:1s; font-size:0.3em; }
@keyframes sparkle { 0%,100%{opacity:0;transform:scale(0) rotate(0deg);} 50%{opacity:1;transform:scale(1) rotate(180deg);} }
```

---

### 45.25 Mirror Reflection 镜像倒影

文字下方有优雅的渐变倒影，hover时倒影微微波动扭曲，奢侈品广告风格。

```html
<div class="mirror-text">Reflection</div>
```
```css
.mirror-text { font-family:var(--font-display); font-size:clamp(2.5rem,6vw,4.5rem); font-weight:500; font-style:italic; color:var(--royal); position:relative; display:inline-block; }
.mirror-text::after { content:attr(data-text); position:absolute; top:100%; left:0; width:100%; color:var(--royal); opacity:0.25; transform:scaleY(-0.5) translateY(-2px); transform-origin:top; filter:blur(1px); -webkit-mask-image:linear-gradient(to bottom,rgba(0,0,0,0.5) 0%,transparent 70%); mask-image:linear-gradient(to bottom,rgba(0,0,0,0.5) 0%,transparent 70%); transition:transform 0.6s var(--ease); }
.mirror-text:hover::after { transform:scaleY(-0.55) translateY(-2px) skewX(2deg); }
```

---

### 45.26 Art Deco Frame 装饰艺术框

Art Deco风格，金色几何边框从四角生长包裹标题，入场时边框先画、文字后显。

```html
<div class="deco-frame">
  <span class="deco-corner tl"></span>
  <span class="deco-corner tr"></span>
  <span class="deco-corner bl"></span>
  <span class="deco-corner br"></span>
  <span class="deco-title">ATELIER</span>
</div>
```
```css
.deco-frame { position:relative; display:inline-block; padding:1.2em 2em; }
.deco-frame .deco-corner { position:absolute; width:30px; height:30px; border-color:var(--gold); border-style:solid; border-width:0; opacity:0; animation:decoCorner 0.8s cubic-bezier(0.16,1,0.3,1) forwards; }
.deco-frame .deco-corner.tl { top:0;left:0; border-top-width:2px;border-left-width:2px; animation-delay:0s; }
.deco-frame .deco-corner.tr { top:0;right:0; border-top-width:2px;border-right-width:2px; animation-delay:0.2s; }
.deco-frame .deco-corner.bl { bottom:0;left:0; border-bottom-width:2px;border-left-width:2px; animation-delay:0.4s; }
.deco-frame .deco-corner.br { bottom:0;right:0; border-bottom-width:2px;border-right-width:2px; animation-delay:0.6s; }
.deco-frame .deco-title { font-family:var(--font-serif); font-size:clamp(1.8rem,4vw,3rem); font-weight:700; color:var(--royal); letter-spacing:0.15em; text-transform:uppercase; opacity:0; transform:scale(0.95); animation:decoTitleIn 0.8s var(--ease) 0.8s forwards; display:block; }
@keyframes decoCorner { to{opacity:1;width:50px;height:50px;} }
@keyframes decoTitleIn { to{opacity:1;transform:scale(1);} }
```

---

### 45.27 Luxury Typewriter 奢华打字机

高端打字机效果，字符逐字敲入，金色光标优雅闪烁，适合引语和Slogan。

```html
<div class="luxury-typewriter" data-text="Crafted with intention."></div>
```
```css
.luxury-typewriter { font-family:var(--font-mono); font-size:clamp(1.2rem,2.5vw,1.8rem); color:var(--ink); display:inline-block; border-right:2px solid var(--gold); padding-right:4px; white-space:nowrap; overflow:hidden; width:0; animation:typing 3s steps(22) 0.5s forwards, cursorBlink 1s step-end infinite; }
@keyframes typing { to{width:100%;} }
@keyframes cursorBlink { 0%,100%{border-color:var(--gold);} 50%{border-color:transparent;} }
```

---

### 45.28 Ink Bleed Spread 墨迹晕染

文字像墨水滴在宣纸上一样，从中心向外晕染扩散显现，边缘有柔和的模糊扩散。

```html
<div class="ink-bleed">墨韵</div>
```
```css
.ink-bleed { font-family:var(--font-serif); font-size:clamp(2.5rem,6vw,4.5rem); font-weight:700; color:var(--ink); display:inline-block; filter:blur(30px); opacity:0; transform:scale(0.5); animation:inkBleed 2s cubic-bezier(0.25,0.46,0.45,0.94) forwards; }
@keyframes inkBleed { 0%{filter:blur(30px);opacity:0;transform:scale(0.5);} 40%{filter:blur(8px);opacity:0.7;transform:scale(1.1);} 70%{filter:blur(2px);opacity:0.9;transform:scale(0.98);} 100%{filter:blur(0);opacity:1;transform:scale(1);} }
```

---

### 45.29 Smoke Form 烟雾聚形

文字从半透明烟雾状态（blur+半透明+轻微位移）逐渐聚拢成清晰实体，神秘优雅。

```html
<div class="smoke-form">Mystère</div>
```
```css
.smoke-form { font-family:var(--font-display); font-size:clamp(2.5rem,6vw,4.5rem); font-weight:400; font-style:italic; color:var(--royal); display:inline-block; opacity:0; filter:blur(25px); transform:translateY(15px) scale(1.1); letter-spacing:0.2em; animation:smokeForm 2.2s cubic-bezier(0.16,1,0.3,1) forwards; }
@keyframes smokeForm { 0%{opacity:0;filter:blur(25px);transform:translateY(15px) scale(1.1);letter-spacing:0.2em;} 60%{opacity:0.6;filter:blur(8px);letter-spacing:0.1em;} 100%{opacity:1;filter:blur(0);transform:translateY(0) scale(1);letter-spacing:0;} }
```

---

### 45.30 Liquid Gold 液态金流

金色文字像液态金属一样，表面有流动的高光波纹，模拟融化的黄金流动感。

```html
<div class="liquid-gold">LIQUID</div>
```
```css
.liquid-gold { font-family:var(--font-serif); font-size:clamp(2.5rem,6vw,4.5rem); font-weight:800; background:linear-gradient(120deg,var(--gold-800) 0%,var(--gold-500) 20%,#FFFEF0 35%,var(--gold-400) 50%,var(--gold-600) 65%,var(--gold-800) 80%,var(--gold-500) 100%); background-size:300% 300%; -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent; animation:liquidFlow 5s ease-in-out infinite; filter:drop-shadow(0 4px 12px rgba(244,211,94,0.4)); }
@keyframes liquidFlow { 0%,100%{background-position:0% 50%;} 50%{background-position:100% 50%;} }
```

---

### 45.31 Marble Vein Flow 大理石纹流动

文字内嵌大理石纹理（灰+金+白），纹理在文字内缓慢流动，高级建筑/室内设计风格。

```html
<div class="marble-text">MARBLE</div>
```
```css
.marble-text { font-family:var(--font-serif); font-size:clamp(2.5rem,6vw,4.5rem); font-weight:700; background:radial-gradient(ellipse at 30% 40%,rgba(244,211,94,0.4) 0%,transparent 50%),radial-gradient(ellipse at 70% 60%,rgba(10,36,99,0.15) 0%,transparent 40%),linear-gradient(135deg,#F5F0E8 0%,#E8E0D0 30%,#D4C8B0 50%,#E8E0D0 70%,#F5F0E8 100%); background-size:200% 200%; -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent; animation:marbleFlow 8s ease-in-out infinite alternate; }
@keyframes marbleFlow { 0%{background-position:0% 0%;} 100%{background-position:100% 100%;} }
```

---

### 45.32 Couture Stitch 高级定制缝线

文字像高级定制服装上的刺绣缝线，逐针显现，带缝线孔眼细节，酒红+金色配色。

```html
<div class="couture-stitch">COUTURE</div>
```
```css
.couture-stitch { font-family:var(--font-mono); font-size:clamp(1.8rem,4vw,3rem); font-weight:700; color:var(--wine); letter-spacing:0.2em; text-transform:uppercase; position:relative; display:inline-block; -webkit-text-stroke:1px dashed var(--gold); text-stroke:1px dashed var(--gold); opacity:0; animation:stitchIn 1.5s cubic-bezier(0.16,1,0.3,1) forwards; }
@keyframes stitchIn { 0%{opacity:0;clip-path:inset(0 100% 0 0);} 100%{opacity:1;clip-path:inset(0 0 0 0);} }
```

---

### 45.33 Paper Tear Reveal 撕纸揭示

文字像被从中间撕开的纸张一样，上下两半分别向上下滑开，揭示下方文字，纸张毛边质感。

```html
<div class="paper-tear">
  <span class="tear-top">SECRET</span>
  <span class="tear-bottom">SECRET</span>
</div>
```
```css
.paper-tear { font-family:var(--font-serif); font-size:clamp(2.2rem,5vw,3.8rem); font-weight:700; color:var(--ink); position:relative; display:inline-block; line-height:1; }
.paper-tear .tear-top, .paper-tear .tear-bottom { display:block; position:relative; }
.paper-tear .tear-top { clip-path:polygon(0 0,100% 0,100% 50%,0 50%); animation:tearTop 1.2s cubic-bezier(0.16,1,0.3,1) 0.5s forwards; }
.paper-tear .tear-bottom { position:absolute; top:0;left:0; clip-path:polygon(0 50%,100% 50%,100% 100%,0 100%); color:var(--royal); animation:tearBottom 1.2s cubic-bezier(0.16,1,0.3,1) 0.5s forwards; }
@keyframes tearTop { to{transform:translateY(-8px);opacity:0.3;} }
@keyframes tearBottom { to{transform:translateY(8px);} }
```

---

### 45.34 Candle Flicker 烛火摇曳

文字像烛光映照一样，亮度和色调微微摇曳变化，边缘有温暖的金色光晕呼吸。

```html
<div class="candle-flicker">Candlelight</div>
```
```css
.candle-flicker { font-family:var(--font-display); font-size:clamp(2.2rem,5vw,3.8rem); font-weight:500; font-style:italic; color:var(--gold-600); animation:candleFlicker 3s ease-in-out infinite; text-shadow:0 0 8px rgba(244,211,94,0.5),0 0 20px rgba(244,211,94,0.3),0 0 40px rgba(244,211,94,0.2); }
@keyframes candleFlicker { 0%,100%{opacity:1;text-shadow:0 0 8px rgba(244,211,94,0.5),0 0 20px rgba(244,211,94,0.3),0 0 40px rgba(244,211,94,0.2);} 25%{opacity:0.92;text-shadow:0 0 6px rgba(244,211,94,0.4),0 0 15px rgba(244,211,94,0.25),0 0 30px rgba(244,211,94,0.15);} 50%{opacity:1;text-shadow:0 0 10px rgba(244,211,94,0.6),0 0 25px rgba(244,211,94,0.35),0 0 50px rgba(244,211,94,0.25);} 75%{opacity:0.95;text-shadow:0 0 7px rgba(244,211,94,0.45),0 0 18px rgba(244,211,94,0.28),0 0 35px rgba(244,211,94,0.18);} }
```

---

### 45.35 Gilded Edge 鎏金描边

文字从黑色实心开始，金色描边从无到有逐渐勾勒笔画轮廓，最后文字填充变为金色。

```html
<div class="gilded-edge">GILDED</div>
```
```css
.gilded-edge { font-family:var(--font-display); font-size:clamp(2.5rem,6vw,4.5rem); font-weight:600; font-style:italic; color:var(--ink); -webkit-text-stroke:0px var(--gold); animation:gildedReveal 2.5s cubic-bezier(0.16,1,0.3,1) forwards; }
@keyframes gildedReveal { 0%{color:var(--ink);-webkit-text-stroke:0px var(--gold);} 40%{color:var(--ink);-webkit-text-stroke:2px var(--gold);} 70%{color:transparent;-webkit-text-stroke:2px var(--gold);} 100%{color:var(--gold);-webkit-text-stroke:0;filter:drop-shadow(0 2px 8px rgba(244,211,94,0.4));} }
```

---

### 45.36 Parallax Layers 视差叠层

三层相同文字叠加（深蓝/金/酒红），hover时三层以不同速度平移，产生视差深度感。

```html
<div class="parallax-text" data-text="PARALLAX">PARALLAX</div>
```
```css
.parallax-text { font-family:var(--font-serif); font-size:clamp(2.2rem,5vw,4rem); font-weight:800; position:relative; display:inline-block; color:var(--royal); transition:transform 0.4s var(--ease); cursor:default; }
.parallax-text::before, .parallax-text::after { content:attr(data-text); position:absolute; top:0;left:0; width:100%;height:100%; pointer-events:none; transition:transform 0.5s cubic-bezier(0.16,1,0.3,1); }
.parallax-text::before { color:var(--gold-400); opacity:0.5; z-index:-1; }
.parallax-text::after { color:var(--wine); opacity:0.3; z-index:-2; }
.parallax-text:hover { transform:translate(-4px,-2px); }
.parallax-text:hover::before { transform:translate(4px,2px); }
.parallax-text:hover::after { transform:translate(8px,4px); }
```

---

### 45.37 Monogram Reveal 花押字揭示

首字母花押字（Monogram）风格，大号首字母旋转缩放入场，周围环绕金色装饰圆环，全名在下方展开。

```html
<div class="monogram">
  <span class="mono-initial">F</span>
  <span class="mono-ring"></span>
  <span class="mono-full">FEIHONG</span>
</div>
```
```css
.monogram { position:relative; display:inline-flex; flex-direction:column; align-items:center; gap:0.5em; }
.monogram .mono-initial { font-family:var(--font-display); font-size:clamp(4rem,10vw,7rem); font-weight:500; font-style:italic; color:var(--royal); line-height:1; opacity:0; transform:rotate(-180deg) scale(0.3); animation:monoInitial 1.2s cubic-bezier(0.34,1.56,0.64,1) forwards; }
.monogram .mono-ring { position:absolute; top:50%;left:50%; width:120px;height:120px; border:1px solid var(--gold); border-radius:50%; transform:translate(-50%,-50%) scale(0); opacity:0; animation:monoRing 1s var(--ease) 0.5s forwards; }
.monogram .mono-ring::before { content:''; position:absolute; top:-4px;left:50%; width:8px;height:8px; background:var(--gold); border-radius:50%; transform:translateX(-50%); }
.monogram .mono-full { font-family:var(--font-mono); font-size:0.75rem; color:var(--gold-700); text-transform:uppercase; letter-spacing:0.3em; opacity:0; transform:translateY(10px); animation:monoFull 0.8s var(--ease) 1s forwards; }
@keyframes monoInitial { to{opacity:1;transform:rotate(0) scale(1);} }
@keyframes monoRing { to{opacity:0.6;transform:translate(-50%,-50%) scale(1);} }
@keyframes monoFull { to{opacity:1;transform:translateY(0);} }
```

---

### 45.38 Magnetic Pull 磁吸字距

文字字符初始分散（大字距），hover时字符像被磁吸引一样向中心聚拢，字距收紧，颜色从灰变金。

```html
<div class="magnetic-text">MAGNETIC</div>
```
```css
.magnetic-text { font-family:var(--font-display); font-size:clamp(2rem,5vw,3.5rem); font-weight:500; font-style:italic; color:var(--ink-300); letter-spacing:0.3em; display:inline-block; transition:all 0.7s cubic-bezier(0.16,1,0.3,1); cursor:default; }
.magnetic-text:hover { color:var(--gold); letter-spacing:0.05em; text-shadow:0 0 20px rgba(244,211,94,0.4); }
```

---

### 45.39 Wavy Serifs 波浪衬线

衬线字体文字整体有柔和的波浪起伏动画，字符逐个上下波动，像水波或丝绸飘动。

```html
<div class="wavy-text">
  <span style="animation-delay:0s;">E</span>
  <span style="animation-delay:0.1s;">l</span>
  <span style="animation-delay:0.2s;">e</span>
  <span style="animation-delay:0.3s;">g</span>
  <span style="animation-delay:0.4s;">a</span>
  <span style="animation-delay:0.5s;">n</span>
  <span style="animation-delay:0.6s;">c</span>
  <span style="animation-delay:0.7s;">e</span>
</div>
```
```css
.wavy-text { font-family:var(--font-display); font-size:clamp(2.2rem,5vw,4rem); font-weight:500; font-style:italic; color:var(--royal); display:inline-block; }
.wavy-text span { display:inline-block; animation:waveChar 2.5s ease-in-out infinite; }
@keyframes waveChar { 0%,100%{transform:translateY(0);} 50%{transform:translateY(-8px);} }
```

---

### 45.40 Chalk Signature 粉笔签名

手写粉笔字效果，文字像在黑板上用粉笔书写，带粉笔纹理和轻微擦痕质感，逐笔书写动画。

```html
<div class="chalk-signature">飞鸿</div>
```
```css
.chalk-signature { font-family:var(--font-display); font-size:clamp(2.5rem,6vw,4.5rem); font-weight:400; font-style:italic; color:var(--cream); text-shadow:0 0 2px rgba(253,251,246,0.5),0 0 6px rgba(253,251,246,0.2); opacity:0; filter:blur(4px); transform:translateY(10px); animation:chalkWrite 1.5s cubic-bezier(0.16,1,0.3,1) forwards; position:relative; }
.chalk-signature::after { content:''; position:absolute; bottom:-4px; left:0; width:0; height:2px; background:var(--cream); opacity:0.4; animation:chalkLine 0.8s var(--ease) 1.2s forwards; }
@keyframes chalkWrite { to{opacity:0.9;filter:blur(0);transform:translateY(0);} }
@keyframes chalkLine { to{width:100%;} }
```

---

### 45.41 Vintage Film Jitter 老电影抖动

文字模拟老电影胶片效果：轻微的上下抖动、随机的亮度闪烁、偶尔的横向偏移，复古胶片质感。

```html
<div class="film-jitter">VINTAGE</div>
```
```css
.film-jitter { font-family:var(--font-serif); font-size:clamp(2.2rem,5vw,3.8rem); font-weight:700; color:var(--ink); display:inline-block; animation:filmJitter 0.15s steps(2) infinite, filmFlicker 3s steps(2) infinite; position:relative; }
.film-jitter::after { content:''; position:absolute; top:0;left:0; right:0;bottom:0; background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,0.03) 2px,rgba(0,0,0,0.03) 4px); pointer-events:none; }
@keyframes filmJitter { 0%{transform:translate(0,0);} 25%{transform:translate(-1px,1px);} 50%{transform:translate(1px,-1px);} 75%{transform:translate(-1px,-1px);} 100%{transform:translate(1px,1px);} }
@keyframes filmFlicker { 0%,96%,100%{opacity:1;} 97%{opacity:0.8;} 98%{opacity:1;} 99%{opacity:0.9;} }
```

---

### 45.42 Hover Split Reveal 悬停分裂揭示

文字默认显示，hover时上下两半分别滑开，中间金色装饰线展开，揭示副标题或日期。

```html
<div class="split-hover">
  <span class="sh-main">DISCOVER</span>
  <span class="sh-reveal">2026</span>
</div>
```
```css
.split-hover { font-family:var(--font-serif); font-size:clamp(2rem,5vw,3.5rem); font-weight:700; color:var(--royal); position:relative; display:inline-block; cursor:pointer; line-height:1; }
.split-hover .sh-main { display:block; position:relative; z-index:2; transition:transform 0.5s cubic-bezier(0.16,1,0.3,1); }
.split-hover .sh-reveal { position:absolute; top:50%;left:50%; transform:translate(-50%,-50%); font-family:var(--font-mono); font-size:0.4em; color:var(--gold); letter-spacing:0.2em; opacity:0; transition:opacity 0.3s var(--ease) 0.1s; z-index:1; }
.split-hover:hover .sh-main { transform:scaleY(1.5); opacity:0.3; letter-spacing:0.1em; }
.split-hover:hover .sh-reveal { opacity:1; }
```

---

---

### 无障碍：prefers-reduced-motion

所有动态文字组件均支持 `prefers-reduced-motion: reduce`，在此模式下动画被禁用，直接显示最终状态（如描边填充完成、模糊消除、clip-path展开等）。

---
