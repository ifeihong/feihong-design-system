# Feihong Design System — Cards
# N°06 · 卡片
> Feature cards, project cards, stat cards, testimonials, editorial cards, and product cards.
> 功能卡片、项目卡片、数据卡片、推荐卡片、杂志编辑卡和产品展示卡。
> Part of Feihong Design System v7.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 5. Cards 卡片

### 5.1 Feature Card（功能/特色卡片）

```html
<div class="card card-feature">
  <div class="card-icon">✦</div>
  <h3 class="card-title">品牌设计</h3>
  <p class="card-desc">从logo到完整视觉体系，打造有记忆点的个人品牌。</p>
  <a href="#" class="card-link">了解更多 →</a>
</div>
```
```css
.card {
  background: #fff;
  border-radius: var(--r-lg);
  padding: var(--sp-6);
  transition: all var(--t-base);
  position: relative;
  overflow: hidden;
}
.card-feature {
  border: 1px solid var(--cream-200);
}
.card-feature::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--royal), var(--gold), var(--wine));
  opacity: 0;
  transition: opacity var(--t-base);
}
.card-feature:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-lg);
  border-color: var(--gold-200);
}
.card-feature:hover::before { opacity: 1; }
.card-icon {
  font-size: 1.75rem;
  color: var(--gold);
  margin-bottom: var(--sp-4);
  display: inline-flex;
  width: 48px;
  height: 48px;
  align-items: center;
  justify-content: center;
  background: var(--gold-50);
  border-radius: var(--r-md);
}
.card-title {
  font-family: var(--font-serif);
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--ink);
  margin: 0 0 var(--sp-2);
}
.card-desc {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  line-height: 1.65;
  color: var(--ink-200);
  margin: 0 0 var(--sp-4);
}
.card-link {
  font-family: var(--font-sans);
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--royal);
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: 4px;
  transition: gap var(--t-fast);
}
.card-link:hover {
  gap: 8px;
  color: var(--wine);
}
```

### 5.2 Project Card（项目/作品集卡片）

```html
<div class="card card-project">
  <div class="card-project-image">
    <img src="project.jpg" alt="项目封面">
    <div class="card-project-overlay">
      <span class="badge badge-gold">查看案例</span>
    </div>
  </div>
  <div class="card-project-body">
    <span class="caption-text">2024 · 品牌视觉</span>
    <h3 class="card-title">某某科技品牌升级</h3>
    <p class="card-desc">从传统到现代的品牌视觉重塑</p>
  </div>
</div>
```
```css
.card-project {
  padding: 0;
  border: none;
  background: #fff;
  overflow: hidden;
  cursor: pointer;
}
.card-project-image {
  position: relative;
  aspect-ratio: 4/3;
  overflow: hidden;
  background: var(--royal-50);
}
.card-project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform var(--t-slow);
}
.card-project:hover .card-project-image img {
  transform: scale(1.05);
}
.card-project-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(10,36,99,0.7), rgba(10,36,99,0.3));
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity var(--t-base);
}
.card-project:hover .card-project-overlay { opacity: 1; }
.card-project-body { padding: var(--sp-5); }
```

### 5.3 Stat Card（数据/统计卡片）

```html
<div class="stat-card">
  <span class="stat-number">8+</span>
  <span class="stat-label">年设计经验</span>
</div>
```
```css
.stat-card {
  text-align: center;
  padding: var(--sp-6) var(--sp-4);
  position: relative;
}
.stat-card::after {
  content: '';
  position: absolute;
  right: 0;
  top: 20%;
  height: 60%;
  width: 1px;
  background: var(--cream-200);
}
.stat-card:last-child::after { display: none; }
.stat-number {
  font-family: var(--font-serif);
  font-size: clamp(2rem, 4vw, 3.5rem);
  font-weight: 700;
  color: var(--royal);
  line-height: 1;
  display: block;
}
.stat-label {
  font-family: var(--font-sans);
  font-size: 0.875rem;
  color: var(--ink-300);
  margin-top: var(--sp-2);
  display: block;
}
```

### 5.4 Testimonial Card（推荐/口碑卡片）

```html
<div class="card card-testimonial">
  <div class="testimonial-stars">★★★★★</div>
  <p class="testimonial-text">飞鸿的设计有一种独特的温度，既专业又有艺术感。</p>
  <div class="testimonial-author">
    <div class="author-avatar">张</div>
    <div>
      <div class="author-name">张先生</div>
      <div class="author-title">创业公司CEO</div>
    </div>
  </div>
</div>
```
```css
.card-testimonial {
  background: var(--cream);
  border: 1px solid var(--cream-200);
}
.testimonial-stars { color: var(--gold); font-size: 1rem; letter-spacing: 2px; margin-bottom: var(--sp-3); }
.testimonial-text {
  font-family: var(--font-display);
  font-size: 1.0625rem;
  font-style: italic;
  line-height: 1.7;
  color: var(--ink-100);
  margin: 0 0 var(--sp-5);
}
.testimonial-author { display: flex; align-items: center; gap: var(--sp-3); }
.author-avatar {
  width: 40px; height: 40px; border-radius: 50%;
  background: var(--royal); color: #fff;
  display: flex; align-items: center; justify-content: center;
  font-family: var(--font-serif); font-weight: 600;
}
.author-name { font-family: var(--font-sans); font-weight: 600; font-size: 0.9375rem; color: var(--ink); }
.author-title { font-family: var(--font-sans); font-size: 0.8125rem; color: var(--ink-300); }
```

### 5.5 Dark Panel Card（深色面板 — 节奏打破）

```html
<div class="dark-panel">
  <span class="eyebrow" style="background:rgba(244,211,94,0.15);color:var(--gold);">深度合作</span>
  <h2 style="color:#fff;">准备好开始你的项目了吗？</h2>
  <p style="color:rgba(255,255,255,0.7);">让我们一起创造有温度的设计。</p>
  <a href="#" class="btn btn-gold">立即联系</a>
</div>
```
```css
.dark-panel {
  background: radial-gradient(ellipse at top left, var(--royal-700) 0%, var(--ink) 70%);
  border-radius: var(--r-xl);
  padding: clamp(var(--sp-8), 8vw, var(--sp-12));
  color: #fff;
  position: relative;
  overflow: hidden;
}
.dark-panel::before {
  content: '';
  position: absolute;
  width: 400px; height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(244,211,94,0.08) 0%, transparent 70%);
  top: -100px; right: -100px;
}
.dark-panel h2 {
  font-family: var(--font-serif);
  font-size: clamp(1.75rem, 3.5vw, 2.75rem);
  color: #fff;
  margin: var(--sp-3) 0 var(--sp-4);
}
.dark-panel p {
  font-family: var(--font-sans);
  font-size: 1.0625rem;
  color: rgba(255,255,255,0.7);
  line-height: 1.7;
  margin: 0 0 var(--sp-6);
  max-width: 500px;
}
```

---

---

## 34. 卡片组件扩展变体（3种新变体）

在原有 5 种卡片基础上，新增杂志编辑风、编号主导风、引用风三种变体。

### 34.1 杂志编辑风 .feature-card.editorial

大号编号作为底层装饰，图片溢出卡片边界，衬线大标题配金色边线。

```html
<article class="feature-card editorial">
  <span class="card-number">01</span>
  <div class="card-image-wrap">
    <img src="https://images.unsplash.com/photo-1544947950-fa07a98d237f?w=500&h=300&fit=crop" alt="书籍">
  </div>
  <div class="card-body">
    <span class="card-tag">随笔</span>
    <h3>关于阅读这件事</h3>
    <p>翻开一本旧书，就像推开一扇通往另一个时代的门。纸张的气味、排版的节奏、批注的痕迹……</p>
    <a href="#" class="card-link">阅读全文</a>
  </div>
</article>
```

```css
.feature-card.editorial {
  position: relative;
  background: #fff;
  padding: var(--sp-8);
  box-shadow: var(--shadow-lg);
  border-top: 3px solid var(--gold);
  overflow: visible;
  max-width: 480px;
}

.feature-card.editorial .card-number {
  position: absolute;
  top: var(--sp-4);
  right: var(--sp-5);
  font-family: var(--font-serif);
  font-size: 6rem;
  font-weight: 700;
  color: var(--cream-100);
  line-height: 1;
  z-index: 0;
  user-select: none;
}

.feature-card.editorial .card-image-wrap {
  margin: calc(-1 * var(--sp-8)) calc(-1 * var(--sp-8)) var(--sp-5);
  height: 220px;
  overflow: hidden;
}

.feature-card.editorial .card-image-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform var(--t-slow);
}

.feature-card.editorial:hover .card-image-wrap img {
  transform: scale(1.05);
}

.feature-card.editorial .card-body {
  position: relative;
  z-index: 1;
}

.feature-card.editorial .card-tag {
  display: inline-block;
  font-family: var(--font-sans);
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--gold-700);
  margin-bottom: var(--sp-2);
}

.feature-card.editorial h3 {
  font-family: var(--font-serif);
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--royal);
  margin: 0 0 var(--sp-3);
  line-height: 1.2;
}

.feature-card.editorial p {
  font-family: var(--font-sans);
  font-size: 0.95rem;
  line-height: 1.7;
  color: var(--ink-200);
  margin: 0 0 var(--sp-4);
}

.feature-card.editorial .card-link {
  font-family: var(--font-serif);
  font-style: italic;
  color: var(--royal);
  text-decoration: none;
  border-bottom: 1px solid var(--gold);
  padding-bottom: 2px;
  transition: color var(--t-fast);
}

.feature-card.editorial .card-link:hover {
  color: var(--wine);
}
```

### 34.2 编号主导 .feature-card.numbered

左侧巨大半透明衬线数字，右侧为文字内容，数字形成强烈视觉锚点。

```html
<article class="feature-card numbered">
  <span class="card-big-num">01</span>
  <div class="card-content">
    <h3>品牌理念</h3>
    <p>以东方美学为根基，融合古典印刷的庄重与当代设计的克制，每一个细节都经得起时间的审视。</p>
  </div>
</article>

<article class="feature-card numbered">
  <span class="card-big-num">02</span>
  <div class="card-content">
    <h3>工艺精神</h3>
    <p>字体间距的微调、色彩饱和度的反复校准、阴影层次的耐心堆叠，追求的是像素级的完美。</p>
  </div>
</article>
```

```css
.feature-card.numbered {
  display: flex;
  align-items: flex-start;
  gap: var(--sp-6);
  padding: var(--sp-6) 0;
  border-bottom: 1px solid var(--cream-200);
  max-width: 600px;
}

.feature-card.numbered .card-big-num {
  font-family: var(--font-serif);
  font-size: 3.5rem;
  font-weight: 700;
  color: var(--cream-200);
  line-height: 1;
  flex-shrink: 0;
  min-width: 4.5rem;
  transition: color var(--t-base);
}

.feature-card.numbered:hover .card-big-num {
  color: var(--gold);
}

.feature-card.numbered .card-content h3 {
  font-family: var(--font-serif);
  font-size: 1.35rem;
  font-weight: 700;
  color: var(--royal);
  margin: 0 0 var(--sp-2);
}

.feature-card.numbered .card-content p {
  font-family: var(--font-sans);
  font-size: 0.95rem;
  line-height: 1.7;
  color: var(--ink-200);
  margin: 0;
}
```

### 34.3 引用风 .feature-card.quote-style

上方大金色引号，中间衬线斜体文字，底部手写签名式落款。

```html
<article class="feature-card quote-style">
  <span class="card-quote-mark">&ldquo;</span>
  <blockquote>
    设计是一种从容的表达，它不喧哗，不张扬，却在每一个细节处诉说着对品质的坚持与对使用者的尊重。
  </blockquote>
  <div class="card-signature">飞鸿</div>
</article>
```

```css
.feature-card.quote-style {
  position: relative;
  background: var(--cream);
  padding: var(--sp-8) var(--sp-8) var(--sp-6);
  max-width: 520px;
  text-align: center;
  border: 1px solid var(--cream-200);
}

.feature-card.quote-style .card-quote-mark {
  font-family: var(--font-serif);
  font-size: 5rem;
  line-height: 0.6;
  color: var(--gold);
  display: block;
  margin-bottom: var(--sp-2);
}

.feature-card.quote-style blockquote {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 1.2rem;
  line-height: 1.8;
  color: var(--ink);
  margin: 0 0 var(--sp-5);
  padding: 0;
}

.feature-card.quote-style .card-signature {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 1.5rem;
  color: var(--ink-200);
  position: relative;
  display: inline-block;
}

.feature-card.quote-style .card-signature::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 10%;
  width: 80%;
  height: 1px;
  background: var(--gold);
  transform: rotate(-2deg);
}
```

---

## 50. Cards 卡片类

### 50.1 Luxury Product Card 奢华产品卡

产品卡片，图片区域有金色角框装饰hover显现，底部产品名衬线大字，价格金色等宽字体，"Add to Bag"按钮滑入效果，奢侈品电商风格。

```html
<div class="product-card">
  <div class="pc-img"><div class="pc-corners"><span></span><span></span><span></span><span></span></div><div class="pc-placeholder">Parfum</div></div>
  <div class="pc-info"><h3 class="pc-name">Noir Élégance</h3><p class="pc-desc">Eau de Parfum · 50ml</p><div class="pc-row"><span class="pc-price">¥1,680</span><button class="pc-add">Add to Bag</button></div></div>
</div>
```
```css
.product-card { background:var(--cream); border-radius:var(--r-lg); overflow:hidden; font-family:var(--font-sans); transition:all var(--t-base); max-width:300px; border:1px solid var(--cream-200); }
.product-card:hover { transform:translateY(-6px); box-shadow:var(--shadow-xl); border-color:var(--gold-200); }
.pc-img { aspect-ratio:4/5; background:linear-gradient(135deg,var(--royal-800),var(--royal)); position:relative; display:flex; align-items:center; justify-content:center; overflow:hidden; }
.pc-placeholder { font-family:var(--font-display); font-style:italic; font-size:1.5rem; color:rgba(244,211,94,0.3); letter-spacing:0.2em; }
.pc-corners span { position:absolute; width:24px; height:24px; border-color:var(--gold); border-style:solid; border-width:0; opacity:0; transition:all var(--t-base); }
.pc-corners span:nth-child(1){top:12px;left:12px;border-top-width:1px;border-left-width:1px;}
.pc-corners span:nth-child(2){top:12px;right:12px;border-top-width:1px;border-right-width:1px;}
.pc-corners span:nth-child(3){bottom:12px;left:12px;border-bottom-width:1px;border-left-width:1px;}
.pc-corners span:nth-child(4){bottom:12px;right:12px;border-bottom-width:1px;border-right-width:1px;}
.product-card:hover .pc-corners span { opacity:1; width:32px; height:32px; }
.pc-info { padding:1.25rem; }
.pc-name { font-family:var(--font-serif); font-size:1.2rem; color:var(--ink); margin:0 0 0.3rem; font-weight:600; }
.pc-desc { font-size:0.8rem; color:var(--ink-300); margin:0 0 1rem; }
.pc-row { display:flex; align-items:center; justify-content:space-between; }
.pc-price { font-family:var(--font-mono); font-size:1.05rem; color:var(--royal); font-weight:600; }
.pc-add { background:transparent; border:1px solid var(--royal); color:var(--royal); padding:0.5rem 1rem; border-radius:var(--r-sm); font-size:0.75rem; cursor:pointer; font-family:var(--font-sans); letter-spacing:0.08em; transition:all var(--t-fast); text-transform:uppercase; }
.pc-add:hover { background:var(--royal); color:var(--gold); }
```

---

### 50.2 Portrait Card 人物卡

人物介绍卡，圆形头像配金色光环，姓名花体大字，职位金色小字，社交图标hover时从底部滑入，团队/设计师介绍风格。

```html
<div class="portrait-card">
  <div class="pt-avatar-wrap"><div class="pt-avatar">ÉL</div><div class="pt-ring"></div></div>
  <h3 class="pt-name">Éloïse Laurent</h3>
  <p class="pt-role">Creative Director</p>
  <p class="pt-bio">Leading the maison's visual language since 2019, with a background in fine arts and typography.</p>
  <div class="pt-social"><a href="#" class="pt-soc">in</a><a href="#" class="pt-soc">tw</a><a href="#" class="pt-soc">ig</a></div>
</div>
```
```css
.portrait-card { background:var(--cream); border-radius:var(--r-lg); padding:2rem 1.5rem; text-align:center; font-family:var(--font-sans); max-width:280px; border:1px solid var(--cream-200); transition:all var(--t-base); position:relative; overflow:hidden; }
.portrait-card:hover { box-shadow:var(--shadow-lg); transform:translateY(-4px); }
.pt-avatar-wrap { position:relative; width:80px; height:80px; margin:0 auto 1rem; }
.pt-avatar { width:80px; height:80px; border-radius:50%; background:linear-gradient(135deg,var(--royal),var(--royal-700)); color:var(--gold); display:flex; align-items:center; justify-content:center; font-family:var(--font-display); font-style:italic; font-size:1.5rem; font-weight:600; position:relative; z-index:1; }
.pt-ring { position:absolute; inset:-6px; border:1px solid var(--gold); border-radius:50%; opacity:0.4; transition:all var(--t-base); }
.portrait-card:hover .pt-ring { inset:-10px; opacity:1; border-width:2px; transform:rotate(45deg); }
.pt-name { font-family:var(--font-display); font-size:1.5rem; font-style:italic; color:var(--royal); margin:0 0 0.25rem; font-weight:500; }
.pt-role { font-family:var(--font-mono); font-size:0.7rem; color:var(--gold-700); text-transform:uppercase; letter-spacing:0.2em; margin:0 0 1rem; }
.pt-bio { font-size:0.82rem; color:var(--ink-300); line-height:1.6; margin:0 0 1.25rem; }
.pt-social { display:flex; justify-content:center; gap:0.75rem; }
.pt-soc { width:32px; height:32px; border-radius:50%; border:1px solid var(--cream-200); display:flex; align-items:center; justify-content:center; font-size:0.7rem; color:var(--ink-300); text-decoration:none; font-family:var(--font-mono); font-weight:700; transition:all var(--t-fast); }
.pt-soc:hover { background:var(--gold); border-color:var(--gold); color:var(--ink); transform:translateY(-2px); }
```

---

### 50.3 Editorial Article Card 杂志文章卡

杂志文章卡，大图片配渐变遮罩，分类标签金色小胶囊，标题叠加在图片底部，阅读时间等宽字体，杂志/journal风格。

```html
<article class="article-card">
  <div class="ac-img"><div class="ac-gradient"></div><span class="ac-tag">Atelier</span><div class="ac-img-text">Craft</div></div>
  <div class="ac-body"><span class="ac-meta">12 min read · Mar 2026</span><h3 class="ac-title">The Silent Language of the Hand-Stitched Hem</h3><p class="ac-excerpt">An exploration into the invisible artistry that defines haute couture's most enduring detail...</p><a href="#" class="ac-read">Read Article <span class="ac-arrow">→</span></a></div>
</article>
```
```css
.article-card { background:var(--cream); border-radius:var(--r-lg); overflow:hidden; font-family:var(--font-sans); max-width:360px; transition:all var(--t-slow); border:1px solid var(--cream-200); }
.article-card:hover { transform:translateY(-4px); box-shadow:var(--shadow-xl); }
.article-card:hover .ac-arrow { transform:translateX(4px); }
.ac-img { aspect-ratio:16/10; background:linear-gradient(135deg,var(--wine-700),var(--royal)); position:relative; display:flex; align-items:center; justify-content:center; }
.ac-img-text { font-family:var(--font-display); font-style:italic; font-size:3rem; color:rgba(253,251,246,0.15); letter-spacing:0.1em; }
.ac-gradient { position:absolute; inset:0; background:linear-gradient(to top,rgba(13,18,37,0.7) 0%,transparent 50%); }
.ac-tag { position:absolute; top:1rem; left:1rem; background:var(--gold); color:var(--ink); font-size:0.65rem; padding:0.3rem 0.7rem; border-radius:var(--r-full); font-family:var(--font-mono); text-transform:uppercase; letter-spacing:0.1em; font-weight:700; z-index:1; }
.ac-body { padding:1.5rem; }
.ac-meta { font-family:var(--font-mono); font-size:0.7rem; color:var(--ink-300); display:block; margin-bottom:0.5rem; }
.ac-title { font-family:var(--font-serif); font-size:1.2rem; color:var(--ink); line-height:1.4; margin:0 0 0.75rem; font-weight:700; }
.ac-excerpt { font-size:0.85rem; color:var(--ink-300); line-height:1.6; margin:0 0 1rem; }
.ac-read { font-family:var(--font-serif); color:var(--royal); text-decoration:none; font-size:0.85rem; font-weight:600; display:inline-flex; align-items:center; gap:0.4rem; }
.ac-arrow { transition:transform var(--t-base); display:inline-block; color:var(--gold); }
```

---

### 50.4 Project Showcase Card 项目展示卡

项目展示卡，全屏图片背景，hover时底部信息面板从下方滑入覆盖，项目名衬线大字，类别金色小字，作品集/建筑风格。

```html
<div class="project-card">
  <div class="pj-placeholder">PALAIS ROYAL</div>
  <div class="pj-overlay"><span class="pj-cat">Architecture</span><h3 class="pj-title">Palais Royal Renovation</h3><p class="pj-loc">Paris, France · 2025</p></div>
</div>
```
```css
.project-card { aspect-ratio:3/4; border-radius:var(--r-lg); overflow:hidden; position:relative; cursor:pointer; font-family:var(--font-sans); background:linear-gradient(160deg,var(--royal-800) 0%,var(--ink) 100%); }
.pj-placeholder { position:absolute; inset:0; display:flex; align-items:center; justify-content:center; font-family:var(--font-display); font-style:italic; font-size:1.2rem; color:rgba(244,211,94,0.2); letter-spacing:0.3em; }
.pj-overlay { position:absolute; bottom:0; left:0; right:0; padding:1.5rem; background:linear-gradient(to top,rgba(13,18,37,0.95) 0%,rgba(13,18,37,0.7) 60%,transparent 100%); transform:translateY(calc(100% - 70px)); transition:transform var(--t-slow); }
.project-card:hover .pj-overlay { transform:translateY(0); }
.pj-cat { font-family:var(--font-mono); font-size:0.65rem; color:var(--gold); text-transform:uppercase; letter-spacing:0.2em; display:block; margin-bottom:0.4rem; }
.pj-title { font-family:var(--font-serif); font-size:1.3rem; color:var(--cream); margin:0 0 0.3rem; font-weight:600; }
.pj-loc { font-size:0.78rem; color:var(--ink-400); margin:0; }
```

---

### 50.5 Premium Pricing Card 高级定价卡

高端会员卡，金色渐变顶部边缘，皇家蓝背景配金色文字，权益列表配金色对勾，底部"尊享"按钮金色实心，信用卡/黑卡风格。

```html
<div class="premium-card">
  <div class="pm-shine"></div>
  <div class="pm-top"><span class="pm-tier">GOLD</span><span class="pm-badge">Elite</span></div>
  <div class="pm-num">•••• •••• •••• 2026</div>
  <div class="pm-row"><div><span class="pm-lbl">Cardholder</span><span class="pm-val">MEMBRE PRIVILÉGIÉ</span></div><div><span class="pm-lbl">Valid</span><span class="pm-val">12/28</span></div></div>
  <div class="pm-perks"><span class="pm-perk">✓ Priority Access</span><span class="pm-perk">✓ Private Events</span><span class="pm-perk">✓ Concierge 24/7</span></div>
</div>
```
```css
.premium-card { width:360px; max-width:100%; background:linear-gradient(135deg,var(--royal-800) 0%,var(--royal) 50%,var(--royal-900) 100%); border-radius:var(--r-lg); padding:2rem; color:var(--cream); font-family:var(--font-sans); position:relative; overflow:hidden; box-shadow:var(--shadow-xl); }
.premium-card::before { content:''; position:absolute; top:0; left:0; right:0; height:3px; background:linear-gradient(90deg,var(--gold-600),var(--gold),var(--gold-600)); }
.pm-shine { position:absolute; top:-50%; left:-50%; width:200%; height:200%; background:linear-gradient(45deg,transparent 40%,rgba(244,211,94,0.08) 50%,transparent 60%); animation:pmShine 6s ease-in-out infinite; }
@keyframes pmShine { 0%,100%{transform:translateX(-100%) translateY(-100%);} 50%{transform:translateX(100%) translateY(100%);} }
.pm-top { display:flex; justify-content:space-between; align-items:center; margin-bottom:2rem; position:relative; }
.pm-tier { font-family:var(--font-serif); font-size:1.5rem; font-weight:700; color:var(--gold); letter-spacing:0.1em; }
.pm-badge { font-family:var(--font-display); font-style:italic; color:var(--royal); background:var(--gold); padding:0.2rem 0.6rem; border-radius:var(--r-sm); font-size:0.7rem; font-weight:600; }
.pm-num { font-family:var(--font-mono); font-size:1.1rem; color:var(--cream); letter-spacing:0.15em; margin-bottom:2rem; opacity:0.9; position:relative; }
.pm-row { display:flex; justify-content:space-between; margin-bottom:1.5rem; position:relative; }
.pm-lbl { display:block; font-size:0.6rem; text-transform:uppercase; letter-spacing:0.15em; color:var(--ink-400); margin-bottom:0.2rem; }
.pm-val { font-family:var(--font-mono); font-size:0.8rem; color:var(--gold); letter-spacing:0.1em; }
.pm-perks { display:flex; flex-wrap:wrap; gap:0.5rem 1rem; position:relative; }
.pm-perk { font-size:0.72rem; color:var(--cream-100); }
```
