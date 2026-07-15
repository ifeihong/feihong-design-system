# Feihong Design System — Signature Collection
# N°12 · 签名组件（书卷气核心特色）
> Book-inspired components: drop caps, marginalia, fleurons, wax seals, bookmarks, TOC, signatures, chapter openings, decorative frames, and footnotes.
> 书卷气核心组件：首字下沉、旁注、花饰、火漆印、角贴、书签丝带、目录、手写签名、章节扉页、装饰引文框和脚注。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
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

## 32. 金色便签签名标签 Gold Sticky Signature Tag

金色底+皇家蓝字圆角便签，默认旋转 -4 度，hover 回正并下移 4px，内含 Cormorant Garamond 衬线斜体签名名和大写小字 title。用于 IP 形象组合右下角签名区域。

```html
<div class="ip-composition">
  <!-- ...其他装饰... -->
  <div class="ip-signature">
    <span class="sig-name">飞鸿</span>
    <span class="sig-title">Designer · Writer</span>
  </div>
</div>
```
```css
/* 金色便签签名标签 */
.ip-signature {
  position: absolute;
  bottom: 8%; right: -2%;
  background: var(--gold);
  color: var(--royal);
  padding: 0.7rem 1rem;
  border-radius: 12px;
  z-index: 5;
  box-shadow: 0 8px 24px rgba(244, 211, 94, 0.35);
  transform: rotate(-4deg);
  transition: transform 400ms var(--ease);
}
.ip-composition:hover .ip-signature { transform: rotate(0deg) translateY(4px); }
.ip-signature .sig-name {
  font-family: var(--font-serif);
  font-weight: 700;
  font-style: italic;
  font-size: 1rem;
  line-height: 1;
  display: block;
}
.ip-signature .sig-title {
  font-size: 0.58rem;
  font-weight: 500;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  margin-top: 0.2rem;
  opacity: 0.75;
}
```

---

## 33. 金环头像徽章 Gold-Ring Avatar Badge

圆形白底头像徽章，4px 内边距，`::after` 伪元素绘制 2px 金色外环，使用 `animation: float 8s reverse` 反向浮动动画。用于 IP 形象组合左上角。

```html
<div class="ip-composition">
  <div class="ip-avatar-badge">
    <div class="ab-inner">
      <img src="assets/avatar.png" alt="飞鸿头像">
    </div>
  </div>
</div>
```
```css
/* 金环头像徽章 */
.ip-avatar-badge {
  position: absolute;
  top: 10%; left: 2%;
  width: 24%;
  aspect-ratio: 1;
  border-radius: 50%;
  z-index: 5;
  background: #fff;
  padding: 4px;
  box-shadow: 0 12px 32px rgba(10, 36, 99, 0.18);
  animation: float 8s ease-in-out infinite reverse;
}
.ip-avatar-badge .ab-inner {
  width: 100%; height: 100%;
  border-radius: 50%;
  overflow: hidden;
  background: var(--royal-50);
  position: relative;
}
.ip-avatar-badge .ab-inner img {
  width: 100%; height: 100%;
  object-fit: cover;
}
/* 金色外环 */
.ip-avatar-badge::after {
  content: '';
  position: absolute;
  inset: -3px;
  border-radius: 50%;
  border: 2px solid var(--gold);
  pointer-events: none;
}
```

---

## 34. ✦星号前缀品牌标签 Star Prefixed Brand Tag

`::before` 伪元素插入 ✦ 星号，大字间距 uppercase，半透明皇家蓝色，用于 IP 形象组合上方品牌标识。

```html
<div class="ip-composition">
  <span class="ip-tag">Design System</span>
</div>
```
```css
/* ✦星号前缀品牌标签 */
.ip-tag {
  position: absolute;
  top: 5%; left: 30%;
  z-index: 4;
  font-size: 0.6rem;
  font-weight: 600;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--royal);
  display: flex;
  align-items: center;
  gap: 8px;
  opacity: 0.6;
}
.ip-tag::before {
  content: '✦';
  color: var(--gold);
  width: auto; height: auto;
  background: none;
  font-size: 0.7rem;
}
```
