# FEIHONG Design System — Tables
# N°07 · 表格
> Brand table, magazine editorial tables, Art Deco tables, pricing tables, and schedules.
> 品牌表格、杂志编辑风表格、装饰艺术表格、价格对比表和时间表。
> Part of FEIHONG Design System v7.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 11. Table（表格）

```html
<div class="table-wrap">
  <table class="brand-table">
    <thead>
      <tr><th>服务</th><th>周期</th><th>价格</th></tr>
    </thead>
    <tbody>
      <tr><td>品牌设计</td><td>4-6周</td><td>¥15,000起</td></tr>
      <tr><td>落地页设计</td><td>2-3周</td><td>¥8,000起</td></tr>
    </tbody>
  </table>
</div>
```
```css
.table-wrap { overflow-x: auto; margin: var(--sp-5) 0; }
.brand-table {
  width: 100%;
  border-collapse: collapse;
  font-family: var(--font-sans);
  font-size: 0.9375rem;
}
.brand-table th {
  text-align: left;
  padding: var(--sp-3) var(--sp-4);
  font-weight: 600;
  color: var(--royal);
  background: var(--royal-50);
  font-size: 0.8125rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}
.brand-table th:first-child { border-radius: var(--r-md) 0 0 0; }
.brand-table th:last-child { border-radius: 0 var(--r-md) 0 0; }
.brand-table td {
  padding: var(--sp-4);
  color: var(--ink-100);
  border-bottom: 1px solid var(--cream-200);
}
.brand-table tr:hover td { background: var(--cream); }
```

---

## 46. Tables 表格类

### 46.1 Magazine Editorial Table 杂志风表格

杂志编辑风格表格，大字号表头配金色细线分隔，行间留白充裕，首列使用衬线字体突出，Vogue/Harper's Bazaar 排版质感。

```html
<table class="mag-table">
  <thead><tr><th>Collection</th><th>Season</th><th>Atelier</th><th>Status</th></tr></thead>
  <tbody>
    <tr><td>Haute Couture</td><td>FW 2026</td><td>Paris</td><td>Available</td></tr>
    <tr><td>Prêt-à-Porter</td><td>SS 2026</td><td>Milan</td><td>Preview</td></tr>
    <tr><td>Accessories</td><td>Resort</td><td>Florence</td><td>Sold Out</td></tr>
  </tbody>
</table>
```
```css
.mag-table { width:100%; border-collapse:collapse; font-family:var(--font-sans); background:var(--cream); }
.mag-table thead th { font-family:var(--font-display); font-size:1.1rem; font-weight:500; font-style:italic; color:var(--royal); text-align:left; padding:1rem 1.25rem; border-bottom:2px solid var(--gold); letter-spacing:0.05em; }
.mag-table tbody td { padding:1rem 1.25rem; font-size:0.9rem; color:var(--ink-200); border-bottom:1px solid var(--cream-200); transition:all var(--t-fast); }
.mag-table tbody td:first-child { font-family:var(--font-serif); font-weight:600; color:var(--ink); font-size:0.95rem; }
.mag-table tbody tr { transition:background var(--t-fast); }
.mag-table tbody tr:hover { background:var(--gold-50); }
.mag-table tbody tr:hover td:first-child { color:var(--royal); }
```

---

### 46.2 Art Deco Table 装饰艺术表格

Art Deco 风格，金色几何边框，对称阶梯式表头，行间金色菱形分隔符，1920年代爵士时代奢华感。

```html
<table class="deco-table">
  <thead><tr><th>Suite</th><th>Carat</th><th>Cut</th><th>Price</th></tr></thead>
  <tbody>
    <tr><td>Émeraude</td><td>3.2</td><td>Brilliant</td><td>¥280,000</td></tr>
    <tr><td>Saphir</td><td>2.8</td><td>Oval</td><td>¥195,000</td></tr>
    <tr><td>Rubis</td><td>2.1</td><td>Cushion</td><td>¥340,000</td></tr>
  </tbody>
</table>
```
```css
.deco-table { width:100%; border-collapse:collapse; font-family:var(--font-serif); background:var(--cream); border:2px solid var(--gold); position:relative; }
.deco-table::before { content:''; position:absolute; inset:6px; border:1px solid var(--gold-300); pointer-events:none; }
.deco-table thead th { font-size:0.85rem; font-weight:700; text-transform:uppercase; letter-spacing:0.2em; color:var(--royal); padding:1.25rem 1.5rem; border-bottom:3px double var(--gold); text-align:center; background:var(--gold-50); }
.deco-table tbody td { padding:1rem 1.5rem; font-size:0.95rem; color:var(--ink); text-align:center; border-bottom:1px solid var(--cream-200); position:relative; }
.deco-table tbody td:not(:last-child)::after { content:'◆'; position:absolute; right:-4px; top:50%; transform:translateY(-50%); color:var(--gold); font-size:0.4rem; }
.deco-table tbody tr:last-child td { border-bottom:none; }
.deco-table tbody tr:hover { background:linear-gradient(90deg,transparent,rgba(244,211,94,0.08),transparent); }
```

---

### 46.3 Striped Luxe Table 条纹奢华表格

交替行使用极淡酒红/米白条纹，表头皇家蓝底配金色文字，悬停行有优雅金色左侧边框滑入效果。

```html
<table class="stripe-table">
  <thead><tr><th>Vintage</th><th>Château</th><th>Region</th><th>Score</th></tr></thead>
  <tbody>
    <tr><td>1982</td><td>Margaux</td><td>Bordeaux</td><td>98</td></tr>
    <tr><td>1990</td><td>Latour</td><td>Bordeaux</td><td>97</td></tr>
    <tr><td>2005</td><td>Lafite</td><td>Bordeaux</td><td>96</td></tr>
    <tr><td>2010</td><td>Pétrus</td><td>Pomerol</td><td>99</td></tr>
  </tbody>
</table>
```
```css
.stripe-table { width:100%; border-collapse:collapse; font-family:var(--font-sans); }
.stripe-table thead th { background:var(--royal); color:var(--gold); font-family:var(--font-serif); font-weight:600; font-size:0.95rem; padding:1rem 1.25rem; text-align:left; letter-spacing:0.05em; border-bottom:2px solid var(--gold-600); }
.stripe-table tbody td { padding:0.9rem 1.25rem; font-size:0.9rem; color:var(--ink); border-bottom:1px solid var(--cream-200); border-left:3px solid transparent; transition:all var(--t-base); }
.stripe-table tbody tr:nth-child(even) { background:var(--wine-50); }
.stripe-table tbody tr:nth-child(odd) { background:var(--cream); }
.stripe-table tbody tr:hover td { border-left-color:var(--gold); background:var(--gold-50); color:var(--royal); font-weight:500; }
```

---

### 46.4 Price Comparison Table 价格对比表

三列价格对比表，中间推荐列有金色光环突出显示，顶部皇冠图标，底部金色装饰线，SaaS/会员定价风格。

```html
<div class="price-compare">
  <div class="pc-col"><div class="pc-tier">Essential</div><div class="pc-price"><span class="pc-cur">¥</span>99<span class="pc-per">/月</span></div><ul class="pc-feats"><li>基础功能</li><li>5GB存储</li><li>邮件支持</li></ul><button class="pc-btn">选择</button></div>
  <div class="pc-col pc-featured"><div class="pc-crown">❖</div><div class="pc-tier">Premium</div><div class="pc-price"><span class="pc-cur">¥</span>299<span class="pc-per">/月</span></div><ul class="pc-feats"><li>全部功能</li><li>100GB存储</li><li>专属客服</li><li>高级分析</li></ul><button class="pc-btn pc-btn-gold">立即加入</button></div>
  <div class="pc-col"><div class="pc-tier">Elite</div><div class="pc-price"><span class="pc-cur">¥</span>999<span class="pc-per">/月</span></div><ul class="pc-feats"><li>定制方案</li><li>无限存储</li><li>1对1顾问</li><li>API接入</li></ul><button class="pc-btn">联系</button></div>
</div>
```
```css
.price-compare { display:grid; grid-template-columns:repeat(3,1fr); gap:1.5rem; font-family:var(--font-sans); max-width:900px; margin:0 auto; }
.pc-col { background:var(--cream); border:1px solid var(--cream-200); border-radius:var(--r-lg); padding:2rem 1.5rem; text-align:center; position:relative; transition:all var(--t-base); }
.pc-col:hover { transform:translateY(-4px); box-shadow:var(--shadow-lg); }
.pc-col.pc-featured { border:2px solid var(--gold); transform:scale(1.03); box-shadow:var(--shadow-gold); }
.pc-crown { font-size:1.5rem; color:var(--gold); margin-bottom:0.25rem; animation:crownFloat 3s ease-in-out infinite; }
@keyframes crownFloat { 0%,100%{transform:translateY(0);} 50%{transform:translateY(-4px);} }
.pc-tier { font-family:var(--font-display); font-size:1.25rem; font-style:italic; color:var(--royal); margin-bottom:0.75rem; }
.pc-price { font-family:var(--font-serif); font-size:2.5rem; font-weight:700; color:var(--ink); margin-bottom:1.25rem; }
.pc-cur { font-size:1rem; vertical-align:super; color:var(--ink-300); }
.pc-per { font-size:0.85rem; font-weight:400; color:var(--ink-300); }
.pc-featured .pc-price { color:var(--royal); }
.pc-feats { list-style:none; padding:0; margin:0 0 1.5rem; text-align:left; }
.pc-feats li { padding:0.5rem 0; font-size:0.85rem; color:var(--ink-200); border-bottom:1px solid var(--cream-200); }
.pc-feats li::before { content:'✓ '; color:var(--gold-600); font-weight:700; }
.pc-btn { display:block; width:100%; padding:0.75rem; border:1px solid var(--royal); background:transparent; color:var(--royal); font-family:var(--font-sans); font-size:0.85rem; border-radius:var(--r-md); cursor:pointer; transition:all var(--t-fast); letter-spacing:0.05em; }
.pc-btn:hover { background:var(--royal); color:var(--cream); }
.pc-btn-gold { background:var(--gold); border-color:var(--gold); color:var(--ink); font-weight:600; }
.pc-btn-gold:hover { background:var(--gold-600); border-color:var(--gold-600); }
@media(max-width:640px){ .price-compare{grid-template-columns:1fr;} .pc-col.pc-featured{transform:none;} }
```

---

### 46.5 Timeline Schedule Table 时间表

横向时间轴日程表，金色竖线标记时间点，事件用酒红/皇家蓝圆点区分，左侧时间列使用等宽字体，会议/活动日程风格。

```html
<div class="timeline-sched">
  <div class="ts-item"><div class="ts-time">09:00</div><div class="ts-dot ts-gold"></div><div class="ts-content"><div class="ts-title">开幕致辞</div><div class="ts-meta">大宴会厅 · 主持</div></div></div>
  <div class="ts-item"><div class="ts-time">10:30</div><div class="ts-dot ts-royal"></div><div class="ts-content"><div class="ts-title">主题演讲</div><div class="ts-meta">A厅 · 特邀嘉宾</div></div></div>
  <div class="ts-item"><div class="ts-time">12:00</div><div class="ts-dot ts-wine"></div><div class="ts-content"><div class="ts-title">午宴交流</div><div class="ts-meta">花园餐厅</div></div></div>
  <div class="ts-item"><div class="ts-time">14:00</div><div class="ts-dot ts-gold"></div><div class="ts-content"><div class="ts-title">工坊体验</div><div class="ts-meta">B/C厅 · 分组</div></div></div>
</div>
```
```css
.timeline-sched { font-family:var(--font-sans); position:relative; padding-left:1rem; }
.timeline-sched::before { content:''; position:absolute; left:80px; top:0; bottom:0; width:1px; background:linear-gradient(to bottom,var(--gold),var(--gold-300),var(--gold)); }
.ts-item { display:flex; align-items:flex-start; gap:1.25rem; padding:1rem 0; position:relative; }
.ts-time { font-family:var(--font-mono); font-size:0.85rem; color:var(--ink-300); width:60px; text-align:right; flex-shrink:0; padding-top:2px; }
.ts-dot { width:12px; height:12px; border-radius:50%; flex-shrink:0; margin-top:4px; position:relative; z-index:1; border:2px solid var(--cream); }
.ts-dot.ts-gold { background:var(--gold); box-shadow:0 0 0 3px rgba(244,211,94,0.2); }
.ts-dot.ts-royal { background:var(--royal); box-shadow:0 0 0 3px rgba(10,36,99,0.15); }
.ts-dot.ts-wine { background:var(--wine); box-shadow:0 0 0 3px rgba(216,49,91,0.15); }
.ts-content { flex:1; }
.ts-title { font-family:var(--font-serif); font-weight:600; color:var(--ink); font-size:1rem; margin-bottom:0.2rem; }
.ts-meta { font-size:0.8rem; color:var(--ink-300); }
```
