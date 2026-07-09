# Feihong Design System — Quality Seal Standards
# 飞鸿品牌设计系统 · 品质封印标准

> This checklist serves as the quality gate for all design deliverables. Every item includes a concrete verification method — no vague subjective judgment.
> 本清单是所有设计交付的质量门禁，每条都有具体验证方法，不是模糊的主观判断。
>
> **Usage / 使用方法：** Cross-reference every item before delivery. All P0 items must pass before the quality seal may be applied.
> 交付前逐条对照，P0必须全部通过方可盖章交付。

---

## 🔴 P0 — Seal Required · 必过（一条不过 = 不合格，必须改，不能盖章交付）

### Color System / 色彩系统

- [ ] **Color Precision / 色值精确**：Verify in HTML that the three brand colors are exactly `#0A2463`, `#F4D35E`, `#D8315B` — no near-miss generic colors (e.g. `#0066CC`, `#FFD700`, `#E74C3C`)
  - 验证方法：`Ctrl+F` 搜索 `#0A`、`#F4D`、`#D83` 确认色值正确
- [ ] **Perceivable Color Ratio / 色彩比例可感知**：Royal Blue is the dominant hue (~55% area), Gold is secondary (~30%), Claret is accent (~15%). No equal three-way split, no Gold/Claret overpowering the primary
  - 肉眼观察页面，皇家蓝是主导色调（约55%面积），金色是辅助（约30%），酒红是点缀（约15%）。不是三色平分，也不是金色/酒红抢占主色
- [ ] **No Large-Area Gold Backgrounds / 金色不做大面积背景**：`#F4D35E` and gold-scale shades are never used for full-screen or full-card backgrounds — only for emphasis, decorative rules, labels, small highlights
  - `#F4D35E` 和金色系色阶不用于整屏/整卡片背景，仅用于强调、装饰线、标签、小面积高亮
- [ ] **Body Text Contrast / 正文对比度足够**：Body text contrast ratio ≥ 4.5:1 (WCAG AA)
  - Royal Blue `#0A2463` on `#FDFBF6` → contrast > 12:1 ✓
  - Ink Black `#0D1225` on `#FDFBF6` → contrast > 15:1 ✓
  - ❌ `#F4D35E` gold must not be used for body text on light backgrounds
- [ ] **No Fourth Dominant Hue / 无第四主色**：Apart from brand triad + neutrals + semantic colors (success green), no competing hue appears at scale (e.g. large purple, cyan, orange areas)
  - 页面中除了品牌三色+中性色+语义色（成功绿），没有出现与品牌竞争的新色相（如紫色、青色、橙色大面积使用）
  - Exception: Terminal Green `#4ADE80` is used only in terminal/code contexts
- [ ] **No Pure Black or Pure White at Scale / 无纯黑纯白大面积**：Background is never `#FFFFFF` pure white; body text is never `#000000` pure black
  - 背景应使用 `#FDFBF6`（暖米白）或深色 `#0A0E1A`
  - 文字应使用 `#0D1225`（墨黑）

### Typography System / 字体系统

- [ ] **Serif + Sans-Serif Pairing / 衬线+无衬线混搭**：Headings (h1/h2/h3) use Playfair Display serif — not Inter/Roboto/Arial or any sans-serif
  - 验证方法：检查标题元素的 `font-family` 是否包含 `'Playfair Display'`
- [ ] **No Single-Font Monoculture / 非全站单一字体**：At least two weight/family contrasts appear on the page (serif headings + sans body, + italic pull-quote, or + monospace code)
  - 页面中至少出现两种字重/字体族的对比
- [ ] **Chinese Body Text ≥ 16px / 中文正文 ≥ 16px**：Chinese body copy is no smaller than 1rem (16px)
- [ ] **Letter-Spaced Uppercase / 全大写文字有字距**：Elements with `text-transform: uppercase` must have `letter-spacing: 0.08–0.15em`
- [ ] **All Required Fonts Loaded / 引入了所有必要字体**：Google Fonts link includes Playfair Display, Cormorant Garamond, Inter, JetBrains Mono, and Chinese Noto fonts

### Layout & Structure / 布局与结构

- [ ] **Single Hero Focus / 第一屏单一焦点**：The hero / cover area has one primary visual focal point — no competing elements vying for attention
- [ ] **Adjacent Sections Differ / 相邻section布局不同**：No two consecutive sections share the same layout pattern (e.g. two back-to-back centered-text sections, two back-to-back three-column card grids)
- [ ] **Mobile Integrity / 移动端无问题**：At ≤ 600px width, no text overlap, no overflow, no buttons extending beyond viewport, no images bleeding out
  - 验证方法：在脑中模拟或检查CSS media query
- [ ] **Three Breakpoints / 响应式三断点**：Adaptations exist for desktop (>960px), tablet (600–960px), and mobile (<600px)
- [ ] **clamp() Fluid Sizing / clamp()流体尺寸**：Key typography (hero title, section titles), section spacing, and card padding use `clamp()` — not hardcoded px values
- [ ] **Content Width Constraint / 内容宽度约束**：A `max-width` is in place (~1200px); content does not stretch edge-to-edge on ultra-wide screens

### Components & Styling / 组件与样式

- [ ] **Zero Default Browser Styles / 零HTML默认样式**：
  - ❌ No default `<blockquote>` left-border styling
  - ❌ No unstyled `<ul>`/`<ol>` (custom list-style required)
  - ❌ No default blue underlined `<a>` links
  - ❌ No default gray 3D buttons
  - ❌ No default-border `<input>`/`<table>`
  - 验证方法：肉眼检查所有列表、引用、链接、按钮、表格、表单
- [ ] **Branded Links / 链接品牌化**：Link color is Royal Blue `#0A2463` or another brand hue — never browser default blue; hover carries gold/branded treatment
- [ ] **Clear Button Hierarchy / 按钮层级清晰**：Primary (Royal Blue fill), CTA (Claret fill), Secondary (Gold / outline / ghost) have visually distinct hierarchy

### Anti-Pattern Check / 禁忌检查

- [ ] **No Glassmorphism / 无Glassmorphism**：No `backdrop-filter: blur()` + translucent background glass effects
- [ ] **No Gradient Text / 无渐变文字**：No `-webkit-background-clip: text` gradient text effects
- [ ] **No Bounce/Elastic Animation / 无Bounce/Elastic动画**：Animations use `ease-out` or `cubic-bezier(0.16,1,0.3,1)` — never elastic curves like `cubic-bezier(0.68,-0.55,0.27,1.55)`
- [ ] **No Infinite Loops / 无无限循环动画**：Apart from loading states and extremely subtle pulse effects, no infinitely looping animations
- [ ] **No AI Light Effects / 无AI光效**：No large blurred light blobs, glow effects, neon treatments
- [ ] **No Notion/Feishu-Style Blockquotes / 无Notion/飞书式引用**：Blockquotes are never a simple `border-left: 3px solid` — they employ gold quotation marks + serif italic or other branded treatment
- [ ] **No Rainbow Gradients / 无多色彩虹渐变**：Gradients are limited to same-hue depth shifts or subtle radial gradients — no blue→purple→pink multi-color gradients

### Anti-AI Detection · 反AI检测

- [ ] **No Generic AI Template / 拒绝AI模板结构**：The layout is not the archetypal "centered headline + three-column card grid + CTA button" AI template pattern
  - 不是典型的"居中标题+三列卡片网格+CTA按钮"AI模板结构
- [ ] **At Least One Human Judgment Call / 至少一个人工判断决策**：At least one deliberate design decision signals human curatorship — asymmetric layout, element overflow, intentional negative space, irregular rhythm, unexpected color application
  - 至少有一个"人工判断"的设计决策（非对称布局、元素溢出、刻意留白、不规则节奏、意外色彩运用）
- [ ] **Restrained Ornamentation / 装饰少而准**：Decorative elements (gold rules, large numerals, quotation marks, dots) do not appear on every section or at mechanical intervals — they are sparse and deliberate
  - 装饰元素不是每页都有、不是等距出现，少而准
- [ ] **Contrasting Whitespace / 留白有疏密对比**：Whitespace exhibits density/breath contrast — not mechanically uniform padding/margin throughout
  - 留白有疏密对比，不是机械等距padding/margin
- [ ] **Feihong Signature Component Present / 必含Signature组件**：At least one Feihong Signature Collection component appears in the page — wax seal, corner sticker, ornament, drop cap, N° numbering, or gold signature
  - 页面中至少使用1个Feihong Signature Collection组件（火漆印章/角贴/花饰/首字下沉/N°编号/金色签名）
- [ ] **CTA Surface Area ≤ 10% / CTA面积受控**：Total CTA button surface area does not exceed 10% of the page
  - CTA按钮总面积不超过页面的10%
- [ ] **Varied Image Treatment / 图片处理有变化**：Not all images share uniform border-radius or uniform shadow — treatment varies with intent
  - 不是所有图片都带统一圆角或统一阴影，有处理变化
- [ ] **Editorial Typography Rhythm / 文字排版有编辑感**：Typography carries an "editorial" quality — varied sizes and weights establish a deliberate hierarchical rhythm, not flat uniformity
  - 文字排版有"编辑感"，不同字号字重形成层级节奏
- [ ] **No AI Cliché Effects / 无AI俗套特效**：No gradient text, glassmorphism, AI light flares, or bounce/elastic animations anywhere
  - 没有使用渐变文字/玻璃拟态/AI光效/bounce弹性动画
- [ ] **Social Media Test / 社交平台直觉测试**：If a screenshot were posted to social media, the viewer's first reaction would not be "this was made by AI"
  - 截图发到社交媒体，不会被人第一反应是"AI做的"

### Motion Check · 动效检查

- [ ] **Easing Discipline / 缓动函数规范**：All animations use `cubic-bezier(0.16, 1, 0.3, 1)` or `ease-out` — no bounce, no elastic curves
  - 所有动画使用cubic-bezier(0.16, 1, 0.3, 1)或ease-out，没有bounce/elastic
- [ ] **Duration Discipline / 时长规范**：Micro-interactions 150–200ms; component entrances 400–600ms; no overlong animations
  - 动效时长：微交互150-200ms，组件入场400-600ms，没有过长动画
- [ ] **Concurrency Limit / 同屏动画上限**：No more than 3 animations run simultaneously on the same viewport
  - 同一屏同时进行的动画不超过3个
- [ ] **Reduced Motion Support / 支持降级**：`prefers-reduced-motion` is respected — animations degrade gracefully
  - 支持prefers-reduced-motion降级

### Technical Standards / 技术规范

- [ ] **HTML Opens Directly / HTML可直接打开**：File is saved as `.html`; all resources use CDN or relative paths; double-click opens correctly in browser
- [ ] **No Missing External Dependencies / 无外部依赖缺失**：Google Fonts loaded via CDN link; no local font files required
- [ ] **Semantic Markup / 语义化标签**：`<nav>`, `<header>`, `<main>`, `<section>`, `<article>`, `<footer>` and other semantic elements are used
- [ ] **Image alt Attributes / 图片有alt属性**：All `<img>` elements carry alt text
- [ ] **DOCTYPE Declaration / DOCTYPE声明**：File begins with `<!DOCTYPE html>`
- [ ] **UTF-8 Encoding / UTF-8编码**：`<meta charset="UTF-8">` is present
- [ ] **Viewport Meta / viewport meta**：`<meta name="viewport" content="width=device-width, initial-scale=1.0">` is present

---

## 🟡 P1 — Quality Expected · 应过（尽量满足，品质要求）

### Brand Recognition / 品牌识别

- [ ] **Royal Blue Leadership / 皇家蓝主导**：Royal Blue carries primary brand recognition (appears in navigation, main headings, primary buttons)
  - 皇家蓝承担主要品牌识别功能（导航、主标题、主按钮中均有出现）
- [ ] **Claret Breathing Room / 酒红有呼吸感**：Claret is not confined to a single button — it appears in appropriate contexts (labels, emphasis text, accent ornaments) to provide emotional tension
  - 酒红不只是出现在一个按钮上，在合适场景有出场机会（标签、强调文字、点缀装饰），提供情绪张力
- [ ] **Vintage Gold as Signature / 复古金是签名**：Gold decorative rules / gold dots / gold highlights function as memorable visual signatures, not meaningless ornament
  - 金色装饰线/金色圆点/金色高亮成为可记忆的视觉签名，不是无意义的装饰
- [ ] **Overall Temperament / 整体气质**：Limpid, artistic, professional, warm — never cold, garish, cheap, or childish
  - 清澈、艺术、专业、温暖，不是冰冷/花哨/廉价/幼稚
- [ ] **Visual Surprise / 视觉惊喜**：At least one section defies expectation (dark panel, IP character overflow, full-bleed pull-quote, extreme size contrast, asymmetric break)
  - 至少有一个section打破预期（深色面板、IP形象溢出、全屏引言、极端字号对比、非对称突破等）

### Typography & Rhythm / 排版与节奏

- [ ] **Extreme Size Contrast / 字号极端对比**：Strong hierarchy exists between oversized display type (clamp hero title or decorative numeral) and small caption text (0.72–0.8rem)
  - 存在超大展示文字（clamp hero标题或装饰数字）与小号说明文字（0.72-0.8rem）的强烈层级对比
- [ ] **Serif Italic Pull-Quote / 衬线斜体引言**：Cormorant Garamond italic appears at least once (pull-quote, golden sentence, subtitle) for humanistic warmth
  - Cormorant Garamond italic 至少出现一次（引言、金句、副标题），增加人文温度
- [ ] **Large Decorative Numerals/English / 大装饰数字/英文**：Low-opacity (0.06–0.12) decorative large numerals or English text serve as visual anchors without overpowering content
  - 有低透明度(opacity 0.06-0.12)的装饰性大数字或英文作为视觉锚点，且不喧宾夺主
- [ ] **Visual Signature Thread / 视觉签名贯穿**：The visual signature element chosen in Step 4c (gold rule / large numeral / italic quote / IP / dots / overflow / dark panel) echoes throughout the page, not just once
  - Step 4c选的视觉签名元素在全页中有呼应，不是只出现一次
- [ ] **Disciplined Alignment / 对齐有纪律**：Element alignment is intentional (left / centered / right) — never random placement
  - 元素对齐有意识（左对齐/居中对齐/右对齐），不是随机放置
- [ ] **Comfortable Line Height / 行高舒适**：Headings 1.05–1.25; body 1.6–1.75; reading comfort verified by eye
  - 标题行高1.05-1.25，正文行高1.6-1.75，肉眼阅读舒适

### Motion & Interaction / 动效与交互

- [ ] **Restrained Motion / 动效克制**：If scroll-reveal / entrance animations exist, duration is 300–600ms with elegant easing; reading flow is never impeded
  - 如有Scroll Reveal/入场动效，时长300-600ms，使用优雅缓动，不影响阅读
- [ ] **prefers-reduced-motion / 尊重动效偏好**：User motion preference settings are honored
  - 尊重用户动效偏好设置
- [ ] **Visible Focus States / 焦点状态可见**：Keyboard Tab navigation reveals visible focus styling (gold outline or Royal Blue outline)
  - 键盘Tab导航时有可见的focus样式（金色outline或皇家蓝outline）
- [ ] **Touch Targets ≥ 44px / 触摸目标≥44px**：Buttons, links, and other tappable elements are no smaller than 44×44px
  - 按钮、链接等可点击元素尺寸不小于44×44px

### Details / 细节

- [ ] **Blue-Tinged Shadows / 阴影有蓝调**：Shadows use `rgba(10,36,99,...)` tonality — not generic black `rgba(0,0,0,...)`
  - 阴影使用 `rgba(10,36,99,...)` 色调，不是通用黑色阴影 `rgba(0,0,0,...)`
- [ ] **Gradated Border Radius / 圆角分级**：Small radius for small elements (buttons 4px, tags 4px); large radius for large containers (cards 8–12px, hero cards 20px) — never global uniform radius
  - 小圆角用于小元素（按钮4px、标签4px），大圆角用于大容器（卡片8-12px、Hero卡片20px），不是全局统一圆角
- [ ] **Breathing Gold Rules / 金色装饰线有呼吸**：Gold rules beneath titles are not full-width — length is ~1/3 to 1/2 of the title width
  - 标题下方金色线不是全宽，长度约为标题1/3-1/2
- [ ] **Subtle Radial Gradient Depth / 径向渐变层次**：Cards / hero / dark panels employ subtle radial gradients for depth — never flat solid color
  - 卡片/Hero/深色面板使用了微妙径向渐变增加深度，不是纯平色
- [ ] **Branded Selection Style / 选中样式品牌化**：`::selection` uses gold background + Royal Blue text
  - `::selection` 使用金色背景+皇家蓝文字

---

## 🟢 P2 — Refinement Bonus · 加分项（锦上添花）

### Artistry / 艺术感

- [ ] **Flowing Line Motif / 流动线条母题**：Subtle curved / diagonal decorative lines serve as a recurring visual motif
  - 有细微的曲线/斜线装饰线条作为视觉母题贯穿
- [ ] **Image Overflow / 图片溢出容器**：Images / IP characters deliberately break card boundaries, creating editorial and artistic tension (without obscuring core text)
  - 图片/IP形象有意溢出卡片边界，制造画册感和艺术张力（不遮挡核心文字）
- [ ] **Dark Panel Rhythm / 深色面板节奏**：A deep blue / dark panel is inserted within a light page to break rhythm (dark does not dominate)
  - 在浅色页面中插入一个深蓝/深色面板打破节奏（深色不主导整体）
- [ ] **Natural IP Placement / IP形象自然出现**：Avatar or character.png appears in appropriate contexts (Hero, About, Footer) — never forced
  - 头像或character.png在合适场景出现（Hero、About、Footer），不是硬塞
- [ ] **Noise / Paper Texture / 噪点/纸质质感**：Extremely subtle noise texture (opacity < 3%) adds paper-like tactility
  - 极细微噪点纹理（opacity < 3%）增加纸质质感
- [ ] **Artistic Panels / 艺术面板**：Editorial / magazine-like special layout treatments exist (text over image, cross-column layout, bleed design)
  - 有类似画册/杂志的特殊排版处理（文字叠加图片、跨栏布局、出血设计）

### Engineering Quality / 工程质量

- [ ] **Reusable CSS Variables/Tokens / CSS变量/token可复用**：Colors, fonts, spacing, radius, shadows are defined in `:root` CSS variables for reuse and modification
  - 颜色、字体、间距、圆角、阴影都定义在 `:root` CSS变量中，易于复用和修改
- [ ] **Portable Brand Consistency / 品牌一致性可迁移**：The design language migrates to other contexts (tutorial → card → social) without losing recognition
  - 设计语言可以迁移到其他场景（教程→卡片→公众号）而不丢失识别
- [ ] **Semantic Class Naming / 组件class命名清晰**：Semantic class names are used — not purely inline styles
  - 有语义化的class名，不是纯inline样式
- [ ] **Print Styles / 打印样式**（resume / long-form scenarios）：`@media print` styles hide navigation and animations; layout is A4-friendly
  - 有 `@media print` 样式，打印时隐藏导航/动效，排版适合A4
- [ ] **Dark Mode Support / Dark Mode支持**（optional）：If dark mode exists, color mapping is correct and contrast is sufficient
  - 如有深色模式，颜色转换正确，对比度足够

### Scenario-Specific Bonuses / 场景专属加分

Different scenarios carry additional bonus items. See `scenes/*.md` for details.
不同场景有各自的加分项，见各 `scenes/*.md` 文件。

---

## 📋 Scenario-Specific Additional Checks / 场景专属额外检查

After completing the general P0/P1/P2 checks, perform additional verification based on scenario type:
完成通用P0/P1/P2后，根据场景类型额外检查：

### Tutorial / Introduction / 教程型/介绍型
- [ ] Clear directory / TOC navigation exists / 有清晰的目录/TOC导航
- [ ] Section hierarchy is clear (h1→h2→h3) / 章节层级清晰（h1→h2→h3）
- [ ] Code blocks have syntax highlighting (JetBrains Mono) / 代码块有语法高亮样式（JetBrains Mono字体）
- [ ] Long-form reading has comfortable line measure (60–75ch) / 长文有舒适的阅读行宽（60-75ch）

### Landing Page / 活动页/Landing
- [ ] CTA buttons appear in both first and last screens / CTA按钮在首屏和末屏均有出现
- [ ] Clear value proposition (one sentence) / 有明确的价值主张（一句话说清楚做什么）
- [ ] Social proof / trust-badge area exists (client logos, data, testimonials) / 有社会证明/信任背书区域（如客户logo、数据、推荐语）
- [ ] Form / conversion entry point is clear / 表单/转化入口清晰

### Portfolio / Personal Site / 作品集/个人主页
- [ ] Project showcase has visual impact / 作品展示有视觉冲击力
- [ ] Project cards have hover interaction / 项目卡片有悬停交互
- [ ] About section carries personal character (avatar / IP / golden sentence) / About区域有个人特色（头像/IP/金句）
- [ ] Contact information is clearly visible / 联系方式清晰可见

### Case Study / 案例研究/Case Study
- [ ] Clear narrative structure: Background → Challenge → Process → Result / 有明确的叙事结构：背景→挑战→过程→结果
- [ ] Process imagery / sketches / wireframes present — not just final renders / 有过程图/草图/wireframe，不只是最终效果图
- [ ] Data / results substantiate claims / 有数据/结果佐证
- [ ] Reflections / learnings included / 有反思/learnings

### Presentation Deck / 演示文稿/Deck
- [ ] 16:9 aspect ratio (1280×720 or 1920×1080) / 16:9比例适配（1280×720或1920×1080）
- [ ] Keyboard navigation (←→ / space) / 键盘翻页（←→/空格）
- [ ] Fullscreen mode adapted / 全屏模式适配
- [ ] No crowded slides (one core idea per slide) / 每页信息不拥挤（一页一核心观点）
- [ ] Page number / progress indicator / 页码/进度指示

### Console / Admin / 后台控制台/功能型
- [ ] Clear functional layout (sidebar / top nav / content area) / 有明确的功能布局（侧边栏/顶部导航/内容区）
- [ ] Interactive elements have state feedback (hover/active/disabled) / 交互元素有状态反馈（hover/active/disabled）
- [ ] Forms have validation styling / 表单有验证样式
- [ ] Data presentation is clear (charts / cards / lists) / 数据展示清晰（图表/卡片/列表）

### Social Card / Xiaohongshu / 图文卡片/小红书
- [ ] 3:4 portrait ratio (1080×1440) / 3:4竖版比例（1080×1440）
- [ ] Type size is large enough (≥14px on mobile; titles sufficiently large) / 字号足够大（手机阅读不小于14px，标题足够大）
- [ ] Each page employs different layout techniques / 每页有不同排版手法
- [ ] Cover page has strong appeal / 封面页有强吸引力
- [ ] html2canvas export functions correctly / html2canvas导出功能正常
- [ ] No dark backgrounds (white/light backgrounds perform best on Xiaohongshu) / 无深色背景（小红书卡片白底/浅底最佳）

### WeChat Article Layout / 公众号排版
- [ ] All styles inline (no external CSS, no classes) / 所有样式内联（无外部CSS、无class）
- [ ] No JavaScript / 无JavaScript
- [ ] Images use WeChat-compatible formats / 图片使用微信兼容格式
- [ ] Width adaptation (max-width: 100%) / 宽度适配（max-width: 100%）
- [ ] Paragraph and letter spacing is comfortable / 段间距、字间距舒适

### Resume / CV / 简历/CV
- [ ] A4 single page (210×297mm) / A4单页（210×297mm）
- [ ] Print styles optimized via `@media print` / 打印样式 `@media print` 优化
- [ ] No animations / video / interactive elements / 无动效/无视频/无交互元素
- [ ] High information density without crowding / 信息密度高但不拥挤
- [ ] Experience listed in reverse chronological order / 经历倒序排列
- [ ] Contact information is clear / 联系方式清晰

### Email / EDM / 邮件/EDM
- [ ] Table layout (not div-based) / Table布局（不是div布局）
- [ ] All styles inline / 所有样式内联
- [ ] No JavaScript / 无JavaScript
- [ ] No external CSS references / 无外部CSS引用
- [ ] Images use absolute-path URLs / 图片有绝对路径URL
- [ ] Outlook compatibility tested (no margin/padding on p/div; use table cellpadding/cellspacing) / Outlook兼容测试（无margin/padding on p/div，用table cellpadding/cellspacing）
- [ ] Plain-text version available as fallback / 有纯文本版本备选
- [ ] Unsubscribe link present (commercial email) / 退订链接（商业邮件）

---

## 🎯 The Final Three Questions · 终极三问（交付前最后问自己）

Before sealing the deliverable, ask yourself:
盖章之前，最后问自己三个问题：

1. **Recognition / 辨识度**：Strip away all color — looking only at silhouette and typography, can you recognize this as Feihong? Or does it read as a generic template?
   去掉所有颜色只看轮廓和排版，能认出是Feihong的吗？

2. **Presence / 气质**：If this design were a person, would you want to be friends with them? (Does it carry warmth, humanity, and presence — or feel mechanical?)
   如果这个设计是一个人，你愿意跟他/她交朋友吗？

3. **Imprint / 记忆点**：After looking away for 30 seconds and closing your eyes, which visual element can you still remember?
   看完30秒闭眼，能记住哪个视觉元素？

---

*v8.0 · Feihong Design System*
