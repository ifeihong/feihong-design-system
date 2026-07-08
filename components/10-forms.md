# FEIHONG Design System — Forms
# N°10 · 表单
> Inputs, textareas, selects, and form groups with royal-blue focus states.
> 输入框、文本域、下拉选择和表单组，配皇家蓝聚焦态。
> Part of FEIHONG Design System v7.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 7. Form Elements 表单

### 7.1 Input（输入框）

```html
<div class="form-group">
  <label class="form-label">姓名</label>
  <input type="text" class="form-input" placeholder="请输入您的姓名">
</div>
```
```css
.form-group { margin-bottom: var(--sp-5); }
.form-label {
  display: block;
  font-family: var(--font-sans);
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--ink);
  margin-bottom: var(--sp-2);
}
.form-input {
  width: 100%;
  font-family: var(--font-sans);
  font-size: 1rem;
  padding: var(--sp-3) var(--sp-4);
  border: 1.5px solid var(--cream-200);
  border-radius: var(--r-md);
  background: #fff;
  color: var(--ink);
  transition: all var(--t-fast);
  outline: none;
}
.form-input:focus {
  border-color: var(--royal);
  box-shadow: 0 0 0 3px var(--royal-50);
}
.form-input::placeholder { color: var(--ink-400); }
```

### 7.2 Textarea

```html
<div class="form-group">
  <label class="form-label">项目描述</label>
  <textarea class="form-input form-textarea" rows="4" placeholder="简单描述您的项目..."></textarea>
</div>
```
```css
.form-textarea { resize: vertical; min-height: 120px; line-height: 1.6; }
```

### 7.3 Select

```html
<div class="form-group">
  <label class="form-label">项目类型</label>
  <select class="form-input form-select">
    <option>品牌设计</option>
    <option>落地页设计</option>
    <option>设计系统</option>
  </select>
</div>
```
```css
.form-select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='8' viewBox='0 0 12 8'%3E%3Cpath d='M1 1l5 5 5-5' stroke='%230A2463' stroke-width='1.5' fill='none' stroke-linecap='round'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right var(--sp-4) center;
  padding-right: var(--sp-8);
}
```
