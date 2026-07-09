# Feihong Design System — Comparison
# N°16 · 对比组件
> Before/after sliders, price tier comparison, feature matrices, version diffs, and pros/cons tables.
> 前后对比滑块、价格层级对比、特性矩阵、版本差异对比和优缺点表。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 53. Comparison 对比类

### 53.1 Before/After Slider 前后对比滑块

Before/After图片对比滑块，可拖动中间金色分隔线左右滑动，两侧显示不同状态，顶部有"Before"/"After"标签，图片修图/改造前后对比风格。

```html
<div class="ba-slider" id="baSlider">
  <div class="ba-after"><div class="ba-placeholder" style="background:var(--royal)">After</div></div>
  <div class="ba-before"><div class="ba-placeholder" style="background:var(--ink-400)">Before</div></div>
  <div class="ba-handle"><span class="ba-line"></span><span class="ba-knob">⇔</span></div>
  <span class="ba-lbl ba-lbl-b">Before</span>
  <span class="ba-lbl ba-lbl-a">After</span>
</div>
```
```css
.ba-slider { position:relative; width:100%; max-width:500px; aspect-ratio:16/10; border-radius:var(--r-lg); overflow:hidden; cursor:ew-resize; font-family:var(--font-sans); user-select:none; --ba-pos:50%; }
.ba-before, .ba-after { position:absolute; inset:0; }
.ba-before { clip-path:inset(0 calc(100% - var(--ba-pos)) 0 0); }
.ba-placeholder { width:100%; height:100%; display:flex; align-items:center; justify-content:center; font-family:var(--font-display); font-style:italic; font-size:2rem; color:var(--cream); }
.ba-handle { position:absolute; top:0; bottom:0; left:var(--ba-pos); width:3px; background:var(--gold); transform:translateX(-50%); z-index:2; pointer-events:none; }
.ba-knob { position:absolute; top:50%; left:50%; transform:translate(-50%,-50%); width:36px; height:36px; background:var(--gold); border-radius:50%; display:flex; align-items:center; justify-content:center; font-size:0.8rem; color:var(--ink); box-shadow:var(--shadow-gold); }
.ba-line { position:absolute; top:0; bottom:0; left:50%; width:2px; background:var(--gold); transform:translateX(-50%); }
.ba-lbl { position:absolute; top:1rem; padding:0.3rem 0.7rem; background:rgba(13,18,37,0.6); color:var(--gold); font-size:0.65rem; text-transform:uppercase; letter-spacing:0.15em; border-radius:var(--r-sm); font-family:var(--font-mono); }
.ba-lbl-b { left:1rem; } .ba-lbl-a { right:1rem; }
```

---

### 53.2 Price Tier Compare 价格层级对比

横向价格层级条形对比，不同价位用不同品牌色条表示（金/蓝/酒红），长度对应价格高低，底部有刻度标注，产品/套餐价格对比风格。

```html
<div class="tier-compare">
  <div class="tc-row"><span class="tc-name">Starter</span><div class="tc-bar-wrap"><div class="tc-bar tc-gold" style="width:30%"></div></div><span class="tc-val">¥99</span></div>
  <div class="tc-row"><span class="tc-name">Pro</span><div class="tc-bar-wrap"><div class="tc-bar tc-royal" style="width:60%"></div></div><span class="tc-val">¥299</span></div>
  <div class="tc-row"><span class="tc-name">Enterprise</span><div class="tc-bar-wrap"><div class="tc-bar tc-wine" style="width:100%"></div></div><span class="tc-val">¥999</span></div>
  <div class="tc-scale"><span>0</span><span>¥500</span><span>¥1000</span></div>
</div>
```
```css
.tier-compare { font-family:var(--font-sans); max-width:500px; }
.tc-row { display:flex; align-items:center; gap:1rem; margin-bottom:1rem; }
.tc-name { font-family:var(--font-serif); font-size:0.9rem; color:var(--ink); width:90px; text-align:right; font-weight:600; }
.tc-bar-wrap { flex:1; height:32px; background:var(--cream-200); border-radius:var(--r-sm); overflow:hidden; position:relative; }
.tc-bar { height:100%; border-radius:var(--r-sm); transition:width 1s cubic-bezier(0.16,1,0.3,1); position:relative; }
.tc-bar::after { content:''; position:absolute; inset:0; background:linear-gradient(90deg,transparent,rgba(255,255,255,0.2),transparent); }
.tc-gold { background:linear-gradient(90deg,var(--gold-600),var(--gold)); }
.tc-royal { background:linear-gradient(90deg,var(--royal-800),var(--royal)); }
.tc-wine { background:linear-gradient(90deg,var(--wine-700),var(--wine)); }
.tc-val { font-family:var(--font-mono); font-size:0.9rem; color:var(--royal); font-weight:700; width:60px; }
.tc-scale { display:flex; justify-content:space-between; padding-left:100px; padding-right:60px; margin-top:0.5rem; }
.tc-scale span { font-size:0.65rem; color:var(--ink-400); font-family:var(--font-mono); }
```

---

### 53.3 Feature Matrix 特性对比矩阵

特性对比矩阵，行是特性，列是方案，勾/叉/横线用金色/酒红/灰色表示，表头有金色背景高亮推荐列，产品功能对比风格。

```html
<table class="feature-matrix">
  <thead><tr><th>Features</th><th>Basic</th><th class="fm-highlight">Pro</th><th>Elite</th></tr></thead>
  <tbody>
    <tr><td>核心功能</td><td class="fm-check">✓</td><td class="fm-check">✓</td><td class="fm-check">✓</td></tr>
    <tr><td>高级分析</td><td class="fm-dash">—</td><td class="fm-check">✓</td><td class="fm-check">✓</td></tr>
    <tr><td>API访问</td><td class="fm-cross">✕</td><td class="fm-check">✓</td><td class="fm-check">✓</td></tr>
    <tr><td>专属顾问</td><td class="fm-cross">✕</td><td class="fm-dash">—</td><td class="fm-check">✓</td></tr>
    <tr><td>定制开发</td><td class="fm-cross">✕</td><td class="fm-cross">✕</td><td class="fm-check">✓</td></tr>
  </tbody>
</table>
```
```css
.feature-matrix { width:100%; border-collapse:collapse; font-family:var(--font-sans); max-width:600px; background:var(--cream); border-radius:var(--r-lg); overflow:hidden; box-shadow:var(--shadow-sm); }
.feature-matrix th { padding:1rem; font-size:0.8rem; text-transform:uppercase; letter-spacing:0.1em; color:var(--ink-200); background:var(--cream-100); border-bottom:2px solid var(--cream-200); text-align:center; }
.feature-matrix th:first-child { text-align:left; font-family:var(--font-serif); color:var(--ink); text-transform:none; letter-spacing:0; font-size:0.9rem; }
.feature-matrix th.fm-highlight { background:var(--gold); color:var(--ink); position:relative; }
.feature-matrix th.fm-highlight::after { content:'推荐'; position:absolute; top:-8px; left:50%; transform:translateX(-50%); background:var(--wine); color:var(--cream); font-size:0.55rem; padding:0.15rem 0.5rem; border-radius:var(--r-full); letter-spacing:0.1em; }
.feature-matrix td { padding:0.85rem 1rem; text-align:center; font-size:0.85rem; color:var(--ink); border-bottom:1px solid var(--cream-200); }
.feature-matrix td:first-child { text-align:left; color:var(--ink-200); }
.fm-check { color:var(--gold); font-weight:700; font-size:1rem; }
.fm-cross { color:var(--wine); opacity:0.5; }
.fm-dash { color:var(--ink-400); }
.feature-matrix tbody tr:hover { background:var(--gold-50); }
```

---

### 53.4 Version Diff 版本对比

版本差异对比，两列并排显示代码/文本变更，删除内容用酒红底色+删除线，新增内容用金色底色，行号在两侧，changelog/代码diff风格。

```html
<div class="version-diff">
  <div class="vd-header"><span class="vd-ver">v2.0</span><span class="vd-arrow">→</span><span class="vd-ver vd-new">v3.0</span><span class="vd-date">2026.03.15</span></div>
  <div class="vd-body">
    <div class="vd-line vd-removed"><span class="vd-ln">42</span><span class="vd-content"><del>color: #333333;</del></span></div>
    <div class="vd-line vd-added"><span class="vd-ln">42</span><span class="vd-content"><ins>color: var(--royal);</ins></span></div>
    <div class="vd-line vd-removed"><span class="vd-ln">87</span><span class="vd-content"><del>font-family: Arial, sans-serif;</del></span></div>
    <div class="vd-line vd-added"><span class="vd-ln">88</span><span class="vd-content"><ins>font-family: var(--font-serif);</ins></span></div>
    <div class="vd-line"><span class="vd-ln">120</span><span class="vd-content">  /* unchanged */</span></div>
  </div>
</div>
```
```css
.version-diff { font-family:var(--font-mono); max-width:600px; border-radius:var(--r-md); overflow:hidden; border:1px solid var(--cream-200); }
.vd-header { display:flex; align-items:center; gap:0.75rem; padding:0.75rem 1rem; background:var(--cream-100); border-bottom:1px solid var(--cream-200); font-size:0.8rem; }
.vd-ver { font-weight:700; color:var(--ink-200); }
.vd-ver.vd-new { color:var(--royal); }
.vd-arrow { color:var(--gold); font-size:1rem; }
.vd-date { margin-left:auto; font-size:0.7rem; color:var(--ink-400); }
.vd-body { background:var(--cream); font-size:0.8rem; line-height:1.8; }
.vd-line { display:flex; }
.vd-ln { width:40px; text-align:right; padding-right:1rem; color:var(--ink-400); user-select:none; flex-shrink:0; border-right:1px solid var(--cream-200); padding-left:0.5rem; }
.vd-content { flex:1; padding:0 1rem; white-space:pre; }
.vd-removed { background:rgba(216,49,91,0.08); }
.vd-removed del { color:var(--wine); text-decoration-color:var(--wine); text-decoration-thickness:1px; }
.vd-added { background:rgba(244,211,94,0.15); }
.vd-added ins { color:var(--gold-800); text-decoration:none; font-weight:600; }
```

---

### 53.5 Pros/Cons Ledger 优缺点表

经典优缺点对比，左右两栏分别用金色（优点）和酒红（缺点），顶部有对应图标标题，底部有总结栏，产品评价/决策辅助风格。

```html
<div class="pros-cons">
  <div class="pc-panel pc-pros">
    <div class="pc-head"><span class="pc-icon-pc">✓</span><span class="pc-title-pc">Advantages</span></div>
    <ul class="pc-list"><li>Timeless aesthetic that transcends trends</li><li>Crafted with premium sustainable materials</li><li>Comprehensive design token system</li><li>Full accessibility compliance built-in</li></ul>
  </div>
  <div class="pc-divider-v"><span>VS</span></div>
  <div class="pc-panel pc-cons">
    <div class="pc-head"><span class="pc-icon-pc pc-icon-con">✕</span><span class="pc-title-pc">Considerations</span></div>
    <ul class="pc-list"><li>Premium investment required</li><li>Learning curve for custom tokens</li><li>Regular updates recommended</li></ul>
  </div>
</div>
```
```css
.pros-cons { display:grid; grid-template-columns:1fr auto 1fr; gap:0; max-width:700px; font-family:var(--font-sans); border-radius:var(--r-lg); overflow:hidden; border:1px solid var(--cream-200); }
.pc-panel { padding:2rem; }
.pc-pros { background:var(--gold-50); }
.pc-cons { background:var(--wine-50); }
.pc-head { display:flex; align-items:center; gap:0.6rem; margin-bottom:1.25rem; }
.pc-icon-pc { width:28px; height:28px; border-radius:50%; background:var(--gold); color:var(--ink); display:flex; align-items:center; justify-content:center; font-weight:700; font-size:0.85rem; }
.pc-icon-pc.pc-icon-con { background:var(--wine); color:var(--cream); }
.pc-title-pc { font-family:var(--font-serif); font-size:1.1rem; font-weight:700; color:var(--ink); }
.pc-list { list-style:none; padding:0; margin:0; }
.pc-list li { font-size:0.85rem; color:var(--ink-200); padding:0.5rem 0; padding-left:1.5rem; position:relative; line-height:1.5; border-bottom:1px solid rgba(0,0,0,0.05); }
.pc-list li::before { content:'+'; position:absolute; left:0; color:var(--gold-600); font-weight:700; }
.pc-cons .pc-list li::before { content:'−'; color:var(--wine); }
.pc-divider-v { display:flex; align-items:center; justify-content:center; background:var(--cream); padding:0 1rem; font-family:var(--font-mono); font-size:0.65rem; color:var(--ink-400); letter-spacing:0.1em; writing-mode:vertical-rl; text-orientation:mixed; }
@media(max-width:640px){ .pros-cons{grid-template-columns:1fr;} .pc-divider-v{writing-mode:horizontal-tb;padding:0.75rem;} }
```
