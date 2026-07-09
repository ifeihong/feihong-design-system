# Feihong Design System — Lists & Tags
# N°18 · 列表与标签组
> Gold dot lists, serif numbered lists, check lists, definition lists, timelines, reviews, icon lists, editorial numbered lists, table of contents, notifications, breadcrumbs, price lists, feature checklists, social links, and luxury tag groups for content organization.
> 金色圆点列表、衬线数字列表、勾选列表、定义列表、时间线、评论、图标列表、编辑式编号列表、目录、通知、面包屑、价目表、功能清单、社交链接与奢华标签组，用于内容组织。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范

---

## Design Tokens（设计令牌）

```css
:root {
  /* Color */
  --royal:        #0A2463;   /* 皇家蓝 — 品牌主色 */
  --royal-light:  #1a3a7a;   /* 皇家蓝浅色 */
  --gold:         #F4D35E;   /* 金色 — 奢华点缀 */
  --gold-soft:    #f7e39a;   /* 金色柔和 */
  --gold-deep:    #c9a832;   /* 金色深调 */
  --wine:         #D8315B;   /* 酒红 — 警示/强调 */
  --cream:        #FDFBF6;   /* 奶油白 — 背景 */
  --paper:        #FAF7F0;   /* 纸色 — 次级背景 */
  --ink:          #1a1a2e;   /* 墨色 — 主文字 */
  --ink-100:      #2d2d44;   /* 正文文字 */
  --ink-200:      #5a5a72;   /* 辅助文字 */
  --ink-300:      #9999aa;   /* 弱化文字 */
  --line:         rgba(10,36,99,0.08); /* 分隔线 */
  --line-gold:    rgba(244,211,94,0.4); /* 金色分隔线 */

  /* Typography */
  --font-serif:   'Cormorant Garamond', 'Noto Serif SC', Georgia, serif;
  --font-sans:    'Inter', 'Noto Sans SC', system-ui, sans-serif;
  --font-mono:    'JetBrains Mono', 'Fira Code', monospace;

  /* Spacing */
  --sp-1: 4px;  --sp-2: 8px;  --sp-3: 12px; --sp-4: 16px;
  --sp-5: 20px; --sp-6: 24px; --sp-7: 32px; --sp-8: 40px;
  --sp-9: 48px; --sp-10: 56px; --sp-12: 64px; --sp-16: 96px;

  /* Radius */
  --radius-sm: 2px;
  --radius-md: 4px;
  --radius-lg: 8px;
  --radius-full: 9999px;
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

---

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

---

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

### 6.4 Definition List（定义/描述列表 — 键值对编辑风格）

> 用于产品规格、属性展示、元数据等场景。金色标签、皇家蓝数值，呈现编辑式奢华排版。

```html
<dl class="def-list">
  <div class="def-list__row">
    <dt>材质</dt>
    <dd>意大利顶级头层小牛皮</dd>
  </div>
  <div class="def-list__row">
    <dt>尺寸</dt>
    <dd>38cm × 26cm × 12cm</dd>
  </div>
  <div class="def-list__row">
    <dt>产地</dt>
    <dd>法国 · 巴黎手工坊</dd>
  </div>
  <div class="def-list__row">
    <dt>限量</dt>
    <dd>全球 88 件，编号发行</dd>
  </div>
</dl>
```
```css
.def-list {
  margin: 0;
  padding: 0;
  border-top: 1px solid var(--line-gold);
}
.def-list__row {
  display: flex;
  align-items: baseline;
  padding: var(--sp-4) 0;
  border-bottom: 1px solid var(--line);
  gap: var(--sp-6);
}
.def-list__row dt {
  font-family: var(--font-sans);
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--gold-deep);
  min-width: 80px;
  flex-shrink: 0;
}
.def-list__row dd {
  margin: 0;
  font-family: var(--font-serif);
  font-size: 1.0625rem;
  color: var(--royal);
  font-weight: 500;
  line-height: 1.5;
}
/* 双列变体 */
.def-list--two-col {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0 var(--sp-8);
}
.def-list--two-col .def-list__row {
  border-bottom: 1px solid var(--line);
}
```

---

### 6.5 Activity Feed / Timeline List（动态时间线 — 金色圆点轴线）

> 用于操作日志、活动流、订单状态追踪。金色圆点串联时间轴，头像+动作+时间三段式布局。

```html
<ul class="timeline">
  <li class="timeline__item">
    <div class="timeline__avatar">
      <img src="avatar-1.jpg" alt="陈逸飞">
    </div>
    <div class="timeline__dot"></div>
    <div class="timeline__body">
      <p class="timeline__text">
        <strong>陈逸飞</strong> 提交了新的设计稿
        <span class="timeline__target">「秋季系列主视觉」</span>
      </p>
      <time class="timeline__time">2 分钟前</time>
    </div>
  </li>
  <li class="timeline__item">
    <div class="timeline__avatar timeline__avatar--initials" data-initials="LM">
    </div>
    <div class="timeline__dot"></div>
    <div class="timeline__body">
      <p class="timeline__text">
        <strong>林沐白</strong> 评论了你的方案
      </p>
      <time class="timeline__time">18 分钟前</time>
    </div>
  </li>
  <li class="timeline__item timeline__item--highlight">
    <div class="timeline__avatar">
      <img src="avatar-3.jpg" alt="系统">
    </div>
    <div class="timeline__dot timeline__dot--wine"></div>
    <div class="timeline__body">
      <p class="timeline__text">
        <strong>项目已交付</strong> 客户已确认验收
      </p>
      <time class="timeline__time">1 小时前</time>
    </div>
  </li>
</ul>
```
```css
.timeline {
  list-style: none;
  margin: 0;
  padding: 0 0 0 var(--sp-1);
  position: relative;
}
.timeline::before {
  content: '';
  position: absolute;
  left: 19px;
  top: var(--sp-6);
  bottom: var(--sp-6);
  width: 1px;
  background: linear-gradient(to bottom, var(--gold), var(--line-gold));
}
.timeline__item {
  display: flex;
  align-items: flex-start;
  gap: var(--sp-4);
  padding: var(--sp-3) 0 var(--sp-3) 0;
  position: relative;
}
.timeline__avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  overflow: hidden;
  flex-shrink: 0;
  border: 2px solid var(--gold);
  background: var(--paper);
  z-index: 1;
}
.timeline__avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.timeline__avatar--initials {
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: var(--font-serif);
  font-size: 1rem;
  font-weight: 700;
  color: var(--royal);
  background: var(--cream);
}
.timeline__dot {
  position: absolute;
  left: 15px;
  top: 18px;
  width: 10px;
  height: 10px;
  background: var(--gold);
  border-radius: 50%;
  border: 2px solid var(--cream);
  z-index: 2;
  box-shadow: 0 0 0 2px var(--gold);
}
.timeline__dot--wine {
  background: var(--wine);
  box-shadow: 0 0 0 2px var(--wine);
}
.timeline__body {
  flex: 1;
  padding-top: var(--sp-1);
  min-width: 0;
}
.timeline__text {
  margin: 0 0 var(--sp-1);
  font-family: var(--font-sans);
  font-size: 0.875rem;
  line-height: 1.6;
  color: var(--ink-100);
}
.timeline__text strong {
  font-family: var(--font-serif);
  font-size: 0.9375rem;
  font-weight: 600;
  color: var(--royal);
}
.timeline__target {
  color: var(--gold-deep);
  font-style: italic;
  font-family: var(--font-serif);
}
.timeline__time {
  font-family: var(--font-mono);
  font-size: 0.6875rem;
  color: var(--ink-300);
  letter-spacing: 0.05em;
}
.timeline__item--highlight .timeline__text strong {
  color: var(--wine);
}
```

---

### 6.6 Comment / Review Item（评论/评价条目 — 星级评分）

> 用于产品评价、文章评论、客户证言。Garamond 衬线姓名、金色星级、编辑式排版。

```html
<article class="review">
  <div class="review__header">
    <div class="review__avatar">
      <img src="reviewer.jpg" alt="苏婉清">
    </div>
    <div class="review__meta">
      <h4 class="review__name">苏婉清</h4>
      <div class="review__rating" aria-label="5星好评">
        <span class="star star--filled">★</span>
        <span class="star star--filled">★</span>
        <span class="star star--filled">★</span>
        <span class="star star--filled">★</span>
        <span class="star star--filled">★</span>
      </div>
    </div>
    <time class="review__date">2026年6月15日</time>
  </div>
  <p class="review__body">
    做工极为精致，皮革手感温润如玉，金属配件的打磨足见工匠之心。
    包装本身就是一件艺术品，开箱的仪式感令人难忘。这不仅是一件皮具，
    更是一种生活态度的表达。
  </p>
  <footer class="review__footer">
    <span class="review__verified">✓ 已验证购买</span>
    <button class="review__helpful">有帮助 (24)</button>
  </footer>
</article>
```
```css
.review {
  background: var(--cream);
  border: 1px solid var(--line);
  border-left: 3px solid var(--gold);
  padding: var(--sp-6);
  margin-bottom: var(--sp-4);
  position: relative;
}
.review::before {
  content: '\201C';
  position: absolute;
  top: -8px;
  right: var(--sp-5);
  font-family: var(--font-serif);
  font-size: 5rem;
  color: var(--gold);
  opacity: 0.25;
  line-height: 1;
}
.review__header {
  display: flex;
  align-items: center;
  gap: var(--sp-3);
  margin-bottom: var(--sp-4);
}
.review__avatar {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  overflow: hidden;
  border: 2px solid var(--gold);
  flex-shrink: 0;
}
.review__avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.review__meta { flex: 1; }
.review__name {
  margin: 0 0 2px;
  font-family: var(--font-serif);
  font-size: 1.25rem;
  font-weight: 600;
  font-style: italic;
  color: var(--royal);
  letter-spacing: 0.02em;
}
.review__rating {
  display: flex;
  gap: 2px;
}
.star {
  font-size: 0.875rem;
  color: var(--ink-300);
}
.star--filled {
  color: var(--gold);
  text-shadow: 0 0 1px var(--gold-deep);
}
.star--half {
  background: linear-gradient(90deg, var(--gold) 50%, var(--ink-300) 50%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.review__date {
  font-family: var(--font-mono);
  font-size: 0.6875rem;
  color: var(--ink-300);
  letter-spacing: 0.05em;
  flex-shrink: 0;
}
.review__body {
  margin: 0 0 var(--sp-4);
  font-family: var(--font-serif);
  font-size: 1.0625rem;
  line-height: 1.8;
  color: var(--ink-100);
  font-style: italic;
}
.review__footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: var(--sp-3);
  border-top: 1px solid var(--line);
}
.review__verified {
  font-family: var(--font-sans);
  font-size: 0.6875rem;
  font-weight: 600;
  color: var(--royal);
  text-transform: uppercase;
  letter-spacing: 0.1em;
}
.review__helpful {
  font-family: var(--font-sans);
  font-size: 0.75rem;
  color: var(--ink-200);
  background: none;
  border: 1px solid var(--line);
  padding: 4px 12px;
  border-radius: var(--radius-full);
  cursor: pointer;
  transition: all 0.2s ease;
}
.review__helpful:hover {
  border-color: var(--gold);
  color: var(--royal);
}
```

---

### 6.7 Icon List（图标列表 — 奢华图标变体）

> 支持对勾、箭头、星标、花饰（fleuron）四种图标，金/蓝/酒红三色搭配。用于特性列表、导航菜单、亮点展示。

```html
<!-- Check 变体 -->
<ul class="icon-list icon-list--check">
  <li>免费全球配送</li>
  <li>30天无理由退换</li>
  <li>终身保养维护</li>
</ul>

<!-- Arrow 变体 -->
<ul class="icon-list icon-list--arrow">
  <li><a href="#">品牌故事</a></li>
  <li><a href="#">工艺探秘</a></li>
  <li><a href="#">预约到店</a></li>
</ul>

<!-- Star 变体 -->
<ul class="icon-list icon-list--star">
  <li>米其林三星主厨亲制</li>
  <li>入选 <em>World's 50 Best</em></li>
  <li>James Beard 获奖</li>
</ul>

<!-- Fleuron 花饰变体 -->
<ul class="icon-list icon-list--fleuron">
  <li>序章 · 起源</li>
  <li>第一章 · 工艺</li>
  <li>第二章 · 传承</li>
</ul>
```
```css
.icon-list {
  list-style: none;
  margin: 0;
  padding: 0;
}
.icon-list li {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  line-height: 1.7;
  color: var(--ink-100);
  padding-left: var(--sp-6);
  position: relative;
  margin-bottom: var(--sp-2);
}
.icon-list li a {
  color: var(--royal);
  text-decoration: none;
  transition: color 0.2s ease;
}
.icon-list li a:hover { color: var(--gold-deep); }

/* Check icon */
.icon-list--check li::before {
  content: '✓';
  position: absolute;
  left: 0;
  top: 0.2em;
  color: var(--gold);
  font-size: 1rem;
  font-weight: 700;
}

/* Arrow icon */
.icon-list--arrow li::before {
  content: '→';
  position: absolute;
  left: 0;
  top: 0;
  color: var(--royal);
  font-size: 1rem;
  font-weight: 400;
  transition: transform 0.2s ease, color 0.2s ease;
}
.icon-list--arrow li:hover::before {
  transform: translateX(3px);
  color: var(--gold-deep);
}

/* Star icon */
.icon-list--star li::before {
  content: '★';
  position: absolute;
  left: 0;
  top: 0.1em;
  color: var(--gold);
  font-size: 0.75rem;
}

/* Fleuron 花饰 ❧ */
.icon-list--fleuron li {
  font-family: var(--font-serif);
  font-size: 1.0625rem;
  font-style: italic;
  color: var(--royal);
  padding-left: var(--sp-7);
}
.icon-list--fleuron li::before {
  content: '❧';
  position: absolute;
  left: 0;
  top: -0.05em;
  color: var(--gold);
  font-size: 1.25rem;
}

/* Wine color variant for alerts */
.icon-list--wine li::before {
  color: var(--wine);
}
```

---

### 6.8 Editorial Numbered List（编辑式编号列表 — 杂志风格大数字）

> 区别于 6.2 的步骤式编号，此组件采用杂志/画册式大尺寸 Garamond 斜体金色数字，搭配衬线标题与正文，适合专题文章、精选榜单、年度回顾。

```html
<ol class="editorial-list">
  <li class="editorial-list__item">
    <span class="editorial-list__num">I</span>
    <div class="editorial-list__content">
      <h3 class="editorial-list__title">Atelier of Dreams</h3>
      <p class="editorial-list__desc">
        走进巴黎玛莱区的手工坊，见证每一针每一线的虔诚。
        匠人以数十年的修为，将皮革塑造成有温度的生命体。
      </p>
    </div>
  </li>
  <li class="editorial-list__item">
    <span class="editorial-list__num">II</span>
    <div class="editorial-list__content">
      <h3 class="editorial-list__title">The Alchemy of Leather</h3>
      <p class="editorial-list__desc">
        从植鞣到染色，从晾晒到打磨，每一道工序都是时间与耐心的炼金术。
        意大利托斯卡纳的皮革大师们，恪守着传承百年的秘方。
      </p>
    </div>
  </li>
  <li class="editorial-list__item">
    <span class="editorial-list__num">III</span>
    <div class="editorial-list__content">
      <h3 class="editorial-list__title">A Signature in Gold</h3>
      <p class="editorial-list__desc">
        每一件作品的内侧，都以金箔烫印着独一无二的编号与匠师印记。
        这不是量产的标记，而是对持有者的专属致意。
      </p>
    </div>
  </li>
</ol>
```
```css
.editorial-list {
  list-style: none;
  margin: 0;
  padding: 0;
  counter-reset: editorial-counter;
}
.editorial-list__item {
  display: flex;
  gap: var(--sp-6);
  padding: var(--sp-7) 0;
  border-bottom: 1px solid var(--line-gold);
  align-items: flex-start;
}
.editorial-list__item:first-child {
  padding-top: 0;
}
.editorial-list__num {
  font-family: var(--font-serif);
  font-size: 4.5rem;
  font-weight: 300;
  font-style: italic;
  color: var(--gold);
  line-height: 0.9;
  min-width: 80px;
  flex-shrink: 0;
  text-align: right;
  padding-top: 4px;
  /* 阿拉伯数字变体（罗马数字用默认） */
}
.editorial-list--arabic .editorial-list__num {
  font-size: 3.5rem;
  font-weight: 700;
}
.editorial-list__content {
  flex: 1;
  border-left: 1px solid var(--line-gold);
  padding-left: var(--sp-6);
}
.editorial-list__title {
  margin: 0 0 var(--sp-2);
  font-family: var(--font-serif);
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--royal);
  letter-spacing: 0.01em;
  line-height: 1.3;
}
.editorial-list__desc {
  margin: 0;
  font-family: var(--font-serif);
  font-size: 1rem;
  line-height: 1.85;
  color: var(--ink-200);
  font-style: italic;
}
```

---

### 6.9 Table of Contents List（目录列表 — 金色引导点）

> 书籍式目录，缩进层级搭配金色引导点线（leader dots），章节数字+标题+页码。用于长文目录、画册导航、电子书章节目录。

```html
<nav class="toc" aria-label="目录">
  <p class="toc__header">Table of Contents</p>
  <p class="toc__subheader">目 录</p>
  <ol class="toc__list">
    <li class="toc__item">
      <span class="toc__chapter">01</span>
      <span class="toc__title"><a href="#">序章 · 品牌哲学</a></span>
      <span class="toc__dots" aria-hidden="true"></span>
      <span class="toc__page">008</span>
    </li>
    <li class="toc__item">
      <span class="toc__chapter">02</span>
      <span class="toc__title"><a href="#">匠心工艺</a></span>
      <span class="toc__dots" aria-hidden="true"></span>
      <span class="toc__page">032</span>
    </li>
    <li class="toc__item toc__item--sub">
      <span class="toc__title"><a href="#">— 皮革的语言</a></span>
      <span class="toc__dots" aria-hidden="true"></span>
      <span class="toc__page">045</span>
    </li>
    <li class="toc__item toc__item--sub">
      <span class="toc__title"><a href="#">— 金属的诗意</a></span>
      <span class="toc__dots" aria-hidden="true"></span>
      <span class="toc__page">062</span>
    </li>
    <li class="toc__item">
      <span class="toc__chapter">03</span>
      <span class="toc__title"><a href="#">经典系列</a></span>
      <span class="toc__dots" aria-hidden="true"></span>
      <span class="toc__page">080</span>
    </li>
    <li class="toc__item">
      <span class="toc__chapter">04</span>
      <span class="toc__title"><a href="#">全球工坊</a></span>
      <span class="toc__dots" aria-hidden="true"></span>
      <span class="toc__page">124</span>
    </li>
  </ol>
</nav>
```
```css
.toc {
  max-width: 480px;
  padding: var(--sp-8);
  background: var(--paper);
  border: 1px solid var(--line);
  position: relative;
}
.toc::before, .toc::after {
  content: '❦';
  display: block;
  text-align: center;
  color: var(--gold);
  font-size: 1.25rem;
  margin-bottom: var(--sp-4);
}
.toc::after { margin-bottom: 0; margin-top: var(--sp-4); }
.toc__header {
  margin: 0;
  font-family: var(--font-serif);
  font-size: 1.5rem;
  font-weight: 600;
  font-style: italic;
  color: var(--royal);
  text-align: center;
  letter-spacing: 0.05em;
}
.toc__subheader {
  margin: 0 0 var(--sp-6);
  font-family: var(--font-sans);
  font-size: 0.6875rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.3em;
  color: var(--gold-deep);
  text-align: center;
}
.toc__list {
  list-style: none;
  margin: 0;
  padding: 0;
}
.toc__item {
  display: flex;
  align-items: baseline;
  gap: var(--sp-2);
  padding: var(--sp-2) 0;
  font-family: var(--font-serif);
  font-size: 1rem;
}
.toc__item--sub {
  padding-left: var(--sp-7);
  font-size: 0.875rem;
  color: var(--ink-200);
  font-style: italic;
}
.toc__chapter {
  font-family: var(--font-mono);
  font-size: 0.6875rem;
  font-weight: 600;
  color: var(--gold-deep);
  min-width: 24px;
  letter-spacing: 0.05em;
}
.toc__title { flex-shrink: 0; }
.toc__title a {
  color: var(--ink-100);
  text-decoration: none;
  transition: color 0.2s ease;
}
.toc__title a:hover { color: var(--royal); }
.toc__item--sub .toc__title a { color: var(--ink-200); }
.toc__dots {
  flex: 1;
  border-bottom: 1px dotted var(--gold);
  margin: 0 var(--sp-1);
  transform: translateY(-3px);
  opacity: 0.5;
}
.toc__page {
  font-family: var(--font-mono);
  font-size: 0.75rem;
  color: var(--ink-300);
  flex-shrink: 0;
  letter-spacing: 0.05em;
}
```

---

### 6.10 Notification List（通知列表 — 已读/未读状态）

> 可点击的通知条目，未读项以金色圆点标识、浅金底色，已读项低调灰色。用于消息中心、系统通知、站内信列表。

```html
<ul class="notif-list">
  <li class="notif notif--unread">
    <a href="#" class="notif__link">
      <span class="notif__dot" aria-hidden="true"></span>
      <span class="notif__icon notif__icon--order">📦</span>
      <span class="notif__body">
        <span class="notif__text">
          <strong>您的订单 #FH-2026-0881</strong> 已发货，预计 3-5 个工作日送达。
        </span>
        <time class="notif__time">10 分钟前</time>
      </span>
    </a>
  </li>
  <li class="notif notif--unread">
    <a href="#" class="notif__link">
      <span class="notif__dot" aria-hidden="true"></span>
      <span class="notif__icon notif__icon--promo">✦</span>
      <span class="notif__body">
        <span class="notif__text">
          <strong>尊享会员专属预览</strong> — 秋季限量系列即将上线，提前 48 小时选购。
        </span>
        <time class="notif__time">2 小时前</time>
      </span>
    </a>
  </li>
  <li class="notif">
    <a href="#" class="notif__link">
      <span class="notif__icon notif__icon--system">ℹ</span>
      <span class="notif__body">
        <span class="notif__text">
          您的个人资料已成功更新。
        </span>
        <time class="notif__time">昨天</time>
      </span>
    </a>
  </li>
  <li class="notif notif--wine">
    <a href="#" class="notif__link">
      <span class="notif__dot notif__dot--wine" aria-hidden="true"></span>
      <span class="notif__icon notif__icon--alert">!</span>
      <span class="notif__body">
        <span class="notif__text">
          <strong>付款未完成</strong> — 订单将在 30 分钟后取消，请尽快完成支付。
        </span>
        <time class="notif__time">3 小时前</time>
      </span>
    </a>
  </li>
</ul>
```
```css
.notif-list {
  list-style: none;
  margin: 0;
  padding: 0;
  border: 1px solid var(--line);
  border-radius: var(--radius-lg);
  overflow: hidden;
}
.notif + .notif {
  border-top: 1px solid var(--line);
}
.notif__link {
  display: flex;
  align-items: flex-start;
  gap: var(--sp-3);
  padding: var(--sp-4) var(--sp-5);
  text-decoration: none;
  transition: background 0.2s ease;
  position: relative;
}
.notif__link:hover {
  background: var(--paper);
}
.notif--unread .notif__link {
  background: rgba(244,211,94,0.06);
}
.notif--unread .notif__link:hover {
  background: rgba(244,211,94,0.12);
}
.notif--wine .notif__link {
  background: rgba(216,49,91,0.04);
}
.notif__dot {
  position: absolute;
  left: var(--sp-2);
  top: 50%;
  transform: translateY(-50%);
  width: 8px;
  height: 8px;
  background: var(--gold);
  border-radius: 50%;
  flex-shrink: 0;
  box-shadow: 0 0 6px rgba(244,211,94,0.5);
}
.notif__dot--wine {
  background: var(--wine);
  box-shadow: 0 0 6px rgba(216,49,91,0.4);
}
.notif__icon {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1rem;
  flex-shrink: 0;
  background: var(--paper);
  color: var(--royal);
  border: 1px solid var(--line);
  margin-left: var(--sp-2);
}
.notif--unread .notif__icon {
  background: var(--gold);
  color: var(--royal);
  border-color: var(--gold);
}
.notif__icon--alert {
  background: var(--wine) !important;
  color: white !important;
  border-color: var(--wine) !important;
}
.notif__body { flex: 1; min-width: 0; }
.notif__text {
  display: block;
  font-family: var(--font-sans);
  font-size: 0.875rem;
  line-height: 1.6;
  color: var(--ink-200);
}
.notif--unread .notif__text {
  color: var(--ink-100);
}
.notif__text strong {
  font-weight: 600;
  color: var(--royal);
}
.notif__time {
  display: block;
  font-family: var(--font-mono);
  font-size: 0.6875rem;
  color: var(--ink-300);
  margin-top: var(--sp-1);
  letter-spacing: 0.05em;
}
```

---

### 6.11 Breadcrumb List（面包屑导航 — 金色分隔符）

> 层级导航，金色斜杠或箭头分隔，当前页皇家蓝加粗不可点击。用于页面层级指示。

```html
<nav aria-label="面包屑">
  <ol class="breadcrumb">
    <li class="breadcrumb__item">
      <a href="#" class="breadcrumb__link">首页</a>
    </li>
    <li class="breadcrumb__item">
      <span class="breadcrumb__sep" aria-hidden="true">/</span>
      <a href="#" class="breadcrumb__link">产品系列</a>
    </li>
    <li class="breadcrumb__item">
      <span class="breadcrumb__sep" aria-hidden="true">/</span>
      <a href="#" class="breadcrumb__link">手袋</a>
    </li>
    <li class="breadcrumb__item breadcrumb__item--current">
      <span class="breadcrumb__sep" aria-hidden="true">/</span>
      <span class="breadcrumb__current">Signature Tote · 经典托特包</span>
    </li>
  </ol>
</nav>
```
```css
.breadcrumb {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 0;
}
.breadcrumb__item {
  display: flex;
  align-items: center;
  font-family: var(--font-sans);
  font-size: 0.8125rem;
}
.breadcrumb__sep {
  color: var(--gold);
  margin: 0 var(--sp-3);
  font-weight: 300;
  font-size: 0.75rem;
  /* Arrow variant: use '›' instead of '/' */
}
.breadcrumb__link {
  color: var(--ink-200);
  text-decoration: none;
  transition: color 0.2s ease;
  padding-bottom: 2px;
  border-bottom: 1px solid transparent;
}
.breadcrumb__link:hover {
  color: var(--royal);
  border-bottom-color: var(--gold);
}
.breadcrumb__current {
  color: var(--royal);
  font-weight: 600;
  font-family: var(--font-serif);
  font-size: 0.875rem;
  font-style: italic;
}
/* Small variant */
.breadcrumb--sm .breadcrumb__item { font-size: 0.6875rem; }
.breadcrumb--sm .breadcrumb__sep { margin: 0 var(--sp-2); }
/* Arrow separator variant */
.breadcrumb--arrow .breadcrumb__sep {
  content: '›';
  font-size: 1rem;
  color: var(--gold);
  line-height: 1;
}
```

---

### 6.12 Price List / Menu（价目表/菜单 — 金色引导点+衬线斜体价格）

> 餐厅菜单、服务价目表、产品定价页。品名+金色引导点+Garamond 斜体价格，呈现米其林餐厅式菜单排版。

```html
<div class="price-list">
  <h3 class="price-list__heading">
    <span class="price-list__ornament">❦</span>
    Signatures · 招牌之作
    <span class="price-list__ornament">❦</span>
  </h3>
  <ul class="price-list__items">
    <li class="price-item">
      <span class="price-item__name">
        <span class="price-item__title">Wagyu A5 Tenderloin</span>
        <span class="price-item__desc">A5和牛菲力 · 黑松露汁 · 时蔬</span>
      </span>
      <span class="price-item__dots" aria-hidden="true"></span>
      <span class="price-item__price">¥1,888</span>
    </li>
    <li class="price-item price-item--featured">
      <span class="price-item__badge">Chef's Selection</span>
      <span class="price-item__name">
        <span class="price-item__title">Lobster Bisque Royale</span>
        <span class="price-item__desc">皇家龙虾浓汤 · 干邑奶油 · 金箔点缀</span>
      </span>
      <span class="price-item__dots" aria-hidden="true"></span>
      <span class="price-item__price">¥388</span>
    </li>
    <li class="price-item">
      <span class="price-item__name">
        <span class="price-item__title">Truffle Risotto</span>
        <span class="price-item__desc">黑松露烩饭 · 帕玛森 · 24个月陈酿香醋</span>
      </span>
      <span class="price-item__dots" aria-hidden="true"></span>
      <span class="price-item__price">¥268</span>
    </li>
    <li class="price-item price-item--unavailable">
      <span class="price-item__name">
        <span class="price-item__title">Foie Gras Terrine</span>
       無
        <span class="price-item__desc">鹅肝酱冻 · 无花果酱 · 布里欧修</span>
      </span>
      <span class="price-item__dots" aria-hidden="true"></span>
      <span class="price-item__price price-item__price--strike">¥228</span>
    </li>
  </ul>
</div>
```
```css
.price-list {
  padding: var(--sp-7) var(--sp-8);
  background: var(--cream);
  border: 1px solid var(--line-gold);
}
.price-list__heading {
  margin: 0 0 var(--sp-6);
  font-family: var(--font-serif);
  font-size: 1.375rem;
  font-weight: 600;
  font-style: italic;
  color: var(--royal);
  text-align: center;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--sp-4);
}
.price-list__ornament {
  color: var(--gold);
  font-size: 1rem;
  font-style: normal;
}
.price-list__items {
  list-style: none;
  margin: 0;
  padding: 0;
}
.price-item {
  display: flex;
  align-items: baseline;
  gap: var(--sp-2);
  padding: var(--sp-3) 0;
  position: relative;
}
.price-item + .price-item {
  border-top: 1px dotted var(--line-gold);
}
.price-item--featured {
  background: rgba(244,211,94,0.06);
  margin: var(--sp-2) calc(-1 * var(--sp-4));
  padding: var(--sp-3) var(--sp-4);
  border-top: none;
  border-left: 2px solid var(--gold);
}
.price-item__badge {
  position: absolute;
  top: -8px;
  right: 0;
  font-family: var(--font-sans);
  font-size: 0.5625rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: white;
  background: var(--royal);
  padding: 2px 8px;
  border-radius: var(--radius-sm);
}
.price-item__name {
  flex-shrink: 0;
  max-width: 65%;
}
.price-item__title {
  display: block;
  font-family: var(--font-serif);
  font-size: 1.0625rem;
  font-weight: 600;
  color: var(--ink);
  line-height: 1.4;
}
.price-item__desc {
  display: block;
  font-family: var(--font-sans);
  font-size: 0.75rem;
  color: var(--ink-300);
  margin-top: 2px;
  line-height: 1.4;
}
.price-item__dots {
  flex: 1;
  border-bottom: 2px dotted var(--gold);
  opacity: 0.4;
  transform: translateY(-3px);
  margin: 0 var(--sp-1);
}
.price-item__price {
  font-family: var(--font-serif);
  font-size: 1.25rem;
  font-weight: 600;
  font-style: italic;
  color: var(--royal);
  flex-shrink: 0;
  min-width: 70px;
  text-align: right;
}
.price-item--unavailable {
  opacity: 0.4;
}
.price-item--unavailable .price-item__title {
  text-decoration: line-through;
  text-decoration-color: var(--wine);
}
.price-item__price--strike {
  text-decoration: line-through;
  color: var(--ink-300);
}
```

---

### 6.13 Feature Checklist（功能对比清单 — 金色对勾/灰色叉号）

> 用于定价方案对比、免费/Pro版功能清单。金色对勾标识包含项，灰色叉号标识不包含项，酒红警示标记需注意的项目。

```html
<div class="feature-check">
  <h4 class="feature-check__title">
    <span class="feature-check__plan feature-check__plan--pro">Pro</span>
    专业版包含功能
  </h4>
  <ul class="feature-check__list">
    <li class="feature-check__item feature-check__item--yes">
      <span class="feature-check__icon">✓</span>
      <span>无限项目数量</span>
    </li>
    <li class="feature-check__item feature-check__item--yes">
      <span class="feature-check__icon">✓</span>
      <span>全部高级模板</span>
    </li>
    <li class="feature-check__item feature-check__item--yes">
      <span class="feature-check__icon">✓</span>
      <span>自定义品牌域名</span>
    </li>
    <li class="feature-check__item feature-check__item--yes">
      <span class="feature-check__icon feature-check__icon--gold">★</span>
      <span>专属客户成功经理 <em>(VIP)</em></span>
    </li>
    <li class="feature-check__item feature-check__item--no">
      <span class="feature-check__icon">✕</span>
      <span>Feihong 水印</span>
    </li>
    <li class="feature-check__item feature-check__item--warn">
      <span class="feature-check__icon feature-check__icon--wine">!</span>
      <span>API 调用上限：10,000次/月</span>
    </li>
  </ul>
</div>
```
```css
.feature-check {
  padding: var(--sp-6);
  background: var(--cream);
  border: 1px solid var(--line);
  border-top: 3px solid var(--gold);
  border-radius: var(--radius-lg);
}
.feature-check__title {
  margin: 0 0 var(--sp-5);
  font-family: var(--font-serif);
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--ink);
  display: flex;
  align-items: center;
  gap: var(--sp-3);
}
.feature-check__plan {
  font-family: var(--font-sans);
  font-size: 0.625rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  padding: 3px 10px;
  border-radius: var(--radius-full);
}
.feature-check__plan--pro {
  background: var(--gold);
  color: var(--royal);
}
.feature-check__plan--free {
  background: var(--ink-300);
  color: white;
}
.feature-check__list {
  list-style: none;
  margin: 0;
  padding: 0;
}
.feature-check__item {
  display: flex;
  align-items: center;
  gap: var(--sp-3);
  padding: var(--sp-2) 0;
  font-family: var(--font-sans);
  font-size: 0.875rem;
  color: var(--ink-100);
  line-height: 1.5;
}
.feature-check__icon {
  width: 22px;
  height: 22px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.6875rem;
  font-weight: 700;
  flex-shrink: 0;
}
/* Included / Yes */
.feature-check__item--yes .feature-check__icon {
  background: var(--gold);
  color: var(--royal);
}
.feature-check__item--yes {
  color: var(--ink-100);
}
/* VIP / Star feature */
.feature-check__item--yes .feature-check__icon--gold {
  background: linear-gradient(135deg, var(--gold) 0%, var(--gold-deep) 100%);
  color: white;
  font-size: 0.625rem;
}
.feature-check__item em {
  font-family: var(--font-serif);
  font-style: italic;
  color: var(--gold-deep);
  font-size: 0.8125rem;
}
/* Not included / No */
.feature-check__item--no .feature-check__icon {
  background: transparent;
  color: var(--ink-300);
  border: 1px solid var(--ink-300);
}
.feature-check__item--no {
  color: var(--ink-300);
}
/* Warning */
.feature-check__item--warn .feature-check__icon--wine {
  background: var(--wine);
  color: white;
}
.feature-check__item--warn {
  color: var(--wine);
}
```

---

### 6.14 Social Link List（社交链接列表 — 金色悬停效果）

> 社交平台链接列表，图标+用户名，金色下划线/高亮悬停效果。用于页脚、作者简介、联系区域。

```html
<ul class="social-list">
  <li class="social-list__item">
    <a href="#" class="social-link">
      <span class="social-link__icon" aria-hidden="true">
        <svg viewBox="0 0 24 24" fill="currentColor" width="18" height="18">
          <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
        </svg>
      </span>
      <span class="social-link__handle">@feihong.official</span>
      <span class="social-link__arrow">→</span>
    </a>
  </li>
  <li class="social-list__item">
    <a href="#" class="social-link">
      <span class="social-link__icon" aria-hidden="true">
        <svg viewBox="0 0 24 24" fill="currentColor" width="18" height="18">
          <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
        </svg>
      </span>
      <span class="social-link__handle">@feihong.studio</span>
      <span class="social-link__arrow">→</span>
    </a>
  </li>
  <li class="social-list__item">
    <a href="#" class="social-link">
      <span class="social-link__icon" aria-hidden="true">
        <svg viewBox="0 0 24 24" fill="currentColor" width="18" height="18">
          <path d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-5.2 1.74 2.89 2.89 0 0 1 2.31-4.64 2.93 2.93 0 0 1 .88.13V9.4a6.84 6.84 0 0 0-1-.05A6.33 6.33 0 0 0 5.8 20.1a6.34 6.34 0 0 0 10.86-4.43V8.88a8.16 8.16 0 0 0 4.77 1.52V7a4.85 4.85 0 0 1-1.84-.31z"/>
        </svg>
      </span>
      <span class="social-link__handle">飞鸿设计</span>
      <span class="social-link__arrow">→</span>
    </a>
  </li>
  <li class="social-list__item">
    <a href="#" class="social-link">
      <span class="social-link__icon social-link__icon--wine" aria-hidden="true">@</span>
      <span class="social-link__handle">hello@feihong.studio</span>
      <span class="social-link__arrow">→</span>
    </a>
  </li>
</ul>
```
```css
.social-list {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: var(--sp-1);
}
.social-list--horizontal {
  flex-direction: row;
  flex-wrap: wrap;
  gap: var(--sp-3);
}
.social-link {
  display: flex;
  align-items: center;
  gap: var(--sp-3);
  padding: var(--sp-3) var(--sp-4);
  text-decoration: none;
  color: var(--ink-200);
  border: 1px solid var(--line);
  border-radius: var(--radius-md);
  transition: all 0.3s ease;
  background: var(--cream);
  position: relative;
  overflow: hidden;
}
.social-link::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 3px;
  background: var(--gold);
  transform: scaleY(0);
  transition: transform 0.3s ease;
}
.social-link:hover {
  color: var(--royal);
  border-color: var(--gold);
  background: white;
  transform: translateX(4px);
  box-shadow: 0 4px 12px rgba(244,211,94,0.15);
}
.social-link:hover::before {
  transform: scaleY(1);
}
.social-link__icon {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--paper);
  color: var(--royal);
  flex-shrink: 0;
  font-size: 0.875rem;
  font-family: var(--font-serif);
  font-weight: 600;
  transition: all 0.3s ease;
}
.social-link:hover .social-link__icon {
  background: var(--gold);
  color: var(--royal);
}
.social-link__icon--wine {
  font-style: italic;
}
.social-link:hover .social-link__icon--wine {
  background: var(--wine);
  color: white;
}
.social-link__handle {
  flex: 1;
  font-family: var(--font-sans);
  font-size: 0.875rem;
  font-weight: 500;
  letter-spacing: 0.01em;
}
.social-link__arrow {
  font-size: 1rem;
  color: var(--gold);
  opacity: 0;
  transform: translateX(-8px);
  transition: all 0.3s ease;
}
.social-link:hover .social-link__arrow {
  opacity: 1;
  transform: translateX(0);
}
/* Horizontal variant: icon only */
.social-list--horizontal .social-link {
  padding: var(--sp-2);
  width: 40px;
  height: 40px;
  justify-content: center;
  border-radius: 50%;
}
.social-list--horizontal .social-link__handle,
.social-list--horizontal .social-link__arrow {
  display: none;
}
.social-list--horizontal .social-link:hover {
  transform: translateY(-2px);
}
```

---

## 7. Tags & Chips 标签与筹码

### 7.1 Tag / Chip Group（标签组 — 可移除/分类/筛选）

> 多功能标签组件。支持可移除标签（金色关闭按钮）、分类标签（皇家蓝/金/酒红/奶油四色变体）、筛选标签（选中/未选中状态）。用于文章标签、筛选器、商品属性、关键词。

```html
<!-- 分类标签（纯色变体） -->
<div class="tag-group">
  <span class="tag tag--royal">品牌设计</span>
  <span class="tag tag--gold">限量发售</span>
  <span class="tag tag--wine">仅剩 3 件</span>
  <span class="tag tag--cream">手工制作</span>
  <span class="tag tag--outline">新品</span>
</div>

<!-- 可移除标签 -->
<div class="tag-group">
  <span class="tag tag--removable">
    巴黎工坊
    <button class="tag__close" aria-label="移除">×</button>
  </span>
  <span class="tag tag--removable tag--gold">
    头层牛皮
    <button class="tag__close" aria-label="移除">×</button>
  </span>
  <span class="tag tag--removable tag--royal">
    2026秋季
    <button class="tag__close" aria-label="移除">×</button>
  </span>
</div>

<!-- 筛选标签（可切换状态） -->
<div class="tag-group tag-group--filter" role="group" aria-label="筛选">
  <button class="tag tag--filter tag--filter-active">全部</button>
  <button class="tag tag--filter">手袋</button>
  <button class="tag tag--filter">钱包</button>
  <button class="tag tag--filter">配饰</button>
  <button class="tag tag--filter">定制</button>
</div>

<!-- 尺寸/价格区间标签 -->
<div class="tag-group">
  <span class="tag tag--size">S</span>
  <span class="tag tag--size tag--size-active">M</span>
  <span class="tag tag--size">L</span>
  <span class="tag tag--size">XL</span>
</div>

<!-- 状态标签 -->
<div class="tag-group">
  <span class="tag tag--status tag--status-success">● 已发货</span>
  <span class="tag tag--status tag--status-pending">● 处理中</span>
  <span class="tag tag--status tag--status-error">● 已取消</span>
</div>
```
```css
.tag-group {
  display: flex;
  flex-wrap: wrap;
  gap: var(--sp-2);
  align-items: center;
}
/* Base tag */
.tag {
  display: inline-flex;
  align-items: center;
  gap: var(--sp-1);
  font-family: var(--font-sans);
  font-size: 0.75rem;
  font-weight: 500;
  padding: 5px 12px;
  border-radius: var(--radius-full);
  border: 1px solid transparent;
  line-height: 1.4;
  white-space: nowrap;
  transition: all 0.2s ease;
  cursor: default;
  user-select: none;
}

/* === Color Variants === */
.tag--royal {
  background: var(--royal);
  color: white;
}
.tag--gold {
  background: var(--gold);
  color: var(--royal);
  font-weight: 600;
}
.tag--wine {
  background: var(--wine);
  color: white;
}
.tag--cream {
  background: var(--cream);
  color: var(--royal);
  border-color: var(--line-gold);
}
.tag--outline {
  background: transparent;
  color: var(--royal);
  border-color: var(--royal);
}
.tag--outline:hover {
  background: var(--royal);
  color: white;
}

/* === Removable Tag === */
.tag--removable {
  background: var(--paper);
  color: var(--ink-100);
  border-color: var(--line);
  padding-right: 4px;
}
.tag--removable.tag--gold {
  background: rgba(244,211,94,0.15);
  border-color: var(--gold);
  color: var(--gold-deep);
}
.tag--removable.tag--royal {
  background: rgba(10,36,99,0.08);
  border-color: var(--royal);
  color: var(--royal);
}
.tag__close {
  width: 18px;
  height: 18px;
  border-radius: 50%;
  border: none;
  background: var(--gold);
  color: var(--royal);
  font-size: 0.8125rem;
  font-weight: 700;
  line-height: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  padding: 0;
  margin-left: 2px;
  transition: all 0.2s ease;
}
.tag__close:hover {
  background: var(--royal);
  color: var(--gold);
  transform: scale(1.15);
}
.tag--removable.tag--royal .tag__close {
  background: var(--royal);
  color: white;
}
.tag--removable.tag--royal .tag__close:hover {
  background: var(--wine);
  color: white;
}

/* === Filter Tag (toggle) === */
.tag-group--filter {
  gap: var(--sp-1);
}
.tag--filter {
  background: transparent;
  color: var(--ink-200);
  border-color: var(--line);
  cursor: pointer;
  padding: 6px 16px;
  font-size: 0.8125rem;
}
.tag--filter:hover {
  border-color: var(--gold);
  color: var(--royal);
}
.tag--filter-active {
  background: var(--royal);
  color: white;
  border-color: var(--royal);
  position: relative;
}
.tag--filter-active::after {
  content: '✓';
  margin-left: 4px;
  font-size: 0.625rem;
  color: var(--gold);
}

/* === Size Tag === */
.tag--size {
  width: 36px;
  height: 36px;
  padding: 0;
  justify-content: center;
  border-radius: var(--radius-md);
  background: var(--cream);
  color: var(--ink-100);
  border-color: var(--line);
  font-family: var(--font-serif);
  font-size: 0.9375rem;
  font-weight: 600;
  cursor: pointer;
}
.tag--size:hover {
  border-color: var(--gold);
}
.tag--size-active {
  background: var(--royal);
  color: var(--gold);
  border-color: var(--royal);
}

/* === Status Tag === */
.tag--status {
  font-size: 0.6875rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  padding: 4px 10px;
  background: var(--paper);
}
.tag--status-success {
  color: var(--royal);
}
.tag--status-success::first-letter { color: #2d8a4e; }
.tag--status-pending {
  color: var(--gold-deep);
}
.tag--status-pending::first-letter { color: var(--gold-deep); }
.tag--status-error {
  color: var(--wine);
}
.tag--status-error::first-letter { color: var(--wine); }

/* === Tag sizes === */
.tag--sm { font-size: 0.625rem; padding: 3px 8px; }
.tag--lg { font-size: 0.875rem; padding: 8px 18px; }

/* === Editorial Tag (luxury serif) === */
.tag--editorial {
  font-family: var(--font-serif);
  font-size: 0.8125rem;
  font-style: italic;
  font-weight: 500;
  background: transparent;
  color: var(--gold-deep);
  border: none;
  padding: 2px 0;
  letter-spacing: 0.05em;
}
.tag--editorial::before { content: '— '; color: var(--gold); }
.tag--editorial::after { content: ' —'; color: var(--gold); }
```

---

## 8. Usage Guidelines 使用指南

| 组件 | 使用场景 | 注意事项 |
|------|---------|---------|
| Gold Dot List (6.1) | 通用无序列表、品牌特性 | 品牌签名式，不要与其他圆点样式混用 |
| Serif Number List (6.2) | 教程步骤、操作流程 | 数字前导零，适合 ≤10 项的列表 |
| Check List (6.3) | 包含项、已完成项 | 金色圆形背景，对勾为皇家蓝 |
| Definition List (6.4) | 产品规格、元数据、属性 | 金色大写标签 + 皇家蓝衬线数值 |
| Timeline (6.5) | 活动流、操作日志、订单追踪 | 金色轴线 + 圆点，酒红点表示重要事件 |
| Review (6.6) | 产品评价、客户证言 | Garamond斜体姓名、金色星级、装饰引号 |
| Icon List (6.7) | 导航、特性、目录 | 四种图标，根据语境选择颜色 |
| Editorial Numbered List (6.8) | 杂志专题、精选榜单 | 大尺寸斜体罗马/阿拉伯数字，适合 ≤5 项 |
| Table of Contents (6.9) | 长文目录、画册章节 | 金色引导点，支持子级缩进 |
| Notification List (6.10) | 消息中心、站内信 | 未读金底+金点，已读灰调 |
| Breadcrumb (6.11) | 页面层级导航 | 金色分隔符，当前页皇家蓝斜体 |
| Price List (6.12) | 菜单、价目表、定价页 | 金色引导点 + Garamond斜体价格 |
| Feature Checklist (6.13) | 方案对比、功能清单 | 金勾=包含，灰叉=不含，酒红叹号=注意 |
| Social Link List (6.14) | 社交链接、联系方式 | 金色悬停动画，箭头滑入效果 |
| Tag Group (7.1) | 标签、筛选器、属性 | 四色变体对应不同语义：蓝=主类/金=奢华/酒红=警示/奶油=中性 |

---

> *"Luxury is in each detail."* — Hubert de Givenchy
> 奢华藏于每一处细节。
