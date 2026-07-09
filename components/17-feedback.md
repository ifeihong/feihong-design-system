# Feihong Design System — Feedback
# N°17 · 反馈组件
> Alerts, notifications, progress indicators, loading states, empty states, and timelines for feedback and storytelling.
> 提示框、通知、进度指示器、加载状态、空状态和时间线，用于状态反馈与叙事。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 12. Alert / Notification（提示框）

```html
<div class="alert alert-info">ℹ️ 这是一条提示信息</div>
<div class="alert alert-success">✓ 操作成功</div>
<div class="alert alert-warning">⚠️ 请注意</div>
<div class="alert alert-wine">重要提醒</div>
```
```css
.alert {
  padding: var(--sp-3) var(--sp-4);
  border-radius: var(--r-md);
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  line-height: 1.6;
  margin: var(--sp-4) 0;
  border-left: 3px solid;
}
.alert-info { background: var(--royal-50); color: var(--royal); border-color: var(--royal); }
.alert-success { background: #ECFDF5; color: #065F46; border-color: var(--success); }
.alert-warning { background: var(--gold-50); color: var(--gold-800); border-color: var(--gold); }
.alert-wine { background: var(--wine-50); color: var(--wine-700); border-color: var(--wine); }
```

---

## 13. Progress / Bar（进度条）

```html
<div class="progress">
  <div class="progress-label">设计能力</div>
  <div class="progress-bar"><div class="progress-fill" style="width:95%"></div></div>
</div>
```
```css
.progress { margin-bottom: var(--sp-4); }
.progress-label {
  font-family: var(--font-sans);
  font-size: 0.875rem;
  color: var(--ink-100);
  margin-bottom: var(--sp-2);
  display: flex;
  justify-content: space-between;
}
.progress-bar {
  height: 6px;
  background: var(--cream-200);
  border-radius: var(--r-full);
  overflow: hidden;
}
.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, var(--royal), var(--gold));
  border-radius: var(--r-full);
  transition: width var(--t-slow);
}
```

---

## 16. Timeline（时间线）

```html
<div class="timeline">
  <div class="timeline-item">
    <div class="timeline-dot"></div>
    <div class="timeline-content">
      <span class="caption-text">2024</span>
      <h4>创立个人工作室</h4>
      <p>专注于为个人品牌和初创公司提供设计服务。</p>
    </div>
  </div>
  <div class="timeline-item">
    <div class="timeline-dot"></div>
    <div class="timeline-content">
      <span class="caption-text">2022</span>
      <h4>加入某科技公司</h4>
      <p>担任高级设计师，主导设计系统搭建。</p>
    </div>
  </div>
</div>
```
```css
.timeline { position: relative; padding-left: var(--sp-8); }
.timeline::before {
  content: '';
  position: absolute;
  left: 7px;
  top: 8px;
  bottom: 8px;
  width: 2px;
  background: linear-gradient(180deg, var(--gold), var(--cream-200));
}
.timeline-item { position: relative; margin-bottom: var(--sp-6); }
.timeline-dot {
  position: absolute;
  left: -25px;
  top: 6px;
  width: 16px; height: 16px;
  border-radius: 50%;
  background: var(--gold);
  border: 3px solid var(--cream);
  box-shadow: 0 0 0 2px var(--gold);
}
.timeline-content h4 {
  font-family: var(--font-serif);
  font-size: 1.0625rem;
  font-weight: 600;
  color: var(--ink);
  margin: var(--sp-1) 0 var(--sp-1);
}
.timeline-content p {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  color: var(--ink-200);
  line-height: 1.6;
  margin: 0;
}
```

---

## 17. Toast / Slide-in Notification（滑入通知）

> 右上角滑入式通知，皇家蓝底色配金色装饰条，自动消失，支持成功/错误/信息三种状态。

```html
<div class="toast-container" id="toastContainer"></div>

<button onclick="showToast('success', '操作已完成', '您的作品已成功保存。')">触发成功通知</button>
```
```css
.toast-container {
  position: fixed;
  top: var(--sp-6);
  right: var(--sp-6);
  z-index: 9999;
  display: flex;
  flex-direction: column;
  gap: var(--sp-3);
  pointer-events: none;
}
.toast {
  display: flex;
  align-items: flex-start;
  gap: var(--sp-3);
  min-width: 320px;
  max-width: 420px;
  padding: var(--sp-4) var(--sp-5);
  background: var(--royal);
  color: #fff;
  border-radius: var(--r-md);
  box-shadow: var(--shadow-lg);
  border-left: 4px solid var(--gold);
  pointer-events: auto;
  transform: translateX(120%);
  opacity: 0;
  transition: transform 0.5s cubic-bezier(0.16,1,0.3,1), opacity 0.4s ease;
  position: relative;
  overflow: hidden;
}
.toast.toast-show {
  transform: translateX(0);
  opacity: 1;
}
.toast.toast-hide {
  transform: translateX(120%);
  opacity: 0;
}
.toast-icon {
  flex-shrink: 0;
  width: 36px; height: 36px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 1rem;
  background: rgba(244,211,94,0.15);
  color: var(--gold);
  border: 1.5px solid rgba(244,211,94,0.3);
}
.toast-body { flex: 1; }
.toast-title {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  font-weight: 600;
  color: var(--gold);
  margin: 0 0 2px;
  letter-spacing: 0.01em;
}
.toast-message {
  font-family: var(--font-sans);
  font-size: 0.875rem;
  color: rgba(255,255,255,0.85);
  line-height: 1.5;
  margin: 0;
}
.toast-close {
  flex-shrink: 0;
  background: none; border: none;
  color: rgba(255,255,255,0.5);
  cursor: pointer;
  font-size: 1.1rem;
  padding: 0;
  line-height: 1;
  transition: color var(--t-fast);
}
.toast-close:hover { color: #fff; }
.toast-progress {
  position: absolute;
  bottom: 0; left: 0;
  height: 2px;
  background: var(--gold);
  animation: toast-progress 4s linear forwards;
}
@keyframes toast-progress {
  from { width: 100%; }
  to { width: 0%; }
}
.toast.toast-error {
  border-left-color: var(--wine);
}
.toast.toast-error .toast-icon {
  background: rgba(216,49,91,0.15);
  color: var(--wine);
  border-color: rgba(216,49,91,0.3);
}
.toast.toast-error .toast-title { color: #FFB3C6; }
.toast.toast-error .toast-progress { background: var(--wine); }
.toast.toast-success .toast-icon { color: var(--gold); }
```
```javascript
function showToast(type, title, message, duration = 4000) {
  const container = document.getElementById('toastContainer');
  const toast = document.createElement('div');
  toast.className = `toast toast-${type}`;
  const iconMap = { success: '✓', error: '✕', info: 'i' };
  toast.innerHTML = `
    <div class="toast-icon">${iconMap[type] || 'i'}</div>
    <div class="toast-body">
      <p class="toast-title">${title}</p>
      <p class="toast-message">${message}</p>
    </div>
    <button class="toast-close" aria-label="关闭">×</button>
    <div class="toast-progress"></div>
  `;
  container.appendChild(toast);
  requestAnimationFrame(() => toast.classList.add('toast-show'));
  const dismiss = () => {
    toast.classList.remove('toast-show');
    toast.classList.add('toast-hide');
    setTimeout(() => toast.remove(), 500);
  };
  toast.querySelector('.toast-close').addEventListener('click', dismiss);
  setTimeout(dismiss, duration);
}
```

---

## 18. Luxury Spinner / Loading Indicator（奢华加载指示器）

> 金色环形旋转器 + 金色圆点脉动，配以 Cormorant Garamond 斜体优雅加载文字。

```html
<!-- 金色环形旋转器 -->
<div class="spinner-ring">
  <svg viewBox="0 0 60 60" width="60" height="60">
    <circle cx="30" cy="30" r="26" fill="none" stroke="rgba(244,211,94,0.15)" stroke-width="2.5"/>
    <circle class="spinner-ring-track" cx="30" cy="30" r="26" fill="none" stroke="#F4D35E" stroke-width="2.5" stroke-linecap="round" stroke-dasharray="80 120"/>
  </svg>
</div>

<!-- 金色圆点脉动 -->
<div class="spinner-dots">
  <span></span><span></span><span></span>
</div>

<!-- 带文字的完整加载 -->
<div class="loading-indicator">
  <div class="spinner-ring">
    <svg viewBox="0 0 60 60" width="48" height="48">
      <circle cx="30" cy="30" r="26" fill="none" stroke="rgba(244,211,94,0.12)" stroke-width="2"/>
      <circle class="spinner-ring-track" cx="30" cy="30" r="26" fill="none" stroke="#F4D35E" stroke-width="2" stroke-linecap="round" stroke-dasharray="80 120"/>
    </svg>
  </div>
  <p class="loading-text"><em>Preparing your experience</em></p>
  <p class="loading-subtext">正在为您精心准备…</p>
</div>
```
```css
.spinner-ring {
  display: inline-flex;
  align-items: center;
  justify-content: center;
}
.spinner-ring svg { animation: spinner-rotate 1.2s linear infinite; }
.spinner-ring-track {
  transform-origin: center;
  animation: spinner-dash 1.8s ease-in-out infinite;
}
@keyframes spinner-rotate {
  to { transform: rotate(360deg); }
}
@keyframes spinner-dash {
  0% { stroke-dasharray: 20 140; stroke-dashoffset: 0; }
  50% { stroke-dasharray: 80 80; stroke-dashoffset: -20; }
  100% { stroke-dasharray: 20 140; stroke-dashoffset: -120; }
}

.spinner-dots {
  display: inline-flex;
  align-items: center;
  gap: 8px;
}
.spinner-dots span {
  width: 10px; height: 10px;
  border-radius: 50%;
  background: var(--gold);
  animation: dot-pulse 1.4s ease-in-out infinite;
}
.spinner-dots span:nth-child(2) { animation-delay: 0.2s; }
.spinner-dots span:nth-child(3) { animation-delay: 0.4s; }
@keyframes dot-pulse {
  0%, 80%, 100% { opacity: 0.25; transform: scale(0.7); }
  40% { opacity: 1; transform: scale(1); }
}

.loading-indicator {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--sp-3);
  padding: var(--sp-8) var(--sp-6);
}
.loading-text {
  font-family: 'Cormorant Garamond', 'Noto Serif SC', serif;
  font-size: 1.35rem;
  font-style: italic;
  font-weight: 400;
  color: var(--royal);
  margin: 0;
  letter-spacing: 0.02em;
}
.loading-subtext {
  font-family: var(--font-sans);
  font-size: 0.8rem;
  color: var(--ink-200);
  margin: 0;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}
```

---

## 19. Skeleton Loader（骨架屏加载器）

> 微光闪烁效果的内容占位骨架，包含卡片骨架、文字骨架和头像骨架。

```html
<!-- 卡片骨架 -->
<div class="skeleton-card">
  <div class="skeleton skeleton-avatar"></div>
  <div class="skeleton-card-body">
    <div class="skeleton skeleton-text skeleton-text-title"></div>
    <div class="skeleton skeleton-text"></div>
    <div class="skeleton skeleton-text skeleton-text-70"></div>
  </div>
</div>

<!-- 纯文字骨架 -->
<div class="skeleton-lines">
  <div class="skeleton skeleton-text skeleton-text-title"></div>
  <div class="skeleton skeleton-text"></div>
  <div class="skeleton skeleton-text"></div>
  <div class="skeleton skeleton-text skeleton-text-60"></div>
</div>

<!-- 头像骨架（圆形） -->
<div class="skeleton skeleton-avatar-circle"></div>
```
```css
.skeleton {
  background: var(--surface);
  border-radius: var(--r-sm);
  position: relative;
  overflow: hidden;
}
.skeleton::after {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background: linear-gradient(90deg, transparent 25%, rgba(244,211,94,0.12) 50%, transparent 75%);
  background-size: 200% 100%;
  animation: skeleton-shimmer 1.8s ease-in-out infinite;
}
@keyframes skeleton-shimmer {
  0% { background-position: 200% 0; }
  100% { background-position: -200% 0; }
}

.skeleton-card {
  display: flex;
  gap: var(--sp-4);
  padding: var(--sp-5);
  background: #fff;
  border-radius: var(--r-lg);
  box-shadow: var(--shadow-sm);
}
.skeleton-avatar {
  flex-shrink: 0;
  width: 56px; height: 56px;
  border-radius: var(--r-md);
}
.skeleton-avatar-circle {
  width: 48px; height: 48px;
  border-radius: 50%;
}
.skeleton-card-body { flex: 1; display: flex; flex-direction: column; gap: var(--sp-2); }
.skeleton-lines { display: flex; flex-direction: column; gap: var(--sp-2); padding: var(--sp-4) 0; }
.skeleton-text {
  height: 14px;
  border-radius: var(--r-sm);
}
.skeleton-text-title { height: 20px; width: 55%; margin-bottom: var(--sp-2); }
.skeleton-text-70 { width: 70%; }
.skeleton-text-60 { width: 60%; }
```

---

## 20. Empty State（空状态）

> 优雅的空状态展示，配 fleuron 装饰符、Cormorant Garamond 斜体文案和金色 CTA 按钮。

```html
<div class="empty-state">
  <div class="empty-fleuron">❧</div>
  <p class="empty-title"><em>Nothing here yet</em></p>
  <p class="empty-description">您还没有创建任何作品。<br>从第一个项目开始，书写您的篇章。</p>
  <a href="#" class="btn btn-gold">创建第一个作品</a>
</div>
```
```css
.empty-state {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: clamp(48px, 8vh, 80px) var(--sp-6);
  background: var(--paper);
  border-radius: var(--r-lg);
  border: 1px dashed var(--border);
}
.empty-fleuron {
  font-size: 2rem;
  color: var(--gold);
  line-height: 1;
  margin-bottom: var(--sp-4);
  opacity: 0.7;
}
.empty-title {
  font-family: 'Cormorant Garamond', 'Noto Serif SC', serif;
  font-size: clamp(1.4rem, 2.5vw, 1.75rem);
  font-style: italic;
  font-weight: 400;
  color: var(--royal);
  margin: 0 0 var(--sp-3);
  letter-spacing: 0.01em;
}
.empty-title::after {
  content: '';
  display: block;
  width: 48px;
  height: 1.5px;
  background: var(--gold);
  margin: var(--sp-3) auto 0;
}
.empty-description {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  color: var(--ink-200);
  line-height: 1.7;
  max-width: 360px;
  margin: 0 0 var(--sp-5);
}
```

---

## 21. Error State / 404 Component（错误状态 / 404页面）

> 画册风格的错误页面，超大 Garamond 数字、金色装饰线、沉稳而有温度的表达。

```html
<div class="error-state">
  <div class="error-number">404</div>
  <div class="error-accent-line"></div>
  <p class="error-title"><em>Page not found</em></p>
  <p class="error-description">您寻找的页面可能已被移动、删除，或从未存在过。<br>让我们带您回到熟悉的地方。</p>
  <div class="error-actions">
    <a href="/" class="btn btn-primary">返回首页</a>
    <a href="javascript:history.back()" class="btn btn-outline">返回上一页</a>
  </div>
</div>
```
```css
.error-state {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: clamp(60px, 12vh, 120px) var(--page-padding);
  position: relative;
}
.error-number {
  font-family: 'Playfair Display', 'Noto Serif SC', serif;
  font-size: clamp(5rem, 15vw, 10rem);
  font-weight: 700;
  color: var(--royal);
  line-height: 1;
  letter-spacing: -0.03em;
  position: relative;
}
.error-number::before {
  content: '404';
  position: absolute;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
  font-size: 1em;
  color: transparent;
  -webkit-text-stroke: 1px rgba(244,211,94,0.25);
  z-index: -1;
}
.error-accent-line {
  width: 64px;
  height: 2px;
  background: var(--gold);
  margin: var(--sp-4) 0 var(--sp-5);
}
.error-title {
  font-family: 'Cormorant Garamond', 'Noto Serif SC', serif;
  font-size: clamp(1.3rem, 2.5vw, 1.75rem);
  font-style: italic;
  font-weight: 400;
  color: var(--ink);
  margin: 0 0 var(--sp-3);
}
.error-description {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  color: var(--ink-200);
  line-height: 1.7;
  max-width: 420px;
  margin: 0 0 var(--sp-6);
}
.error-actions {
  display: flex;
  gap: var(--sp-3);
  flex-wrap: wrap;
  justify-content: center;
}
```

---

## 22. Circular Progress Ring（环形进度指示器）

> 基于 SVG 的环形进度，支持金色/皇家蓝/酒红三种变体，中心配以 Garamond 百分比数字。

```html
<!-- 金色（默认/成功） -->
<div class="progress-ring" style="--progress: 75;">
  <svg viewBox="0 0 120 120" width="120" height="120">
    <circle cx="60" cy="60" r="52" fill="none" stroke="var(--cream-200)" stroke-width="6"/>
    <circle class="progress-ring-fill progress-ring-gold" cx="60" cy="60" r="52" fill="none" stroke-width="6" stroke-linecap="round"/>
  </svg>
  <div class="progress-ring-label">
    <span class="progress-ring-value">75%</span>
    <span class="progress-ring-caption">完成度</span>
  </div>
</div>

<!-- 皇家蓝（进行中） -->
<div class="progress-ring" style="--progress: 45;">
  <svg viewBox="0 0 120 120" width="120" height="120">
    <circle cx="60" cy="60" r="52" fill="none" stroke="var(--cream-200)" stroke-width="6"/>
    <circle class="progress-ring-fill progress-ring-royal" cx="60" cy="60" r="52" fill="none" stroke-width="6" stroke-linecap="round"/>
  </svg>
  <div class="progress-ring-label">
    <span class="progress-ring-value">45%</span>
    <span class="progress-ring-caption">上传中</span>
  </div>
</div>

<!-- 酒红（警告/低进度） -->
<div class="progress-ring" style="--progress: 22;">
  <svg viewBox="0 0 120 120" width="120" height="120">
    <circle cx="60" cy="60" r="52" fill="none" stroke="var(--cream-200)" stroke-width="6"/>
    <circle class="progress-ring-fill progress-ring-wine" cx="60" cy="60" r="52" fill="none" stroke-width="6" stroke-linecap="round"/>
  </svg>
  <div class="progress-ring-label">
    <span class="progress-ring-value">22%</span>
    <span class="progress-ring-caption">储存空间</span>
  </div>
</div>
```
```css
.progress-ring {
  position: relative;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}
.progress-ring svg { transform: rotate(-90deg); }
.progress-ring-fill {
  stroke-dasharray: 327; /* 2 * PI * 52 ≈ 327 */
  stroke-dashoffset: calc(327 - (327 * var(--progress)) / 100);
  transition: stroke-dashoffset var(--t-slow) cubic-bezier(0.16,1,0.3,1);
}
.progress-ring-gold { stroke: var(--gold); }
.progress-ring-royal { stroke: var(--royal); }
.progress-ring-wine { stroke: var(--wine); }

.progress-ring-label {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2px;
}
.progress-ring-value {
  font-family: 'Cormorant Garamond', 'Noto Serif SC', serif;
  font-size: 1.6rem;
  font-weight: 600;
  color: var(--royal);
  line-height: 1;
}
.progress-ring-caption {
  font-family: var(--font-sans);
  font-size: 0.7rem;
  color: var(--ink-200);
  letter-spacing: 0.08em;
  text-transform: uppercase;
}
```

---

## 23. Confirmation Dialog（确认对话框）

> 模态对话框，皇家蓝头部配金色装饰，确认/取消按钮组合，支持遮罩层。

```html
<div class="dialog-overlay" id="dialogOverlay">
  <div class="dialog">
    <div class="dialog-header">
      <div class="dialog-gold-bar"></div>
      <h3 class="dialog-title">确认操作</h3>
      <button class="dialog-close" aria-label="关闭">×</button>
    </div>
    <div class="dialog-body">
      <div class="dialog-icon dialog-icon-warn">!</div>
      <p class="dialog-message">
        您即将删除 <strong>「品牌设计作品集」</strong>，此操作不可撤销。<br>
        <span class="dialog-sub">删除后，所有相关数据将永久丢失。</span>
      </p>
    </div>
    <div class="dialog-footer">
      <button class="btn btn-outline dialog-btn-cancel">取消</button>
      <button class="btn btn-cta dialog-btn-confirm">确认删除</button>
    </div>
  </div>
</div>
```
```css
.dialog-overlay {
  position: fixed;
  inset: 0;
  background: rgba(13,18,37,0.5);
  backdrop-filter: blur(4px);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9998;
  padding: var(--sp-4);
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s ease, visibility 0.3s ease;
}
.dialog-overlay.dialog-open {
  opacity: 1;
  visibility: visible;
}
.dialog {
  background: #fff;
  border-radius: var(--r-lg);
  box-shadow: var(--shadow-lg);
  width: 100%;
  max-width: 440px;
  overflow: hidden;
  transform: scale(0.95) translateY(10px);
  transition: transform 0.4s cubic-bezier(0.16,1,0.3,1);
}
.dialog-overlay.dialog-open .dialog {
  transform: scale(1) translateY(0);
}
.dialog-header {
  position: relative;
  background: var(--royal);
  padding: var(--sp-5) var(--sp-6);
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.dialog-gold-bar {
  position: absolute;
  bottom: 0; left: 0;
  width: 100%;
  height: 3px;
  background: linear-gradient(90deg, var(--gold), transparent 60%);
}
.dialog-title {
  font-family: var(--font-serif);
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--gold);
  margin: 0;
  letter-spacing: 0.01em;
}
.dialog-close {
  background: none; border: none;
  color: rgba(255,255,255,0.6);
  font-size: 1.4rem;
  cursor: pointer;
  padding: 0;
  line-height: 1;
  transition: color var(--t-fast);
}
.dialog-close:hover { color: #fff; }
.dialog-body {
  padding: var(--sp-6);
  display: flex;
  gap: var(--sp-4);
  align-items: flex-start;
}
.dialog-icon {
  flex-shrink: 0;
  width: 40px; height: 40px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-family: 'Playfair Display', serif;
  font-size: 1.2rem;
  font-weight: 700;
}
.dialog-icon-warn {
  background: var(--wine-100);
  color: var(--wine);
  border: 2px solid rgba(216,49,91,0.2);
}
.dialog-message {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  color: var(--ink);
  line-height: 1.6;
  margin: 0;
}
.dialog-message strong { color: var(--royal); font-weight: 600; }
.dialog-sub {
  display: block;
  font-size: 0.8125rem;
  color: var(--ink-200);
  margin-top: var(--sp-2);
}
.dialog-footer {
  padding: 0 var(--sp-6) var(--sp-6);
  display: flex;
  justify-content: flex-end;
  gap: var(--sp-3);
}
```

---

## 24. Success Check Animation（成功勾选动画）

> 金色圆形勾选动画，绘制弧线后弹出对勾，优雅而克制。

```html
<div class="success-check">
  <svg viewBox="0 0 80 80" width="80" height="80">
    <circle class="success-circle" cx="40" cy="40" r="36" fill="none" stroke="#F4D35E" stroke-width="3"/>
    <path class="success-tick" d="M24 41 L36 53 L58 30" fill="none" stroke="#F4D35E" stroke-width="3.5" stroke-linecap="round" stroke-linejoin="round"/>
  </svg>
  <p class="success-label"><em>Completed</em></p>
</div>
```
```css
.success-check {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--sp-3);
}
.success-check svg { display: block; }
.success-circle {
  stroke-dasharray: 226; /* 2 * PI * 36 ≈ 226 */
  stroke-dashoffset: 226;
  animation: success-draw-circle 0.6s cubic-bezier(0.16,1,0.3,1) forwards;
}
.success-tick {
  stroke-dasharray: 60;
  stroke-dashoffset: 60;
  animation: success-draw-tick 0.4s cubic-bezier(0.16,1,0.3,1) 0.5s forwards;
}
@keyframes success-draw-circle {
  to { stroke-dashoffset: 0; }
}
@keyframes success-draw-tick {
  to { stroke-dashoffset: 0; }
}
.success-label {
  font-family: 'Cormorant Garamond', 'Noto Serif SC', serif;
  font-size: 1.25rem;
  font-style: italic;
  font-weight: 400;
  color: var(--royal);
  margin: 0;
  opacity: 0;
  animation: success-fade-in 0.5s ease 0.8s forwards;
}
@keyframes success-fade-in {
  to { opacity: 1; }
}
```

---

## 25. Inline Validation Message（内联验证消息）

> 表单内联验证反馈，支持错误/成功/警告/信息四种状态，配以线性图标。

```html
<div class="validation validation-error">
  <svg class="validation-icon" viewBox="0 0 20 20" width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round">
    <circle cx="10" cy="10" r="8"/>
    <line x1="10" y1="6" x2="10" y2="10"/>
    <line x1="10" y1="13" x2="10.01" y2="13"/>
  </svg>
  <span>请输入有效的邮箱地址</span>
</div>

<div class="validation validation-success">
  <svg class="validation-icon" viewBox="0 0 20 20" width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
    <path d="M5 10 L8.5 13.5 L15 6.5"/>
  </svg>
  <span>用户名可以使用</span>
</div>

<div class="validation validation-warning">
  <svg class="validation-icon" viewBox="0 0 20 20" width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round">
    <path d="M10 3 L18 16 L2 16 Z"/>
    <line x1="10" y1="8" x2="10" y2="11"/>
    <line x1="10" y1="13.5" x2="10.01" y2="13.5"/>
  </svg>
  <span>密码强度较弱，建议增加特殊字符</span>
</div>

<div class="validation validation-info">
  <svg class="validation-icon" viewBox="0 0 20 20" width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round">
    <circle cx="10" cy="10" r="8"/>
    <line x1="10" y1="9" x2="10" y2="13"/>
    <line x1="10" y1="7" x2="10.01" y2="7"/>
  </svg>
  <span>用户名将作为您的个人主页地址</span>
</div>
```
```css
.validation {
  display: flex;
  align-items: flex-start;
  gap: var(--sp-2);
  font-family: var(--font-sans);
  font-size: 0.8125rem;
  line-height: 1.5;
  margin-top: var(--sp-2);
  padding: var(--sp-2) var(--sp-3);
  border-radius: var(--r-sm);
}
.validation-icon {
  flex-shrink: 0;
  margin-top: 1px;
}
.validation-error {
  color: var(--wine-700);
  background: var(--wine-100);
}
.validation-error .validation-icon { color: var(--wine); }

.validation-success {
  color: #065F46;
  background: #ECFDF5;
}
.validation-success .validation-icon { color: var(--success); }

.validation-warning {
  color: var(--gold-800);
  background: var(--gold-100);
}
.validation-warning .validation-icon { color: var(--gold-700); }

.validation-info {
  color: var(--royal);
  background: var(--royal-100);
}
.validation-info .validation-icon { color: var(--royal); }
```

---

## 26. Progress Steps / Stepper（步骤指示器）

> 水平步骤指示器，金色已完成步骤、皇家蓝当前步骤、灰色待完成步骤。

```html
<div class="stepper">
  <div class="step step-completed">
    <div class="step-marker">✓</div>
    <div class="step-label">
      <span class="step-title">基本信息</span>
      <span class="step-caption">填写资料</span>
    </div>
  </div>
  <div class="step-connector step-connector-completed"></div>
  <div class="step step-active">
    <div class="step-marker">2</div>
    <div class="step-label">
      <span class="step-title">选择方案</span>
      <span class="step-caption">定制服务</span>
    </div>
  </div>
  <div class="step-connector"></div>
  <div class="step">
    <div class="step-marker">3</div>
    <div class="step-label">
      <span class="step-title">确认支付</span>
      <span class="step-caption">完成订单</span>
    </div>
  </div>
</div>
```
```css
.stepper {
  display: flex;
  align-items: flex-start;
  width: 100%;
  padding: var(--sp-4) 0;
}
.step {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex-shrink: 0;
  min-width: 0;
}
.step-marker {
  width: 36px; height: 36px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-family: var(--font-sans);
  font-size: 0.875rem;
  font-weight: 600;
  background: var(--surface);
  color: var(--ink-200);
  border: 2px solid var(--border);
  transition: all var(--t-fast);
  z-index: 1;
}
.step-label {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: var(--sp-2);
  text-align: center;
  gap: 2px;
}
.step-title {
  font-family: var(--font-sans);
  font-size: 0.8125rem;
  font-weight: 500;
  color: var(--ink-200);
  white-space: nowrap;
}
.step-caption {
  font-family: var(--font-sans);
  font-size: 0.7rem;
  color: var(--subtle);
  letter-spacing: 0.03em;
}

/* Completed step */
.step-completed .step-marker {
  background: var(--gold);
  color: var(--royal);
  border-color: var(--gold);
  box-shadow: 0 2px 8px rgba(244,211,94,0.3);
}
.step-completed .step-title { color: var(--royal); font-weight: 600; }
.step-completed .step-caption { color: var(--ink-200); }

/* Active step */
.step-active .step-marker {
  background: var(--royal);
  color: var(--gold);
  border-color: var(--royal);
  box-shadow: 0 4px 12px rgba(10,36,99,0.25);
}
.step-active .step-title { color: var(--royal); font-weight: 600; }
.step-active .step-caption { color: var(--royal-500); }

/* Connector */
.step-connector {
  flex: 1;
  height: 2px;
  background: var(--border);
  margin-top: 17px; /* align with center of marker */
  margin-left: -4px;
  margin-right: -4px;
  transition: background var(--t-fast);
}
.step-connector-completed {
  background: var(--gold);
}
```

---

## 27. Notification Badge / Dot（通知徽章/圆点）

> 金色/红色通知圆点和数字徽章，可附着于图标或头像角落。

```html
<!-- 金色圆点（提示有新内容） -->
<button class="icon-btn badge-wrap">
  <svg viewBox="0 0 24 24" width="20" height="20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"><path d="M18 8A6 6 0 0 0 6 8c0 7-3 9-3 9h18s-3-2-3-9"/><path d="M13.73 21a2 2 0 0 1-3.46 0"/></svg>
  <span class="badge-dot badge-gold"></span>
</button>

<!-- 红色数字徽章 -->
<button class="icon-btn badge-wrap">
  <svg viewBox="0 0 24 24" width="20" height="20" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
  <span class="badge-number badge-wine">3</span>
</button>

<!-- 大号数字徽章（99+） -->
<a href="#" class="badge-wrap">
  <div class="avatar-mini"></div>
  <span class="badge-number badge-gold">99+</span>
</a>

<!-- 独立状态圆点 -->
<span class="status-dot status-online"></span> 在线
<span class="status-dot status-away"></span> 离开
<span class="status-dot status-offline"></span> 离线
```
```css
.icon-btn {
  position: relative;
  width: 40px; height: 40px;
  border-radius: var(--r-md);
  border: none;
  background: var(--surface);
  color: var(--ink-100);
  display: flex; align-items: center; justify-content: center;
  cursor: pointer;
  transition: all var(--t-fast);
}
.icon-btn:hover { background: var(--royal-100); color: var(--royal); }
.avatar-mini {
  width: 40px; height: 40px;
  border-radius: 50%;
  background: var(--royal-200);
}

.badge-wrap {
  position: relative;
  display: inline-flex;
}

/* Dot badge */
.badge-dot {
  position: absolute;
  top: 6px; right: 6px;
  width: 9px; height: 9px;
  border-radius: 50%;
  border: 2px solid #fff;
  z-index: 2;
}
.badge-gold { background: var(--gold); box-shadow: 0 0 0 2px rgba(244,211,94,0.3); }
.badge-wine { background: var(--wine); box-shadow: 0 0 0 2px rgba(216,49,91,0.25); }

/* Number badge */
.badge-number {
  position: absolute;
  top: -4px; right: -4px;
  min-width: 18px; height: 18px;
  padding: 0 5px;
  border-radius: var(--r-pill);
  font-family: var(--font-sans);
  font-size: 0.65rem;
  font-weight: 600;
  display: flex; align-items: center; justify-content: center;
  border: 2px solid #fff;
  z-index: 2;
  line-height: 1;
}
.badge-number.badge-wine {
  background: var(--wine);
  color: #fff;
}
.badge-number.badge-gold {
  background: var(--gold);
  color: var(--royal);
}

/* Status dots */
.status-dot {
  display: inline-block;
  width: 8px; height: 8px;
  border-radius: 50%;
  margin-right: 6px;
  vertical-align: middle;
}
.status-online { background: var(--success); box-shadow: 0 0 0 2px rgba(45,155,94,0.2); }
.status-away { background: var(--gold); box-shadow: 0 0 0 2px rgba(244,211,94,0.2); }
.status-offline { background: var(--subtle); }
```

---

## 28. Banner Alert（全宽横幅提示）

> 全宽横幅通知，支持金色信息提示、酒红错误警告、皇家蓝公告三种变体。

```html
<!-- 金色信息提示 -->
<div class="banner banner-info">
  <div class="banner-inner">
    <svg class="banner-icon" viewBox="0 0 20 20" width="18" height="18" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round">
      <circle cx="10" cy="10" r="8"/>
      <line x1="10" y1="9" x2="10" y2="13"/>
      <line x1="10" y1="7" x2="10.01" y2="7"/>
    </svg>
    <div class="banner-content">
      <span class="banner-tag">提示</span>
      <span class="banner-text">系统将于今晚 23:00 - 次日 02:00 进行维护升级，期间可能无法访问。</span>
    </div>
    <button class="banner-close" aria-label="关闭">×</button>
  </div>
</div>

<!-- 酒红错误警告 -->
<div class="banner banner-error">
  <div class="banner-inner">
    <svg class="banner-icon" viewBox="0 0 20 20" width="18" height="18" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round">
      <circle cx="10" cy="10" r="8"/>
      <line x1="10" y1="6" x2="10" y2="10"/>
      <line x1="10" y1="13" x2="10.01" y2="13"/>
    </svg>
    <div class="banner-content">
      <span class="banner-tag">错误</span>
      <span class="banner-text">网络连接异常，请检查您的网络设置后重试。</span>
    </div>
    <button class="banner-btn">重试</button>
    <button class="banner-close" aria-label="关闭">×</button>
  </div>
</div>

<!-- 皇家蓝公告 -->
<div class="banner banner-announce">
  <div class="banner-inner">
    <span class="banner-fleuron">❦</span>
    <div class="banner-content">
      <span class="banner-tag banner-tag-light">重要公告</span>
      <span class="banner-text banner-text-light">全新作品集模板已上线，<a href="#" class="banner-link">立即查看</a>。</span>
    </div>
    <button class="banner-close banner-close-light" aria-label="关闭">×</button>
  </div>
</div>
```
```css
.banner {
  width: 100%;
  padding: var(--sp-3) var(--sp-5);
  border-radius: 0;
  position: relative;
}
.banner-inner {
  display: flex;
  align-items: center;
  gap: var(--sp-3);
  max-width: 1200px;
  margin: 0 auto;
}
.banner-icon { flex-shrink: 0; }
.banner-content {
  flex: 1;
  display: flex;
  align-items: center;
  gap: var(--sp-3);
  font-family: var(--font-sans);
  font-size: 0.875rem;
  line-height: 1.5;
}
.banner-tag {
  flex-shrink: 0;
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 2px 8px;
  border-radius: var(--r-sm);
}
.banner-close {
  flex-shrink: 0;
  background: none; border: none;
  font-size: 1.2rem;
  cursor: pointer;
  padding: 4px;
  line-height: 1;
  opacity: 0.6;
  transition: opacity var(--t-fast);
}
.banner-close:hover { opacity: 1; }
.banner-btn {
  flex-shrink: 0;
  font-family: var(--font-sans);
  font-size: 0.8125rem;
  font-weight: 500;
  padding: 6px 16px;
  border-radius: var(--r-sm);
  border: 1.5px solid currentColor;
  background: transparent;
  cursor: pointer;
  transition: all var(--t-fast);
}
.banner-fleuron {
  flex-shrink: 0;
  font-size: 1.1rem;
  line-height: 1;
}

/* Info variant (gold) */
.banner-info {
  background: var(--gold-100);
  color: var(--gold-800);
  border-bottom: 2px solid var(--gold);
}
.banner-info .banner-tag {
  background: var(--gold);
  color: var(--royal);
}
.banner-info .banner-btn:hover {
  background: var(--gold);
  color: var(--royal);
}

/* Error variant (wine) */
.banner-error {
  background: var(--wine-100);
  color: var(--wine-700);
  border-bottom: 2px solid var(--wine);
}
.banner-error .banner-tag {
  background: var(--wine);
  color: #fff;
}
.banner-error .banner-btn:hover {
  background: var(--wine);
  color: #fff;
}

/* Announce variant (royal blue) */
.banner-announce {
  background: var(--royal);
  color: rgba(255,255,255,0.85);
  border-bottom: 3px solid var(--gold);
}
.banner-tag-light {
  background: var(--gold);
  color: var(--royal) !important;
}
.banner-text-light { color: rgba(255,255,255,0.9); }
.banner-close-light { color: rgba(255,255,255,0.6); }
.banner-close-light:hover { color: #fff; }
.banner-link {
  color: var(--gold);
  text-decoration: none;
  font-weight: 500;
  border-bottom: 1px solid transparent;
  transition: border-color var(--t-fast);
}
.banner-link:hover { border-bottom-color: var(--gold); }
.banner-announce .banner-fleuron { color: var(--gold); }
```

---

*Feihong Design System v8.0 · Feedback Components · 反馈组件集*
*所有组件遵循品牌基因 DNA.md 规范：Royal Blue #0A2463 · Vintage Gold #F4D35E · Burgundy Wine #D8315B*
*字体：Playfair Display / Cormorant Garamond / Inter + Noto Sans SC / JetBrains Mono*