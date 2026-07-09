# Feihong Design System — Forms
# N°10 · 表单
> Inputs, textareas, selects, and form groups with royal-blue focus states.
> 输入框、文本域、下拉选择和表单组，配皇家蓝聚焦态。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## Design Tokens 设计令牌

```css
:root {
  /* Brand Colors */
  --royal: #0A2463;
  --royal-700: #081C4F;
  --royal-500: #1A3A7A;
  --royal-100: #DDE3F0;
  --royal-50:  rgba(10, 36, 99, 0.08);
  --gold: #F4D35E;
  --gold-600: #D4B239;
  --gold-500: #E8C547;
  --gold-100: #FDF6D9;
  --gold-50:  rgba(244, 211, 94, 0.15);
  --wine: #D8315B;
  --wine-100: #FBE4E9;
  --wine-50:  rgba(216, 49, 91, 0.1);
  --cream: #FDFBF6;
  --paper: #FAF7F0;
  --cream-200: #EDE8DB;
  --cream-300: #DFD9C9;
  --ink: #1A1A2E;
  --ink-700: #3A3A4E;
  --ink-400: #8A8A9A;
  --ink-200: #C8C6D2;
  --success: #2E7D5B;
  --success-100: #DFF0E7;
  --warning: #C47D2A;
  --warning-100: #FBEDD8;

  /* Typography */
  --font-serif: 'Cormorant Garamond', 'Noto Serif SC', Georgia, serif;
  --font-sans: 'Inter', 'Noto Sans SC', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', monospace;

  /* Spacing */
  --sp-1: 0.25rem;
  --sp-2: 0.5rem;
  --sp-3: 0.75rem;
  --sp-4: 1rem;
  --sp-5: 1.25rem;
  --sp-6: 1.5rem;
  --sp-8: 2rem;
  --sp-10: 2.5rem;

  /* Radius */
  --r-sm: 4px;
  --r-md: 8px;
  --r-lg: 12px;
  --r-xl: 16px;

  /* Transitions */
  --t-fast: 200ms cubic-bezier(0.4, 0, 0.2, 1);
  --t-med: 300ms cubic-bezier(0.4, 0, 0.2, 1);
  --t-slow: 500ms cubic-bezier(0.4, 0, 0.2, 1);

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(10, 36, 99, 0.06);
  --shadow-md: 0 4px 12px rgba(10, 36, 99, 0.08);
  --shadow-lg: 0 8px 32px rgba(10, 36, 99, 0.12);
  --shadow-gold: 0 4px 16px rgba(244, 211, 94, 0.3);
}
```

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
  letter-spacing: 0.02em;
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

---

### 7.4 Luxury Checkbox（奢华复选框）

> 皇家蓝描边 + 金色勾选标记 + Garamond 衬线标签，呈现编辑级质感。
> Royal-blue border with gold checkmark and Garamond serif label.

```html
<label class="lux-checkbox">
  <input type="checkbox" class="lux-checkbox-input" checked>
  <span class="lux-checkbox-box">
    <svg class="lux-checkbox-tick" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
      <polyline points="20 6 9 17 4 12"></polyline>
    </svg>
  </span>
  <span class="lux-checkbox-label">我已阅读并同意<em>服务条款</em></span>
</label>

<label class="lux-checkbox">
  <input type="checkbox" class="lux-checkbox-input">
  <span class="lux-checkbox-box">
    <svg class="lux-checkbox-tick" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
      <polyline points="20 6 9 17 4 12"></polyline>
    </svg>
  </span>
  <span class="lux-checkbox-label">订阅<em>飞鸿通讯</em>季刊</span>
</label>
```
```css
.lux-checkbox {
  display: inline-flex;
  align-items: flex-start;
  gap: var(--sp-3);
  cursor: pointer;
  user-select: none;
  margin-bottom: var(--sp-3);
  font-family: var(--font-sans);
}
.lux-checkbox-input {
  position: absolute;
  opacity: 0;
  width: 0;
  height: 0;
}
.lux-checkbox-box {
  flex-shrink: 0;
  width: 22px;
  height: 22px;
  border: 1.5px solid var(--royal);
  border-radius: var(--r-sm);
  background: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 2px;
  transition: all var(--t-fast);
}
.lux-checkbox-tick {
  width: 14px;
  height: 14px;
  color: transparent;
  transition: color var(--t-fast), transform var(--t-med);
  transform: scale(0.5);
}
.lux-checkbox-input:checked + .lux-checkbox-box {
  background: var(--royal);
  border-color: var(--royal);
}
.lux-checkbox-input:checked + .lux-checkbox-box .lux-checkbox-tick {
  color: var(--gold);
  transform: scale(1);
}
.lux-checkbox-input:focus-visible + .lux-checkbox-box {
  box-shadow: 0 0 0 3px var(--royal-50);
}
.lux-checkbox-label {
  font-size: 0.9375rem;
  line-height: 1.6;
  color: var(--ink-700);
}
.lux-checkbox-label em {
  font-family: var(--font-serif);
  font-style: italic;
  font-size: 1.05em;
  color: var(--royal);
  font-weight: 600;
}
.lux-checkbox:hover .lux-checkbox-box {
  border-color: var(--royal-500);
  box-shadow: 0 0 0 3px var(--royal-50);
}
```

---

### 7.5 Luxury Radio Button（奢华单选按钮）

> 金色圆心指示器 + 皇家蓝外环选中态，搭配衬线标签。
> Gold dot indicator inside royal-blue selected ring.

```html
<div class="lux-radio-group">
  <label class="lux-radio">
    <input type="radio" name="plan" class="lux-radio-input" checked>
    <span class="lux-radio-dot">
      <span class="lux-radio-inner"></span>
    </span>
    <span class="lux-radio-label"><em>典藏</em>版 · ¥2,880/年</span>
  </label>
  <label class="lux-radio">
    <input type="radio" name="plan" class="lux-radio-input">
    <span class="lux-radio-dot">
      <span class="lux-radio-inner"></span>
    </span>
    <span class="lux-radio-label"><em>臻选</em>版 · ¥5,880/年</span>
  </label>
  <label class="lux-radio">
    <input type="radio" name="plan" class="lux-radio-input">
    <span class="lux-radio-dot">
      <span class="lux-radio-inner"></span>
    </span>
    <span class="lux-radio-label"><em>定制</em>服务 · 面议</span>
  </label>
</div>
```
```css
.lux-radio-group { display: flex; flex-direction: column; gap: var(--sp-3); }
.lux-radio {
  display: inline-flex;
  align-items: center;
  gap: var(--sp-3);
  cursor: pointer;
  user-select: none;
  font-family: var(--font-sans);
}
.lux-radio-input {
  position: absolute;
  opacity: 0;
  width: 0;
  height: 0;
}
.lux-radio-dot {
  flex-shrink: 0;
  width: 22px;
  height: 22px;
  border: 1.5px solid var(--cream-300);
  border-radius: 50%;
  background: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all var(--t-fast);
}
.lux-radio-inner {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: transparent;
  transform: scale(0);
  transition: all var(--t-med);
}
.lux-radio-input:checked + .lux-radio-dot {
  border-color: var(--royal);
  background: #fff;
}
.lux-radio-input:checked + .lux-radio-dot .lux-radio-inner {
  background: var(--gold);
  transform: scale(1);
  box-shadow: 0 0 0 3px var(--royal);
}
.lux-radio-input:focus-visible + .lux-radio-dot {
  box-shadow: 0 0 0 3px var(--royal-50);
}
.lux-radio-label {
  font-size: 0.9375rem;
  color: var(--ink-700);
}
.lux-radio-label em {
  font-family: var(--font-serif);
  font-style: italic;
  font-size: 1.15em;
  font-weight: 700;
  color: var(--royal);
}
.lux-radio:hover .lux-radio-dot {
  border-color: var(--royal-500);
}
```

---

### 7.6 Toggle / Velvet Switch（丝绒开关）

> 金色滑块在皇家蓝与奶油色轨道间滑动，如天鹅绒幕布开合。
> Gold thumb gliding between royal-blue and cream track, evoking velvet curtains.

```html
<label class="lux-switch">
  <input type="checkbox" class="lux-switch-input" checked>
  <span class="lux-switch-track">
    <span class="lux-switch-thumb"></span>
  </span>
  <span class="lux-switch-label">启用<em>高级</em>模式</span>
</label>

<label class="lux-switch">
  <input type="checkbox" class="lux-switch-input">
  <span class="lux-switch-track">
    <span class="lux-switch-thumb"></span>
  </span>
  <span class="lux-switch-label">邮件通知</span>
</label>
```
```css
.lux-switch {
  display: inline-flex;
  align-items: center;
  gap: var(--sp-3);
  cursor: pointer;
  user-select: none;
  font-family: var(--font-sans);
  margin-bottom: var(--sp-3);
}
.lux-switch-input {
  position: absolute;
  opacity: 0;
  width: 0;
  height: 0;
}
.lux-switch-track {
  position: relative;
  flex-shrink: 0;
  width: 52px;
  height: 28px;
  border-radius: 14px;
  background: var(--cream-300);
  transition: background var(--t-med);
  border: 1px solid transparent;
}
.lux-switch-thumb {
  position: absolute;
  top: 3px;
  left: 3px;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: var(--gold);
  box-shadow: 0 1px 3px rgba(0,0,0,0.15), inset 0 -1px 0 rgba(0,0,0,0.05);
  transition: transform var(--t-med), background var(--t-med), box-shadow var(--t-med);
}
.lux-switch-input:checked + .lux-switch-track {
  background: var(--royal);
  border-color: var(--royal-700);
}
.lux-switch-input:checked + .lux-switch-track .lux-switch-thumb {
  transform: translateX(24px);
  background: var(--gold);
  box-shadow: 0 2px 8px rgba(244, 211, 94, 0.5), 0 1px 3px rgba(0,0,0,0.2);
}
.lux-switch-input:focus-visible + .lux-switch-track {
  box-shadow: 0 0 0 3px var(--gold-50);
}
.lux-switch-label {
  font-size: 0.9375rem;
  color: var(--ink-700);
}
.lux-switch-label em {
  font-family: var(--font-serif);
  font-style: italic;
  font-size: 1.1em;
  font-weight: 600;
  color: var(--royal);
}
.lux-switch:active .lux-switch-thumb {
  width: 24px;
}
```

---

### 7.7 Search Input（搜索输入框）

> 金色放大镜图标 + 皇家蓝聚焦光环，适合导航栏与筛选区。
> Gold search icon with royal-blue focus ring, ideal for nav bars and filters.

```html
<div class="lux-search">
  <svg class="lux-search-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
    <circle cx="11" cy="11" r="8"></circle>
    <line x1="21" y1="21" x2="16.65" y2="16.65"></line>
  </svg>
  <input type="search" class="lux-search-input" placeholder="搜索作品、文章、设计师…">
  <kbd class="lux-search-kbd">⌘K</kbd>
</div>
```
```css
.lux-search {
  position: relative;
  display: flex;
  align-items: center;
  background: #fff;
  border: 1.5px solid var(--cream-200);
  border-radius: var(--r-lg);
  padding: 0 var(--sp-4);
  transition: all var(--t-fast);
}
.lux-search:focus-within {
  border-color: var(--royal);
  box-shadow: 0 0 0 4px var(--royal-50), var(--shadow-md);
}
.lux-search-icon {
  width: 18px;
  height: 18px;
  color: var(--gold-600);
  flex-shrink: 0;
  margin-right: var(--sp-3);
}
.lux-search-input {
  flex: 1;
  border: none;
  outline: none;
  background: transparent;
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  color: var(--ink);
  padding: var(--sp-3) 0;
}
.lux-search-input::placeholder { color: var(--ink-400); }
.lux-search-kbd {
  font-family: var(--font-mono);
  font-size: 0.75rem;
  color: var(--ink-400);
  background: var(--paper);
  border: 1px solid var(--cream-200);
  border-radius: var(--r-sm);
  padding: 2px 6px;
  margin-left: var(--sp-2);
  flex-shrink: 0;
}
```

---

### 7.8 File Upload（文件上传区）

> 金色虚线边框 + 花饰（fleuron）装饰，拖拽区呈现精致邀请函质感。
> Gold dashed border with fleuron ornament — evokes a fine invitation card.

```html
<div class="lux-upload" id="uploadZone">
  <input type="file" class="lux-upload-input" id="fileInput" multiple accept=".pdf,.doc,.docx,.jpg,.png">
  <div class="lux-upload-fleuron">❦</div>
  <svg class="lux-upload-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
    <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
    <polyline points="17 8 12 3 7 8"></polyline>
    <line x1="12" y1="3" x2="12" y2="15"></line>
  </svg>
  <p class="lux-upload-title"><em>拖拽</em>文件至此，或 <span class="lux-upload-browse">浏览文件</span></p>
  <p class="lux-upload-hint">支持 PDF / Word / 图片 · 单个文件不超过 20MB</p>
</div>
```
```css
.lux-upload {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: var(--sp-10) var(--sp-6);
  border: 2px dashed var(--gold-500);
  border-radius: var(--r-lg);
  background: var(--cream);
  cursor: pointer;
  transition: all var(--t-med);
  overflow: hidden;
}
.lux-upload::before {
  content: '';
  position: absolute;
  inset: 6px;
  border: 1px solid var(--gold-100);
  border-radius: calc(var(--r-lg) - 4px);
  pointer-events: none;
}
.lux-upload:hover,
.lux-upload.is-dragover {
  border-color: var(--gold);
  background: var(--gold-50);
  box-shadow: var(--shadow-gold);
}
.lux-upload-input {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  cursor: pointer;
}
.lux-upload-fleuron {
  font-family: var(--font-serif);
  font-size: 1.5rem;
  color: var(--gold);
  line-height: 1;
  margin-bottom: var(--sp-3);
}
.lux-upload-icon {
  width: 36px;
  height: 36px;
  color: var(--royal);
  margin-bottom: var(--sp-4);
}
.lux-upload-title {
  font-family: var(--font-sans);
  font-size: 1rem;
  color: var(--ink);
  margin: 0 0 var(--sp-2);
}
.lux-upload-title em {
  font-family: var(--font-serif);
  font-style: italic;
  font-size: 1.15em;
  font-weight: 600;
  color: var(--royal);
}
.lux-upload-browse {
  color: var(--royal);
  font-weight: 600;
  text-decoration: underline;
  text-decoration-color: var(--gold);
  text-underline-offset: 3px;
}
.lux-upload-hint {
  font-family: var(--font-sans);
  font-size: 0.8125rem;
  color: var(--ink-400);
  margin: 0;
}
```

---

### 7.9 Input with Icon（图标输入组）

> 图标前缀/后缀以金色细线分隔，营造编辑级排版感。
> Icon prefix/suffix separated by a gold hairline for editorial typography.

```html
<!-- Prefix icon 前缀图标 -->
<div class="lux-input-group">
  <label class="form-label">邮箱地址</label>
  <div class="lux-input-wrap">
    <span class="lux-input-icon lux-input-icon--prefix">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
        <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
        <polyline points="22,6 12,13 2,6"></polyline>
      </svg>
    </span>
    <input type="email" class="lux-input lux-input--prefix" placeholder="name@example.com">
  </div>
</div>

<!-- Suffix icon 后缀图标 -->
<div class="lux-input-group">
  <label class="form-label">个人网站</label>
  <div class="lux-input-wrap">
    <input type="url" class="lux-input lux-input--suffix" placeholder="https://yourdomain.com">
    <span class="lux-input-icon lux-input-icon--suffix">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
        <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
        <polyline points="15 3 21 3 21 9"></polyline>
        <line x1="10" y1="14" x2="21" y2="3"></line>
      </svg>
    </span>
  </div>
</div>

<!-- Both sides 两侧图标 -->
<div class="lux-input-group">
  <label class="form-label">预算范围</label>
  <div class="lux-input-wrap">
    <span class="lux-input-icon lux-input-icon--prefix">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
        <line x1="12" y1="1" x2="12" y2="23"></line>
        <path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"></path>
      </svg>
    </span>
    <input type="text" class="lux-input lux-input--both" placeholder="¥50,000 – ¥200,000">
    <span class="lux-input-icon lux-input-icon--suffix">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
        <polyline points="6 9 12 15 18 9"></polyline>
      </svg>
    </span>
  </div>
</div>
```
```css
.lux-input-group { margin-bottom: var(--sp-5); }
.lux-input-wrap {
  position: relative;
  display: flex;
  align-items: center;
  background: #fff;
  border: 1.5px solid var(--cream-200);
  border-radius: var(--r-md);
  transition: all var(--t-fast);
}
.lux-input-wrap:focus-within {
  border-color: var(--royal);
  box-shadow: 0 0 0 3px var(--royal-50);
}
.lux-input {
  flex: 1;
  border: none;
  outline: none;
  background: transparent;
  font-family: var(--font-sans);
  font-size: 1rem;
  color: var(--ink);
  padding: var(--sp-3) var(--sp-4);
  min-width: 0;
}
.lux-input::placeholder { color: var(--ink-400); }
.lux-input--prefix { padding-left: 0; }
.lux-input--suffix { padding-right: 0; }
.lux-input--both { padding-left: 0; padding-right: 0; }
.lux-input-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  width: 44px;
  color: var(--gold-600);
}
.lux-input-icon svg { width: 18px; height: 18px; }
.lux-input-icon--prefix {
  border-right: 1px solid var(--gold-100);
  padding-left: var(--sp-1);
}
.lux-input-icon--suffix {
  border-left: 1px solid var(--gold-100);
  padding-right: var(--sp-1);
  cursor: pointer;
  transition: color var(--t-fast);
}
.lux-input-icon--suffix:hover { color: var(--royal); }
```

---

### 7.10 Input Validation States（输入校验状态）

> 酒红描边 + 错误文案（error）、金色勾选（success）、琥珀警示（warning）。
> Wine-red border for error, gold check for success, amber for warning.

```html
<!-- Error state -->
<div class="form-group">
  <label class="form-label">邮箱地址</label>
  <div class="lux-input-wrap has-error">
    <input type="email" class="lux-input" placeholder="name@example.com" value="invalid-email">
    <span class="lux-input-icon lux-input-icon--suffix">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <circle cx="12" cy="12" r="10"></circle>
        <line x1="15" y1="9" x2="9" y2="15"></line>
        <line x1="9" y1="9" x2="15" y2="15"></line>
      </svg>
    </span>
  </div>
  <p class="lux-form-message lux-form-message--error">
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <circle cx="12" cy="12" r="10"></circle><line x1="12" y1="8" x2="12" y2="12"></line><line x1="12" y1="16" x2="12.01" y2="16"></line>
    </svg>
    请输入有效的邮箱地址
  </p>
</div>

<!-- Success state -->
<div class="form-group">
  <label class="form-label">用户名</label>
  <div class="lux-input-wrap has-success">
    <input type="text" class="lux-input" placeholder="用户名" value="feihong_studio">
    <span class="lux-input-icon lux-input-icon--suffix">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
        <polyline points="20 6 9 17 4 12"></polyline>
      </svg>
    </span>
  </div>
  <p class="lux-form-message lux-form-message--success">
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
      <polyline points="20 6 9 17 4 12"></polyline>
    </svg>
    该用户名可用
  </p>
</div>

<!-- Warning state -->
<div class="form-group">
  <label class="form-label">密码</label>
  <div class="lux-input-wrap has-warning">
    <input type="password" class="lux-input" placeholder="密码" value="123">
  </div>
  <p class="lux-form-message lux-form-message--warning">
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="M10.29 3.86L1.82 18a2 2 0 0 0 1.71 3h16.94a2 2 0 0 0 1.71-3L13.71 3.86a2 2 0 0 0-3.42 0z"></path><line x1="12" y1="9" x2="12" y2="13"></line><line x1="12" y1="17" x2="12.01" y2="17"></line>
    </svg>
    密码强度过低，建议使用 8 位以上含特殊字符的组合
  </p>
</div>
```
```css
.has-error { border-color: var(--wine) !important; background: #fff; }
.has-error:focus-within { box-shadow: 0 0 0 3px var(--wine-50) !important; border-color: var(--wine) !important; }
.has-error .lux-input-icon--suffix { color: var(--wine); border-left-color: var(--wine-100); }

.has-success { border-color: var(--success) !important; }
.has-success:focus-within { box-shadow: 0 0 0 3px rgba(46,125,91,0.12) !important; border-color: var(--success) !important; }
.has-success .lux-input-icon--suffix { color: var(--gold-600); border-left-color: var(--gold-100); }

.has-warning { border-color: var(--warning) !important; }
.has-warning:focus-within { box-shadow: 0 0 0 3px var(--warning-100) !important; border-color: var(--warning) !important; }

.lux-form-message {
  display: flex;
  align-items: center;
  gap: var(--sp-2);
  font-family: var(--font-sans);
  font-size: 0.8125rem;
  margin: var(--sp-2) 0 0;
  line-height: 1.5;
}
.lux-form-message svg { width: 14px; height: 14px; flex-shrink: 0; }
.lux-form-message--error { color: var(--wine); }
.lux-form-message--success { color: var(--success); }
.lux-form-message--warning { color: var(--warning); }
```

---

### 7.11 Password Input（密码输入 · 显示/隐藏）

> 右侧金色眼睛图标切换明文/密文，皇家蓝聚焦态。
> Gold eye icon toggles visibility; royal-blue focus.

```html
<div class="lux-input-group">
  <label class="form-label">账户密码</label>
  <div class="lux-input-wrap">
    <input type="password" class="lux-input lux-input--suffix" id="pwdInput" placeholder="请输入密码">
    <button type="button" class="lux-input-icon lux-input-icon--suffix lux-pwd-toggle" id="pwdToggle" aria-label="显示密码">
      <svg class="lux-eye-open" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
        <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path>
        <circle cx="12" cy="12" r="3"></circle>
      </svg>
      <svg class="lux-eye-closed" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round" style="display:none">
        <path d="M17.94 17.94A10.07 10.07 0 0 1 12 20c-7 0-11-8-11-8a18.45 18.45 0 0 1 5.06-5.94M9.9 4.24A9.12 9.12 0 0 1 12 4c7 0 11 8 11 8a18.5 18.5 0 0 1-2.16 3.19m-6.72-1.07a3 3 0 1 1-4.24-4.24"></path>
        <line x1="1" y1="1" x2="23" y2="23"></line>
      </svg>
    </button>
  </div>
</div>
```
```css
.lux-pwd-toggle {
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  color: var(--gold-600);
  display: flex;
  align-items: center;
  justify-content: center;
  width: 44px;
  height: 100%;
  border-left: 1px solid var(--gold-100);
  transition: color var(--t-fast);
}
.lux-pwd-toggle:hover { color: var(--royal); }
.lux-pwd-toggle svg { width: 18px; height: 18px; }
```
```javascript
const pwdInput = document.getElementById('pwdInput');
const pwdToggle = document.getElementById('pwdToggle');
const eyeOpen = pwdToggle.querySelector('.lux-eye-open');
const eyeClosed = pwdToggle.querySelector('.lux-eye-closed');
pwdToggle.addEventListener('click', () => {
  const isPwd = pwdInput.type === 'password';
  pwdInput.type = isPwd ? 'text' : 'password';
  eyeOpen.style.display = isPwd ? 'none' : '';
  eyeClosed.style.display = isPwd ? '' : 'none';
});
```

---

### 7.12 Date Picker（日期选择器）

> 日历图标前缀 + 衬线数字呈现，弹出面板采用皇家蓝主色。
> Calendar icon prefix with serif numerals; royal-blue popover theme.

```html
<div class="lux-input-group">
  <label class="form-label">预约日期</label>
  <div class="lux-input-wrap">
    <span class="lux-input-icon lux-input-icon--prefix">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
        <rect x="3" y="4" width="18" height="18" rx="2" ry="2"></rect>
        <line x1="16" y1="2" x2="16" y2="6"></line>
        <line x1="8" y1="2" x2="8" y2="6"></line>
        <line x1="3" y1="10" x2="21" y2="10"></line>
      </svg>
    </span>
    <input type="date" class="lux-input lux-input--prefix lux-date-input" placeholder="YYYY / MM / DD">
  </div>
</div>
```
```css
.lux-date-input {
  font-family: var(--font-serif);
  font-size: 1.05rem;
  font-weight: 500;
  letter-spacing: 0.02em;
  color: var(--ink);
  cursor: pointer;
}
.lux-date-input::-webkit-calendar-picker-indicator {
  position: absolute;
  right: var(--sp-4);
  top: 50%;
  transform: translateY(-50%);
  width: 20px;
  height: 20px;
  cursor: pointer;
  opacity: 0;
}
.lux-date-input::after {
  /* suffix chevron handled by wrapper; rely on native indicator */
}
/* For Firefox */
.lux-date-input[type="date"] {
  padding-right: var(--sp-4);
}
```

---

### 7.13 Stepper / Number Input（数字步进器）

> 金色 +/- 按钮 + 衬线数字，适合数量、年限、数量级选择。
> Gold increment buttons with serif numerals.

```html
<div class="lux-input-group">
  <label class="form-label">订购数量</label>
  <div class="lux-stepper">
    <button type="button" class="lux-stepper-btn" data-step="-1" aria-label="减少">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><line x1="5" y1="12" x2="19" y2="12"></line></svg>
    </button>
    <input type="number" class="lux-stepper-input" value="1" min="1" max="99" id="stepperInput">
    <button type="button" class="lux-stepper-btn" data-step="1" aria-label="增加">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
    </button>
  </div>
</div>
```
```css
.lux-stepper {
  display: inline-flex;
  align-items: center;
  border: 1.5px solid var(--cream-200);
  border-radius: var(--r-md);
  background: #fff;
  overflow: hidden;
  transition: all var(--t-fast);
}
.lux-stepper:focus-within {
  border-color: var(--royal);
  box-shadow: 0 0 0 3px var(--royal-50);
}
.lux-stepper-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 44px;
  background: var(--paper);
  border: none;
  color: var(--royal);
  cursor: pointer;
  transition: all var(--t-fast);
}
.lux-stepper-btn svg { width: 16px; height: 16px; }
.lux-stepper-btn:hover {
  background: var(--gold);
  color: var(--royal);
}
.lux-stepper-btn:active { background: var(--gold-600); }
.lux-stepper-btn:first-child { border-right: 1px solid var(--cream-200); }
.lux-stepper-btn:last-child { border-left: 1px solid var(--cream-200); }
.lux-stepper-input {
  width: 64px;
  border: none;
  outline: none;
  text-align: center;
  font-family: var(--font-serif);
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--ink);
  background: transparent;
  padding: var(--sp-2) 0;
  -moz-appearance: textfield;
}
.lux-stepper-input::-webkit-outer-spin-button,
.lux-stepper-input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
```
```javascript
document.querySelectorAll('.lux-stepper-btn').forEach(btn => {
  btn.addEventListener('click', () => {
    const input = document.getElementById('stepperInput');
    const step = parseInt(btn.dataset.step);
    const min = parseInt(input.min) || 0;
    const max = parseInt(input.max) || 999;
    const next = Math.max(min, Math.min(max, parseInt(input.value) + step));
    input.value = next;
  });
});
```

---

### 7.14 Floating Label Input（浮动标签输入框）

> 标签在聚焦/有值时优雅上浮并缩小为金色小字，如印刷品脚注。
> Label floats up and shrinks to gold on focus/filled, like a printed footnote.

```html
<div class="lux-float">
  <input type="text" class="lux-float-input" id="floatName" required>
  <label class="lux-float-label" for="floatName">您的尊姓大名</label>
  <span class="lux-float-line"></span>
</div>

<div class="lux-float">
  <input type="email" class="lux-float-input" id="floatEmail" required>
  <label class="lux-float-label" for="floatEmail">联系邮箱</label>
  <span class="lux-float-line"></span>
</div>
```
```css
.lux-float {
  position: relative;
  margin-bottom: var(--sp-6);
}
.lux-float-input {
  width: 100%;
  font-family: var(--font-sans);
  font-size: 1rem;
  padding: var(--sp-5) 0 var(--sp-2);
  border: none;
  border-bottom: 1.5px solid var(--cream-300);
  background: transparent;
  color: var(--ink);
  outline: none;
  transition: border-color var(--t-med);
}
.lux-float-line {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--royal);
  transition: width var(--t-med);
}
.lux-float-input:focus ~ .lux-float-line,
.lux-float-input:not(:placeholder-shown) ~ .lux-float-line {
  width: 100%;
}
.lux-float-label {
  position: absolute;
  left: 0;
  top: var(--sp-5);
  font-family: var(--font-serif);
  font-size: 1.125rem;
  font-style: italic;
  color: var(--ink-400);
  pointer-events: none;
  transition: all var(--t-med);
  transform-origin: left center;
}
.lux-float-input:focus ~ .lux-float-label,
.lux-float-input:not(:placeholder-shown) ~ .lux-float-label {
  top: 0;
  transform: translateY(0) scale(0.78);
  color: var(--gold-600);
  letter-spacing: 0.08em;
  text-transform: uppercase;
  font-style: normal;
  font-weight: 600;
}
/* Use a trick to make :placeholder-shown work on empty */
.lux-float-input::placeholder { color: transparent; }
```

---

### 7.15 Multi-column Form Layout（多列表单布局 · 完整示例）

> 以皇家蓝分隔线和金色花饰为章节装饰的完整联系表单，双列栅格自适应。
> A complete contact/edit form with royal-blue dividers and gold fleuron ornaments; responsive two-column grid.

```html
<form class="lux-form" onsubmit="event.preventDefault(); alert('感谢您的来函。');">
  <div class="lux-form-section">
    <span class="lux-form-fleuron">❦</span>
    <h3 class="lux-form-heading"><em>联系</em>我们</h3>
    <p class="lux-form-subtitle">所有字段均以加密方式保存，我们将在两个工作日内回复。</p>
  </div>

  <div class="lux-form-grid">
    <div class="lux-input-group">
      <label class="form-label">姓氏</label>
      <input type="text" class="form-input" placeholder="张">
    </div>
    <div class="lux-input-group">
      <label class="form-label">名字</label>
      <input type="text" class="form-input" placeholder="飞鸿">
    </div>
    <div class="lux-input-group">
      <label class="form-label">邮箱地址</label>
      <div class="lux-input-wrap">
        <span class="lux-input-icon lux-input-icon--prefix">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
            <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline>
          </svg>
        </span>
        <input type="email" class="lux-input lux-input--prefix" placeholder="name@example.com">
      </div>
    </div>
    <div class="lux-input-group">
      <label class="form-label">联系电话</label>
      <input type="tel" class="form-input" placeholder="+86 138 0000 0000">
    </div>
    <div class="lux-input-group lux-span-2">
      <label class="form-label">咨询类型</label>
      <select class="form-input form-select">
        <option>品牌全案设计</option>
        <option>视觉识别系统</option>
        <option>高端网站定制</option>
        <option>艺术指导与策展</option>
      </select>
    </div>
    <div class="lux-input-group lux-span-2">
      <label class="form-label">项目简述</label>
      <textarea class="form-input form-textarea" rows="5" placeholder="请告诉我们您的愿景、时间节点与预算范围…"></textarea>
      <div class="lux-char-count"><span>0</span> / 800</div>
    </div>
  </div>

  <div class="lux-form-divider"><span>❦</span></div>

  <div class="lux-form-options">
    <label class="lux-checkbox">
      <input type="checkbox" class="lux-checkbox-input" checked>
      <span class="lux-checkbox-box">
        <svg class="lux-checkbox-tick" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
      </span>
      <span class="lux-checkbox-label">我已阅读并同意<em>隐私政策</em></span>
    </label>
    <label class="lux-switch">
      <input type="checkbox" class="lux-switch-input" checked>
      <span class="lux-switch-track"><span class="lux-switch-thumb"></span></span>
      <span class="lux-switch-label">订阅<em>飞鸿季刊</em></span>
    </label>
  </div>

  <div class="lux-form-actions">
    <button type="button" class="lux-btn lux-btn--ghost">稍后再说</button>
    <button type="submit" class="lux-btn lux-btn--primary">
      <span>寄出函件</span>
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
    </button>
  </div>
</form>
```
```css
.lux-form {
  background: var(--paper);
  border: 1px solid var(--cream-200);
  border-radius: var(--r-xl);
  padding: var(--sp-10);
  box-shadow: var(--shadow-md);
}
.lux-form-section {
  text-align: center;
  margin-bottom: var(--sp-8);
}
.lux-form-fleuron {
  display: block;
  font-family: var(--font-serif);
  font-size: 1.75rem;
  color: var(--gold);
  line-height: 1;
  margin-bottom: var(--sp-3);
}
.lux-form-heading {
  font-family: var(--font-serif);
  font-size: 2rem;
  font-weight: 500;
  color: var(--royal);
  margin: 0 0 var(--sp-2);
  letter-spacing: 0.02em;
}
.lux-form-heading em {
  font-style: italic;
  font-weight: 600;
}
.lux-form-subtitle {
  font-family: var(--font-sans);
  font-size: 0.875rem;
  color: var(--ink-400);
  margin: 0;
}
.lux-form-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: var(--sp-5) var(--sp-6);
}
.lux-span-2 { grid-column: span 2; }
.lux-form-divider {
  display: flex;
  align-items: center;
  gap: var(--sp-4);
  margin: var(--sp-8) 0;
  color: var(--gold);
  font-size: 1.25rem;
}
.lux-form-divider::before,
.lux-form-divider::after {
  content: '';
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--cream-300), transparent);
}
.lux-form-options {
  display: flex;
  flex-direction: column;
  gap: var(--sp-3);
  margin-bottom: var(--sp-8);
}
.lux-form-actions {
  display: flex;
  justify-content: flex-end;
  gap: var(--sp-3);
}
.lux-char-count {
  text-align: right;
  font-family: var(--font-mono);
  font-size: 0.75rem;
  color: var(--ink-400);
  margin-top: var(--sp-2);
}
.lux-btn {
  display: inline-flex;
  align-items: center;
  gap: var(--sp-2);
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  font-weight: 500;
  padding: var(--sp-3) var(--sp-6);
  border-radius: var(--r-md);
  cursor: pointer;
  border: 1.5px solid transparent;
  transition: all var(--t-fast);
}
.lux-btn svg { width: 16px; height: 16px; }
.lux-btn--ghost {
  background: transparent;
  color: var(--ink-400);
  border-color: var(--cream-200);
}
.lux-btn--ghost:hover {
  color: var(--royal);
  border-color: var(--royal);
  background: var(--royal-50);
}
.lux-btn--primary {
  background: var(--royal);
  color: var(--gold);
  border-color: var(--royal);
  letter-spacing: 0.04em;
}
.lux-btn--primary:hover {
  background: var(--royal-700);
  box-shadow: var(--shadow-lg), var(--shadow-gold);
  transform: translateY(-1px);
}
@media (max-width: 640px) {
  .lux-form-grid { grid-template-columns: 1fr; }
  .lux-span-2 { grid-column: span 1; }
  .lux-form { padding: var(--sp-6); }
  .lux-form-actions { flex-direction: column-reverse; }
  .lux-btn { width: 100%; justify-content: center; }
}
```

---

### 7.16 Textarea Variants（文本域变体）

> 自动扩展文本域 + 字数统计，优雅适配长文创作与反馈场景。
> Auto-resize textarea with character counter for long-form input.

```html
<!-- Auto-resize with character count -->
<div class="lux-input-group">
  <label class="form-label">您的寄语</label>
  <textarea class="form-input form-textarea lux-textarea-auto" rows="3"
    maxlength="500" placeholder="在此书写您的留言……"
    oninput="this.style.height='auto'; this.style.height=this.scrollHeight+'px';
             this.nextElementSibling.querySelector('span').textContent=this.value.length;"></textarea>
  <div class="lux-char-count"><span>0</span> / 500</div>
</div>

<!-- Editorial / large variant 编辑级大号文本域 -->
<div class="lux-input-group">
  <label class="form-label lux-label-serif"><em>序</em> · Prologue</label>
  <textarea class="form-input form-textarea lux-textarea-editorial" rows="6"
    placeholder="用一段文字开启您的故事……"
    style="font-family: var(--font-serif); font-size: 1.125rem; line-height: 1.9;
           padding: var(--sp-5); background: var(--cream);
           border: 1px solid var(--cream-200); border-radius: var(--r-lg);"></textarea>
</div>
```
```css
.lux-textarea-auto {
  overflow: hidden;
  resize: none;
  line-height: 1.7;
}
.lux-char-count {
  text-align: right;
  font-family: var(--font-mono);
  font-size: 0.75rem;
  color: var(--ink-400);
  margin-top: var(--sp-2);
  transition: color var(--t-fast);
}
.lux-char-count.is-near { color: var(--warning); }
.lux-char-count.is-over { color: var(--wine); }
.lux-label-serif {
  font-family: var(--font-serif);
  font-size: 1rem;
  font-weight: 600;
  color: var(--royal);
  letter-spacing: 0.05em;
}
.lux-label-serif em {
  font-style: italic;
  font-size: 1.3em;
  color: var(--gold-600);
  margin-right: var(--sp-1);
}
.lux-textarea-editorial::placeholder {
  font-family: var(--font-serif);
  font-style: italic;
  color: var(--ink-200);
}
.lux-textarea-editorial:focus {
  border-color: var(--royal);
  box-shadow: 0 0 0 3px var(--royal-50);
  background: #fff;
}
```

---

### 7.17 Luxury Select Dropdown（奢华下拉选择器）

> 金色 V 形箭头 + 皇家蓝悬浮选项 + 衬线分组标题，超越原生样式。
> Gold chevron, royal-blue hover options, serif group headings — surpasses native styling.

```html
<div class="lux-select-group">
  <label class="form-label">服务级别</label>
  <div class="lux-select" id="luxSelect1">
    <button type="button" class="lux-select-trigger" aria-haspopup="listbox">
      <span class="lux-select-value"><em>请选择</em>服务级别</span>
      <svg class="lux-select-chevron" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <polyline points="6 9 12 15 18 9"></polyline>
      </svg>
    </button>
    <ul class="lux-select-menu" role="listbox">
      <li class="lux-select-optgroup"><span>❦ 定制服务</span></li>
      <li class="lux-select-option is-selected" role="option" data-value="essential">
        <span class="lux-option-title"><em>Essential</em> · 基础</span>
        <span class="lux-option-desc">适合初创品牌</span>
      </li>
      <li class="lux-select-option" role="option" data-value="signature">
        <span class="lux-option-title"><em>Signature</em> · 签名</span>
        <span class="lux-option-desc">完整视觉系统</span>
      </li>
      <li class="lux-select-option" role="option" data-value="atelier">
        <span class="lux-option-title"><em>Atelier</em> · 工坊</span>
        <span class="lux-option-desc">一对一艺术指导</span>
      </li>
      <li class="lux-select-optgroup"><span>❦ 订阅计划</span></li>
      <li class="lux-select-option" role="option" data-value="monthly">月度订阅</li>
      <li class="lux-select-option" role="option" data-value="annual">年度订阅（省 20%）</li>
    </ul>
  </div>
</div>
```
```css
.lux-select-group { margin-bottom: var(--sp-5); position: relative; }
.lux-select { position: relative; }
.lux-select-trigger {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  padding: var(--sp-3) var(--sp-4);
  background: #fff;
  border: 1.5px solid var(--cream-200);
  border-radius: var(--r-md);
  font-family: var(--font-sans);
  font-size: 1rem;
  color: var(--ink);
  cursor: pointer;
  transition: all var(--t-fast);
  text-align: left;
}
.lux-select-trigger:hover { border-color: var(--royal-500); }
.lux-select.is-open .lux-select-trigger,
.lux-select-trigger:focus {
  outline: none;
  border-color: var(--royal);
  box-shadow: 0 0 0 3px var(--royal-50);
}
.lux-select-value em {
  font-family: var(--font-serif);
  font-style: italic;
  font-weight: 600;
  color: var(--ink-400);
  margin-right: var(--sp-1);
}
.lux-select.is-selected .lux-select-value em {
  color: var(--royal);
}
.lux-select-chevron {
  width: 18px;
  height: 18px;
  color: var(--gold-600);
  transition: transform var(--t-med);
  flex-shrink: 0;
  margin-left: var(--sp-3);
}
.lux-select.is-open .lux-select-chevron { transform: rotate(180deg); }

.lux-select-menu {
  position: absolute;
  top: calc(100% + 6px);
  left: 0;
  right: 0;
  margin: 0;
  padding: var(--sp-2);
  background: #fff;
  border: 1px solid var(--cream-200);
  border-radius: var(--r-lg);
  box-shadow: var(--shadow-lg);
  list-style: none;
  z-index: 50;
  max-height: 320px;
  overflow-y: auto;
  opacity: 0;
  visibility: hidden;
  transform: translateY(-4px);
  transition: all var(--t-fast);
}
.lux-select.is-open .lux-select-menu {
  opacity: 1;
  visibility: visible;
  transform: translateY(0);
}
.lux-select-optgroup {
  padding: var(--sp-2) var(--sp-3) var(--sp-1);
  font-family: var(--font-serif);
  font-size: 0.8125rem;
  font-style: italic;
  color: var(--gold-600);
  letter-spacing: 0.08em;
  text-transform: uppercase;
  border-bottom: 1px solid var(--cream-200);
  margin: var(--sp-1) 0;
}
.lux-select-optgroup:first-child { margin-top: 0; }
.lux-select-optgroup span { font-family: var(--font-serif); }
.lux-select-option {
  padding: var(--sp-3) var(--sp-3);
  border-radius: var(--r-sm);
  cursor: pointer;
  transition: all var(--t-fast);
  display: flex;
  flex-direction: column;
  gap: 2px;
}
.lux-select-option:hover,
.lux-select-option.is-highlighted {
  background: var(--royal-50);
}
.lux-select-option.is-selected {
  background: var(--royal);
  color: #fff;
}
.lux-select-option.is-selected .lux-option-desc { color: rgba(255,255,255,0.7); }
.lux-option-title {
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  color: inherit;
}
.lux-option-title em {
  font-family: var(--font-serif);
  font-style: italic;
  font-weight: 600;
  font-size: 1.1em;
  margin-right: var(--sp-1);
}
.lux-option-desc {
  font-family: var(--font-sans);
  font-size: 0.75rem;
  color: var(--ink-400);
}
```
```javascript
// Minimal luxury select interaction
document.querySelectorAll('.lux-select').forEach(select => {
  const trigger = select.querySelector('.lux-select-trigger');
  const menu = select.querySelector('.lux-select-menu');
  const options = select.querySelectorAll('.lux-select-option');
  const valueEl = trigger.querySelector('.lux-select-value');

  trigger.addEventListener('click', (e) => {
    e.stopPropagation();
    document.querySelectorAll('.lux-select.is-open').forEach(s => {
      if (s !== select) s.classList.remove('is-open');
    });
    select.classList.toggle('is-open');
  });

  options.forEach(opt => {
    opt.addEventListener('click', () => {
      options.forEach(o => o.classList.remove('is-selected'));
      opt.classList.add('is-selected');
      const title = opt.querySelector('.lux-option-title');
      valueEl.innerHTML = title.innerHTML;
      select.classList.add('is-selected');
      select.classList.remove('is-open');
    });
  });
});
document.addEventListener('click', () => {
  document.querySelectorAll('.lux-select.is-open').forEach(s => s.classList.remove('is-open'));
});
```

---

## 8. Form Accessibility & Best Practices（可访问性与最佳实践）

> - 所有原生 `<input>` 保留，隐藏视觉样式但保留焦点与屏幕阅读器可达性。
> - 表单控件颜色对比度符合 WCAG AA（皇家蓝 #0A2463 on #fff = 14.9:1，金色 #F4D35E on #0A2463 = 9.1:1）。
> - 错误信息使用 `role="alert"` 与 `aria-invalid="true"` 绑定到对应字段。
> - 浮动标签必须始终关联 `<label for>` 与 `<input id>`，避免仅依赖 placeholder。
> - 开关、复选、单选组件均支持键盘操作（Space / Enter / Arrow keys）。
> - 提交按钮采用皇家蓝 + 金色字，避免纯金色按钮（金色在白底上对比度不足）。
