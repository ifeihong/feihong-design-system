# Feihong Design System — Dividers & Decorations
# N°11 · 分隔与装饰
> Gold dividers, decorative numbers, avatars, IP characters, and hand-drawn pen stroke dividers.
> 金色分隔线、装饰数字、头像、IP形象和手绘钢笔画分隔线。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 9. Dividers & Decorative Elements（分隔与装饰）

### 9.1 Gold Line Divider（金色装饰分隔线）

```html
<div class="divider-gold"></div>
<div class="divider-dots"></div>
```
```css
.divider-gold {
  height: 1px;
  background: linear-gradient(90deg, transparent 0%, var(--gold) 30%, var(--gold) 70%, transparent 100%);
  margin: var(--sp-8) 0;
}
.divider-dots {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--sp-3);
  margin: var(--sp-8) 0;
}
.divider-dots span {
  width: 6px; height: 6px; border-radius: 50%;
  background: var(--gold);
}
.divider-dots span:nth-child(2) { background: var(--royal); width: 8px; height: 8px; }
.divider-dots span:nth-child(3) { background: var(--wine); }
```

### 9.2 Decorative Section Number（装饰性大数字）

```html
<div class="decor-number" aria-hidden="true">01</div>
```
```css
.decor-number {
  position: absolute;
  font-family: var(--font-serif);
  font-size: clamp(6rem, 15vw, 12rem);
  font-weight: 700;
  font-style: italic;
  color: var(--royal);
  opacity: 0.04;
  line-height: 1;
  z-index: 0;
  pointer-events: none;
  user-select: none;
}
```

### 9.3 Decorative English Text（装饰性英文）

```html
<div class="decor-text" aria-hidden="true">PORTFOLIO</div>
```
```css
.decor-text {
  position: absolute;
  font-family: var(--font-serif);
  font-size: clamp(4rem, 10vw, 8rem);
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--royal);
  opacity: 0.04;
  white-space: nowrap;
  z-index: 0;
  pointer-events: none;
  user-select: none;
}
```

### 9.4 Avatar（头像）

```html
<div class="avatar avatar-lg">
  <img src="assets/avatar.png" alt="飞鸿">
</div>
```
```css
.avatar {
  border-radius: 50%;
  overflow: hidden;
  border: 3px solid var(--gold);
  box-shadow: var(--shadow-gold);
}
.avatar img { width: 100%; height: 100%; object-fit: cover; }
.avatar-sm { width: 40px; height: 40px; }
.avatar-md { width: 64px; height: 64px; }
.avatar-lg { width: 120px; height: 120px; }
.avatar-xl {
  width: clamp(200px, 25vw, 320px);
  height: clamp(200px, 25vw, 320px);
  border-width: 4px;
}
```

### 9.5 IP Character（IP形象展示）

```html
<div class="character-wrap">
  <img src="assets/character.png" alt="飞鸿IP形象" class="character-img">
</div>
```
```css
.character-wrap {
  position: relative;
}
.character-img {
  max-width: 100%;
  height: auto;
  filter: drop-shadow(0 20px 40px rgba(10,36,99,0.15));
  transition: transform var(--t-slow);
}
.character-img:hover { transform: translateY(-8px) rotate(-2deg); }
```

---

---

## 33. 钢笔画分隔线 Pen Stroke Divider

手绘质感的分隔线，模拟钢笔在纸上划过的痕迹，比直线更有人文温度。提供单线、双线中点、波浪线三种变体。

```html
<hr class="pen-divider">

<hr class="pen-divider double">

<hr class="pen-divider wave">
```

```css
/* 钢笔画分隔线 — 默认：手绘感金色单线 */
hr.pen-divider {
  border: none;
  margin: var(--sp-8) 0;
  position: relative;
  height: 6px;
  background: none;
  overflow: visible;
}

hr.pen-divider::before {
  content: '';
  position: absolute;
  top: 0;
  left: 5%;
  right: 5%;
  height: 2px;
  background: var(--gold);
  opacity: 0.7;
  transform: rotate(-0.3deg);
  border-radius: 1px;
}

hr.pen-divider::after {
  content: '';
  position: absolute;
  top: 3px;
  left: 10%;
  right: 15%;
  height: 1px;
  background: var(--gold);
  opacity: 0.4;
  transform: rotate(0.2deg);
}

/* 双线 + 中间小点变体 */
hr.pen-divider.double {
  height: 14px;
}

hr.pen-divider.double::before {
  top: 0;
  left: 10%;
  right: 10%;
  height: 1px;
  opacity: 0.6;
  transform: rotate(-0.2deg);
}

hr.pen-divider.double::after {
  content: '';
  top: 50%;
  left: 50%;
  width: 5px;
  height: 5px;
  background: var(--gold);
  border-radius: 50%;
  opacity: 0.7;
  transform: translate(-50%, -50%);
}

/* 上线用包装伪元素实现双线 */
hr.pen-divider.double {
  background-image: linear-gradient(var(--gold), var(--gold));
  background-size: 80% 1px;
  background-position: center bottom;
  background-repeat: no-repeat;
}

/* 波浪线变体（SVG data URI） */
hr.pen-divider.wave {
  height: 14px;
  background: none;
}

hr.pen-divider.wave::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  height: 12px;
  transform: translateY(-50%);
  background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 200 12'%3E%3Cpath d='M0 6 Q 12 0, 25 6 T 50 6 T 75 6 T 100 6 T 125 6 T 150 6 T 175 6 T 200 6' stroke='%23F4D35E' stroke-width='1.5' fill='none' stroke-linecap='round' opacity='0.7'/%3E%3C/svg%3E") repeat-x center;
  background-size: 200px 12px;
  opacity: 1;
}

hr.pen-divider.wave::after {
  display: none;
}
```
