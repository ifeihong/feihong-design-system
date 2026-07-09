# Feihong Design System — Feedback
# N°17 · 反馈组件
> Alerts, notifications, progress bars, and timelines for feedback and storytelling.
> 提示框、通知、进度条和时间线，用于状态反馈与叙事。
> Part of Feihong Design System v7.0 · 所有组件遵循 DNA.md 色彩字体规范
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
