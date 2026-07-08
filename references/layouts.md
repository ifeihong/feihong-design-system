# Feihong Design System · Layout Patterns
# 飞鸿品牌设计系统 · 16种布局模式

> 每个 section 选择不同的布局模式，避免页面单调重复。
> 布局搭配原则：密→疏→密→疏，强→弱→强，形成呼吸节奏。
> 所有布局使用 brand-dna 的 CSS 变量和 components.md 的组件。

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
    <div class="avatar avatar-xl"><img src="assets/avatar.jpg" alt="飞鸿"></div>
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
        <a href="mailto:hello@feihong.art" class="btn btn-gold btn-lg">发送邮件</a>
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

*Layout Patterns v1.0 · Feihong Design System*
