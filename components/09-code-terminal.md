# Feihong Design System — Code & Terminal
# N°09 · 代码/终端
> Code blocks, terminal windows, file tabs, line-numbered code, copy buttons, and multi-file tabs.
> 代码块、终端窗口、文件标签、行号代码、复制按钮和多文件标签栏。
> Part of Feihong Design System v8.0 · 所有组件遵循 DNA.md 色彩字体规范
---

## 10. Code Block（代码块）

```html
<pre class="code-block"><code>const design = "有温度的设计";
console.log(design);</code></pre>
```
```css
.code-block {
  background: var(--ink);
  color: #E2E8F0;
  font-family: var(--font-mono);
  font-size: 0.875rem;
  line-height: 1.7;
  padding: var(--sp-5);
  border-radius: var(--r-lg);
  overflow-x: auto;
  border-left: 3px solid var(--gold);
  margin: var(--sp-5) 0;
}
.code-block code { font-family: inherit; }
/* Inline code */
code.inline-code {
  font-family: var(--font-mono);
  font-size: 0.875em;
  background: var(--royal-50);
  color: var(--royal);
  padding: 0.15em 0.4em;
  border-radius: var(--r-sm);
}
```

---

## 48. Code / Terminal 代码/终端类

### 48.1 Terminal Window 终端窗口

macOS风格终端窗口，顶部红黄绿交通灯按钮，深色背景配绿色等宽字体文字，带闪烁光标，命令行/开发者文档风格。

```html
<div class="term-window">
  <div class="term-bar"><span class="term-dot r"></span><span class="term-dot y"></span><span class="term-dot g"></span><span class="term-title">zsh — Feihong</span></div>
  <div class="term-body">
    <div class="term-line"><span class="term-prompt">$</span> npm install @Feihong/ui</div>
    <div class="term-line term-out">✓ Installed 42 packages in 3.2s</div>
    <div class="term-line"><span class="term-prompt">$</span> <span class="term-cursor"></span></div>
  </div>
</div>
```
```css
.term-window { background:var(--ink); border-radius:var(--r-md); overflow:hidden; font-family:var(--font-mono); box-shadow:var(--shadow-xl); max-width:600px; }
.term-bar { background:var(--ink-100); padding:0.75rem 1rem; display:flex; align-items:center; gap:0.5rem; position:relative; }
.term-dot { width:12px; height:12px; border-radius:50%; }
.term-dot.r { background:#FF5F57; } .term-dot.y { background:#FEBC2E; } .term-dot.g { background:#28C840; }
.term-title { position:absolute; left:50%; transform:translateX(-50%); font-size:0.75rem; color:var(--ink-400); }
.term-body { padding:1.25rem; font-size:0.85rem; line-height:1.7; color:var(--cream); }
.term-line { white-space:pre-wrap; }
.term-prompt { color:var(--gold); margin-right:0.5rem; }
.term-out { color:var(--terminal); }
.term-cursor { display:inline-block; width:8px; height:1.1em; background:var(--cream); vertical-align:text-bottom; animation:termBlink 1s step-end infinite; }
@keyframes termBlink { 0%,100%{opacity:1;} 50%{opacity:0;} }
```

---

### 48.2 File Tab Label 文件名标签

文件名标签组件，左侧文件图标区域配金色底色，右侧显示文件名和语言标识，可关闭，VS Code风格的高奢变体。

```html
<div class="file-tab">
  <span class="ft-icon">JS</span>
  <span class="ft-name">config.js</span>
  <span class="ft-close">×</span>
</div>
```
```css
.file-tab { display:inline-flex; align-items:stretch; background:var(--cream); border:1px solid var(--cream-200); border-radius:var(--r-sm); overflow:hidden; font-family:var(--font-mono); font-size:0.8rem; transition:all var(--t-fast); }
.file-tab:hover { border-color:var(--gold); box-shadow:var(--shadow-sm); }
.ft-icon { background:var(--gold); color:var(--ink); padding:0.5rem 0.6rem; font-weight:700; font-size:0.65rem; display:flex; align-items:center; letter-spacing:0.05em; }
.ft-name { padding:0.5rem 0.75rem; color:var(--ink-200); border-right:1px solid var(--cream-200); }
.ft-close { padding:0.5rem 0.6rem; color:var(--ink-400); cursor:pointer; transition:all var(--t-fast); font-size:1rem; line-height:1; display:flex; align-items:center; }
.ft-close:hover { background:var(--wine); color:var(--cream); }
```

---

### 48.3 Line Number Code Block 行号代码块

带行号的代码块，左侧金色渐变行号列，代码区域深色背景，语法高亮用品牌色系（金色关键字、酒红字符串、皇家蓝函数）。

```html
<pre class="code-block"><code><span class="cl">1</span><span class="ck">import</span> { <span class="cf">Button</span> } <span class="ck">from</span> <span class="cs">'@Feihong/ui'</span>;
<span class="cl">2</span>
<span class="cl">3</span><span class="ck">const</span> <span class="cv">App</span> = () => (
<span class="cl">4</span>  &lt;<span class="ct">Button</span> <span class="cp">variant</span>=<span class="cs">"gold"</span>&gt;
<span class="cl">5</span>    Cliquez ici
<span class="cl">6</span>  &lt;/<span class="ct">Button</span>&gt;
<span class="cl">7</span>);</code></pre>
```
```css
.code-block { background:var(--ink); border-radius:var(--r-md); padding:1.25rem 0; font-family:var(--font-mono); font-size:0.82rem; line-height:1.8; overflow-x:auto; margin:0; }
.code-block code { display:block; color:var(--cream); }
.cl { display:inline-block; width:2.5rem; text-align:right; padding-right:1rem; margin-right:1rem; color:var(--ink-400); border-right:1px solid var(--ink-100); user-select:none; }
.ck { color:var(--wine-300); } .cs { color:var(--gold); } .cf { color:#82AAFF; } .cv { color:var(--gold-300); } .ct { color:#7FDBCA; } .cp { color:var(--wine-300); font-style:italic; }
```

---

### 48.4 Copy Code Button 复制按钮

代码块右上角的复制按钮，默认显示金色复制图标，点击后变为对勾和"Copié!"文字，带优雅的缩放反馈动画。

```html
<button class="copy-btn" onclick="this.classList.toggle('copied')">
  <span class="cb-default"><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="9" y="9" width="13" height="13" rx="2"/><path d="M5 15H4a2 2 0 01-2-2V4a2 2 0 012-2h9a2 2 0 012 2v1"/></svg> Copy</span>
  <span class="cb-copied">✓ Copié!</span>
</button>
```
```css
.copy-btn { position:absolute; top:0.75rem; right:0.75rem; background:rgba(253,251,246,0.1); border:1px solid rgba(244,211,94,0.3); color:var(--gold); padding:0.4rem 0.75rem; border-radius:var(--r-sm); font-family:var(--font-mono); font-size:0.7rem; cursor:pointer; display:flex; align-items:center; gap:0.4rem; transition:all var(--t-fast); overflow:hidden; }
.copy-btn:hover { background:rgba(244,211,94,0.15); border-color:var(--gold); }
.cb-default, .cb-copied { display:flex; align-items:center; gap:0.4rem; transition:all var(--t-base); }
.cb-copied { position:absolute; color:var(--terminal); opacity:0; transform:translateY(10px); }
.copy-btn.copied .cb-default { opacity:0; transform:translateY(-10px); }
.copy-btn.copied .cb-copied { opacity:1; transform:translateY(0); }
```

---

### 48.5 Multi-File Tabs 多文件标签

多文件标签栏，激活标签有金色底部边框和更亮背景，非激活标签半透明，底部有金色细线分隔，编辑器风格。

```html
<div class="multi-tabs">
  <div class="mt-tab mt-active"><span class="mt-ic" style="color:#E8D44D">JS</span>app.js</div>
  <div class="mt-tab"><span class="mt-ic" style="color:#38BDF8">TS</span>config.ts</div>
  <div class="mt-tab"><span class="mt-ic" style="color:#F4D35E">CSS</span>theme.css</div>
  <div class="mt-tab"><span class="mt-ic" style="color:#4ADE80">JSX</span>App.jsx</div>
</div>
```
```css
.multi-tabs { display:flex; background:var(--ink-100); border-bottom:1px solid var(--ink); font-family:var(--font-mono); font-size:0.78rem; overflow-x:auto; }
.mt-tab { display:flex; align-items:center; gap:0.5rem; padding:0.7rem 1rem; color:var(--ink-400); cursor:pointer; border-bottom:2px solid transparent; transition:all var(--t-fast); white-space:nowrap; position:relative; }
.mt-tab:hover { color:var(--cream); background:rgba(253,251,246,0.05); }
.mt-tab.mt-active { color:var(--cream); background:var(--ink); border-bottom-color:var(--gold); }
.mt-ic { font-size:0.6rem; font-weight:700; padding:0.15rem 0.3rem; border-radius:2px; background:rgba(255,255,255,0.08); }
```
