# Feihong Design System — Navigation
# N°08 · 导航
> Navbar, footer, social links, magazine nav, side drawer, breadcrumbs, pagination, and anchor nav.
> 顶部导航、页脚、社交链接、杂志风导航、侧边抽屉、面包屑、分页器和锚点导航。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 8. Navigation 导航

### 8.1 Navbar（顶部导航栏）

```html
<nav class="navbar">
  <a href="#" class="nav-logo">Feihong<span style="color:var(--gold)">.</span></a>
  <div class="nav-links">
    <a href="#work" class="nav-link">作品</a>
    <a href="#about" class="nav-link">关于</a>
    <a href="#services" class="nav-link">服务</a>
    <a href="#contact" class="btn btn-primary btn-sm">联系我</a>
  </div>
</nav>
```
```css
.navbar {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: var(--sp-4) clamp(var(--sp-4), 4vw, var(--sp-8));
  background: rgba(253,251,246,0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid transparent;
  transition: all var(--t-base);
}
.navbar.scrolled {
  border-bottom-color: var(--cream-200);
  box-shadow: var(--shadow-sm);
}
.nav-logo {
  font-family: var(--font-serif);
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--royal);
  text-decoration: none;
}
.nav-links { display: flex; align-items: center; gap: var(--sp-6); }
.nav-link {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  color: var(--ink-100);
  text-decoration: none;
  position: relative;
  transition: color var(--t-fast);
}
.nav-link::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--gold);
  transition: width var(--t-base);
}
.nav-link:hover { color: var(--royal); }
.nav-link:hover::after { width: 100%; }
```

### 8.2 Footer（页脚）

```html
<footer class="footer">
  <div class="footer-inner">
    <div class="footer-brand">
      <a href="#" class="nav-logo">Feihong<span style="color:var(--gold)">.</span></a>
      <p class="body-text" style="font-size:0.9375rem;color:var(--ink-300);margin-top:var(--sp-3);">
        设计有温度的数字体验。
      </p>
    </div>
    <div class="footer-links">
      <div class="footer-col">
        <h4>导航</h4>
        <a href="#">作品</a><a href="#">关于</a><a href="#">服务</a>
      </div>
      <div class="footer-col">
        <h4>联系</h4>
        <a href="#">hello@Feihong.art</a><a href="#">微信</a><a href="#">小红书</a>
      </div>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2024 Feihong. Designed with ♥</p>
  </div>
</footer>
```
```css
.footer {
  background: var(--ink);
  color: #fff;
  padding: var(--sp-12) var(--sp-6) var(--sp-6);
  margin-top: var(--sp-16);
}
.footer-inner {
  max-width: var(--container);
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--sp-8);
}
.footer-col h4 {
  font-family: var(--font-sans);
  font-size: 0.8125rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.12em;
  color: var(--gold);
  margin: 0 0 var(--sp-4);
}
.footer-col a {
  display: block;
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  color: rgba(255,255,255,0.6);
  text-decoration: none;
  margin-bottom: var(--sp-2);
  transition: color var(--t-fast);
}
.footer-col a:hover { color: var(--gold); }
.footer-bottom {
  max-width: var(--container);
  margin: var(--sp-8) auto 0;
  padding-top: var(--sp-4);
  border-top: 1px solid rgba(255,255,255,0.1);
  font-family: var(--font-sans);
  font-size: 0.8125rem;
  color: rgba(255,255,255,0.4);
}
@media (max-width: 600px) {
  .footer-inner { grid-template-columns: 1fr; }
}
```

---

## 14. Social Links（社交链接）

```html
<div class="social-links">
  <a href="#" class="social-link" aria-label="GitHub">GH</a>
  <a href="#" class="social-link" aria-label="微信">WX</a>
  <a href="#" class="social-link" aria-label="小红书">RED</a>
  <a href="#" class="social-link" aria-label="邮箱">@</a>
</div>
```
```css
.social-links { display: flex; gap: var(--sp-3); }
.social-link {
  width: 40px; height: 40px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-family: var(--font-sans);
  font-size: 0.75rem;
  font-weight: 600;
  background: var(--royal-50);
  color: var(--royal);
  text-decoration: none;
  transition: all var(--t-fast);
}
.social-link:hover {
  background: var(--royal);
  color: var(--gold);
  transform: translateY(-2px);
}
```

---

## 47. Navigation 导航类

### 47.1 Magazine Nav 杂志风导航

顶部水平导航，杂志标题风格，当前页有金色下划线从中心展开，logo使用花体衬线，链接hover时有优雅颜色过渡，高端杂志网站风格。

```html
<nav class="mag-nav">
  <div class="mn-logo">Feihong</div>
  <ul class="mn-links">
    <li><a href="#" class="mn-active">Collections</a></li>
    <li><a href="#">Atelier</a></li>
    <li><a href="#">Journal</a></li>
    <li><a href="#">Boutique</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```
```css
.mag-nav { display:flex; align-items:center; justify-content:space-between; padding:1.5rem 3rem; background:var(--cream); border-bottom:1px solid var(--cream-200); font-family:var(--font-sans); }
.mn-logo { font-family:var(--font-display); font-size:1.75rem; font-weight:600; font-style:italic; color:var(--royal); letter-spacing:0.02em; }
.mn-links { list-style:none; display:flex; gap:2rem; margin:0; padding:0; }
.mn-links a { text-decoration:none; color:var(--ink-200); font-size:0.8rem; text-transform:uppercase; letter-spacing:0.15em; position:relative; padding:0.5rem 0; transition:color var(--t-fast); }
.mn-links a::after { content:''; position:absolute; bottom:0; left:50%; width:0; height:1px; background:var(--gold); transition:all var(--t-base); transform:translateX(-50%); }
.mn-links a:hover { color:var(--ink); }
.mn-links a:hover::after, .mn-links a.mn-active::after { width:100%; }
.mn-links a.mn-active { color:var(--royal); font-weight:600; }
```

---

### 47.2 Side Drawer Nav 侧边抽屉导航

固定侧边导航，金色图标+衬线文字组合，hover时右侧金色指示条滑出，当前项有酒红圆点标记，后台管理/应用风格。

```html
<nav class="side-drawer">
  <div class="sd-brand">FH</div>
  <ul class="sd-items">
    <li><a href="#" class="sd-active"><span class="sd-icon">◈</span><span class="sd-label">Dashboard</span></a></li>
    <li><a href="#"><span class="sd-icon">◆</span><span class="sd-label">Analytics</span></a></li>
    <li><a href="#"><span class="sd-icon">❖</span><span class="sd-label">Projects</span></a></li>
    <li><a href="#"><span class="sd-icon">✦</span><span class="sd-label">Messages</span></a></li>
    <li><a href="#"><span class="sd-icon">⚙</span><span class="sd-label">Settings</span></a></li>
  </ul>
</nav>
```
```css
.side-drawer { width:240px; background:var(--royal-900); min-height:100vh; padding:2rem 0; font-family:var(--font-sans); position:sticky; top:0; }
.sd-brand { font-family:var(--font-display); font-size:2rem; font-weight:700; font-style:italic; color:var(--gold); text-align:center; margin-bottom:2.5rem; letter-spacing:0.1em; }
.sd-items { list-style:none; margin:0; padding:0; }
.sd-items a { display:flex; align-items:center; gap:0.85rem; padding:0.85rem 1.75rem; color:var(--ink-400); text-decoration:none; font-size:0.85rem; position:relative; transition:all var(--t-fast); }
.sd-items a::before { content:''; position:absolute; right:0; top:0; bottom:0; width:3px; background:var(--gold); transform:scaleY(0); transition:transform var(--t-base); }
.sd-items a:hover { color:var(--cream); background:rgba(244,211,94,0.05); }
.sd-items a:hover::before { transform:scaleY(1); }
.sd-items a.sd-active { color:var(--cream); }
.sd-items a.sd-active::before { transform:scaleY(1); background:var(--wine); }
.sd-items a.sd-active::after { content:''; position:absolute; left:1rem; width:6px; height:6px; background:var(--wine); border-radius:50%; }
.sd-icon { color:var(--gold); font-size:1rem; width:1.25rem; text-align:center; }
.sd-label { font-family:var(--font-serif); font-size:0.9rem; letter-spacing:0.03em; }
```

---

### 47.3 Breadcrumb Trail 面包屑

面包屑导航，金色斜纹分隔符，当前页使用衬线斜体，hover项有金色底部装饰线，优雅过渡效果。

```html
<nav class="breadcrumb">
  <a href="#">Home</a><span class="bc-sep">/</span>
  <a href="#">Collections</a><span class="bc-sep">/</span>
  <a href="#">Haute Couture</a><span class="bc-sep">/</span>
  <span class="bc-current">FW 2026</span>
</nav>
```
```css
.breadcrumb { display:flex; align-items:center; gap:0.5rem; font-family:var(--font-sans); font-size:0.8rem; padding:1rem 0; flex-wrap:wrap; }
.breadcrumb a { color:var(--ink-300); text-decoration:none; position:relative; transition:color var(--t-fast); padding-bottom:2px; }
.breadcrumb a::after { content:''; position:absolute; bottom:0; left:0; width:0; height:1px; background:var(--gold); transition:width var(--t-base); }
.breadcrumb a:hover { color:var(--royal); }
.breadcrumb a:hover::after { width:100%; }
.bc-sep { color:var(--gold); font-family:var(--font-display); font-style:italic; font-size:0.9rem; user-select:none; }
.bc-current { font-family:var(--font-display); font-style:italic; color:var(--royal); font-weight:500; }
```

---

### 47.4 Luxury Pagination 奢华分页器

分页器使用金色圆形按钮，当前页有皇家蓝实心圆配金色描边，hover时按钮有金色光晕扩散，首尾使用花体箭头装饰。

```html
<nav class="lux-pagination">
  <a href="#" class="pg-prev">‹</a>
  <a href="#">1</a>
  <a href="#" class="pg-active">2</a>
  <a href="#">3</a>
  <a href="#">4</a>
  <span class="pg-dots">···</span>
  <a href="#">12</a>
  <a href="#" class="pg-next">›</a>
</nav>
```
```css
.lux-pagination { display:flex; align-items:center; justify-content:center; gap:0.5rem; font-family:var(--font-serif); }
.lux-pagination a { display:inline-flex; align-items:center; justify-content:center; width:40px; height:40px; border-radius:50%; text-decoration:none; color:var(--ink-200); font-size:0.9rem; border:1px solid transparent; transition:all var(--t-base); position:relative; }
.lux-pagination a:hover { color:var(--royal); border-color:var(--gold); box-shadow:0 0 0 4px rgba(244,211,94,0.15); }
.lux-pagination a.pg-active { background:var(--royal); color:var(--gold); border-color:var(--gold); font-weight:700; box-shadow:0 0 0 3px rgba(10,36,99,0.1); }
.lux-pagination .pg-prev, .lux-pagination .pg-next { font-family:var(--font-display); font-size:1.3rem; font-style:italic; color:var(--gold); }
.lux-pagination .pg-dots { color:var(--ink-400); letter-spacing:0.2em; font-size:0.7rem; }
```

---

### 47.5 Anchor Dot Nav 锚点导航

右侧固定圆形锚点导航，每个点有金色外圈，hover时展开显示标签文字，当前激活点有脉冲呼吸动画，单页滚动/作品集风格。

```html
<nav class="anchor-nav">
  <a href="#s1" class="an-active" data-label="Cover"><span class="an-dot"></span></a>
  <a href="#s2" data-label="About"><span class="an-dot"></span></a>
  <a href="#s3" data-label="Works"><span class="an-dot"></span></a>
  <a href="#s4" data-label="Process"><span class="an-dot"></span></a>
  <a href="#s5" data-label="Contact"><span class="an-dot"></span></a>
</nav>
```
```css
.anchor-nav { position:fixed; right:2rem; top:50%; transform:translateY(-50%); display:flex; flex-direction:column; gap:1rem; z-index:100; }
.anchor-nav a { display:flex; align-items:center; gap:0.75rem; text-decoration:none; position:relative; justify-content:flex-end; }
.an-dot { width:10px; height:10px; border-radius:50%; border:1.5px solid var(--gold); background:transparent; transition:all var(--t-base); flex-shrink:0; }
.anchor-nav a::before { content:attr(data-label); font-family:var(--font-sans); font-size:0.7rem; color:var(--royal); text-transform:uppercase; letter-spacing:0.1em; opacity:0; transform:translateX(8px); transition:all var(--t-base); white-space:nowrap; }
.anchor-nav a:hover::before { opacity:1; transform:translateX(0); }
.anchor-nav a:hover .an-dot { background:var(--gold); transform:scale(1.3); }
.anchor-nav a.an-active .an-dot { background:var(--gold); box-shadow:0 0 0 4px rgba(244,211,94,0.2); animation:anPulse 2s ease-in-out infinite; }
@keyframes anPulse { 0%,100%{box-shadow:0 0 0 4px rgba(244,211,94,0.2);} 50%{box-shadow:0 0 0 8px rgba(244,211,94,0.08);} }
```

---

### 47.6 Scroll-State Glass Navbar 滚动变色毛玻璃导航栏

滚动变色毛玻璃导航栏，`backdrop-filter:blur(20px)`+半透明cream底色，`.scrolled`状态切换底边边框+缩小padding，金色下划线hover动画（从左展开），内嵌CTA皇家蓝按钮，滚动超过30px自动切换状态，高端landing page风格。

```html
<nav class="nav" id="nav">
  <a href="#" class="nav-logo">Feihong<span>.</span>Art</a>
  <div class="nav-links">
    <a href="#philosophy">设计哲学</a>
    <a href="#templates">HTML模板</a>
    <a href="#workflow">精工流程</a>
    <a href="#quality">质量门槛</a>
    <a href="#docs">规范文档</a>
    <a href="https://github.com/" target="_blank" class="nav-cta">GitHub 获取</a>
  </div>
</nav>
```
```css
/* 导航栏基础 — 毛玻璃效果 */
.nav {
  position:fixed; top:0; left:0; right:0;
  z-index:100;
  padding:1.25rem 2.5rem;
  display:flex;
  align-items:center;
  justify-content:space-between;
  background:rgba(253,251,246,0.85);
  backdrop-filter:blur(20px);
  -webkit-backdrop-filter:blur(20px);
  border-bottom:1px solid transparent;
  transition:all 300ms var(--ease);
  font-family:var(--font-sans);
}
/* 滚动后状态 — 底边边框+缩小padding */
.nav.scrolled {
  border-bottom-color:var(--cream-200);
  padding:0.85rem 2.5rem;
}
/* Logo */
.nav-logo {
  font-family:var(--font-serif);
  font-size:1.4rem;
  font-weight:700;
  color:var(--ink);
  letter-spacing:-0.01em;
  text-decoration:none;
}
.nav-logo span { color:var(--gold); font-style:italic; }
/* 导航链接 */
.nav-links { display:flex; gap:2rem; align-items:center; }
.nav-links a {
  font-size:0.85rem;
  font-weight:500;
  color:var(--ink-200);
  text-decoration:none;
  transition:color 200ms;
  position:relative;
}
.nav-links a:hover { color:var(--royal); }
/* 金色下划线hover动画 — 从左展开 */
.nav-links a::after {
  content:'';
  position:absolute; bottom:-4px; left:0;
  width:0; height:1.5px;
  background:var(--gold);
  transition:width 300ms var(--ease);
}
.nav-links a:hover::after { width:100%; }
/* 内嵌CTA按钮 */
.nav-cta {
  background:var(--royal);
  color:#fff !important;
  padding:0.5rem 1.1rem;
  border-radius:8px;
  font-size:0.85rem !important;
  font-weight:500;
  transition:all 200ms var(--ease) !important;
}
.nav-cta:hover { background:var(--royal-700); transform:translateY(-1px); }
.nav-cta::after { display:none !important; }
```
```javascript
// 导航栏滚动状态切换 — scrollY > 30 时添加 .scrolled 类
const nav = document.getElementById('nav');
window.addEventListener('scroll', () => {
  nav.classList.toggle('scrolled', window.scrollY > 30);
});
```

---

### 8.3 Minimal Centered Footer 极简居中页脚

极简居中页脚，深色墨色底，居中衬线logo（金色句点），版权行+金色外链，顶部1px半透明白分隔线，简洁收尾风格。

```html
<footer class="footer">
  <div class="footer-logo">Feihong<span>.</span>Art</div>
  <p>Feihong Design System · <a href="https://feihong.art" target="_blank">Feihong.Art</a></p>
</footer>
```
```css
.footer {
  background:var(--ink);
  color:rgba(255,255,255,0.5);
  padding:3rem 2.5rem;
  text-align:center;
  border-top:1px solid rgba(255,255,255,0.05);
  font-family:var(--font-sans);
}
/* 居中衬线logo */
.footer-logo {
  font-family:var(--font-serif);
  font-size:1.3rem;
  font-weight:700;
  color:#fff;
  margin-bottom:0.5rem;
  letter-spacing:-0.01em;
}
.footer-logo span { color:var(--gold); font-style:italic; }
/* 版权行 */
.footer p { font-size:0.82rem; margin:0; }
/* 金色链接 */
.footer a { color:var(--gold); text-decoration:none; transition:opacity var(--t-fast); }
.footer a:hover { opacity:0.7; }
```
