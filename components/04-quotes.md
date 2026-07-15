# Feihong Design System — Quotes & Pull Quotes
# N°04 · 引用/金句
> Pull quotes, blockquotes, editorial quotations, poetry verses, and dialogue bubbles.
> 引用块、拉引、杂志风金句、诗行引用和对话气泡。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
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

## 49. Quotes 引用/金句类

### 49.1 Magazine Pull Quote 杂志大引号

杂志拉引（Pull Quote），超大金色花体引号作为装饰，居中衬线引文，底部有金色细线加签名，高端杂志跨页引用风格。

```html
<blockquote class="pull-quote">
  <span class="pq-mark pq-open">"</span>
  <p class="pq-text">Elegance is refusal. The true luxury lies in what we choose not to include.</p>
  <span class="pq-mark pq-close">"</span>
  <cite class="pq-cite">— Coco Chanel</cite>
</blockquote>
```
```css
.pull-quote { position:relative; text-align:center; padding:3rem 2rem; max-width:700px; margin:2rem auto; }
.pq-mark { font-family:var(--font-display); font-size:6rem; line-height:1; color:var(--gold); position:absolute; opacity:0.5; font-style:normal; }
.pq-open { top:0; left:1rem; }
.pq-close { bottom:1rem; right:1rem; }
.pq-text { font-family:var(--font-display); font-size:clamp(1.4rem,3vw,2rem); font-weight:400; font-style:italic; color:var(--royal); line-height:1.6; margin:0 0 1.5rem; }
.pq-cite { font-family:var(--font-sans); font-size:0.8rem; color:var(--ink-300); text-transform:uppercase; letter-spacing:0.2em; font-style:normal; display:block; position:relative; padding-top:1rem; }
.pq-cite::before { content:''; position:absolute; top:0; left:50%; transform:translateX(-50%); width:40px; height:1px; background:var(--gold); }
```

---

### 49.2 Dialogue Bubble 对话气泡

优雅对话气泡，左侧皇家蓝/右侧酒红两种样式，气泡有金色小三角指向头像方向，底部显示时间戳，聊天/访谈记录风格。

```html
<div class="dialogue">
  <div class="dl-bubble dl-left">
    <div class="dl-avatar dl-av-r"></div>
    <div class="dl-body"><p>What defines true craftsmanship?</p><span class="dl-time">14:32</span></div>
  </div>
  <div class="dl-bubble dl-right">
    <div class="dl-body dl-body-wine"><p>It is the invisible stitch — the detail no one sees but everyone feels.</p><span class="dl-time">14:33</span></div>
    <div class="dl-avatar dl-av-g"></div>
  </div>
</div>
```
```css
.dialogue { display:flex; flex-direction:column; gap:1.25rem; font-family:var(--font-sans); max-width:500px; }
.dl-bubble { display:flex; align-items:flex-end; gap:0.75rem; }
.dl-bubble.dl-right { flex-direction:row-reverse; }
.dl-avatar { width:36px; height:36px; border-radius:50%; flex-shrink:0; border:2px solid var(--gold); }
.dl-av-r { background:var(--royal); } .dl-av-g { background:var(--wine); }
.dl-body { background:var(--royal); color:var(--cream); padding:0.85rem 1.1rem; border-radius:var(--r-lg); position:relative; max-width:75%; }
.dl-body::before { content:''; position:absolute; bottom:10px; border:6px solid transparent; }
.dl-left .dl-body::before { left:-12px; border-right-color:var(--royal); }
.dl-body-wine { background:var(--wine); }
.dl-right .dl-body-wine::before { right:-12px; border-left-color:var(--wine); }
.dl-body p { margin:0; font-size:0.9rem; line-height:1.5; }
.dl-time { display:block; font-size:0.65rem; opacity:0.6; margin-top:0.4rem; text-align:right; font-family:var(--font-mono); }
```

---

### 49.3 Poetry Verse Quote 诗行引用

诗行引用，竖排金色装饰线在左侧，使用花体字体，行间留白充裕，行首缩进，古典诗集/文学引用风格。

```html
<blockquote class="verse-quote">
  <p>Through amber light and velvet rain,</p>
  <p>The atelier weaves gold again.</p>
  <p>A thread of blue, a stitch of wine,</p>
  <p>Where craft and quietness align.</p>
  <cite>— Atelier Verse, 2026</cite>
</blockquote>
```
```css
.verse-quote { position:relative; padding:1.5rem 2rem 1.5rem 2.5rem; font-family:var(--font-display); font-style:italic; max-width:500px; }
.verse-quote::before { content:''; position:absolute; left:0; top:1rem; bottom:1rem; width:2px; background:linear-gradient(to bottom,transparent,var(--gold),transparent); }
.verse-quote p { font-size:1.15rem; color:var(--ink); line-height:2; margin:0; font-weight:400; }
.verse-quote p:first-letter { font-size:2.5em; float:left; line-height:0.8; margin-right:0.1em; color:var(--royal); font-family:var(--font-serif); font-weight:700; }
.verse-quote cite { display:block; margin-top:1rem; font-family:var(--font-sans); font-style:normal; font-size:0.75rem; color:var(--ink-300); letter-spacing:0.1em; }
```

---

### 49.4 Callout Box 标注框

重点标注框，金色左侧粗边框，浅色米白背景，顶部有小标签，内容区支持图标+文字+行动链接，文档/NPS提示风格。

```html
<div class="callout">
  <div class="co-tag"><span class="co-icon">✦</span> Note</div>
  <p class="co-text">所有组件均遵循 WCAG 2.1 AA 级无障碍标准，支持键盘导航与屏幕阅读器。</p>
  <a href="#" class="co-link">了解更多 →</a>
</div>
```
```css
.callout { background:var(--gold-50); border-left:4px solid var(--gold); border-radius:0 var(--r-md) var(--r-md) 0; padding:1.25rem 1.5rem; font-family:var(--font-sans); position:relative; }
.co-tag { display:inline-flex; align-items:center; gap:0.4rem; font-family:var(--font-mono); font-size:0.7rem; text-transform:uppercase; letter-spacing:0.15em; color:var(--gold-700); font-weight:700; margin-bottom:0.5rem; }
.co-icon { color:var(--gold-600); }
.co-text { font-size:0.9rem; color:var(--ink-200); line-height:1.6; margin:0 0 0.75rem; }
.co-link { font-family:var(--font-serif); font-size:0.85rem; color:var(--royal); text-decoration:none; font-weight:600; transition:gap var(--t-fast); display:inline-flex; gap:0.25rem; }
.co-link:hover { gap:0.5rem; color:var(--wine); }
```

---

### 49.5 Side Marginalia 侧边引述

侧边注（Marginalia），正文旁的窄栏引述，使用金色竖线连接到正文对应位置，花体小字，学术/高端出版风格。

```html
<div class="marginalia-wrap">
  <p class="mg-text">The philosophy of the house is rooted in the principle that <mark class="mg-anchor">every detail deserves devotion</mark>, from the selection of the raw material to the final stitch of the hem.</p>
  <aside class="marginalia">
    <span class="mg-line"></span>
    <p class="mg-quote">"Devotion is the thread that binds luxury to legacy."</p>
    <span class="mg-note">— Maison Founder</span>
  </aside>
</div>
```
```css
.marginalia-wrap { position:relative; font-family:var(--font-serif); font-size:1rem; line-height:1.8; color:var(--ink); max-width:680px; padding-right:200px; }
.mg-anchor { background:linear-gradient(to top,rgba(244,211,94,0.3) 40%,transparent 40%); padding:0 2px; }
.marginalia { position:absolute; right:0; top:50%; transform:translateY(-50%); width:170px; font-family:var(--font-display); font-style:italic; }
.mg-line { position:absolute; left:-20px; top:20%; bottom:20%; width:1px; background:var(--gold); }
.mg-line::before { content:''; position:absolute; top:0; left:-2px; width:5px; height:5px; background:var(--gold); border-radius:50%; }
.mg-quote { font-size:0.95rem; color:var(--royal); line-height:1.5; margin:0; font-weight:500; }
.mg-note { display:block; font-size:0.7rem; color:var(--ink-300); font-style:normal; font-family:var(--font-sans); margin-top:0.5rem; letter-spacing:0.05em; }
@media(max-width:768px){ .marginalia-wrap{padding-right:0;} .marginalia{position:static;transform:none;width:100%;margin-top:1rem;padding-left:1rem;border-left:2px solid var(--gold);} .mg-line{display:none;} }
```

---

### 49.6 卡片式大引号引用块（Blockquote Card with Giant Quote Mark）

白底圆角卡片式引用块，左上角使用 `::before` 伪元素放置 5rem 超大金色引号，正文为花体斜体皇家蓝引文，底部为大写小字出处署名，适合设计哲学/理念陈述。

```html
<blockquote class="philosophy-quote">
  <p>好的设计让人感到被理解，而不是被炫技。每一个间距、每一处金色装饰线的长度，都是经过反复斟酌的决定。</p>
  <cite>— Feihong Design System</cite>
</blockquote>
```
```css
.philosophy-quote { position:relative; padding:2.5rem; background:#fff; border-radius:20px; border:1px solid var(--cream-200); box-shadow:0 4px 24px rgba(10,36,99,0.05); }
.philosophy-quote::before { content:'"'; position:absolute; top:0.5rem; left:1.5rem; font-family:var(--font-serif); font-size:5rem; font-weight:700; color:var(--gold); line-height:1; opacity:0.5; }
.philosophy-quote p { font-family:var(--font-display); font-size:1.35rem; font-style:italic; font-weight:400; line-height:1.6; color:var(--royal); margin-bottom:1rem; padding-top:1.5rem; }
.philosophy-quote cite { font-size:0.8rem; font-style:normal; color:var(--ink-300); letter-spacing:0.1em; text-transform:uppercase; }
```

---

### 49.7 左边线金色引文（Left-Bordered Gold Pull Quote）

深色背景区域使用的引文样式，3px 金色左边框（`border-left`），金色花体斜体大字，适合嵌入流程引导/深色板块中作为点睛金句。

```html
<div class="flow-quote">"帮我做一个设计课程的报名页"</div>
```
```css
.flow-quote { font-family:var(--font-display); font-style:italic; font-size:1.6rem; font-weight:500; color:var(--gold); margin:0 0 36px; padding-left:20px; border-left:3px solid var(--gold); line-height:1.4; }
@media(max-width:768px){ .flow-quote{font-size:1.2rem;} }
```
