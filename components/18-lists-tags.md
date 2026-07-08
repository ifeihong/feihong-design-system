# FEIHONG Design System — Lists & Tags
# N°18 · 列表与标签组
> Gold dot lists, serif numbered lists, check lists, and tag groups for content organization.
> 金色圆点列表、衬线数字列表、勾选列表和标签组，用于内容组织。
> Part of FEIHONG Design System v7.0 · 所有组件遵循 DNA.md 色彩字体规范
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
