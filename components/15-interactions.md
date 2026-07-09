# Feihong Design System — Interactions
# N°15 · 交互组件
> Scroll reveal, modals, accordions, tabs, count-up, typewriter, scroll-spy, hover effects, tooltips, dropdowns, toggles, and sliders.
> 滚动入场、模态框、手风琴、标签切换、数字递增、打字机、滚动高亮、悬停效果、工具提示、下拉、开关和滑块。
> Part of Feihong Design System v7.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 18. Scroll Reveal Animation（滚动入场动画）

```css
/* 在 <style> 中加入 */
.reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 700ms var(--ease), transform 700ms var(--ease);
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}
.reveal-delay-1 { transition-delay: 100ms; }
.reveal-delay-2 { transition-delay: 200ms; }
.reveal-delay-3 { transition-delay: 300ms; }

@media (prefers-reduced-motion: reduce) {
  .reveal { opacity: 1; transform: none; }
}
```

```javascript
// 在 <script> 中加入
const revealEls = document.querySelectorAll('.reveal');
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); }});
}, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });
revealEls.forEach(el => observer.observe(el));
```

使用方式：给需要入场动画的元素加 `class="reveal"`。

---

---

## 37. 交互组件：Modal 模态框

点击按钮弹出居中模态框，带半透明遮罩、右上角关闭按钮（hover 旋转 90 度），入场有 scale + opacity 动画。

```html
<button class="btn btn-primary" onclick="document.getElementById('modal1').classList.add('open')">打开模态框</button>

<div class="modal" id="modal1">
  <div class="modal-backdrop" onclick="this.parentElement.classList.remove('open')"></div>
  <div class="modal-content">
    <button class="modal-close" onclick="this.closest('.modal').classList.remove('open')">&times;</button>
    <h3>关于飞鸿</h3>
    <p>飞鸿设计系统致力于将古典印刷美学带入数字界面。我们相信好的设计应当经得起时间的审视，如同一本好书，常读常新。</p>
    <p>每一个组件都经过精心打磨，从字体的选择、色彩的搭配到间距的呼吸，都追求那份恰到好处的从容。</p>
  </div>
</div>
```

```css
/* 模态框遮罩 */
.modal {
  display: none;
  position: fixed;
  inset: 0;
  z-index: 1000;
  align-items: center;
  justify-content: center;
  padding: var(--sp-4);
}

.modal.open {
  display: flex;
}

.modal-backdrop {
  position: absolute;
  inset: 0;
  background: rgba(13, 18, 37, 0.6);
  animation: modalFadeIn 0.3s var(--ease);
}

.modal-content {
  position: relative;
  background: #fff;
  border-radius: var(--r-lg);
  padding: 2.5rem;
  max-width: 560px;
  width: 100%;
  max-height: 85vh;
  overflow-y: auto;
  box-shadow: 0 25px 60px rgba(10, 36, 99, 0.3);
  animation: modalScaleIn 0.4s var(--ease);
  z-index: 1;
}

.modal-content h3 {
  font-family: var(--font-serif);
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--royal);
  margin: 0 0 var(--sp-4);
  padding-right: var(--sp-8);
}

.modal-content p {
  font-family: var(--font-sans);
  font-size: 1rem;
  line-height: 1.8;
  color: var(--ink-200);
  margin: 0 0 var(--sp-4);
}

/* 关闭按钮 */
.modal-close {
  position: absolute;
  top: var(--sp-4);
  right: var(--sp-4);
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: none;
  background: var(--cream);
  color: var(--ink);
  font-family: var(--font-serif);
  font-size: 1.5rem;
  line-height: 1;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform var(--t-base), background var(--t-fast);
}

.modal-close:hover {
  transform: rotate(90deg);
  background: var(--wine);
  color: #fff;
}

/* 入场动画 */
@keyframes modalFadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes modalScaleIn {
  from {
    opacity: 0;
    transform: scale(0.95) translateY(10px);
  }
  to {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
}
```

---

## 38. 交互组件：Accordion 手风琴

使用原生 `<details>/<summary>` 实现的手风琴组件，summary 右侧 +/− 号切换，衬线字体标题，适合 FAQ 场景。

```html
<div class="accordion">
  <details class="accordion-item" open>
    <summary>飞鸿设计系统的核心理念是什么？</summary>
    <div class="accordion-body">
      核心理念是"书卷气"——将古典印刷美学与当代界面设计相结合，追求沉稳、典雅、经得住时间审视的视觉语言。我们相信好的设计不是追随时尚，而是建立自己的节奏与气质。
    </div>
  </details>
  <details class="accordion-item">
    <summary>如何在项目中引入设计系统？</summary>
    <div class="accordion-body">
      直接复制所需组件的 HTML + CSS 代码即可使用。所有组件均不依赖 JavaScript 框架，仅使用原生 CSS 变量，你可以在任何技术栈中引入。建议先引入 Brand Tokens，再按需引入组件。
    </div>
  </details>
  <details class="accordion-item">
    <summary>字体和色彩可以自定义吗？</summary>
    <div class="accordion-body">
      可以。所有设计决策都通过 CSS 变量暴露，你只需要修改 :root 中对应的变量值，即可全局调整色彩、字体、间距等系统属性。我们建议在保持品牌气质的前提下进行微调。
    </div>
  </details>
</div>
```

```css
/* 手风琴容器 */
.accordion {
  max-width: 680px;
  margin: var(--sp-6) 0;
}

/* 单个手风琴项 */
.accordion-item {
  border-bottom: 1px solid var(--cream-200);
}

/* summary 标题 */
.accordion-item summary {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.25rem 0;
  font-family: var(--font-serif);
  font-weight: 600;
  font-size: 1.05rem;
  color: var(--ink);
  cursor: pointer;
  list-style: none;
  transition: color var(--t-fast);
  user-select: none;
}

/* 移除 WebKit 默认 marker */
.accordion-item summary::-webkit-details-marker {
  display: none;
}

.accordion-item summary::after {
  content: '+';
  font-family: var(--font-serif);
  font-size: 1.5rem;
  font-weight: 300;
  color: var(--gold);
  line-height: 1;
  transition: transform var(--t-base);
  flex-shrink: 0;
  margin-left: var(--sp-4);
}

.accordion-item[open] summary::after {
  content: '\2212'; /* − 减号 */
  transform: rotate(180deg);
}

.accordion-item summary:hover {
  color: var(--royal);
}

/* 展开内容区 */
.accordion-body {
  padding: 0 0 1.25rem;
  color: var(--ink-200);
  line-height: 1.7;
  font-family: var(--font-sans);
  font-size: 0.95rem;
}
```

---

## 39. 交互组件：Tabs 标签切换

衬线字体的标签切换组件，底部金色指示线，支持多标签内容切换。附 JS 事件委托脚本。

```html
<div class="tabs">
  <div class="tabs-nav">
    <button class="tab-btn active" data-tab="t1">品牌理念</button>
    <button class="tab-btn" data-tab="t2">设计原则</button>
    <button class="tab-btn" data-tab="t3">使用指南</button>
  </div>
  <div class="tab-panel active" id="t1">
    <p>飞鸿设计系统以"书卷气"为核心，将古典印刷美学融入数字界面。我们追求的不是视觉的冲击，而是阅读的从容。每一个字号的选择、每一处间距的确定，都有其内在的节奏与理由。</p>
  </div>
  <div class="tab-panel" id="t2">
    <p>克制、典雅、留白、呼吸。我们相信少即是多，但"少"不是贫瘠，而是恰到好处。色彩使用克制而有力——皇家蓝奠定基调，金色点缀精神，酒红注入温度。</p>
  </div>
  <div class="tab-panel" id="t3">
    <p>从 Brand Tokens 开始引入，再按需取用组件。所有组件无框架依赖，原生 HTML + CSS 即可运行。交互组件附有简洁的 JS 脚本，可直接复制使用。</p>
  </div>
</div>
```

```css
/* Tabs 导航 */
.tabs {
  max-width: 680px;
  margin: var(--sp-6) 0;
}

.tabs-nav {
  display: flex;
  border-bottom: 2px solid var(--cream-200);
  gap: 0;
}

.tab-btn {
  background: none;
  border: none;
  padding: 0.75rem 1.25rem;
  font-family: var(--font-serif);
  font-weight: 600;
  font-size: 1rem;
  color: var(--ink-300);
  cursor: pointer;
  border-bottom: 2px solid transparent;
  margin-bottom: -2px;
  transition: color var(--t-fast), border-color var(--t-fast);
}

.tab-btn:hover {
  color: var(--ink);
}

.tab-btn.active {
  color: var(--royal);
  border-bottom-color: var(--gold);
}

/* Tab 面板 */
.tab-panel {
  display: none;
  padding: 1.5rem 0;
}

.tab-panel.active {
  display: block;
  animation: tabFadeIn 0.4s var(--ease);
}

.tab-panel p {
  font-family: var(--font-sans);
  font-size: 1rem;
  line-height: 1.8;
  color: var(--ink-200);
  margin: 0;
}

@keyframes tabFadeIn {
  from { opacity: 0; transform: translateY(4px); }
  to { opacity: 1; transform: translateY(0); }
}
```

```html
<script>
// Tabs 切换 — 事件委托
document.addEventListener('click', function (e) {
  var btn = e.target.closest('.tab-btn');
  if (!btn) return;
  var tabs = btn.closest('.tabs');
  if (!tabs) return;
  var target = btn.dataset.tab;
  tabs.querySelectorAll('.tab-btn').forEach(function (b) { b.classList.remove('active'); });
  tabs.querySelectorAll('.tab-panel').forEach(function (p) { p.classList.remove('active'); });
  btn.classList.add('active');
  var panel = tabs.querySelector('#' + target);
  if (panel) panel.classList.add('active');
});
</script>
```

---

## 40. 交互组件：数字递增动画 Count-Up

进入视口时数字从 0 递增到目标值，衬线大字呈现，适合数据展示场景。支持前后缀自定义。

```html
<div style="display: flex; gap: var(--sp-10); flex-wrap: wrap; justify-content: center; padding: var(--sp-8);">
  <div style="text-align: center;">
    <span class="count-up" data-target="1200" data-suffix="+">0</span>
    <p style="font-family: var(--font-sans); font-size: 0.9rem; color: var(--ink-300); margin: var(--sp-2) 0 0;">设计案例</p>
  </div>
  <div style="text-align: center;">
    <span class="count-up" data-target="15" data-suffix="年">0</span>
    <p style="font-family: var(--font-sans); font-size: 0.9rem; color: var(--ink-300); margin: var(--sp-2) 0 0;">品牌沉淀</p>
  </div>
  <div style="text-align: center;">
    <span class="count-up" data-target="98" data-suffix="%">0</span>
    <p style="font-family: var(--font-sans); font-size: 0.9rem; color: var(--ink-300); margin: var(--sp-2) 0 0;">客户满意度</p>
  </div>
</div>
```

```css
.count-up {
  font-family: var(--font-serif);
  font-weight: 700;
  font-size: clamp(2rem, 4vw, 3.5rem);
  color: var(--royal);
  line-height: 1;
  display: inline-block;
}
```

```html
<script>
// Count-Up 数字递增动画
(function () {
  function animateCount(el) {
    var target = parseInt(el.dataset.target, 10) || 0;
    var suffix = el.dataset.suffix || '';
    var prefix = el.dataset.prefix || '';
    var duration = parseInt(el.dataset.duration, 10) || 2000;
    var start = 0;
    var startTime = null;
    function step(timestamp) {
      if (!startTime) startTime = timestamp;
      var progress = Math.min((timestamp - startTime) / duration, 1);
      var eased = 1 - Math.pow(1 - progress, 3); // easeOutCubic
      var current = Math.floor(eased * (target - start) + start);
      el.textContent = prefix + current.toLocaleString() + suffix;
      if (progress < 1) requestAnimationFrame(step);
      else el.textContent = prefix + target.toLocaleString() + suffix;
    }
    requestAnimationFrame(step);
  }

  var observer = new IntersectionObserver(function (entries) {
    entries.forEach(function (entry) {
      if (entry.isIntersecting) {
        animateCount(entry.target);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.3 });

  document.querySelectorAll('.count-up').forEach(function (el) { observer.observe(el); });
})();
</script>
```

---

## 41. 交互组件：衬线打字机效果 Typewriter

进入视口后逐字显示文字，配有金色闪烁光标，使用 Cormorant Garamond 斜体，营造手稿书写感。

```html
<span class="typewriter" data-text="设计不是装饰，是表达。" data-speed="60"></span>
```

```css
.typewriter {
  font-family: var(--font-display);
  font-style: italic;
  font-size: clamp(1.5rem, 3vw, 2.5rem);
  color: var(--ink);
  line-height: 1.4;
  display: inline;
  position: relative;
}

/* 闪烁光标 */
.typewriter::after {
  content: '';
  display: inline-block;
  width: 2px;
  height: 1em;
  background: var(--gold);
  margin-left: 2px;
  vertical-align: text-bottom;
  animation: cursorBlink 0.8s step-end infinite;
}

.typewriter.typing-done::after {
  display: none;
}

@keyframes cursorBlink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}
```

```html
<script>
// Typewriter 打字机效果
(function () {
  function typeWriter(el) {
    var text = el.dataset.text || '';
    var speed = parseInt(el.dataset.speed, 10) || 60;
    var i = 0;
    el.textContent = '';
    function type() {
      if (i < text.length) {
        el.textContent += text.charAt(i);
        i++;
        setTimeout(type, speed);
      } else {
        el.classList.add('typing-done');
      }
    }
    type();
  }

  var observer = new IntersectionObserver(function (entries) {
    entries.forEach(function (entry) {
      if (entry.isIntersecting) {
        typeWriter(entry.target);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.5 });

  document.querySelectorAll('.typewriter').forEach(function (el) { observer.observe(el); });
})();
</script>
```

---

## 42. 交互组件：滚动高亮导航 Scroll-Spy

侧边或顶部导航，自动监听页面内各 section 的滚动位置，当前章节对应的导航项自动高亮（金边+粗体）。

```html
<nav class="scrollspy-nav">
  <a href="#section1" class="spy-link active">初见</a>
  <a href="#section2" class="spy-link">笔墨</a>
  <a href="#section3" class="spy-link">留白</a>
  <a href="#section4" class="spy-link">印记</a>
</nav>

<!-- 对应的页面区块 -->
<section id="section1" style="padding: var(--sp-8); min-height: 60vh;"><h2 style="font-family:var(--font-serif); color:var(--royal);">初见</h2></section>
<section id="section2" style="padding: var(--sp-8); min-height: 60vh;"><h2 style="font-family:var(--font-serif); color:var(--royal);">笔墨</h2></section>
<section id="section3" style="padding: var(--sp-8); min-height: 60vh;"><h2 style="font-family:var(--font-serif); color:var(--royal);">留白</h2></section>
<section id="section4" style="padding: var(--sp-8); min-height: 60vh;"><h2 style="font-family:var(--font-serif); color:var(--royal);">印记</h2></section>
```

```css
/* 滚动监听导航 */
.scrollspy-nav {
  position: sticky;
  top: var(--sp-4);
  display: flex;
  flex-direction: column;
  gap: 0;
  padding: var(--sp-3) 0;
}

.spy-link {
  display: block;
  padding: 0.5rem 0 0.5rem 1rem;
  font-size: 0.85rem;
  font-family: var(--font-sans);
  color: var(--ink-300);
  text-decoration: none;
  border-left: 2px solid transparent;
  transition: color var(--t-fast), border-color var(--t-fast), font-weight var(--t-fast);
  line-height: 1.4;
}

.spy-link:hover {
  color: var(--ink);
}

.spy-link.active {
  color: var(--royal);
  border-left-color: var(--gold);
  font-weight: 600;
}
```

```html
<script>
// Scroll-Spy 滚动高亮
(function () {
  var links = document.querySelectorAll('.spy-link');
  if (links.length === 0) return;
  var sectionIds = Array.from(links).map(function (l) { return l.getAttribute('href').substring(1); });
  var sections = sectionIds.map(function (id) { return document.getElementById(id); }).filter(Boolean);

  var observer = new IntersectionObserver(function (entries) {
    entries.forEach(function (entry) {
      if (entry.isIntersecting) {
        var id = entry.target.id;
        links.forEach(function (l) {
          l.classList.toggle('active', l.getAttribute('href') === '#' + id);
        });
      }
    });
  }, { rootMargin: '-20% 0px -60% 0px', threshold: 0 });

  sections.forEach(function (s) { observer.observe(s); });
})();
</script>
```

---

## 52. Interactions 交互类

### 52.1 Elegant Hover Lift 悬停提升

卡片/元素悬停效果，hover时元素微微上浮（translateY）并投射更深的皇家蓝阴影，同时有微妙的金色光晕从边缘渗出，通用hover交互。

```html
<div class="hover-lift">
  <div class="hl-icon">❖</div>
  <h4>Premium Quality</h4>
  <p>Crafted with the finest materials and meticulous attention to every detail.</p>
</div>
```
```css
.hover-lift { background:var(--cream); border:1px solid var(--cream-200); border-radius:var(--r-lg); padding:2rem; font-family:var(--font-sans); text-align:center; transition:all var(--t-base); cursor:pointer; max-width:280px; position:relative; }
.hover-lift::before { content:''; position:absolute; inset:-1px; border-radius:var(--r-lg); background:linear-gradient(135deg,var(--gold),transparent,var(--gold)); opacity:0; transition:opacity var(--t-base); z-index:-1; padding:1px; -webkit-mask:linear-gradient(#fff 0 0) content-box,linear-gradient(#fff 0 0); mask:linear-gradient(#fff 0 0) content-box,linear-gradient(#fff 0 0); -webkit-mask-composite:xor; mask-composite:exclude; }
.hover-lift:hover { transform:translateY(-8px); box-shadow:var(--shadow-xl), 0 0 40px rgba(244,211,94,0.15); border-color:var(--gold-200); }
.hover-lift:hover::before { opacity:1; }
.hl-icon { font-size:2rem; color:var(--gold); margin-bottom:1rem; display:block; transition:transform var(--t-slow); }
.hover-lift:hover .hl-icon { transform:scale(1.1) rotate(5deg); }
.hover-lift h4 { font-family:var(--font-serif); font-size:1.15rem; color:var(--royal); margin:0 0 0.5rem; }
.hover-lift p { font-size:0.85rem; color:var(--ink-300); line-height:1.6; margin:0; }
```

---

### 52.2 Gold Tooltip 金色工具提示

金色工具提示，hover触发元素时从上方淡入滑下，小三角指向触发元素，使用花体斜体字，表单/图标按钮辅助说明。

```html
<div class="tooltip-wrap">
  <button class="tt-trigger">?</button>
  <span class="tooltip">This action cannot be undone.</span>
</div>
```
```css
.tooltip-wrap { position:relative; display:inline-block; font-family:var(--font-sans); }
.tt-trigger { width:28px; height:28px; border-radius:50%; border:1px solid var(--gold); background:transparent; color:var(--gold); font-family:var(--font-serif); font-weight:700; cursor:pointer; transition:all var(--t-fast); }
.tt-trigger:hover { background:var(--gold); color:var(--ink); }
.tooltip { position:absolute; bottom:calc(100% + 10px); left:50%; transform:translateX(-50%) translateY(4px); background:var(--ink); color:var(--gold); padding:0.6rem 1rem; border-radius:var(--r-sm); font-size:0.75rem; white-space:nowrap; opacity:0; pointer-events:none; transition:all var(--t-base); font-family:var(--font-display); font-style:italic; z-index:10; box-shadow:var(--shadow-lg); }
.tooltip::after { content:''; position:absolute; top:100%; left:50%; transform:translateX(-50%); border:5px solid transparent; border-top-color:var(--ink); }
.tooltip-wrap:hover .tooltip { opacity:1; transform:translateX(-50%) translateY(0); }
```

---

### 52.3 Art Deco Dropdown 装饰艺术下拉

Art Deco风格下拉菜单，触发按钮带金色下边框，下拉面板从按钮下方优雅展开（高度+透明度动画），菜单项有金色左侧指示条滑入，导航/筛选器风格。

```html
<div class="deco-dropdown">
  <button class="dd-btn">Select Language ▾</button>
  <div class="dd-menu">
    <a href="#" class="dd-item dd-active">Français</a>
    <a href="#" class="dd-item">English</a>
    <a href="#" class="dd-item">中文</a>
    <a href="#" class="dd-item">日本語</a>
  </div>
</div>
```
```css
.deco-dropdown { position:relative; display:inline-block; font-family:var(--font-sans); }
.dd-btn { background:var(--cream); border:1px solid var(--cream-200); border-bottom:2px solid var(--gold); padding:0.75rem 1.25rem; border-radius:var(--r-sm) var(--r-sm) 0 0; font-size:0.85rem; color:var(--ink); cursor:pointer; font-family:var(--font-serif); font-weight:600; transition:all var(--t-fast); min-width:180px; text-align:left; display:flex; justify-content:space-between; align-items:center; }
.dd-btn:hover { background:var(--gold-50); }
.deco-dropdown:hover .dd-btn { border-bottom-color:var(--gold-600); }
.dd-menu { position:absolute; top:100%; left:0; min-width:100%; background:var(--cream); border:1px solid var(--cream-200); border-top:none; border-radius:0 0 var(--r-sm) var(--r-sm); box-shadow:var(--shadow-md); opacity:0; transform:translateY(-8px); pointer-events:none; transition:all var(--t-base); z-index:20; overflow:hidden; }
.deco-dropdown:hover .dd-menu { opacity:1; transform:translateY(0); pointer-events:auto; }
.dd-item { display:block; padding:0.7rem 1.25rem; font-size:0.85rem; color:var(--ink-200); text-decoration:none; border-left:3px solid transparent; transition:all var(--t-fast); }
.dd-item:hover { background:var(--gold-50); color:var(--royal); border-left-color:var(--gold); padding-left:1.5rem; }
.dd-item.dd-active { color:var(--royal); font-weight:600; border-left-color:var(--wine); background:var(--wine-50); }
```

---

### 52.4 Velvet Toggle Switch 丝绒开关切换

丝绒质感开关切换，酒红关闭态/金色开启态，滑块滑动时有弹性缓动（cubic-bezier弹性），开启时背景有金色光晕扩散，设置/偏好开关风格。

```html
<label class="velvet-toggle">
  <input type="checkbox" checked>
  <span class="vt-track"><span class="vt-thumb"></span></span>
  <span class="vt-label">Premium Mode</span>
</label>
```
```css
.velvet-toggle { display:inline-flex; align-items:center; gap:0.75rem; font-family:var(--font-sans); cursor:pointer; user-select:none; }
.velvet-toggle input { display:none; }
.vt-track { width:48px; height:26px; background:var(--wine-200); border-radius:var(--r-full); position:relative; transition:all var(--t-base); flex-shrink:0; }
.vt-thumb { position:absolute; top:3px; left:3px; width:20px; height:20px; background:var(--cream); border-radius:50%; transition:all 0.5s cubic-bezier(0.34,1.56,0.64,1); box-shadow:0 2px 6px rgba(0,0,0,0.15); }
.velvet-toggle input:checked + .vt-track { background:var(--gold); box-shadow:0 0 12px rgba(244,211,94,0.4); }
.velvet-toggle input:checked + .vt-track .vt-thumb { left:calc(100% - 23px); background:var(--cream); }
.vt-label { font-size:0.85rem; color:var(--ink-200); }
.velvet-toggle input:checked ~ .vt-label { color:var(--royal); font-weight:500; }
```

---

### 52.5 Gilded Range Slider 鎏金滑动选择器

自定义range滑块，金色轨道填充，皇家蓝圆形滑块带金色描边和光晕，拖动时光晕放大，数值实时显示在滑块上方金色小标签中。

```html
<div class="gilded-slider">
  <span class="gs-val" id="gsVal">50</span>
  <input type="range" min="0" max="100" value="50" oninput="document.getElementById('gsVal').textContent=this.value; this.style.setProperty('--val',this.value+'%')">
</div>
```
```css
.gilded-slider { position:relative; padding-top:2rem; font-family:var(--font-sans); max-width:300px; }
.gs-val { position:absolute; top:0; left:50%; transform:translateX(-50%); background:var(--gold); color:var(--ink); font-family:var(--font-mono); font-size:0.7rem; font-weight:700; padding:0.25rem 0.6rem; border-radius:var(--r-sm); transition:left var(--t-fast); }
.gs-val::after { content:''; position:absolute; top:100%; left:50%; transform:translateX(-50%); border:4px solid transparent; border-top-color:var(--gold); }
.gilded-slider input { -webkit-appearance:none; appearance:none; width:100%; height:4px; border-radius:var(--r-full); background:linear-gradient(to right,var(--gold) var(--val,50%),var(--cream-200) var(--val,50%)); outline:none; transition:all var(--t-fast); }
.gilded-slider input::-webkit-slider-thumb { -webkit-appearance:none; appearance:none; width:20px; height:20px; border-radius:50%; background:var(--royal); border:2px solid var(--gold); cursor:pointer; transition:all var(--t-fast); box-shadow:0 0 0 0 rgba(244,211,94,0.4); }
.gilded-slider input::-webkit-slider-thumb:hover { box-shadow:0 0 0 8px rgba(244,211,94,0.2); transform:scale(1.1); }
.gilded-slider input::-moz-range-thumb { width:20px; height:20px; border-radius:50%; background:var(--royal); border:2px solid var(--gold); cursor:pointer; }
```
