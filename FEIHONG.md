---
name: feihong-design-system
description: FEIHONG Design System — Premium personal brand design system for AI-assisted creation. For HTML pages, portfolios, landing pages, case studies, tutorials, decks, apps, cards, resumes, emails and any frontend design task. Signature palette: Royal Blue #0A2463 + Vintage Gold #F4D35E + Burgundy Wine #D8315B. Core principle: Anti-AI > Artistic Quality > Human Warmth > Designer's Eye.
---

# FEIHONG Design System
## Premium Brand Design System · 工作流手册

> This document is the operating system of FEIHONG Design System. It defines the complete process from requirement to delivery.
> 本文件是设计系统的「大脑」，规定了从需求到交付的完整工作流程。
>
> **Mission**: Produce work that is artistically refined, recognizably FEIHONG, and unmistakably human — never looking AI-generated.
> **核心目标**：产出不像AI的、有FEIHONG品牌辨识度的、艺术且有品质的设计作品。

---

## Scene Maturity · 场景成熟度分级

### ⭐ Stable Scenes (v2.0) — Production Ready · 核心场景

| Scene · 场景 | Specification · 规范 | Template · 模板 | Maturity | Recommendation |
|------|------|------|--------|--------|
| Portfolio / Personal Site · 作品集 | `scenes/portfolio.md` | `assets/portfolio.html` | ✅ Stable | 🌟🌟🌟🌟🌟 |
| Landing Page · 活动页 | `scenes/landing.md` | `assets/landing.html` | ✅ Stable | 🌟🌟🌟🌟🌟 |
| Tutorial / Long-form · 教程 | `scenes/tutorial.md` | `assets/tutorial.html` | ✅ Stable | 🌟🌟🌟🌟🌟 |
| Presentation Deck · 演示文稿 | `scenes/deck.md` | `assets/deck.html` | ✅ Stable | 🌟🌟🌟🌟🌟 |

### 🧪 Beta Scenes — Iterating · Beta场景

| Scene · 场景 | Specification · 规范 | Template · 模板 | Status | Notes |
|------|------|------|------|----------|
| Case Study · 案例研究 | `scenes/case-study.md` | `assets/case-study.html` | 🧪 Beta | Narrative complete, details refining |
| App / Dashboard · 功能页 | `scenes/app.md` | `assets/app.html` | 🧪 Beta | Terminal green + luxe components |
| Social Cards · 图文卡片 | `scenes/cards.md` | `assets/cards.html` | 🧪 Beta | Export ready, variants expanding |
| Resume / CV · 简历 | `scenes/resume.md` | `assets/resume.html` | 🧪 Beta | A4 print ready |
| WeChat Article · 公众号 | `scenes/wechat.md` | Inline HTML | 🧪 Beta | WeChat compatible |
| Email / EDM · 邮件 | `scenes/email.md` | `assets/email.html` | 🧪 Beta | Outlook compatible |

> **Usage Guide**: Recommend Stable scenes first. Beta scenes are usable; inform users they are under continuous refinement.
> **使用建议**：优先推荐核心场景，Beta场景可使用但告知用户是持续迭代版本。

---

## Activation · 触发条件

The system activates automatically when the request matches these scenarios:

| Trigger Keywords · 触发关键词 | Scene Type · 场景 | Maturity |
|----------------|-------------|--------|
| 个人主页、个人网站、Portfolio | Portfolio | ⭐ Stable |
| 作品集、作品展示、项目展示 | Portfolio | ⭐ Stable |
| 教程、教学、科普、博客、文章页 | Tutorial | ⭐ Stable |
| Landing Page、落地页、活动页、报名页 | Landing | ⭐ Stable |
| 演示文稿、slides、幻灯片、deck、演讲 | Deck | ⭐ Stable |
| 案例研究、Case Study、项目复盘 | Case Study | 🧪 Beta |
| App、功能页、看板、仪表盘 | App | 🧪 Beta |
| 简历、CV、履历 | Resume | 🧪 Beta |
| 邮件模板、EDM、Newsletter | Email | 🧪 Beta |
| 图文卡片、小红书图文、社交卡片 | Cards | 🧪 Beta |
| 公众号排版、微信图文 | WeChat | 🧪 Beta |

> **Adaptive Judgment**: For simple modifications (e.g., "change a button color", "add a section"), use **Fast Track**. For new pages / complete designs, use the **Full 8-Step Process**.
> **自适应判断**：需求简单时走快速路径；新建页面/完整设计走完整8步工作流。

---

## ⚡ Fast Track · 快速路径（Simple Modifications）

For:
- Minor changes to existing pages
- Single component adjustments, text replacements, color tweaks
- Post-feedback local modifications
- Single section additions

Process:
1. Read the existing HTML file
2. Apply changes following `DNA.md` standards
3. Quick verify against P0 items relevant to the change
4. If changes affect color/typography/layout → check related P0 items
5. Deliver

**Not for Fast Track**: New complete pages, changes spanning 3+ sections, color palette adjustments, overall style changes.

---

## 📋 FEIHONG 8-Step Process · 完整8步工作流

---

### Step 01 — Discover · 洞察需求（Adaptive Triage）

Before starting, quickly assess what is already known from the user input:

- [ ] **Type** clear? (Which scene? Stable or Beta?)
- [ ] **Audience** clear? (Who is it for?)
- [ ] **Scale** known? (How many screens/pages/cards/slides?)
- [ ] **Assets** available? (Copy/images/data/avatar/IP character)
- [ ] **Constraints** clear? (Must-haves, brand partners, forbidden elements)

**Decision Rules**:
- **4+ items clear** → Skip to Step 03
- **2-3 items clear** → Ask only the missing critical questions
- **0-1 items clear** → Enter Step 02 for full clarification

---

### Step 02 — Define · 定调定向（Clarify When Needed）

Do not mechanically ask all 5 questions. Based on Step 01, **ask only the missing critical questions**.

Core questions to confirm (select only what's missing):

1. **Type** (when uncertain): Offer 2-3 most likely options, not open-ended
2. **Audience** (when not mentioned): "Who is the primary audience?"
3. **Scale** (when not stated): "Approximately how many screens/pages/cards?"
4. **Assets** (when no copy provided): "Do you have prepared copy, images or data?"
5. **Constraints** (when special needs): "Any mandatory elements or partner brand colors?"

> **Communication Principle**: Talk like a designer with a client, not like filling a form. Use natural language, max 2-3 questions at a time.
> **沟通原则**：像设计师跟客户沟通，不像填表。用自然语言，一次最多问2-3个问题。

---

### Step 03 — Inject DNA · 品牌注入（Read Specifications）

**Mandatory Reading** (every project):
- `DNA.md` — Memorize these essentials:
  - 🔴 Exact color values: `#0A2463` (Royal Blue 55%), `#F4D35E` (Vintage Gold 30%), `#D8315B` (Burgundy Wine 15%)
  - 🔴 Typography strategy: Playfair Display (serif headings) + Inter (sans body) + Cormorant Garamond (italic quotes) + JetBrains Mono (code)
  - 🔴 Priority order: Anti-AI > Artistic Quality > Human Warmth > Designer's Eye
  - 🔴 Warm cream background `#FDFBF6`, ink black text `#0D1225`
  - 🔴 Key forbidden items
  - 🔴 Motion language from `MOTION.md` (easing, duration, principles)

**Selective Reading** (by scene type):

**⭐ Stable Scenes (read corresponding spec):**

| Scene | Specification | Template |
|----------|-------------|---------|
| Tutorial / Long-form | `scenes/tutorial.md` | `assets/tutorial.html` |
| Landing Page | `scenes/landing.md` | `assets/landing.html` |
| Portfolio | `scenes/portfolio.md` | `assets/portfolio.html` |
| Deck / Presentation | `scenes/deck.md` | `assets/deck.html` |

**🧪 Beta Scenes (optional reading):**

| Scene | Specification | Template |
|----------|-------------|---------|
| Case Study | `scenes/case-study.md` | `assets/case-study.html` |
| App / Dashboard | `scenes/app.md` | `assets/app.html` |
| Social Cards | `scenes/cards.md` | `assets/cards.html` |
| WeChat Article | `scenes/wechat.md` | Inline HTML |
| Resume / CV | `scenes/resume.md` | `assets/resume.html` |
| Email / EDM | `scenes/email.md` | `assets/email.html` |

**After Reading, you must be clear on 5 things:**
1. What is the typical structure / rhythm of this scene?
2. Are there technical constraints? (email tables, WeChat inline styles, Deck fullscreen)
3. What role do the three brand colors play in this scene?
4. What is the core emotional tone? (Solemn? Dynamic? Professional? Artistic?)
5. Any scene-specific taboos?

---

### Step 04 — Structure · 架构搭建（Choose Starting Point）

**Default strategy: Start from templates, never from zero.**
**默认策略：从模板开始改，不从零写。**

**⭐ Stable Scenes:**

| Scene | Template | Special Notes |
|----------|---------|---------|
| Tutorial | `assets/tutorial.html` | Long-form reading, TOC nav, progress bar |
| Landing | `assets/landing.html` | CTA-driven, visual impact, form interaction |
| Portfolio | `assets/portfolio.html` | Project grid, visual-first, dark Hero option |
| Deck | `assets/deck.html` | Fullscreen slides, keyboard nav, 16:9, F for fullscreen |

**🧪 Beta Scenes:**

| Scene | Template | Special Notes |
|----------|---------|---------|
| Case Study | `assets/case-study.html` | Context→Challenge→Process→Result structure |
| App | `assets/app.html` | Functional UI, components, Terminal Green available |
| Social Cards | `assets/cards.html` | 3:4 portrait pagination, html2canvas export |
| WeChat | Inline HTML | WeChat compatible, no external CSS/JS |
| Resume | `assets/resume.html` | A4 single page, print-friendly, no animations |
| Email | `assets/email.html` | Table layout, inline styles, Outlook compatible |

**When to deviate from templates:**
- Template structure truly doesn't fit (but CSS variables, font imports, base reset must remain)
- User explicitly requests a unique design approach
- **Brand tokens (`:root` CSS variables), font imports, base reset styles must always be preserved**

**Template modification principles:**
- Preserve template `:root` CSS variables
- Preserve font `<link>` tags
- Replace content areas, adjust layout structure
- Do not remove base style resets

---

### Step 05 — Compose · 组件编排（Direction Setting & Layout）

**This is the most critical step against AI generic output — AI assembles without direction. This step decides whether the output is "design" or "assembly."**
**这是最容易被跳过但最重要的步骤——AI没有"方向判断"，它直接组装。这一步决定了产出是"设计"还是"组装"。**

Before filling components, define 4 direction decisions:

#### 5a. Emotional Tone (choose 1-2 primary)
- **Sovereign Authority · 沉稳权威**: Generous whitespace, Royal Blue dominant, gold used sparingly, serif headlines, minimal animation
- **Dynamic Creative · 活力创意**: Gold and burgundy more active, asymmetric layouts, elements breaking containers, slightly more animation
- **Art Editorial · 艺术画册**: Large images, text as visual element, images overflowing containers, generous whitespace, dark panels
- **Warm Humanist · 温暖人文**: More Cormorant italic, slightly higher burgundy ratio, warm tones, IP character appears
- **Refined Minimal · 专业极简**: Restrained color, generous whitespace, higher Inter ratio, geometric precision

#### 5b. Hero Strategy (choose 1)
- **Visual-led**: Large image / IP / abstract visual as primary, minimal text
- **Typography-led**: Large headline + pull quote primary, visual elements secondary
- **Portrait-led**: Avatar / IP character as centerpiece, text beside
- **Data/Achievement-led**: Large numbers + labels primary, establishing trust

#### 5c. Signature Elements (choose 1-2 to carry through the page)
- Gold decorative line (beneath headlines)
- Large decorative numerals / English (low opacity background)
- Serif italic pull quotes
- IP character / avatar interspersed
- Gold dots for list / timeline markers
- Images overflowing containers
- Deep blue panels breaking rhythm
- FEIHONG Signature Collection elements (wax seal, photo corners, fleuron ❦, drop cap, large quotes)

#### 5d. Rhythm Planning
- Total screens/pages: ___
- Density rhythm: Dense→Sparse→Dense→Sparse? Or Strong→Weak→Strong?
- Where is the visual surprise screen placed?
- Dark panels? Where?

> **Direction Output**: You don't need to write this down, but it must be crystal clear in your mind. Subsequent layout and component choices serve this direction.

Then select layout patterns from `components/14-layouts.md` for each section/page.

**Core principle: Every section must use a different layout. Layout choices serve the direction set in 5a-5d.**

---

### Step 06 — Signature · 签名点睛（Component Filling）

Select appropriate components from the `components/` files.

**🔴 Hard Rule (P0 level): Zero default HTML styles.**
**🔴 硬规则（P0级别）：禁止使用任何HTML默认样式。**

Specific zero-default-style requirements:
- ❌ Default `<blockquote>` (left-border is Notion/Feishu generic)
- ❌ Default `border-left` quote blocks
- ❌ Unstyled `<ul>`/`<ol>` (must customize — gold dots, serif numerals, custom icons)
- ❌ Default `<table>` borders
- ❌ Default blue underlined links
- ❌ Default button styles (gray, 3D effects, default borders)
- ❌ Default input styles
- ❌ Default form control styles
- ✅ All components selected from component library
- ✅ Components not in library: design consistent with DNA.md, never browser default

**Brand injection checkpoints:**
- **Links**: Royal Blue `#0A2463`, hover with gold underline / background tint
- **Buttons**: Primary Royal Blue, CTA Burgundy, Secondary Gold outlined/filled
- **Quote blocks**: Large gold serif quotes + Cormorant italic + gold decorative line
- **List markers**: Gold dots or Playfair Display serif numerals
- **Tags/Badges**: Gold fill (secondary), Burgundy fill (emphasis), Royal Blue light bg (category)
- **Headlines**: Playfair Display serif, optional gold decorative short line beneath
- **Dividers**: Not simple `border-bottom`; use gold thin line + gradient fade or gold dot separators
- **Animation** (if any): Light, slow, restrained, `cubic-bezier(0.16, 1, 0.3, 1)`, no bounce

**FEIHONG Signature Collection — strongly recommended** (especially Stable scenes):
- Drop Cap (first paragraph of tutorials)
- Marginalia (tutorial side notes)
- Wax Seal (portfolio / certification feel)
- Photo Corner (portfolio / editorial feel)
- Gold Signature (article endings / About pages)
- Fleuron ❦ (section dividers)
- N° Serial Badge (numbered items, limited edition feel)

---

### Step 07 — Refine · 精工细作（Quality Self-Check）

This is the most critical step. **Do not skip.**
这是最关键的一步，**不能跳过**。

Check against `QUALITY.md` + `DNA.md` quality gate standards item by item.

#### 🔴 P0 — Seal Required · 必过（一条不过就必须改）

- [ ] **Exact colors**: Search HTML to confirm three colors are exactly `#0A2463`, `#F4D35E`, `#D8315B`, no approximations
- [ ] **Color proportions**: Royal Blue dominant ~55%, Gold supporting ~30%, Burgundy accent ~15%
- [ ] **Gold never large background**: Only for emphasis / decoration / highlight
- [ ] **Body contrast**: ≥4.5:1, no gold body text on light backgrounds
- [ ] **Single Hero focus**: Only one primary visual focal point
- [ ] **Mobile adaptation**: <600px layout reasonable, no text overlap/overflow
- [ ] **No fourth primary**: Success green only functional, Terminal green only terminal scenes
- [ ] **Taboo check**: No glassmorphism / bounce / gradient text / AI glow / default quote blocks
- [ ] **Zero default styles**: All ul/ol/blockquote/table/button/input/links branded
- [ ] **Serif + Sans mix**: Headlines Playfair Display, body Inter, never single font throughout
- [ ] **Responsive complete**: Desktop + tablet + mobile, using clamp()
- [ ] **Section/page layouts differ**: Adjacent areas never repeat layout
- [ ] **clamp() usage**: Key font sizes / spacing / containers use clamp(), not hardcoded px
- [ ] **Tone consistent**: Matches emotional direction set in Step 05
- [ ] **Anti-AI detection**: Screenshot would not be identified as AI-generated on social platforms
- [ ] **Motion compliance**: Follows `MOTION.md` easing, duration, reduced-motion rules

#### 🟡 P1 — Quality Expected · 应该通过（尽量满足）

- [ ] Typography strategy correct: Display serif, UI sans
- [ ] Overall feel: refined, artistic, professional, warm
- [ ] Royal Blue carries brand recognition
- [ ] Burgundy provides breathing room (appears meaningfully, not just one button)
- [ ] Vintage Gold is a memorable signature detail
- [ ] Layout alignment disciplined, not random decoration
- [ ] At least one visual surprise section breaking template feel
- [ ] Extreme typography contrast (very large ↔ truly small)
- [ ] Animation light, slow, restrained
- [ ] Large decorative numerals/English present but unobtrusive (opacity 0.06-0.12)
- [ ] Signature elements from Step 05c carry through the page
- [ ] Motion follows Feihong Easing `cubic-bezier(0.16, 1, 0.3, 1)`

#### 🟢 P2 — Refinement Bonus · 加分项（锦上添花）

- [ ] Subtle flowing line / art panel motif
- [ ] CSS variables/tokens reusable
- [ ] Brand migratable to other scenes
- [ ] Images/IP overflow containers (editorial feel)
- [ ] Dark panels break rhythm without dominating
- [ ] Decorative elements few and precise
- [ ] Radial gradients instead of flat color
- [ ] Avatar/IP appear naturally
- [ ] FEIHONG Signature Collection elements used appropriately

#### Scene Additional Checks
- Deck → Confirm 16:9, keyboard navigation (←→/Space/F/Esc), fullscreen
- Cards → `scenes/cards.md` dedicated Checklist
- Email → Confirm table layout, Outlook compatible, no external CSS
- WeChat → Confirm inline styles, no external JS, WeChat-compatible tags
- Resume → Confirm A4 print, single page, no animations, print-friendly
- App / Terminal → Terminal Green `#4ADE80` restricted to code/terminal elements only

**Self-check failure handling**:
- P0 failure → Fix immediately → Re-check all P0
- P1 failure → Assess fix cost, fix if time allows
- Changes affecting other parts → Re-check affected P0 items

---

### Step 08 — Seal & Deliver · 封印交付

Delivery standards:
1. HTML file complete, opens directly in browser
2. External resources via CDN (Google Fonts), no local file dependency (except avatar/IP)
3. File encoding UTF-8
4. Special scenes meet technical constraints (email tables, WeChat inline, Deck nav JS, resume print CSS)

**When delivering**:
- ✅ File link (computer:// path)
- ✅ 1-2 sentences describing design signature (e.g., "Asymmetric Hero + gold signature line, deep blue panel with IP overflow on third screen creating editorial feel")
- ✅ Notes (e.g., "Replace avatar in assets/avatar.jpg", "Press F11 for best fullscreen presentation", "Beta scene, continuously iterating")

**When delivering, do NOT**:
- ❌ "This was generated according to the specification"
- ❌ "Used the three brand colors"
- ❌ List technical implementation details

---

## 🗺️ Scene Quick Reference · 10种场景速查表

### ⭐ Stable Core Scenes

| N° | Scene | Spec | Template | Core Features | Interaction |
|---|----------|---------|------|---------|---------|
| 01 | Portfolio / 作品集 | `scenes/portfolio.md` | `assets/portfolio.html` | Project showcase, visual-first, grid, asymmetric | Long scroll |
| 02 | Landing Page / 活动页 | `scenes/landing.md` | `assets/landing.html` | Conversion-driven, visual impact, clear CTA, forms | Long scroll |
| 03 | Tutorial / 教程 | `scenes/tutorial.md` | `assets/tutorial.html` | Long reading, TOC, progress bar, drop cap | Long scroll |
| 04 | Deck / 演示文稿 | `scenes/deck.md` | `assets/deck.html` | Fullscreen, 16:9, keyboard nav, large type minimal text | Slide navigation |

### 🧪 Beta Scenes

| N° | Scene | Spec | Template | Core Features | Status |
|---|----------|---------|------|---------|------|
| 05 | Case Study / 案例 | `scenes/case-study.md` | `assets/case-study.html` | Narrative: problem→solution→result | 🧪 Beta |
| 06 | App / 功能页 | `scenes/app.md` | `assets/app.html` | Functional, interactive, Terminal Green available | 🧪 Beta |
| 07 | Social Cards / 图文卡片 | `scenes/cards.md` | `assets/cards.html` | 3:4 portrait, pagination, html2canvas export | 🧪 Beta |
| 08 | Resume / 简历 | `scenes/resume.md` | `assets/resume.html` | A4 single page, print-friendly, no animation | 🧪 Beta |
| 09 | WeChat / 公众号 | `scenes/wechat.md` | Inline HTML | WeChat compatible, inline styles | 🧪 Beta |
| 10 | Email / 邮件 | `scenes/email.md` | `assets/email.html` | Table layout, Outlook compatible | 🧪 Beta |

### Scene Classification Memory

**Long Scroll (6)**: Tutorial, Landing, Portfolio, Case Study, App, WeChat
**Paged/Paginated (2)**: Deck (fullscreen slides), Cards (3:4 paged)
**Single-page Static (2)**: Resume (A4 single), Email (table static)

---

## 🔑 Key Principles · 关键原则（时刻记住）

1. **8 Steps, no shortcuts** — Step 05 direction setting is the anti-AI key; never skip it
2. **Start from templates, never from zero** — Templates have brand tokens built in
3. **Stable scenes first** — 4 Stable scenes are primary, Beta scenes supplementary
4. **Every section layout must differ** — Avoid monotonous repetition
5. **Checklist must pass** — P0 all clear before delivery
6. **Brand colors exact to HEX** — `#0A2463` / `#F4D35E` / `#D8315B`, not "blue""gold""red"
7. **Serif + Sans must mix** — All Inter = AI template signature
8. **clamp() preferred** — Font sizes, spacing, container sizes use fluid sizing
9. **Decoration few and precise** — Gold lines, numerals, quotes: 2-3 per page, not stacked
10. **Warm base tone** — `#FDFBF6` warm cream, not cold white `#FFFFFF`
11. **Radial gradients for depth** — Not flat color; subtle gradients add texture
12. **Signature Collection adds human warmth** — Drop cap, wax seal, fleuron used appropriately
13. **Motion follows MOTION.md** — Easing, duration, restraint, reduced-motion support

---

## 🚫 Core Bottom Line · 核心底线

Strictly follow the taboo list in `DNA.md`. Core bottom line:

**A screenshot shared to any social platform must never trigger the reaction "that's AI-generated."**
**截图发到任何社交平台，不会让人第一反应是"又是AI做的"。**

Anti-AI strategies:
- No symmetric centered card grids (AI's favorite)
- No Glassmorphism / gradient text / glow effects (AI signature)
- Extreme typography contrast (large→very large, small→truly small)
- At least one "human judgment" decision: asymmetric layout, element overflow, irregular rhythm, deliberate whitespace
- Cormorant Garamond italic quotes add humanist warmth
- Gold decorative lines add hand-crafted signature feel
- Radius hierarchy (not uniform sizing)
- Shadows with blue tint (not generic black shadows)
- Whitespace with breathing rhythm (not mechanically equal spacing)
- Step 05 direction setting must be executed — AI has no "tonal judgment", it assembles
- Motion has weight and restraint, never bouncy or frantic

---

*FEIHONG Design System v7.0*
*Anti-AI · Artistic Quality · Human Warmth*
*4 Stable Scenes · 6 Beta Scenes · 148 Components · 250+ Variants*
