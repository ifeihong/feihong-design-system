# Feihong Design System — Brand DNA
# 飞鸿品牌设计系统 · 品牌基因手册

> **本文件是整个设计系统的「宪法」** — This document is the **Constitution** of the entire design system.
> 所有模板、组件、场景规范均以此为基础。修改本文件意味着改变整个品牌的视觉语言，请谨慎操作。
> All templates, components, and scene specifications are built upon this foundation. Modify with extreme care.

---

## Table of Contents / 目录

1. [Brand Core Positioning / 品牌核心定位](#-brand-core-positioning--品牌核心定位)
2. [Avatar & Personal Identity / 头像与个人形象](#-avatar--personal-identity--头像与个人形象)
3. [Color System / 色彩系统](#-color-system--色彩系统)
4. [Typography System / 字体系统](#-typography-system--字体系统)
5. [Space & Scale System / 空间与尺度系统](#-space--scale-system--空间与尺度系统)
6. [Visual Language / 视觉语言](#-visual-language--视觉语言)
7. [Essence Keywords / 气质关键词](#-essence-keywords--气质关键词)
8. [Forbidden List / 禁忌清单](#-forbidden-list--禁忌清单)
9. [Quality Gate / 质量门槛](#-quality-gate--质量门槛)
10. [Responsive & Accessibility / 响应式与可访问性](#-responsive--accessibility--响应式与可访问性)
11. [Scene Color Guide / 场景色彩指南](#-scene-color-guide--场景色彩指南)

---

## Brand Core Positioning / 品牌核心定位

### Brand Archetype / 品牌原型

**The Sovereign / The Artist（君主/艺术家）**

| Archetype | Core Drive / 核心驱动力 | Fear / 恐惧 | Strategy / 策略 | Tone / 语气 |
|-----------|----------------------|-------------|----------------|-------------|
| **Sovereign 君主** | Authority, command, timeless excellence / 权威、掌控、恒久之卓越 | Chaos, being undermined, mediocrity / 混乱、失序、平庸 | Establish order through mastery; lead with quiet conviction / 以精湛技艺建立秩序，以沉稳笃定引领 | Commanding, composed, authoritative / 威严、从容、有分量 |
| **Artist 艺术家** | Refined taste, creative vision, emotional depth / 品味精湛、创意远见、情感深度 | Vulgarity, soulless output, generic results / 粗鄙、无灵魂的输出、千篇一律 | Infuse craft and aesthetic judgment into every detail / 将匠心与审美判断注入每一处细节 | Cultured, expressive, discerning / 有涵养、有表达力、有鉴赏力 |

### Brand Core Values / 品牌核心价值观

| Dimension / 维度 | Keywords / 关键词 | Design Expression / 设计体现 |
|-----------------|-------------------|------------------------------|
| **Professional 专业感** | Depth, Precision, Trustworthy / 深邃、精准、可信 | Royal Blue primary, generous whitespace, serif headings / 皇家蓝主色、大留白、衬线标题 |
| **Premium 品质感** | Classic, Refined, Timeless / 经典、精致、恒久 | Vintage Gold accents, subtle shadows, premium typography / 复古金点缀、细腻阴影、高级字体 |
| **Warmth 温度感** | Sincere, Cultured, Not cold / 真诚、有涵养、不冰冷 | Burgundy accents, warm neutrals, serif italics / 酒红点缀、暖色调中性色、衬线斜体 |
| **Artistic 艺术感** | Aesthetic, Tasteful, Not mechanical / 有审美、有品味、不机械 | Serif typography, ornamental details, restrained color / 衬线排版、装饰细节、色彩克制 |

### Brand Voice / 品牌声音

| IS / 是 | IS NOT / 不是 |
|---------|--------------|
| **Confident** / 自信笃定 | Flashy / 浮夸张扬 |
| **Refined** / 精致有品 | Cheap / 廉价讨好 |
| **Cultured** / 有涵养 | Cold-tech / 冰冷技术感 |
| **Warm but poised** / 温暖但沉稳 | Cute / 幼稚可爱 |
| **Articulate** / 言之有物 | Over-marketed / 过度营销 |
| | AI-generated look / 像AI生成 |

### Brand Name / 品牌名字

- **Primary Name / 主名称**: **Feihong**（全大写 / ALL CAPS）
- **Chinese Subtitle / 中文副标题**: 飞鸿
- **Tagline**: **"Timeless Vision, Crafted with Precision"**（远见卓识，精工细作）

---

## Avatar & Personal Identity / 头像与个人形象

### Avatar Usage Rules / 头像使用规则

- Place your avatar file at `assets/avatar.jpg`（recommended square, minimum 400×400px）。
  - Currently configured: 使用附件图1作为品牌头像
- Always prefer `assets/avatar.jpg` when an avatar is needed
- Avatar presentation styles:
  - Circular avatar（导航栏、作者信息区 / nav, author info）: `border-radius: 50%`，可加 2px 金色描边
  - Square/rounded avatar（卡片、Hero区 / cards, Hero section）: `border-radius: 8-12px`
  - Avatar size scales fluidly per scene using `clamp()`

### IP Character Usage Rules / IP形象使用规则

- If you have a complete IP character（全身/半身/三视图 / full body/half body/three views）, place at `assets/character.png`.
  - Currently configured: 使用附件图2作为IP形象
- IP character usage scenarios:
  - Hero section large display（可适当溢出容器，制造画册感 / may overflow container for editorial feel）
  - 404 pages, empty states
  - Guiding character in tutorial pages
  - Decorative element on share cards
- IP character is not required on every page; use as visual easter egg and brand identity reinforcement

---

## Color System / 色彩系统

### I. Brand Triad（Core, do not replace arbitrarily / 核心，不可随意替换）

Based on the **55-30-15** brand color ratio（黄金比例微调版本，更适合三色经典搭配）:

| Role / 角色 | Color Name / 色名 | HEX | RGB | HSL | CMYK | Ratio / 占比 | Core Usage / 核心用途 |
|------------|-------------------|-----|-----|-----|------|-------------|----------------------|
| **Primary 主色** | Royal Blue 皇家蓝 | `#0A2463` | `10, 36, 99` | `hsl(223, 82%, 21%)` | `90, 64, 0, 61` | **55%** | 导航栏、主标题、主按钮、重要卡片背景、品牌识别核心 / Nav, headings, primary buttons, key card backgrounds, core brand identity |
| **Secondary 辅助色** | Vintage Gold 复古金 | `#F4D35E` | `244, 211, 94` | `hsl(47, 87%, 66%)` | `0, 14, 61, 4` | **30%** | 强调标记、高亮、装饰线、次要按钮、徽章、图标点缀、签名细节 / Emphasis marks, highlights, decorative lines, secondary buttons, badges, icon accents, signature details |
| **Accent 点缀色** | Burgundy Wine 酒红 | `#D8315B` | `216, 49, 91` | `hsl(345, 67%, 52%)` | `0, 77, 58, 15` | **15%** | CTA按钮、关键提醒、重要标签、链接悬停、情绪强调、呼吸感 / CTAs, key alerts, important tags, link hover, emotional emphasis, breathing room |

> **Ratio Law / 比例铁律**: The primary establishes tone, the secondary creates rhythm, the accent creates focal points. Vintage Gold is for emphasis, not large-area backgrounds; Burgundy provides breathing room and emotional tension — it must not be drowned out by the primary.
> 主色建立基调，辅助色创造节奏，点缀色制造焦点。复古金用于重点强调而非大面积背景；酒红提供呼吸感和情绪张力，不能被主色淹没。

### II. Complete Color Scale System（9 levels / 9级色阶）

Each brand color has a 9-level scale from darkest to lightest for different scenarios:

#### Royal Blue 皇家蓝色阶
| Level / 级别 | HEX | Usage / 用途 |
|-------------|-----|-------------|
| 900 (darkest / 最深) | `#040F2A` | Dark mode backgrounds, dark cards / 深色模式背景、深色卡片 |
| 800 | `#061842` | Primary button hover state, dark navigation / 悬停态主按钮、深色导航 |
| 700 (primary / 主色) | `#0A2463` | **Brand Primary** — primary buttons, headings, brand identity / **品牌主色** — 主按钮、主标题、品牌识别 |
| 600 | `#0F3480` | Primary hover state, default link color / 主色悬停态、链接默认色 |
| 500 | `#1E4DAA` | Link color, icon color / 链接颜色、图标色 |
| 400 | `#3E6EC9` | Secondary links, secondary icon color / 次要链接、图标次要色 |
| 300 | `#7B9DDB` | Borders, dividers, disabled states / 边框、分隔线、禁用态 |
| 200 | `#B8C9EB` | Light background blocks, selected state backgrounds / 浅色背景块、选中态背景 |
| 100 (lightest / 最浅) | `#F0F4FA` | Ultra-light backgrounds, hover backgrounds, selected base color / 极浅背景、悬停背景、选中底色 |

#### Vintage Gold 复古金色阶
| Level / 级别 | HEX | Usage / 用途 |
|-------------|-----|-------------|
| 900 | `#6B5210` | Gold text on ultra-light backgrounds / 金色文字在极浅背景上 |
| 800 | `#8F7018` | Gold text on dark backgrounds / 深色背景上的金色文字 |
| 700 | `#B8951F` | Gold intensified on dark backgrounds / 金色在深色上的强化 |
| 600 | `#DDB835` | Gold hover state / 金色悬停态 |
| 500 (primary / 主色) | `#F4D35E` | **Brand Secondary** — highlights, decoration, badges, signatures / **品牌辅助色** — 高亮、装饰、徽章、签名 |
| 400 | `#F7E08E` | Gold light state / 金色浅色态 |
| 300 | `#FAECB8` | Gold background blocks / 金色背景块 |
| 200 | `#FBF2CC` | Highlight background（highlighter effect / 荧光笔效果：`linear-gradient(transparent 60%, #F4D35E 60%)`） |
| 100 | `#FEFAED` | Ultra-light gold background, soft emphasis base / 极浅金色背景、柔和强调底色 |

#### Burgundy Wine 酒红色阶
| Level / 级别 | HEX | Usage / 用途 |
|-------------|-----|-------------|
| 900 | `#5A1226` | Burgundy in dark mode / 深色模式上的酒红 |
| 800 | `#851A36` | Burgundy dark state / 酒红深色态 |
| 700 | `#B02448` | Burgundy hover state / 酒红悬停态 |
| 600 (primary / 主色) | `#D8315B` | **Brand Accent** — CTAs, alerts, key tags / **品牌点缀色** — CTA、提醒、关键标签 |
| 500 | `#E56081` | Burgundy light state / 酒红浅色态 |
| 400 | `#ED8BA2` | Burgundy light border / 酒红边框浅色 |
| 300 | `#F4B6C4` | Burgundy background blocks / 酒红背景块 |
| 200 | `#F8D7E0` | Tip background color / 提示背景色 |
| 100 | `#FDF0F4` | Ultra-light burgundy background, error alert base / 极浅酒红背景、错误提示底色 |

### III. Neutral Color System / 中性色系统（品牌调性底色）

> **Important Principle / 重要原则**: Warm-toned neutrals for a composed, premium feel. Never use cold grays.
> 暖色调中性色，营造沉稳高级感，绝不使用冷灰。

| Role / 角色 | HEX | RGB | Usage / 用途 |
|------------|-----|-----|-------------|
| Ink Black 墨黑 | `#0D1225` | `13, 18, 37` | Body text, headings — **never use pure black #000** / 正文主文字、标题 — **永远不用纯黑 #000** |
| Dark Gray 深灰 | `#1A1F35` | `26, 31, 53` | Secondary headings, dark card text / 次要标题、深色卡片文字 |
| Body Gray 正文灰 | `#3D4358` | `61, 67, 88` | Long-form body text（most comfortable for reading）/ 正文长文本（阅读最舒适） |
| Muted Gray 辅助灰 | `#6B7288` | `107, 114, 136` | Auxiliary text, captions, timestamps / 辅助文字、说明文字、时间戳 |
| Subtle Gray 弱灰 | `#9CA3B5` | `156, 163, 181` | Placeholder text, disabled text, secondary icon color / 占位文字、禁用文字、图标次要色 |
| Border 边框色 | `#D8DCE8` | `216, 220, 232` | Borders, dividers — **warm border, no cold grays** / 边框、分隔线 — **暖调边框，不用冷灰** |
| Divider 分割线 | `#E8EAF0` | `232, 234, 240` | Light dividers, in-card separators / 轻分割线、卡片内分隔 |
| Surface 表面色 | `#F7F8FA` | `247, 248, 250` | Card backgrounds, input backgrounds / 卡片背景、输入框背景 |
| Background 页面底色 | `#FDFBF6` | `253, 251, 246` | Page main background — **warm cream, no pure white #FFF** / 页面主背景 — **暖米色，不用纯白 #FFF** |
| White 纯白 | `#FFFFFF` | `255, 255, 255` | Only inside cards, scenarios requiring pure white contrast / 仅用于卡片内部、需要纯白对比的场景 |

### IV. Semantic Functional Colors / 语义功能色

| Function / 功能 | HEX | Usage / 用途 |
|----------------|-----|-------------|
| Success 成功 | `#2D9B5E` | Success alerts, completed states, positive feedback / 成功提示、完成状态、正向反馈 |
| Warning 警告 | `#E6A23C` | Warning alerts, states requiring attention / 警告提示、需要注意的状态 |
| Error 错误 | `#D8315B` | Error alerts, dangerous actions — reuses Burgundy, no new color introduced / 错误提示、危险操作 — 复用酒红色，不额外引入新色 |
| Info 信息 | `#0A2463` | Info alerts — reuses Royal Blue, no new color introduced / 信息提示 — 复用皇家蓝，不额外引入新色 |
| **Terminal Green 终端绿** | `#4ADE80` | **For terminal-style scenarios only**（code editors, terminal emulators, developer themes）; prohibited on regular pages / **仅终端风格场景使用**（代码编辑器、终端模拟器、开发者主题），普通页面禁止使用 |

### V. Gradient & Layering Principles / 渐变与层次原则

1. **Radial gradients create depth — avoid flat colors / 径向渐变制造层次，不用纯平色**
   - Cards, Hero areas, dark panels may use subtle radial gradients for depth
   - Gradient direction: `radial-gradient(circle at top right, color1, color2)`
   - Gradient opacity controlled between 5%-15%, visible but not obtrusive
   - Primarily same-hue gradients（Royal Blue depth gradients, Gold micro-gradients）; no rainbow multi-color gradients
   - 卡片、Hero区域、深色面板可使用微妙的径向渐变增加深度；同色系渐变为主，不做多色彩虹渐变

2. **Never use pure black `#000` or pure white `#FFF` as large-area backgrounds / 永远不使用纯黑或纯白作为大面积背景**
   - Background: `#FDFBF6`（warm cream / 暖米白）
   - Text: `#0D1225`（ink black / 墨黑）

3. **Contrast requirements（WCAG AA）/ 对比度要求**
   - Body text contrast ≥ 4.5:1
   - Large text（≥18pt bold or ≥24pt regular）contrast ≥ 3:1
   - Royal Blue `#0A2463` on white/cream: contrast > 12:1 ✓
   - Vintage Gold `#F4D35E` **must not be used for body text**（insufficient contrast）; only for decoration, large headings, and highlights

4. **Gold text rules / 金色文字规则**
   - Vintage Gold `#F4D35E` may only be used as text on **dark backgrounds**（Royal Blue 700+）
   - On light backgrounds, gold text must use Gold 700/800 dark scales（`#B8951F` or darker）

5. **Dark mode / 深色模式**
   - Dark mode base: `#0A0E1A`（not pure black / 不是纯黑）
   - Dark mode cards: `#121828`
   - Dark mode dividers: `#1E2740`
   - Subtle radial gradients may add depth in dark mode（e.g., blue glow at top-right, opacity 0.08）
   - 3:4 Xiaohongshu card scenarios **prohibited from dark mode**（full-screen HTML pages only）

---

## Typography System / 字体系统

### I. Font License Statement / 字体许可声明

> **All fonts are open-source, free for commercial use** under SIL Open Font License 1.1 or Apache 2.0. Freely usable for personal and commercial projects at no cost.
> **所有字体均为开源免费可商用字体**，采用 SIL Open Font License 1.1 或 Apache 2.0 协议，可自由用于个人和商业项目，无需付费。

### II. Font Family Strategy / 字体家族策略

**Core Principle: Classic serif + Modern sans-serif combination, creating tension between "traditional heritage + artistic quality + modern sensibility"**
**核心原则：经典衬线 + 现代无衬线 组合，建立「传统底蕴 + 艺术品质 + 现代感」的张力**

| Hierarchy / 层级 | Font Family / 字体家族 | License / 许可 | Weights / 字重 | Style Match / 风格匹配 | Usage / 用途 |
|-----------------|----------------------|---------------|---------------|----------------------|-------------|
| **Display 展示字体** | `Playfair Display` | SIL OFL 1.1 | 400, 700, 900, 400italic | High-contrast serif, classically elegant, editorial quality / 高对比度衬线，经典优雅，有编辑品质感 | Large headings, Hero text, brand logo, large decorative numerals / 大标题、Hero文字、品牌Logo、大数字装饰 |
| **Serif Italic 衬线斜体** | `Cormorant Garamond` | SIL OFL 1.1 | 400italic, 600italic | Classic Garamond serif, elegantly poetic, humanistic warmth / Garamond 经典衬线，优雅诗意，有人文温度 | Quotes, subtitles, decorative text, poetic passages, golden phrases / 引言、副标题、装饰性文字、诗意段落、金句 |
| **Body 正文字体** | `Inter` | SIL OFL 1.1 | 300, 400, 500, 600, 700 | Modern geometric sans-serif, extremely legible, optimal for screen reading / 现代几何无衬线，极度清晰，屏幕阅读最优 | Body text, UI text, buttons, forms, navigation, labels / 正文、UI文字、按钮、表单、导航、标签 |
| **Mono 等宽字体** | `JetBrains Mono` | SIL OFL 1.1 / Apache 2.0 | 400, 500, 700 | Developer-friendly monospace, technical texture / 开发者友好等宽字体，有技术质感 | Code, HEX values, tags, data, technical annotations, terminal scenarios / 代码、HEX色值、标签、数据、技术标注、终端场景 |

#### Chinese Font Stack / 中文字体栈（System font fallback, all free system fonts）
```css
/* Chinese headings (serif) — prefer system serif fonts / 中文标题（衬线） */
font-family: 'Noto Serif SC', 'Source Han Serif SC', 'Songti SC', 'STSong', 'SimSun', serif;
/* Chinese body (sans-serif) / 中文正文（无衬线） */
font-family: 'Noto Sans SC', 'Source Han Sans SC', 'PingFang SC', 'Microsoft YaHei', 'Hiragino Sans GB', sans-serif;
```

> **Chinese Font Note / 中文字体说明**: Noto Serif SC / Noto Sans SC are also SIL OFL open-source free fonts available on Google Fonts, loadable via Google Fonts CDN. System font fallbacks ensure good display when Google Fonts are not loaded.

### III. Font Import（Google Fonts CDN）/ 字体引入方式
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400;1,600&family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500;700&family=Noto+Serif+SC:wght@400;700;900&family=Noto+Sans+SC:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

### IV. Type Scale / 字号阶梯系统

Using the **1.250 Major Third** ratio, all implemented with `clamp()` for fluid sizing:

| Token | Font Size (clamp) | Line Height | Letter Spacing | Weight | Usage / 用途 |
|-------|-------------------|-------------|----------------|--------|-------------|
| `text-hero` | `clamp(2.8rem, 7vw, 5rem)` | 1.05 | -0.035em | 900 | Hero headings / Hero 大标题 |
| `text-h1` | `clamp(2rem, 4.5vw, 3.2rem)` | 1.15 | -0.025em | 700/900 | Page-level headings / 页面一级标题 |
| `text-h2` | `clamp(1.5rem, 3vw, 2.2rem)` | 1.25 | -0.02em | 700 | Section headings / Section 标题 |
| `text-h3` | `clamp(1.2rem, 2vw, 1.5rem)` | 1.35 | -0.01em | 600 | Card titles, subheadings / 卡片标题、子标题 |
| `text-h4` | `1.1rem` | 1.4 | 0 | 600 | Small headings, component titles / 小标题、组件标题 |
| `text-lead` | `clamp(1.05rem, 1.5vw, 1.2rem)` | 1.6 | 0 | 400 | Intro paragraphs, lead text / 引言段落、Lead 文字 |
| `text-body` | `1rem (16px)` | 1.7 | 0 | 400 | Body text（base size / 基准字号） |
| `text-body-sm` | `0.9rem` | 1.6 | 0 | 400 | Small body text, card content / 小号正文、卡片内容 |
| `text-caption` | `0.8rem` | 1.5 | 0.01em | 400/500 | Captions, image descriptions / 辅助说明、图片说明 |
| `text-label` | `0.72rem` | 1.4 | 0.05em | 500/600 | Tags, badges, button microtext, all-caps text / 标签、徽章、按钮小字、全大写文字 |
| `text-mono` | `0.85rem` | 1.5 | 0 | 400/500 | Code, HEX values, data / 代码、HEX值、数据 |
| `text-display-lg` | `clamp(3.5rem, 10vw, 8rem)` | 1 | -0.04em | 300/700 | Decorative large numerals/English（visual anchor, opacity 0.06-0.12）/ 装饰性大数字/大英文 |

### V. Typography Commandments / 字体使用铁律

1. **Serif for headings（Playfair Display）, sans-serif for body（Inter）/ 标题用衬线，正文用无衬线** — Must demonstrate serif+sans-serif mixing strategy; never use one default font across the entire site
2. **Cormorant Garamond italic for quotes and golden phrases / 斜体用于引言和金句** — Adds humanistic warmth and artistry, avoids mechanical feel
3. **Extreme size contrast / 字号对比要极端** — Large must be large enough; small must be truly small, creating strong hierarchical rhythm
4. **Chinese body text always starts at 16px / 中文正文永远16px起** — No smaller than 16px for readability
5. **Line height rules / 行高规则**: Headings 1.05-1.25, body 1.6-1.75, auxiliary text 1.4-1.5
6. **All-caps text / 全大写文字**: Must add `letter-spacing: 0.08-0.15em`, weight 500/600
7. **Never use Inter/Roboto/Arial for headings / 禁止使用 Inter/Roboto/Arial 作为标题字体** — Too generic, no character, looks like AI templates
8. **Never use a single font site-wide / 禁止全站只用一种字体** — Must have serif+sans-serif contrast rhythm
9. **No cute handwriting fonts / 禁止可爱手写体**（Comic Sans, 站酷快乐体 etc.）— Childish and unprofessional; use Cormorant italic when a handwritten feel is needed

---

## Space & Scale System / 空间与尺度系统

### I. Spacing System（8px base grid / 8px 基准网格）

All multiples of 4px/8px, using `clamp()` for fluid spacing:

| Token | Value / 数值 | Usage / 用途 |
|-------|-------------|-------------|
| `space-1` | `4px` | Micro spacing, icon-text gap / 极小间距、图标与文字间距 |
| `space-2` | `8px` | Inner element spacing, tag padding / 内部元素间距、标签内边距 |
| `space-3` | `12px` | Small spacing, button padding / 小间距、按钮内边距 |
| `space-4` | `16px` | Base spacing, card inner element spacing / 基础间距、卡片内元素间距 |
| `space-5` | `24px` | Element group spacing, card inner padding / 元素组间距、卡片内padding |
| `space-6` | `32px` | Block spacing / 区块间距 |
| `space-8` | `48px` | Inter-block spacing within sections / Section内区块间距 |
| `space-section` | `clamp(64px, 10vh, 120px)` | **Between sections / Section 之间** |
| `space-block` | `clamp(32px, 5vw, 64px)` | **Between content blocks / 内容块之间** |
| `space-card` | `clamp(24px, 3vw, 40px)` | **Card inner padding / 卡片内 padding** |
| `page-padding` | `clamp(20px, 4vw, 48px)` | **Page left/right padding / 页面左右padding** |

### II. Border Radius System / 圆角系统

| Token | Value / 数值 | Usage / 用途 |
|-------|-------------|-------------|
| `radius-sm` | `4px` | Small buttons, tags, inputs, badges / 小按钮、标签、输入框、徽章 |
| `radius-md` | `8px` | Cards, default buttons / 卡片、按钮默认 |
| `radius-lg` | `12px` | Large cards, containers / 大卡片、容器 |
| `radius-xl` | `20px` | Hero cards, large containers / Hero卡片、大型容器 |
| `radius-pill` | `999px` | Pill buttons, avatars, dot tags / 胶囊按钮、头像、圆点标签 |

> **Radius Principle / 圆角原则**: Smaller elements get smaller radius; larger containers get larger radius. No global large border radius（avoids iOS/cute style）.
> 越小的元素圆角越小，越大的容器圆角越大。不使用全局统一的大圆角（避免iOS风/可爱风）。

### III. Shadow System / 阴影系统

| Token | CSS Value | Usage / 用途 |
|-------|-----------|-------------|
| `shadow-sm` | `0 2px 8px rgba(10,36,99,0.06)` | Button hover, small cards / 按钮悬停、小卡片 |
| `shadow-md` | `0 8px 24px rgba(10,36,99,0.08)` | Default cards, dropdowns / 卡片默认、下拉菜单 |
| `shadow-lg` | `0 16px 48px rgba(10,36,99,0.12)` | Large cards, overlays, modals / 大卡片、浮层、模态框 |
| `shadow-gold` | `0 8px 24px rgba(244,211,94,0.2)` | Gold buttons, gold-highlighted elements / 金色按钮、金色高亮元素 |
| `shadow-wine` | `0 8px 24px rgba(216,49,91,0.15)` | Burgundy CTA buttons / 酒红CTA按钮 |

> **Shadow Principle / 阴影原则**: Shadow tones lean toward Royal Blue; no generic black shadows. Shadows should feel breathable, not heavy.
> 阴影色调偏皇家蓝，不使用通用的黑色阴影。阴影要有呼吸感，不厚重。

### IV. Layout Constraints / 布局约束

- Max content width: `max-width: 1200px`（special design pages may extend to 1400px / 特殊设计页可放宽到1400px）
- Content centering: `margin: 0 auto`
- All sizes prefer `clamp()` for fluid responsiveness, avoiding rigid breakpoints
- Key font sizes, spacing, and container dimensions must use `clamp()`

---

## Visual Language / 视觉语言

### I. Shape Language / 形状语言

| Shape / 形状 | Usage Scenarios / 使用场景 | Essence / 气质 |
|-------------|--------------------------|---------------|
| **Rectangle (right angle or small radius) / 矩形（直角或小圆角）** | Cards, buttons, containers — default shape / 卡片、按钮、容器 — 默认形状 | Professional, composed, orderly / 专业、稳重、规整 |
| **Circle / 圆形** | Avatars, dots, decorative elements, icon backgrounds / 头像、圆点、装饰元素、图标背景 | Soft, focused / 柔和、聚焦 |
| **Thin lines / 细线** | Dividers, decorative lines, underlines / 分隔线、装饰线、下划线 | Refined, elegant / 精致、优雅 |
| **Long horizontal lines (gold) / 水平长线（金色）** | Decorative lines below headings, divisions / 标题下方装饰线、分割 | Classic, ceremonial / 经典、仪式感 |
| **Flowing curves (P2 bonus) / 流动曲线** | Subtle decorative line motifs, artistic panel dividers / 细微的装饰线条母题、艺术面板分隔 | Artistic, editorial / 艺术感、画册感 |

**Do not use / 不使用**:
- Large rounded-rectangle pill-shaped cards（too cute/tech-feeling / 过于可爱/科技风）
- Wavy lines, jagged edges and other childish shapes / 波浪线、锯齿边等幼稚形状
- Irregular blob shapes as primary elements / 不规则blob形状作为主要元素
- Glassmorphism / 玻璃拟态

### II. Decorative Elements / 装饰元素

1. **Gold decorative lines / 金色装饰线**
   - 1.5px-2px gold horizontal line below headings, approximately 1/3-1/2 the heading width
   - Not full-width horizontal lines; must have breathing room
   - This is the brand's "signature detail" — must become a memorable visual identifier
   - 标题下方 1.5px-2px 的金色水平线，长度约为标题宽度的1/3-1/2；不要全宽横线；品牌「签名细节」

2. **Large numerals/English decoration / 大数字/大英文装饰**
   - Use `Playfair Display` at ultra-light opacity（0.06-0.12）oversized numerals/English as background visual anchors
   - Font size: `clamp(4rem, 12vw, 10rem)`
   - Color: Primary or ink
   - Must not compete with content; serves only as visual rhythm
   - 超浅透明度超大数字/英文作为背景视觉锚点，不能喧宾夺主

3. **Gold dots/color blocks / 金色圆点/色块**
   - Small gold dots as list markers, timeline nodes
   - Diameter 8-12px
   - 小面积金色圆点作为列表标记、时间线节点

4. **Serif quotation mark decoration / 衬线引号装饰**
   - Blockquotes use large gold serif quotation marks as decoration
   - Font size approximately 60-80px, opacity 0.2-0.3
   - 引用块使用大号金色衬线引号作为装饰

5. **Image overflow containers (P2 bonus) / 图片溢出容器**
   - Consciously let images/IP character overflow card boundaries, creating editorial feel and artistic tension
   - Must not obscure core text
   - Use `margin-top: -XXpx` or `transform: translateY(-XXpx)`
   - 有意识地让图片/IP形象溢出卡片边界，制造画册感和艺术张力，不能遮挡核心文字

6. **Dark panels (P2 bonus) / 深色面板**
   - A dark panel（deep Royal Blue）may be inserted in a light page to break rhythm
   - Dark must not become the dominant tone; only for rhythm adjustment
   - Gold and Burgundy perform best on dark panels
   - 浅色页面中加入深色面板打破节奏，深色不能成为主色调

### III. Texture & Tactility / 纹理与质感

- Default to solid colors; **no texture backgrounds / 不使用纹理背景**
- Extremely subtle noise texture allowed（opacity < 3%）for paper-like quality / 允许极细腻的噪点纹理增加纸质质感
- Gold elements may simulate faint metallic foil quality（inner shadow + subtle gradient）, but not exaggeratedly
- Use radial gradients for depth, not flat colors（see Color System Section V）
- Do not use: Multi-color gradient backgrounds, glassmorphism, neon glow effects, AI glow effects, gradient text（`background-clip: text`）
- 不使用：多色渐变背景、玻璃拟态、霓虹光效、AI光效、渐变文字

### IV. Image Style / 图片风格

- Photo style: High contrast, warm-toned, tactile, authentic, human / 高对比度、偏暖色调、有质感、真实感、有人味
- Do not use: AI-generated fake-smile business photos, over-filtered images, meaningless unsplash-style filler images / 不使用AI生成假笑商务图、过度滤镜图片、无意义配图
- Image border radius: Consistent with container radius; no special radius on images alone
- Image processing: May overlay very warm filter to unify tone
- IP character（character.png）may consciously overflow containers for artistic tension

### V. Icon Style / 图标风格

- Icon stroke: 1.5-2px line weight, linear style / 1.5-2px 线条粗细，线性风格
- Icon caps: Rounded endpoints（stroke-linecap: round）
- Icon color: Default `#6B7288`, active state Royal Blue `#0A2463`
- Do not use: Filled icons, colored icons, 3D icons, emoji as functional icons / 不使用填充风格图标、彩色图标、3D图标、emoji作为功能图标

### VI. Motion Principles / 动效原则

> For detailed motion specifications, see **MOTION.md**.
> 详细动效规范参见 **MOTION.md**。

- Scroll Reveal animations may be used, but must be **light, slow, restrained / 轻、慢、克制**
- Animation duration: 300-600ms, using `cubic-bezier(0.16, 1, 0.3, 1)` or `ease-out`
- No bounce/elastic animations — frivolous and unsteady / 禁止 bounce/elastic 弹性动画 — 轻浮不稳重
- No infinite loop animations — disrupts reading / 禁止无限循环动画 — 干扰阅读
- Respect `prefers-reduced-motion`
- Motion is seasoning, not the main course / 动效是调味料，不是主菜

---

## Essence Keywords / 气质关键词

Design output should evoke these feelings:
设计出来的东西应该让人感到：

### Core Essence — P0（Highest priority — must achieve / 最高优先级 — 必须达成）

- **Not AI-looking / 不像AI** — This is the highest-priority constraint. Screenshots shared on social must not draw comments like "another AI job." Must demonstrate human aesthetic judgment, detail control, and personal signature.
- **Artistic & Premium / 艺术且有品质** — Not childish or ostentatious luxury; a refined designer-grade sophistication.
- **Warm & Human / 有温度、有人味** — Not cold, not mechanical, not templated. Like a cultivated person conversing with you, not a system outputting.
- **Designer's Eye / 有设计师眼光** — Detail-conscious, spacing-precise, color-restrained, rhythmically typeset.
- **Content with Depth / 有内容有深度** — Not empty decoration; form serves content; visual hierarchy clearly expresses information architecture.
- **Personal Brand Identity / 个人品牌感** — Recognizable at a glance as "Feihong's," with a unique visual signature.
- 最高优先级：不像AI、艺术有品质、有温度有人味、有设计师眼光、有内容有深度、个人品牌感

### Core Essence — P1（Must achieve / 必须达成）

- **Composed & Grand / 沉稳大气** — Not impetuous, not showy, with substance
- **Timeless Classic / 经典恒久** — Does not chase trends; still looks good in 5 years
- **Refined Taste / 精致有品** — Detail-conscious, spacing-precise
- **Professional & Trustworthy / 专业可信** — Clearly reliable, with depth
- **Warm & Gentle / 温润有温度** — Not cold, not mechanical, cultivated

### Bonus Essence — P2（Strive for / 加分气质）

- **Scholarly / 有书卷气** — Cultural depth, like a beautifully bound book
- **Unhurried / 从容不迫** — Generous whitespace, not crowded, not rushed
- **Quiet Luxury / 低调奢华** — Quality speaks through details, not shouts
- **Luminous Clarity / 清澈通透** — Overall feeling of clarity, artistry, professionalism, warmth
- **Visual Surprise / 有视觉惊喜** — At least one section breaks template feel and creates a memorable moment

---

## Forbidden List / 禁忌清单

### I. Color Forbidden / 配色禁忌

| Forbidden / 禁止 | Reason / 原因 | Should / 应该 |
|-----------------|--------------|--------------|
| Pure black `#000` or pure white `#FFF` in large areas / 纯黑或纯白大面积使用 | Harsh, glaring, cheap feel / 生硬、刺眼、廉价感 | Use ink black `#0D1225`, warm cream `#FDFBF6` |
| Blue-purple gradients, cyan, neon, fluorescent（except terminal green）/ 蓝紫渐变、青色、霓虹色、荧光色 | Destroys composed brand tone, overly tech-heavy / 破坏品牌沉稳调性，科技感过重 | Maintain triad system; gradients limited to same-hue depth radial gradients |
| Cold gray tones（`#888`, `#999` etc.）/ 冷灰色调 | Cold, warmthless / 冰冷、无温度 | Use warm neutrals `#6B7288`, `#9CA3B5` |
| Multi-color rainbow gradient backgrounds / 多种颜色的彩虹渐变背景 | Garish, cheap, unprofessional, AI-like / 花哨、廉价、不专业、像AI | Solid backgrounds or extremely subtle same-hue radial gradients |
| Burgundy/Gold as large-area backgrounds / 酒红/金色作为大面积背景色 | Drowns out primary, disrupts tonal foundation / 喧宾夺主，破坏主色基调 | Burgundy/Gold only for accents and small-area emphasis |
| Vintage Gold `#F4D35E` as text on light backgrounds / 复古金在浅色背景上做文字 | Insufficient contrast, poor readability / 对比度不足，可读性差 | Use dark Gold scales `#B8951F` on light backgrounds |
| Introducing a 4th primary color competing with the brand / 引入与品牌竞争的第四种主色 | Color chaos, blurred brand identity / 色彩混乱，品牌识别模糊 | Semantic colors reuse brand colors（success green only for functional alerts） |

### II. Typography Forbidden / 字体禁忌

| Forbidden / 禁止 | Reason / 原因 | Should / 应该 |
|-----------------|--------------|--------------|
| Inter/Roboto/Arial as heading fonts / Inter/Roboto/Arial 作为标题字体 | Too generic, no character, AI-template feel / 太普通、无特色、像AI模板 | Use Playfair Display serif for headings |
| Cute handwriting fonts（Comic Sans, etc.）/ 可爱手写体 | Childish, unprofessional / 幼稚、不专业 | Use Cormorant Garamond italic for handwritten feel |
| Single font across entire site / 全站只用一种字体 | Monotonous, no hierarchy, AI-default feel / 单调、无层次、像AI默认输出 | Serif+sans-serif+mono multi-font combination |
| Body text smaller than 16px / 正文小于16px | Poor readability / 可读性差 | Chinese body text always ≥ 16px |
| Default letter-spacing for all / 字间距全为默认值 | All-caps text appears cramped / 全大写文字会显得拥挤 | All-caps: add 0.08-0.15em letter-spacing |
| Line height too tight (<1.5) or too loose (>2) / 行高过紧或过松 | Poor reading experience / 阅读体验差 | Body 1.6-1.75, headings 1.05-1.25 |
| Using unlicensed commercial fonts / 使用未授权商用字体 | Legal risk / 法律风险 | All fonts are SIL OFL / Apache 2.0 open-source free |

### III. Layout Forbidden / 布局禁忌

| Forbidden / 禁止 | Reason / 原因 | Should / 应该 |
|-----------------|--------------|--------------|
| All sections centered symmetric layout / 所有 Section 居中对称布局 | Monotonous, template-like, no design sense / 单调、像模板、无设计感 | Alternate symmetric and asymmetric layouts; each section has different format |
| Monotonous card grids（3-col/4-col card walls）/ 千篇一律的卡片网格 | Generic template feel, no distinctiveness / 通用模板感，无辨识度 | Mixed layouts: large cards + small cards, asymmetric grids |
| Cards nested in cards / Cards 嵌套 Cards | Visual chaos, unclear hierarchy / 视觉混乱、层次不清 | Maximum two levels of card nesting |
| Global uniform large border radius（16px+）/ 全局统一大圆角 | Too cute, iOS-feel, unsteady / 过于可爱、iOS风、不沉稳 | Graded radius by element size |
| Zero whitespace / content crammed together / 零留白/内容挤在一起 | Oppressive, not premium, AI-like / 压迫感、不高级、像AI | Generous whitespace; `clamp(64px, 10vh, 120px)` section spacing |
| Excessive decorative element stacking / 过多装饰元素堆砌 | Garish, distracting, meaningless / 花哨、喧宾夺主、无意义 | Decorative elements: few and precise, with functional or emotional value |
| Major sections reusing same format / 主要section复用同一种版式 | Monotonous, template feel / 单调、模板感 | Each section should have different information structure, rhythm, or visual center |

### IV. Component & Effect Forbidden / 组件与效果禁忌

| Forbidden / 禁止 | Reason / 原因 | Should / 应该 |
|-----------------|--------------|--------------|
| Glassmorphism / 玻璃拟态 | Dated, garish, unsteady / 过时、花哨、不稳重 | Solid or extremely faint opacity cards; use radial gradients for depth |
| Gradient text（background-clip: text）/ 渐变文字 | Cheap tech feel, not classic, AI-like / 廉价科技感、不经典、像AI | Solid color text; gold text only on dark backgrounds |
| Bounce/Elastic animations / Bounce/Elastic 弹性动画 | Frivolous, unsteady / 轻浮、不稳重 | Use ease-out/cubic-bezier easing, elegant and restrained |
| Infinite loop animations / 无限循环动画 | Disrupts reading, cheap / 干扰阅读、廉价 | Animations trigger only on interaction/scroll, single play |
| AI glow effects, bloom, blurred light orbs / AI 光效、发光效果、模糊光斑 | Classic AI-generation tell / 典型AI生成痕迹 | Use real shadows and subtle radial gradients |
| Left-border vertical-line blockquotes（Notion/Feishu style）/ 左边框竖线引用块 | Ubiquitous, no character / 千篇一律、无特色 | Large gold serif quotation marks + Cormorant italic quote style |
| Browser default styles（ul/ol/blockquote/table/button/input）/ 浏览器默认样式 | Ugly, no brand feel / 丑陋、无品牌感 | All components must be branded; never retain default styles |
| HTML default link style（blue underline）/ HTML 默认链接样式 | Breaks brand feel / 破坏品牌感 | Links use brand colors; hover uses gold underline or background block |

### V. Global Forbidden / 整体禁忌

- Looks like a generic AI template — highest-priority red line / 看起来像通用AI模板 — 最高优先级红线
- Overusing animations and motion effects — motion is seasoning, not the main course / 过度使用动画和动效
- Meaningless stock photos / AI-generated fake people images / 无意义的装饰图/Stock Photo/AI生成假人图
- Borders too thin（accent decorative borders uniformly 2-3px, no less than 1.5px）/ 边框过细
- Flat colors without depth — use radial gradients for subtle layering / 纯平色无层次

---

## Quality Gate / 质量门槛

> Before delivering any Feihong design, you **must** self-check against the following list. All P0 items must pass.
> 完成任何 Feihong 设计之前，**必须**使用以下清单自检。P0 必须全部通过才能交付。
> Detailed quality standards: see **QUALITY.md**.
> 详细质量标准参见 **QUALITY.md**。

### P0 — Must Pass（Fail any one = cannot deliver / 一条不过就不能交付）

- [ ] Three primary colors must be strictly `#0A2463`（Royal Blue）, `#F4D35E`（Vintage Gold）, `#D8315B`（Burgundy）
- [ ] Page clearly demonstrates 55/30/15 color logic（primary leads, gold assists, burgundy accents）
- [ ] Vintage Gold emphasis used for focal points, not large-area backgrounds
- [ ] Body text is readable with sufficient contrast（WCAG AA 4.5:1）
- [ ] First screen has one clear focal point; visual hierarchy is explicit
- [ ] Text does not overlap, overflow, or become illegible on mobile
- [ ] Design does not introduce a 4th primary color competing with the brand（terminal green only in terminal scenarios）
- [ ] No elements from this document's "Explicitly Forbidden" list appear
- [ ] No HTML default style traces remain; all headings, paragraphs, lists, buttons, inputs, and links must be branded
- [ ] Serif + sans-serif mixing strategy must be evident; cannot use one default font temperament site-wide
- [ ] Must be responsively adapted for desktop, tablet, and mobile
- [ ] Major sections must not reuse the same format; each section should have different information structure, rhythm, or visual center
- [ ] Key font sizes, spacing, or container dimensions prefer `clamp()` for fluid sizing, avoiding rigid breakpoints
- [ ] When screenshot is shared on social media, the first reaction must not be "another AI job"; must demonstrate human aesthetic, detail judgment, and personal brand identity

### P1 — Should Pass（Strive to satisfy / 尽量满足）

- [ ] Typography strategy follows "serif for display, sans-serif for reading and UI"
- [ ] Design overall feels luminous, artistic, professional, warm
- [ ] Royal Blue carries primary brand identity function
- [ ] Burgundy provides sufficient breathing room and emotional tension
- [ ] Vintage Gold becomes a memorable signature detail
- [ ] Layout alignment is disciplined, not random decoration
- [ ] At least one visual surprise section to break template feel and create a memorable moment
- [ ] Font size contrast can be more extreme: allow oversized display headings, decorative numerals or English to form strong hierarchy with small caption text
- [ ] Scroll Reveal animations may be used on scroll, but must be light, slow, restrained, not disrupting reading
- [ ] Large decorative numerals or English may be used as visual anchors but must not compete（opacity 0.06-0.12）

### P2 — Bonus Items（Icing on the cake / 锦上添花）

- [ ] Subtle flowing line motifs or artistic panel motifs appear
- [ ] Output includes reusable tokens or classes（CSS variables, utility classes）
- [ ] Design can be migrated to tutorial pages, event pages, apps, Xiaohongshu cards, or WeChat public account scenarios without losing brand identity
- [ ] Images/IP character may consciously overflow containers for editorial feel and artistic tension, but must not obscure core text
- [ ] A dark panel may be added to break page rhythm, but dark must not become the dominant tone
- [ ] Decorative elements remain restrained: few and precise, with functional or emotional value, no meaningless stacking
- [ ] Use radial gradients instead of flat colors to create subtle depth
- [ ] Avatar/IP character appear naturally in appropriate scenarios, reinforcing personal brand identity

### Self-Check Three Questions / 自检三问（Final pass before delivery / 交付前最后过一遍）

1. **Distinctiveness / 辨识度**: If a screenshot of this page were posted on social media, would it be instantly recognizable as "Feihong's"? Or does it look like any random template?
2. **Essence / 气质**: Does it look composed, premium, warm, and trustworthy? Or does it come across as cheap, frivolous, AI-generated?
3. **Details / 细节**: Are line-heights and letter-spacing comfortable? Is color contrast sufficient? Is there any element that makes you think "I've seen this a hundred times"?

---

## Responsive & Accessibility / 响应式与可访问性

### Breakpoint System / 断点系统
| Breakpoint / 断点 | Value / 数值 | Adjustments / 调整 |
|------------------|-------------|-------------------|
| Desktop | > 960px | Full layout / 完整布局 |
| Tablet | 600px - 960px | Two columns to one, slight font size reduction / 两栏变单栏，字号微缩 |
| Mobile | < 600px | Single column, reduced spacing, floating decorative elements hidden / 单栏布局，间距缩小，浮动装饰元素隐藏 |

### Responsive Principles / 响应式原则
- Mobile is **rearrangement**, not **shrinking** / 移动端是「重新排列」不是「缩小」
- Do not hide content on mobile — adapt, don't amputate / 移动端不隐藏内容 — adapt 不 amputate
- Respect `prefers-reduced-motion` for users with motion sickness
- Minimum touch target size: 44×44px / 触摸目标最小尺寸
- Mobile font size no smaller than 14px; body text maintains 16px

### Accessibility (A11y) / 可访问性
- All images have `alt` text
- Semantic HTML tags（`nav`, `main`, `section`, `article`, `footer`）
- Keyboard navigable（logical Tab order, visible focus styles）
- Color is not the sole means of conveying information（add icons/text to assist）
- Form controls have associated `label`s
- Visible focus state（gold outline or Royal Blue outline）

---

## Scene Color Guide / 场景色彩快速指南

| Scene / 场景 | Primary Usage / 主色使用 | Gold Usage / 金色使用 | Burgundy Usage / 酒红使用 | Background / 背景 | Template / 模板 |
|-------------|------------------------|----------------------|--------------------------|-----------------|----------------|
| **Personal Homepage/Landing / 个人主页** | Nav + headings + primary buttons / 导航+主标题+主按钮 | Logo + decorative lines + highlights + signature details / Logo+装饰线+高亮+签名细节 | CTA buttons + important tags / CTA按钮+重要标签 | Warm cream `#FDFBF6` / 暖米白 | `landing.html` |
| **Tutorial/Article Page / 教程/文章页** | Headings + links + nav / 标题+链接+导航 | Quote marks + keyword highlights + highlighter / 引用标记+关键词高亮+荧光笔 | Key tips + warnings / 重点提示+警告 | Warm cream / 暖米白 | `tutorial.html` |
| **Portfolio Cards / 作品集卡片** | Card titles + tags / 卡片标题+标签 | Decorative elements + year / 装饰元素+年份 | Featured mark / Featured标记 | White `#FFF` cards / 白色卡片 | `portfolio.html` |
| **Dark Showcase Page / 深色展示页** | Background + cards（deep blue radial gradient）/ 背景+卡片（深蓝径向渐变） | Headings + decoration + icons + signature / 标题+装饰+图标+签名 | CTA + emphasis text / CTA+强调文字 | Deep blue-black `#0A0E1A` / 深蓝黑 | `showcase.html` |
| **Xiaohongshu Cards / 小红书卡片** | Heading color block + border / 标题色块+边框 | Highlight tags + decoration / 高亮标签+装饰 | Key marks / 重点标记 | White/cream cards（no dark mode）/ 白色/米白卡片（禁深色） | `card.html` |
| **Terminal/Code Page / 终端/代码页** | Background + UI / 背景+UI | Keyword highlights / 关键词高亮 | Errors/Warnings / 错误/警告 | Dark background, terminal green `#4ADE80` available / 深色背景，可用终端绿 | `terminal.html` |

> Scene specifications: see **scenes/*.md** for detailed scene guides.
> 场景详细规范参见 **scenes/*.md**。

---

*This document is the foundation of the Feihong Design System. All templates, components, and scene specifications are built upon it. For skill implementation guidance, see **FEIHONG.md**.*
*本文件是 Feihong Design System 的基石。所有模板、组件、场景规范均在此基础上构建。技能实现指南参见 **FEIHONG.md**。*

*Version: **v7.0** · Last updated: 2026-07-09*
*版本：**v7.0** · 最后更新：2026-07-09*

*Font Licensing: All fonts are SIL Open Font License 1.1 / Apache 2.0 open-source, free for commercial use.*
*字体许可：所有字体均为 SIL Open Font License 1.1 / Apache 2.0 开源免费可商用*
