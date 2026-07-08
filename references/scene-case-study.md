# Feihong Design System · Scene: Case Study
# 飞鸿品牌设计系统 · 场景规范：案例研究 / Case Study

> 本规范定义飞鸿品牌设计系统在「项目复盘 / 案例研究 / 设计过程展示」中的具体应用方式。
> 所有规则建立在 `brand-dna.md`、`layouts.md`、`components.md` 基础之上，场景专属规则以本文件为准。
> Case Study 场景的核心使命是**叙事性展示设计思考深度**——不是结果的陈列馆，而是一段从背景到挑战、从探索到结果的完整故事。让读者跟随你的思路走完全程，看到"为什么这样做"比"做了什么"更重要。

---

## 1. 场景定义

### 适用页面类型

Case Study 场景适用于以下以**项目深度叙事为核心目标**的内容形态：

| 类型 | 说明 | 典型长度 | 核心目标 |
|------|------|----------|---------|
| **设计项目复盘** | 品牌设计/UI/UX/产品设计完整案例 | 8-15屏 | 展示设计思考过程与方法论 |
| **作品集详情页** | Portfolio中点击作品进入的案例详情 | 6-12屏 | 深度呈现单个项目，证明专业能力 |
| **设计过程文档** | 研究过程、迭代记录、设计决策推演 | 7-12屏 | 透明化设计过程，建立专业权威 |
| **获奖/投稿案例** | 设计奖申报、杂志投稿、平台发布案例 | 8-14屏 | 完整叙事+数据结果，符合评审标准 |
| **客户案例展示** | 服务型公司/工作室的客户成功案例 | 6-10屏 | 展示解决问题的能力，赢得新客户 |

### 场景核心气质

- **叙事性第一**：案例研究是"讲故事"而非"堆图片"，读者应该能像读文章一样跟随你的思路从头走到尾
- **思考深度可见**：不仅展示最终方案，更要展示"为什么不选B而选A"的决策过程
- **过程与结果并重**：草图、wireframe、失败的尝试和最终稿同等重要——过程证明能力
- **数据说话**：结果部分必须有可量化的数据佐证，"用户满意度提升"不如"NPS从32提升到58"
- **画册级质感**：图片可溢出容器、文字与图交替呼吸，像翻阅一本精装画册而非浏览网页

### 场景核心约束

1. **必须有完整叙事结构**：背景 → 挑战 → 过程 → 结果 → 反思，缺一不可
2. **必须有过程图**：草图、wireframe、迭代版本、探索方向——不能只放最终效果图
3. **结果必须有数据**：至少2-3个量化数据点（转化率、满意度、时间节省、营收增长等）
4. **必须有反思/Learnings**：一个不反思的案例研究只是作品集，不是Case Study
5. **文字量比Portfolio大**：Case Study是"深度阅读"场景，不要害怕长段落，但要通过排版让长文好读

---

## 2. 典型页面结构

Case Study 页面采用 **Hero项目封面 → 项目概览 → 背景与挑战 → 设计过程 → 最终方案 → 结果与数据 → 反思与Learnings → 导航/CTA** 的八段式叙事结构：

```
┌─────────────────────────────────────────────────────────┐
│  ① Hero 项目封面（L4 全屏视觉 — 首选）                    │
│     - 项目最终效果图/代表性视觉（全屏背景）                │
│     - 项目名称（超大衬线，叠在图片上）                     │
│     - 客户名称 + 项目类型标签                             │
│     - 可选：年份标签（金色）                              │
│     * 作用：第一眼建立项目印象，像画册封面                 │
├─────────────────────────────────────────────────────────┤
│  ② 项目概览（L15 双栏对比 或 L14 数据条）                 │
│     - 客户/Client、周期/Duration、角色/Role、团队/Team   │
│     - 项目标签（金色badge：品牌设计/UI/UX/包装等）        │
│     - 1-2段项目摘要（一句话讲清楚"做了什么"）             │
│     - 可选：关键成果数据预览（stat-card × 2-3）          │
│     * 作用：快速给读者项目全局信息，像图书扉页            │
├─────────────────────────────────────────────────────────┤
│  ③ 背景与挑战（L5/L6 图文并排 或 L7 单栏长文）            │
│     - 项目背景：客户是谁、行业现状、为什么要做这个项目     │
│     - 核心挑战：1-3个关键设计挑战（用酒红标注挑战点）     │
│     - 设计目标：可量化的目标（"提升注册转化率20%"）      │
│     - 可选：用户画像/市场数据引用                        │
│     * 作用：建立"问题"，让读者理解设计的起点             │
├─────────────────────────────────────────────────────────┤
│  ④ 设计过程（L11 交错瀑布流 — 核心区域）                  │
│     - 阶段一：研究与洞察（用户调研/竞品分析/草图）        │
│     - 阶段二：概念探索（方向发散/wireframe/情绪板）       │
│     - 阶段三：迭代与决策（多版本对比/用户测试/设计推演）   │
│     - 阶段四：最终确定（设计系统/规范/交付物）            │
│     - 图文交替：一段文字描述配一张过程图（草图→线框→视觉） │
│     - 可用timeline串联各阶段                              │
│     * 作用：这是Case Study的灵魂，展示思考深度            │
├─────────────────────────────────────────────────────────┤
│  ⑤ 最终方案展示（L16 画册溢出式 / 大图展示）              │
│     - 最终设计稿大图展示（可溢出容器，画册感）            │
│     - 核心设计决策说明（为什么这样做）                    │
│     - 多设备/多场景mockup展示                            │
│     - 设计系统/组件展示（如有）                          │
│     - card-project大图展示最终视觉                        │
│     * 作用：呈现设计成果，视觉高潮                        │
├─────────────────────────────────────────────────────────┤
│  ⑥ 结果与数据（L8 大引文 + L14 数据条）                   │
│     - 客户评价/引言（pull-quote，金色引号装饰）           │
│     - 关键数据（stat-card × 3-4，数据可视化）            │
│     - 对比数据（before/after，用酒红/金色标注提升幅度）   │
│     - 业务影响描述                                       │
│     * 作用：用数据证明设计价值                            │
├─────────────────────────────────────────────────────────┤
│  ⑦ 反思与Learnings（L7 单栏长文 或 L13 深色面板）        │
│     - 做对了什么？做错了什么？                            │
│     - 如果重来会怎么做？                                  │
│     - 从项目中学到的3个关键lesson                        │
│     - 可用深色面板制造视觉停顿，像画册的结尾篇章          │
│     * 作用：体现思考深度，区别于单纯的作品展示            │
├─────────────────────────────────────────────────────────┤
│  ⑧ 导航与CTA（普通段落 / L13变体）                       │
│     - 上一篇/下一篇项目导航                               │
│     - "查看更多作品"按钮 / "联系我"CTA                   │
│     - 返回作品集首页                                      │
│     * 作用：引导读者继续浏览，促成联系                    │
└─────────────────────────────────────────────────────────┘
```

### 结构要点

1. **叙事节奏要有起承转合**：Hero（视觉冲击）→ 概览（信息铺垫）→ 挑战（建立张力）→ 过程（展开叙事）→ 方案（视觉高潮）→ 结果（数据验证）→ 反思（深度升华）
2. **过程区域占比最大**：设计过程应占页面总长度的 40%-50%，这是Case Study与Portfolio最大的区别
3. **图文交替节奏**：不要连续出现3张以上图片而没有文字说明，也不要连续3段文字没有图片——保持图-文-图-文的呼吸节奏
4. **每个阶段有小标题**：设计过程分2-4个阶段，每个阶段有明确的小标题和阶段说明
5. **数据在结果区集中呈现**：不要在过程中过早展示结果数据，保持叙事的悬念感

---

## 3. 色彩使用指南

Case Study 场景遵循品牌 55-30-15 色彩比例，但三色在叙事场景中承担更明确的**语义角色**——金色用于"信息标记"，酒红用于"关键强调"，皇家蓝主导整体阅读框架。

### 3.1 皇家蓝 `#0A2463`（55%）— 阅读框架与标题导航

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **页面主标题** | h1 项目名称（Hero区）、h2 章节标题 | Playfair Display 衬线，皇家蓝或白色（叠在图上时） |
| **导航栏** | 顶部导航、面包屑导航 | 品牌色建立阅读框架 |
| **正文小标题** | h3/h4 子标题、过程阶段标题 | 皇家蓝引导阅读节奏 |
| **正文链接** | 文内引用链接、相关项目链接 | 皇家蓝默认，hover转酒红 |
| **时间线连线** | timeline 组件的垂直连线 | 串联设计过程各阶段 |
| **卡片边框/描边** | card-project、stat-card 的默认边框 | 统一视觉框架 |
| **深色面板背景** | L13 反思区可用皇家蓝深蓝渐变 | 深色面板打破长文节奏 |
| **blockquote 引用线** | 客户引言左侧的竖线装饰 | 皇家蓝3px竖线 |

### 3.2 复古金 `#F4D35E`（30%）— 信息标记与数据高亮

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **项目信息标签** | 客户名、周期、角色、年份等元信息标签 | badge-gold 或金色文字，标记"信息性内容" |
| **时间标记** | 时间线日期、阶段编号（01/02/03） | 金色序号串联叙事时间线 |
| **数据高亮** | stat-card 中的关键数字、数据提升幅度 | 金色数字在白底上最醒目 |
| **项目标签badge** | 项目类型标签（品牌设计/UI/UX等） | 金色底+皇家蓝文字 |
| **引号装饰** | pull-quote 的大引号装饰 | 金色`"`符号，Cormorant大字号 |
| **荧光笔高亮** | 正文中的关键结论/核心洞察文字 | `linear-gradient(transparent 60%, rgba(244,211,94,0.4) 60%)` |
| **页码/章节序号** | 大装饰数字 01/02/03 | Cormorant 斜体金色大数字 |
| **before/after对比标记** | 对比数据中的"提升/增长"标记 | 金色箭头↑+百分比 |
| **图片标注线/标注点** | 设计稿上的标注引出线和圆点 | 金色细线+圆点，标注设计细节 |

### 3.3 酒红 `#D8315B`（15%）— 关键成果与挑战标注

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **挑战点标注** | 背景章节中的核心挑战标题/图标 | 酒红标记"问题"和"困难"，建立张力 |
| **关键成果数据** | 最重要的1-2个结果数字 | 酒红数字比金色更有"战果"感 |
| **数据提升标注** | 结果区的核心提升百分比 | 如"+45%"用酒红标注 |
| **关键决策标记** | 设计过程中重要转折点 | 酒红小标签标记"Aha Moment" |
| **失败尝试标注** | 过程中被否决的方案/走的弯路 | 酒红文字+删除线或特殊样式，诚实地展示试错 |
| **CTA按钮** | "查看更多作品"/"联系我"按钮 | 页面结尾行动引导 |
| **内联强调** | 正文中最核心的一句话（不超过10字） | 酒红色加粗，一屏最多1处 |

### 3.4 背景与中性色

| 元素 | 色值 | 说明 |
|------|------|------|
| 页面主背景 | `#FDFBF6` (`var(--cream)`) | 暖米白，长阅读舒适不刺眼 |
| 卡片/图注背景 | `#FFFFFF` 或 `var(--cream-100)` | 白色卡片+暖米白页面，层次分明 |
| 交替section背景 | `var(--cream-100)` (`#F8F4EB`) | 每隔1-2个section切换极浅暖米色，区分节奏 |
| 深色面板背景 | 皇家蓝深蓝径向渐变 | 反思区(Learnings)可用，打破长文阅读疲劳 |
| 图注文字 | `var(--ink-300)` (`#6D7487`) | Inter小字，灰色，图片下方说明 |
| 正文文字 | `var(--ink-100)` (`#2C3347`) | 深灰，长阅读舒适 |
| 标题文字 | `var(--ink)` (`#0D1225`) 或 `#FFFFFF`（叠图/深色面板） | 墨黑或纯白，对比强烈 |
| 元信息文字 | `var(--ink-300)` | 客户/日期/角色等次要信息 |
| 边框/分隔线 | `var(--cream-200)` (`#F0EAD9`) | 暖调分隔线，章节之间呼吸 |

### 色彩使用铁律（Case Study 场景）

1. **金色用于"信息标记"而非"装饰"**：在Case Study中金色的核心语义是"这是一个元数据/标签/编号"，不是单纯的装饰色
2. **酒红一屏最多出现2-3处**：酒红是"关键标记"，泛滥使用会失去强调效果
3. **挑战用酒红，成果也可用酒红**：酒红在Case Study中同时标记"问题"和"战果"，形成首尾呼应
4. **过程图上的标注线统一用金色**：设计稿上的标注引出线、圆点统一使用金色细线，清晰但不喧宾夺主
5. **深色面板仅用于反思区或客户引言区**：全页1-2次即可，不要频繁打断阅读流

---

## 4. 排版规范

### 4.1 项目名排版：超大衬线（核心约束）

Case Study 首屏的项目名称是整个页面最重要的排版元素，必须使用**超大Playfair Display衬线**，叠在项目封面图上或与封面图并置：

| 指标 | 规范值 | 说明 |
|------|--------|------|
| **h1 项目名字号** | `clamp(2.5rem, 7vw, 5rem)` | 桌面端最大可达 80px，移动端不小于 40px |
| h1 项目名字重 | 700/900 | Playfair Display 粗体 |
| h1 项目名字式 | normal（正体，非斜体） | 案例研究标题正体更有"文献感"，与Portfolio斜体名字区分 |
| h1 行高 | 1.05 | 大标题紧凑 |
| h1 字距 | -0.02em | 微缩字距 |
| h1 颜色 | `#FFFFFF`（叠图）或 `var(--ink)`（白底） | 叠在深色图片上必须白色，确保可读 |
| **eyebrow 客户标签** | `0.75rem`（12px） | 全大写，宽字距，金色或白色 |
| **项目副标题** | `clamp(1rem, 1.5vw, 1.25rem)` | Inter无衬线，项目类型/年份等元信息 |

**字号对比示例**：
```
eyebrow:     12px  ●●● （极小，如"CLIENT: 某科技公司 / 2025"）
h1 项目名:   72px  ●●●●●●●●●●●●●●●●●● （极大，衬线粗体，叠在封面图上）
subtitle:    18px  ●●●● （中等，无衬线，项目类型简述）
正文:        16px  ●●● （标准阅读字号，Inter）
```

> **铁律**：项目名h1必须是页面最大字号，与eyebrow元信息形成至少1:5的字号比。项目名用正体（`font-style: normal`），区别于Portfolio的斜体签名感——案例研究标题需要"文献感"而非"签名感"。

### 4.2 元信息 eyebrow + caption 风格

项目概览区的元信息（客户/周期/角色/团队）使用统一的 eyebrow-label + caption-value 风格：

```css
.meta-group {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
  gap: var(--sp-6);
  padding: var(--sp-6) 0;
  border-top: 1px solid var(--cream-200);
  border-bottom: 1px solid var(--cream-200);
}
.meta-item {}
.meta-label {
  font-size: 0.6875rem; /* 11px */
  font-weight: 600;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--gold);
  display: block;
  margin-bottom: var(--sp-2);
  /* 金色小标签：CLIENT / ROLE / DURATION */
}
.meta-value {
  font-family: var(--font-sans);
  font-size: 1rem; /* 16px */
  font-weight: 500;
  color: var(--ink);
  line-height: 1.5;
}
```

- 标签（Client/Role/Duration）：11px Inter 600，全大写，金色，宽字距
- 值（客户名/角色名/时间）：16px Inter 500，墨黑色
- 标签组用金色上下边框包裹，形成信息卡片感
- 一行排列4-5个元信息项，移动端改为2列

### 4.3 正文排版规范（长阅读优化）

Case Study 是深度阅读场景，正文排版比Portfolio更注重**长文可读性**：

| 元素 | 字号 | 行高 | 字体 | 颜色 | 说明 |
|------|------|------|------|------|------|
| **正文段落** | `1.0625rem`（17px） | **1.8** | Inter | `var(--ink-100)` | 行高1.8比Portfolio的1.7更宽松，长阅读不累 |
| **正文宽度** | 不超过 680px | — | — | — | 单栏阅读最佳宽度，过宽眼睛容易走行 |
| **图注/说明** | `0.8125rem`（13px） | 1.5 | Inter | `var(--ink-300)` | 图片下方说明文字，斜体可选 |
| **阶段小标题** | `0.75rem`（12px） | 1.4 | Inter 600 | `var(--gold)` | 全大写宽字距，如"PHASE 01 / 研究" |
| **过程描述** | `1rem`（16px） | 1.7 | Inter | `var(--ink-100)` | 设计过程中的叙述文字 |
| **pull-quote/引言** | `clamp(1.5rem, 3vw, 2.5rem)` | 1.4 | Cormorant Garamond italic | `var(--royal)` 或 `#fff` | 客户评价/关键洞察 |
| **数据数字** | `clamp(2.5rem, 5vw, 4rem)` | 1 | Playfair Display 700 | `var(--gold)` 或 `var(--wine)` | 结果数据比Portfolio更大 |
| **数据标签** | `0.8125rem`（13px） | 1.4 | Inter 500 | `var(--ink-200)` | 数据下方的说明文字 |
| **章节大序号** | `clamp(4rem, 10vw, 8rem)` | 1 | Cormorant Garamond italic | `rgba(244,211,94,0.15)` | 章节旁的巨型装饰数字 |

### 4.4 标题层级（Case Study 场景适配）

| 层级 | 字体 | 字号 (clamp) | 行高 | 字重 | 字式 | 颜色 | 装饰 |
|------|------|-------------|------|------|------|------|------|
| **h1** 项目名 | Playfair Display | `clamp(2.5rem, 7vw, 5rem)` | 1.05 | 700/900 | **normal** | #fff / `var(--ink)` | 叠封面图时白色，加文字阴影 |
| **h2** 章节标题 | Playfair Display | `clamp(1.5rem, 3vw, 2.25rem)` | 1.2 | 700 | normal | `var(--ink)` | 可选金色大序号旁置 |
| **h3** 阶段标题 | Playfair Display | `clamp(1.15rem, 2vw, 1.35rem)` | 1.3 | 600 | normal | `var(--royal)` | 前有金色阶段标签 |
| **h4** 小标题 | Inter | `0.9375rem` | 1.4 | 600 | normal | `var(--ink)` | 无装饰 |

### 4.5 排版特殊规则

1. **首字下沉可选**：背景章节的第一段可使用首字下沉（drop cap），增加画册感：
   ```css
   .drop-cap::first-letter {
     font-family: var(--font-serif);
     font-size: 3.5em;
     font-weight: 700;
     float: left;
     line-height: 0.8;
     margin: 0.05em 0.1em 0 0;
     color: var(--royal);
   }
   ```

2. **图片标注样式**：设计稿上的标注用金色细线+圆点+文字：
   ```css
   .annotation {
     position: absolute;
     font-size: 0.75rem;
     font-family: var(--font-mono); /* JetBrains Mono 等宽 */
     color: var(--gold);
   }
   .annotation::before {
     content: '';
     display: inline-block;
     width: 8px; height: 8px;
     border-radius: 50%;
     background: var(--gold);
     margin-right: 6px;
     vertical-align: middle;
   }
   .annotation-line {
     position: absolute;
     background: var(--gold);
     height: 1px;
     transform-origin: left center;
   }
   ```

3. **正文段落间距**：段落之间 `margin-bottom: 1.5em`，比普通网页更宽松，营造阅读呼吸感

4. **长引文独立成块**：超过2行的引用不要嵌在正文中，使用 pull-quote 组件独立展示

---

## 5. 推荐布局组合

从 L1-L16 中选取适合 Case Study 叙事的布局，按叙事节奏推荐如下：

### 5.1 首屏布局（1个首选 + 1个备选）

| 布局 | 适用场景 | 视觉特点 |
|------|----------|---------|
| **L4 全屏视觉Hero** | **Case Study首选**，项目封面 | 全屏项目效果图做背景，项目名白色大字叠在图上，金色客户/年份标签，画册封面感 |
| L3 分屏Hero | 文字较多的项目介绍 | 一侧深色+项目名+摘要，一侧大幅项目图，信息密度更高 |

**首屏选择建议**：
- **绝大多数案例** → 首选 **L4 全屏视觉Hero**（一张最强视觉做封面，最像画册）
- **B端/复杂产品/需要更多文字铺垫** → 可选 **L3 分屏Hero**（有空间放项目摘要）

### 5.2 项目概览区域布局

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **L15 双栏对比** | 概览首选，左侧项目摘要+右侧元信息网格 | 左：2-3句项目概述；右：4-5个meta-item（客户/周期/角色/团队/行业） |
| **L14 数据条** | 概览区紧接数据条，快速展示3-4个关键数据 | stat-card横排，预览项目规模和影响 |

### 5.3 背景与挑战区域布局

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **L5 左图右文 / L6 左文右图** | 背景描述+辅助图片 | 一侧放项目原始状态/旧版截图/行业图片，一侧放背景文字 |
| **L7 单栏长文** | 纯文字背景叙述 | 680px宽度居中，可选首字下沉，适合深度叙述 |
| **L15 双栏对比** | 核心挑战呈现 | 左栏"Before/问题现状"，右栏"设计目标/期望"，用酒红标注挑战点 |

### 5.4 设计过程区域布局（核心，占比最大）

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **L11 交错瀑布流** | **过程区首选布局**，图+文交替展示 | 奇行左图右文，偶行左文右图，节奏感强，像翻画册 |
| **L12 时间线** | 串联设计过程各阶段 | 皇家蓝连线+金色节点，左侧阶段时间，右侧阶段内容+图片 |
| **L10 非对称bento** | 多图并列展示（如多个探索方向） | 大小图错落，一个方向大图+其他方向小图对比 |

**过程区布局要点**：
- 设计过程是Case Study的核心，建议使用 **L11交错瀑布流** 作为主要布局
- 每个过程阶段有明确的阶段标签（金色"PHASE 01"等）+ 阶段标题 + 描述文字 + 过程图
- 过程图包括但不限于：草图照片、白板照片、wireframe线框图、情绪板、探索稿、迭代版本对比
- 图文比例约 1:1，保持"一段文字一张图"的节奏
- 被否决的方案也要展示，并说明为什么否决——这是思考深度的体现

### 5.5 最终方案区域布局

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **L16 画册溢出式** | **方案展示首选**，最终设计稿大图 | 图片溢出容器宽度，满屏展示，制造画册翻页的视觉冲击 |
| **L10 非对称bento** | 多页面/多设备方案展示 | 主视觉大图+辅助小图（细节/组件/多设备mockup） |
| **card-project大图模式** | 单张核心最终稿展示 | 大图aspect-ratio 16/9或3/2，下方图注说明 |

### 5.6 结果与数据区域布局

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **L8 大引文全屏** | 客户评价/关键洞察 | Cormorant斜体金句，金色大引号，深色或暖米白背景 |
| **L14 数据统计条** | 结果数据展示 | 3-4个stat-card横排，金色/酒红大数字+灰色标签 |
| **L15 双栏对比** | Before/After对比 | 旧数据vs新数据，用酒红/金色标注提升幅度 |

### 5.7 反思区域布局

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **L13 深色面板** | **反思首选**，深蓝背景+白色/金色文字 | 制造视觉停顿，像画册的终章，Learnings用金色序号排列 |
| **L7 单栏长文** | 文字反思 | 680px宽度居中，朴实的文字叙述 |

### 5.8 结尾导航布局

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **普通段落** | 上/下项目导航 + CTA | 左右分栏：←上一项目 / 下一项目→ + 中间"返回作品集"+"联系我" |
| **L13 深色面板**（可选） | 如果反思区未用L13，结尾CTA可用 | "有类似项目？聊聊" + 联系方式 |

### 5.9 经典 Case Study 布局配方

#### 配方 A：品牌/视觉设计案例（10屏，最常用）

| 顺序 | 布局 | 内容 |
|------|------|------|
| 1 | **L4 全屏视觉Hero** | 品牌最终主视觉全屏背景 + 白色项目名 + 金色客户/年份标签 |
| 2 | **L15 双栏对比** | 左侧：项目摘要（2-3段）；右侧：元信息网格（客户/周期/角色/ Deliverables） |
| 3 | **L5 左图右文** | 背景：旧品牌/市场现状图 + 背景叙述文字 |
| 4 | **L15 双栏对比** | 挑战：左栏"问题"（酒红标注），右栏"目标"（金色标注） |
| 5 | **L11 交错瀑布流** | 设计过程：草图→情绪板→方向探索→迭代→定稿（图文交替，4-6屏） |
| 6 | **L16 画册溢出式** | 最终方案：品牌主视觉+logo大图溢出展示 |
| 7 | **L10 bento网格** | 最终方案：应用场景mockup（名片/包装/网站等） |
| 8 | **L8 大引文 + L14 数据条** | 客户评价pull-quote + 3-4个stat-card成果数据 |
| 9 | **L13 深色面板** | 反思：Learnings 3条，金色序号，白色文字 |
| 10 | **普通段落** | 上下项目导航 + "查看更多作品"CTA |

#### 配方 B：UI/UX产品设计案例（12屏，过程更重）

| 顺序 | 布局 | 内容 |
|------|------|------|
| 1 | **L4 全屏视觉Hero** | 产品最终界面全屏背景 + 项目名 |
| 2 | **L15 双栏 + L14数据条** | 元信息概览 + 项目规模数据 |
| 3 | **L7 单栏长文** | 背景与用户痛点（首字下沉可选） |
| 4 | **L15 双栏对比** | 核心挑战 vs 设计目标 |
| 5 | **L11 交错瀑布流** | 研究阶段：用户画像/竞品分析/用户旅程图 |
| 6 | **L11 交错瀑布流** | 概念阶段：wireframe/信息架构/流程图 |
| 7 | **L12 时间线** | 迭代过程：版本1→测试→版本2→测试→最终版 |
| 8 | **L16 画册溢出式** | 最终方案：核心界面大图溢出 |
| 9 | **L10 bento网格** | 多页面/组件/设计系统展示 |
| 10 | **L14 数据条 + L8引文** | 数据结果（转化率/满意度/任务完成率）+ 用户引言 |
| 11 | **L13 深色面板** | 反思与Learnings |
| 12 | **普通段落** | 导航 + CTA |

### 5.10 布局使用禁忌

| 布局 | Case Study 场景不推荐原因 |
|------|------------------------|
| L1 非对称图文Hero | 适用于Portfolio首屏（个人介绍），Case Study首屏应以项目视觉为主 |
| L2 居中大字Hero | 信息量太少，无法承载项目封面需要的客户名/标签等元信息 |
| L9 三列卡片网格 | 适用于功能/服务介绍，Case Study以叙事为主，不适合大量并列卡片 |
| 连续两个相同布局 | 连续两个L11或连续两个L10=单调，必须交替不同布局制造节奏 |
| 多个L13深色面板 | 深色面板仅在反思区用1次（结尾CTA可选第2次），频繁打断阅读流 |
| L14数据条在过程中 | 数据应集中在结果区展示，过程中过早展示数据会破坏叙事悬念 |

---

## 6. 组件选用指南

### 6.1 必用组件（Case Study 场景核心组件，缺一不可）

| 组件 | 组件名 | 使用场景 | 使用频率 |
|------|--------|----------|----------|
| **项目卡片（大图）** | `card-project` | 最终方案展示区、Hero封面 | 2-4次，大图模式 |
| **数据卡片** | `stat-card` | 结果与数据区、概览区数据预览 | 3-6个 |
| **时间线** | `timeline` | 设计过程阶段串联 | 1次（L12）或贯穿过程区 |
| **大引文** | `pull-quote` | 客户评价、关键洞察、金句 | 1-3次 |
| **代码块** | `code-block` | 如有技术实现部分（前端/开发交付） | 按需 |

#### 项目大图卡片（`card-project` 大图模式）使用规范

Case Study中的card-project与Portfolio中的卡片hover交互不同——这里以**静态大图展示**为主，不需要hover遮罩：

```html
<!-- Case Study 中的最终方案大图展示 -->
<figure class="case-figure">
  <div class="case-image-wide">
    <img src="assets/case-final-1.jpg" alt="最终品牌主视觉">
  </div>
  <figcaption class="case-caption">
    <span class="caption-num">01</span>
    品牌主视觉应用于官网首页，深色背景下金色logo更具品质感。
  </figcaption>
</figure>
```

```css
.case-figure { margin: var(--sp-8) 0; }
.case-image-wide {
  border-radius: var(--r-lg);
  overflow: hidden;
  background: #fff;
  box-shadow: var(--shadow-md);
}
.case-image-wide img { width: 100%; display: block; }
.case-caption {
  font-size: 0.8125rem;
  color: var(--ink-300);
  text-align: center;
  margin-top: var(--sp-3);
  font-style: italic;
}
.caption-num {
  font-family: var(--font-mono);
  color: var(--gold);
  font-weight: 600;
  font-style: normal;
  margin-right: var(--sp-2);
}

/* L16 画册溢出式图片 */
.case-image-bleed {
  width: 100vw;
  margin-left: calc(-50vw + 50%);
  border-radius: 0;
  overflow: hidden;
}
.case-image-bleed img { width: 100%; display: block; }
```

- Case Study中的图片以**静态展示**为主，不需要Portfolio式的hover交互
- 普通图片用 `.case-figure` + `.case-image-wide`，白色背景+圆角+阴影
- 关键视觉用 `.case-image-bleed` 溢出容器宽度，制造画册翻页感
- 每张重要图片配 `.case-caption` 图注，用等宽字体金色序号标注

#### 数据卡片（`stat-card`）使用规范

```html
<div class="stat-grid">
  <div class="stat-card">
    <span class="stat-value" style="color:var(--wine)">+45%</span>
    <span class="stat-label">用户转化率提升</span>
  </div>
  <div class="stat-card">
    <span class="stat-value">3.2s</span>
    <span class="stat-label">页面加载时间（原8.7s）</span>
  </div>
  <div class="stat-card">
    <span class="stat-value">NPS 58</span>
    <span class="stat-label">用户净推荐值（原32）</span>
  </div>
  <div class="stat-card">
    <span class="stat-value" style="color:var(--gold)">¥2.3M</span>
    <span class="stat-label">首月营收贡献</span>
  </div>
</div>
```

```css
.stat-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: var(--sp-5);
  padding: var(--sp-6) 0;
}
.stat-card {
  text-align: center;
  padding: var(--sp-5);
  background: #fff;
  border-radius: var(--r-lg);
  border: 1px solid var(--cream-200);
}
.stat-value {
  font-family: var(--font-serif);
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 700;
  color: var(--royal);
  line-height: 1;
  display: block;
  margin-bottom: var(--sp-2);
}
.stat-label {
  font-size: 0.8125rem;
  color: var(--ink-300);
  line-height: 1.4;
}
```

- 最重要的1-2个数据用酒红（`var(--wine)`），其余用皇家蓝或金色
- 数据必须有标签说明，不能只放数字
- Before/After数据在标签中说明原始值（如"原8.7s"）
- 移动端单列或双列排列

#### 时间线（`timeline`）Case Study变体

Case Study的timeline用于展示设计过程，比Portfolio的职业时间线更丰富（可包含图片）：

```html
<div class="process-timeline">
  <div class="process-phase">
    <div class="phase-marker">
      <span class="phase-num">01</span>
    </div>
    <div class="phase-content">
      <span class="phase-label">RESEARCH</span>
      <h3 class="phase-title">用户研究与洞察</h3>
      <p class="phase-desc">通过12场用户深度访谈和200份问卷，我们发现核心痛点在于...</p>
      <div class="phase-image">
        <img src="assets/case-research.jpg" alt="用户访谈照片">
      </div>
    </div>
  </div>
  <!-- 更多 phase... -->
</div>
```

```css
.process-timeline { position: relative; padding-left: 80px; }
.process-timeline::before {
  content: ''; position: absolute;
  left: 30px; top: 0; bottom: 0;
  width: 2px; background: linear-gradient(180deg, var(--royal), rgba(10,36,99,0.1));
}
.process-phase { position: relative; padding-bottom: var(--sp-8); }
.phase-marker {
  position: absolute; left: -80px; top: 0;
  width: 60px; text-align: center;
}
.phase-num {
  font-family: var(--font-display);
  font-size: 1.5rem;
  font-style: italic;
  font-weight: 600;
  color: var(--gold);
  display: block;
  background: var(--cream);
  position: relative; z-index: 1;
}
.phase-label {
  font-size: 0.6875rem; font-weight: 600;
  letter-spacing: 0.15em; text-transform: uppercase;
  color: var(--gold); display: block; margin-bottom: var(--sp-1);
}
.phase-title {
  font-family: var(--font-serif); font-size: 1.25rem;
  font-weight: 700; color: var(--royal); margin-bottom: var(--sp-3);
}
.phase-desc { font-size: 1rem; line-height: 1.7; color: var(--ink-100); margin-bottom: var(--sp-4); }
.phase-image {
  border-radius: var(--r-lg); overflow: hidden;
  box-shadow: var(--shadow-md); background: #fff;
}
.phase-image img { width: 100%; display: block; }
```

- 每个阶段包含：金色序号 + 阶段标签(RESEARCH/CONCEPT/ITERATE/FINAL) + 阶段标题 + 描述文字 + 过程图
- 连线为皇家蓝垂直线，序号为Cormorant斜体金色
- 阶段之间间距宽松（`padding-bottom: 2rem`），避免拥挤

#### 大引文（`pull-quote`）Case Study变体

```html
<blockquote class="case-quote">
  <p>"新版设计上线后，我们的客服咨询量下降了40%，用户终于能自己找到想要的功能了。"</p>
  <cite>—— 产品总监，某科技公司</cite>
</blockquote>
```

```css
.case-quote {
  position: relative;
  padding: var(--sp-8) var(--sp-6);
  margin: var(--sp-10) 0;
  text-align: center;
  background: var(--cream-100);
  border-radius: var(--r-xl);
}
.case-quote::before {
  content: '"';
  font-family: var(--font-display);
  font-size: 6rem;
  color: var(--gold);
  opacity: 0.3;
  position: absolute;
  top: -0.2em;
  left: 50%;
  transform: translateX(-50%);
  line-height: 1;
}
.case-quote p {
  font-family: var(--font-display);
  font-size: clamp(1.25rem, 2.5vw, 1.75rem);
  font-style: italic;
  color: var(--royal);
  line-height: 1.5;
  max-width: 600px;
  margin: 0 auto;
}
.case-quote cite {
  display: block;
  font-family: var(--font-sans);
  font-size: 0.875rem;
  font-style: normal;
  color: var(--ink-300);
  margin-top: var(--sp-4);
}
/* 深色面板引文变体 */
.case-quote-dark {
  background: linear-gradient(135deg, var(--royal), #061540);
}
.case-quote-dark p { color: #fff; }
.case-quote-dark cite { color: rgba(255,255,255,0.6); }
.case-quote-dark::before { color: var(--gold); opacity: 0.2; }
```

- Case Study中的pull-quote主要用于**客户评价**和**关键洞察**
- 浅色版本（暖米白底+皇家蓝文字+金色引号）用于穿插在正文中
- 深色版本（皇家蓝渐变+白色文字+金色引号）用于独立成屏的视觉停顿
- 引用必须标注来源（人名+职位/公司），不能放无出处的"名言"

### 6.2 推荐组件（按需使用）

| 组件 | 使用场景 |
|------|----------|
| `badge-gold` | 项目类型标签、年份标签、阶段标签 |
| `badge-wine` | 核心挑战标记、关键成果标记 |
| `dark-panel` | 反思区(Learnings)、结尾CTA |
| `section-title`（含金色序号） | 每个大章节的标题区 |
| `divider-gold` | 章节之间的金色分隔线（克制使用） |
| `navbar`（固定导航） | 所有Case Study页必备，可加入面包屑 |
| `progress-bar`（阅读进度条） | 顶部细进度条显示阅读进度（P2加分） |
| `image-compare`（before/after滑块） | 新旧版本对比，可拖动滑块比较（P2加分） |

### 6.3 Case Study 场景专属组件模式

#### 过程图瀑布流项（L11 交错单元）

```html
<!-- L11 交错瀑布流：左图右文 -->
<div class="process-row process-row--image-left">
  <div class="process-visual">
    <img src="assets/case-sketch.jpg" alt="初始草图">
  </div>
  <div class="process-text">
    <span class="phase-label">PHASE 01 · SKETCH</span>
    <h3>从草图开始</h3>
    <p>项目最初从纸面草图开始。我们尝试了多种布局方向——从传统的三栏布局到更激进的单页叙事...</p>
    <p>最终选择了以内容为核心的居中布局，因为目标用户是...</p>
  </div>
</div>

<!-- L11 交错瀑布流：左文右图（交替） -->
<div class="process-row process-row--image-right">
  <div class="process-text">
    <span class="phase-label">PHASE 02 · WIREFRAME</span>
    <h3>线框图验证信息架构</h3>
    <p>在确定方向后，我们快速产出了3套wireframe方案进行内部评审...</p>
    <p class="text-wine">方案B因为导航层级过深被否决——用户测试中60%的参与者无法在3步内找到核心功能。</p>
  </div>
  <div class="process-visual">
    <img src="assets/case-wireframe.jpg" alt="Wireframe方案对比">
  </div>
</div>
```

```css
.process-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--sp-8);
  align-items: center;
  margin: var(--sp-10) 0;
}
.process-row--image-right .process-visual { order: 2; }
.process-visual {
  border-radius: var(--r-lg);
  overflow: hidden;
  box-shadow: var(--shadow-md);
  background: #fff;
}
.process-visual img { width: 100%; display: block; }
.process-text .phase-label {
  font-size: 0.6875rem; font-weight: 600;
  letter-spacing: 0.15em; text-transform: uppercase;
  color: var(--gold); display: block; margin-bottom: var(--sp-2);
}
.process-text h3 {
  font-family: var(--font-serif); font-size: 1.35rem;
  font-weight: 700; color: var(--royal); margin-bottom: var(--sp-3);
}
.process-text p {
  font-size: 1rem; line-height: 1.7; color: var(--ink-100);
  margin-bottom: var(--sp-3);
}
.text-wine { color: var(--wine) !important; font-weight: 500; }
```

- 交错瀑布流是Case Study过程区的核心布局模式
- 奇数行图左文右，偶数行文左图右，形成节奏感
- 酒红色文字标记关键决策点/失败原因
- 图片宽度占半栏，文字宽度控制在舒适阅读范围内

### 6.4 不推荐组件

| 组件 | 不推荐原因 |
|------|-----------|
| `countdown`（倒计时） | 营销紧迫感组件，Case Study不需要 |
| `price-table` | 无数价格对比场景 |
| `filter-tabs` | 单篇案例不需要筛选功能 |
| `card-testimonial`（卡片式推荐） | 推荐语用pull-quote更合适，卡片式太轻量 |
| `progress`（技能进度条） | 与案例叙事无关 |
| `btn-cta`（酒红按钮）频繁使用 | CTA只在结尾出现1-2次，不要在正文中频繁打断阅读 |

---

## 7. 特殊注意事项

### 7.1 必须有过程图，不仅是最终效果图（铁律）

这是Case Study与Portfolio作品展示最本质的区别。过程图包括但不限于：

| 过程图类型 | 说明 | 示例 |
|-----------|------|------|
| **草图/手绘** | 纸面草图、白板照片、手绘wireframe | 初始想法的快速可视化 |
| **情绪板/Moodboard** | 视觉方向探索的参考图拼贴 | 展示设计灵感来源 |
| **Wireframe/线框图** | 黑白线框、信息架构图 | 展示布局和结构思考 |
| **探索稿/被否方案** | 做了但没选的方向 | 展示思考广度和决策过程 |
| **迭代对比** | 同一设计的不同版本并排 | 展示迭代优化过程 |
| **用户测试照片/记录** | 用户测试现场照片、热力图、记录 | 证明设计决策有据可依 |
| **流程图/架构图** | 用户旅程图、信息架构图、系统图 | 展示系统性思考 |
| **标注图** | 最终稿上的细节标注（金色标注线） | 展示设计细节考量 |

> **铁律**：过程图数量应不少于最终效果图数量。如果一个Case Study只有最终漂亮的mockup而没有任何过程图，它就不是Case Study，只是作品展示。

### 7.2 结果必须有数据佐证

结果区域不能只写"获得了客户好评"、"用户反馈良好"这类无数据的结论。必须有至少2-3个可量化的数据点：

**好的数据示例**：
- "注册转化率从2.3%提升到3.4%（+47.8%）"
- "用户完成核心任务的平均时间从87秒降低到32秒"
- "上线首月新增用户12,000人，客户复购率提升至38%"
- "NPS从32分提升至58分"
- "客服相关咨询量下降40%"
- "获得Awwwards SOTD提名，页面上线首周访问量突破20万"

**不好的表述**：
- "用户体验大幅提升" → 提升了多少？怎么衡量的？
- "获得了客户的高度认可" → 客户原话是什么？
- "设计效果显著" → 什么效果？数字呢？

**数据获取建议**：
- 设计过程中就与客户/产品团队约定数据追踪指标
- 上线后2-4周收集数据，再写Case Study
- 如果确实无法获取精确数据，用客户的直接引语替代（标注姓名和职位）

### 7.3 必须有反思/Learnings体现深度

反思部分是Case Study的"文眼"，体现设计师的成长思维和专业深度。每个案例至少写2-3条Learning：

**好的反思示例**：
- "如果重来一次，我会在wireframe阶段就邀请开发人员参与评审——这次有3个交互方案因为技术实现成本过高而被迫修改，浪费了2周时间。"
- "过于追求视觉完美让我们忽视了低端设备的性能问题——首屏3MB的hero图在4G网络下加载超过5秒，后来我们做了响应式图片优化。"
- "早期用户测试只覆盖了年轻用户，导致我们忽视了中老年用户的字体大小需求——好的设计不是让目标用户满意，而是不让任何用户被排除。"

**不好的反思**：
- "这次合作很愉快，学到了很多" → 学到了什么？具体的。
- "团队配合很好，客户很满意" → 这是总结不是反思。
- "设计还有提升空间" → 废话，什么设计没有提升空间？

**反思写作原则**：
- 诚实面对不足和错误，不要把反思写成"自夸大会"
- 每条Learning有具体的事件/决策作为支撑
- 说"如果重来会怎么做"而不是"我们本来可以做得更好"
- 可放在深色面板(L13)中，用金色序号01/02/03排列，形成视觉和内容的双重收尾

### 7.4 图片可溢出容器制造画册感（L16风格）

Case Study允许并鼓励关键图片突破容器宽度限制，像画册一样"出血"展示：

```css
/* 画册式溢出图片 */
.bleed-image {
  width: min(1400px, 100vw);
  margin-left: calc((min(1400px, 100vw) - 100%) / -2);
  border-radius: 0;
  overflow: hidden;
}
.bleed-image img { width: 100%; display: block; }

/* 全屏出血 */
.bleed-full {
  width: 100vw;
  margin-left: calc(-50vw + 50%);
  border-radius: 0;
}
```

- L16画册溢出式用于：最终方案主视觉、最有冲击力的过程图、项目封面
- 不要每张图都溢出——一个Case Study中3-5张出血图即可，过多会降低冲击力
- 出血图不加圆角（`border-radius: 0`），保持边缘齐整
- 出血图之间用普通图片和文字交替，形成"紧-松-紧"的视觉节奏

### 7.5 长文阅读体验优化

Case Study文字量较大，必须注意长阅读体验：

1. **正文宽度严格控制**：680px最大宽度，居中或偏左
2. **行高1.8**：比普通网页（1.6）更宽松，长阅读眼睛不疲劳
3. **段落间距大**：`margin-bottom: 1.5em`，避免大段文字堆叠
4. **章节间有视觉呼吸**：每个大章节之间留 `margin: 4rem 0` 以上间距
5. **小标题频繁出现**：每2-3段有一个小标题或金色标签，给读者"进度感"
6. **首屏不要大段文字**：首屏Hero以视觉为主，文字从概览区开始
7. **引用块/数据块打散长文**：每3-4段文字插入一个pull-quote、stat-card组或图片，避免阅读疲劳
8. **滚动阅读进度条**（P2）：顶部2px高的金色进度条，显示当前阅读位置

### 7.6 导航与面包屑

Case Study页面的导航比Portfolio更需要**上下文感知**：

```html
<nav class="navbar case-navbar">
  <a href="index.html" class="nav-logo">飞鸿<span class="gold-dot">.</span></a>
  <div class="breadcrumb">
    <a href="index.html#works">作品</a>
    <span class="breadcrumb-sep">/</span>
    <span class="breadcrumb-current">品牌重塑项目</span>
  </div>
  <a href="index.html#contact" class="btn btn-cta btn-sm">联系我</a>
</nav>
```

- 面包屑导航：`首页 > 作品 > 项目名`，让读者知道自己在哪
- 底部必须有上下篇导航：`← 上一个项目` / `下一个项目 →`
- "返回作品集"按钮始终可见
- 顶部导航可随页面滚动显示阅读进度条（P2）

### 7.7 移动端适配要点

1. **L11交错瀑布流改为单列**：移动端不再左右交错，改为图上文下堆叠
2. **L16溢出图片保持全屏宽**：移动端出血图效果更好，直接100vw
3. **元信息网格改为2列**：Client/Role/Duration等meta-item改为2列排列
4. **数据卡片改为2列**：stat-card移动端2列排列，数字字号适当缩小
5. **时间线左侧间距缩小**：`padding-left: 50px`，序号字号适当缩小
6. **正文宽度使用padding**：移动端正文区域左右各16-20px padding
7. **大引文内边距缩小**：移动端pull-quote padding减小，避免过多空白
8. **首屏不使用100vh**：使用 `min-height: 75vh`，避免浏览器地址栏问题

---

## 8. 场景专属 Checklist

在交付任何 Case Study / 项目复盘页面之前，必须通过以下检查：

### P0 — 必须通过（缺一不可，直接影响案例质量）

- [ ] **有完整叙事结构**：背景 → 挑战 → 过程 → 结果 → 反思，五个叙事环节清晰可辨
- [ ] **有过程图不仅是效果图**：草图/wireframe/探索稿/迭代图等过程图数量不少于最终效果图
- [ ] **结果有数据佐证**：至少2-3个可量化数据点（含具体数字和单位），不是模糊的"好评""显著提升"
- [ ] **项目名使用超大衬线正体**：h1为Playfair Display normal（非斜体），字号≥clamp(2.5rem,7vw,5rem)
- [ ] **元信息使用eyebrow+caption风格**：客户/周期/角色等标签11px金色全大写，值16px墨黑
- [ ] **三种品牌色严格为 `#0A2463` / `#F4D35E` / `#D8315B`**
- [ ] **正文行高1.8、宽度≤680px**，长阅读舒适
- [ ] **首屏使用L4全屏视觉或L3分屏**，以项目视觉为主角
- [ ] **设计过程区使用L11交错瀑布流或L12时间线**，图文交替展示
- [ ] **结尾有反思/Learnings**：至少2条具体的、诚实的反思，不是泛泛而谈
- [ ] **衬线+无衬线混搭**：标题Playfair Display，正文Inter，引言Cormorant Garamond italic
- [ ] **页面背景为暖米白 `#FDFBF6`**
- [ ] **有客户评价或关键洞察pull-quote**
- [ ] **底部有上/下项目导航**，方便读者继续浏览
- [ ] **响应式适配**：移动端单列，图片全宽，字号可读

### P1 — 应该通过（尽量满足，影响质感和专业度）

- [ ] **有客户引言**：pull-quote标注客户姓名+职位，用真实引语
- [ ] **过程区展示了被否决的方案**：诚实地说明为什么某些方向没被选择
- [ ] **图片有图注说明**：重要图片配有caption（金色序号+说明文字）
- [ ] **数据有before/after对比**：不仅说"提升了X"，还说明"从Y提升到X"
- [ ] **反思区使用L13深色面板**：深蓝背景+白色文字+金色序号，形成视觉和内容的双重收尾
- [ ] **关键图片溢出容器（L16画册感）**：3-5张出血图，制造画册翻页感
- [ ] **设计过程分阶段**：有明确的阶段标签（RESEARCH/CONCEPT/ITERATE/FINAL等）
- [ ] **金色用于信息标记（标签/序号/数据）**而非大面积装饰
- [ ] **酒红用于标注挑战点和关键成果**，一屏不超过2-3处
- [ ] **每个大section版式不同**：不连续使用两个相同布局
- [ ] **有Scroll Reveal入场动画**，轻、慢、克制
- [ ] **选中文本背景为金色**：`::selection { background: var(--gold); color: var(--royal); }`
- [ ] **有面包屑导航**或清晰的返回作品集路径

### P2 — 加分项（锦上添花，提升专业度）

- [ ] **图片溢出画册感**：L16出血图恰到好处，不是每张图都溢出
- [ ] **深色面板打破阅读节奏**：在长文中穿插1-2次深色背景引文或数据区
- [ ] **阅读进度条**：顶部2px金色进度条显示阅读位置
- [ ] **Before/After滑块**：可拖动比较新旧版本（image-compare组件）
- [ ] **设计稿上有金色标注线**：标注设计细节和决策点
- [ ] **首字下沉**：背景章节第一段使用drop cap增加画册感
- [ ] **JetBrains Mono等宽字体用于代码/标注/序号**：技术感细节
- [ ] **相关案例推荐**：结尾推荐2-3个相关项目
- [ ] **可分享链接/按钮**：方便读者分享案例
- [ ] **图片懒加载**：长页面性能优化
- [ ] **打印样式优化**：案例研究常被打印，确保打印效果良好（隐藏导航/CTA，文字黑色）

### 交付前自检三问

1. **这是一个"故事"还是"作品集"？**：读者能从背景跟随你的思路走到结果吗？还是只是漂亮图片的堆砌？
2. **过程足够透明吗？**：看到草图、失败的尝试、决策推演了吗？还是只有完美的最终稿？
3. **结果可信吗？**：有数据、有客户反馈支撑吗？还是只有自说自话的"效果显著"？

---

## 附录：Case Study 页面快速模板骨架

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>项目名称 · 飞鸿设计</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400;1,600&family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  <style>
    :root {
      --royal: #0A2463; --gold: #F4D35E; --wine: #D8315B;
      --cream: #FDFBF6; --ink: #0D1225;
      --royal-50: #EEF1FA; --gold-200: #FAEBA3;
      --ink-100: #2C3347; --ink-200: #4C546A; --ink-300: #6D7487;
      --cream-100: #F8F4EB; --cream-200: #F0EAD9;
      --font-serif: 'Playfair Display', 'Noto Serif SC', Georgia, serif;
      --font-sans: 'Inter', 'Noto Sans SC', -apple-system, sans-serif;
      --font-display: 'Cormorant Garamond', 'Noto Serif SC', Georgia, serif;
      --font-mono: 'JetBrains Mono', 'Fira Code', monospace;
      --r-lg: 12px; --r-xl: 20px;
      --sp-1: 0.25rem; --sp-2: 0.5rem; --sp-3: 0.75rem; --sp-4: 1rem;
      --sp-5: 1.5rem; --sp-6: 2rem; --sp-8: 3rem; --sp-10: 5rem;
      --shadow-md: 0 4px 16px rgba(10,36,99,0.10);
      --shadow-lg: 0 8px 32px rgba(10,36,99,0.12);
      --ease: cubic-bezier(0.16, 1, 0.3, 1);
      --container: min(1100px, 92vw);
      --reading: 680px;
    }
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; -webkit-text-size-adjust: 100%; }
    body {
      font-family: var(--font-sans); font-size: 1.0625rem;
      background: var(--cream); color: var(--ink-100);
      line-height: 1.8; -webkit-font-smoothing: antialiased;
    }
    ::selection { background: var(--gold); color: var(--royal); }
    .container { max-width: var(--container); margin: 0 auto; padding: 0 var(--sp-4); }
    .reading { max-width: var(--reading); margin: 0 auto; }

    /* Navbar */
    .navbar {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: var(--sp-3) clamp(var(--sp-4), 4vw, var(--sp-8));
      background: rgba(253,251,246,0.9); backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--cream-200);
    }
    .nav-logo { font-family: var(--font-serif); font-size: 1.4rem; font-weight: 700; color: var(--royal); text-decoration: none; }
    .nav-logo .gold-dot { color: var(--gold); }
    .breadcrumb { font-size: 0.8125rem; color: var(--ink-300); }
    .breadcrumb a { color: var(--ink-200); text-decoration: none; }
    .breadcrumb a:hover { color: var(--royal); }
    .breadcrumb-sep { margin: 0 var(--sp-2); color: var(--cream-200); }
    .btn {
      display: inline-flex; align-items: center; gap: 0.5rem;
      font-family: var(--font-sans); font-size: 0.875rem; font-weight: 500;
      padding: 0.5rem var(--sp-4); border-radius: 8px; border: none;
      cursor: pointer; text-decoration: none; transition: all 0.2s; white-space: nowrap;
    }
    .btn-cta { background: var(--wine); color: #fff; }
    .btn-cta:hover { background: #AD2749; transform: translateY(-1px); }

    /* === ① Hero L4 全屏视觉 === */
    .hero-l4 {
      position: relative; height: 85vh; min-height: 500px;
      display: flex; align-items: flex-end;
      background: var(--ink); overflow: hidden;
    }
    .hero-l4 img {
      position: absolute; inset: 0; width: 100%; height: 100%;
      object-fit: cover; opacity: 0.7;
    }
    .hero-l4 .hero-overlay {
      position: absolute; inset: 0;
      background: linear-gradient(to top, rgba(13,18,37,0.9) 0%, rgba(13,18,37,0.2) 50%, transparent 100%);
    }
    .hero-l4 .hero-content {
      position: relative; z-index: 2;
      padding: 0 clamp(var(--sp-4), 6vw, var(--sp-10)) var(--sp-10);
      max-width: 900px;
    }
    .hero-eyebrow {
      font-size: 0.75rem; font-weight: 500; letter-spacing: 0.2em;
      text-transform: uppercase; color: var(--gold);
      display: block; margin-bottom: var(--sp-4);
    }
    .hero-title {
      font-family: var(--font-serif); font-size: clamp(2.5rem, 7vw, 5rem);
      font-weight: 900; font-style: normal; line-height: 1.05;
      color: #fff; letter-spacing: -0.02em; margin-bottom: var(--sp-3);
    }
    .hero-sub { font-size: 1rem; color: rgba(255,255,255,0.7); }

    /* === Section 通用 === */
    section { padding: var(--sp-10) 0; }
    .phase-label {
      font-size: 0.6875rem; font-weight: 600; letter-spacing: 0.15em;
      text-transform: uppercase; color: var(--gold); display: block; margin-bottom: var(--sp-2);
    }
    h2 {
      font-family: var(--font-serif); font-size: clamp(1.5rem, 3vw, 2.25rem);
      font-weight: 700; color: var(--ink); line-height: 1.2; margin-bottom: var(--sp-6);
    }
    h3 {
      font-family: var(--font-serif); font-size: 1.25rem;
      font-weight: 700; color: var(--royal); margin-bottom: var(--sp-3);
    }
    p { margin-bottom: var(--sp-4); }

    /* === ② Meta Grid === */
    .meta-grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
      gap: var(--sp-5); padding: var(--sp-6) 0;
      border-top: 1px solid var(--cream-200); border-bottom: 1px solid var(--cream-200);
    }
    .meta-label {
      font-size: 0.6875rem; font-weight: 600; letter-spacing: 0.15em;
      text-transform: uppercase; color: var(--gold); display: block; margin-bottom: var(--sp-1);
    }
    .meta-value { font-size: 1rem; font-weight: 500; color: var(--ink); }

    /* === ④ Process Row (L11 交错) === */
    .process-row {
      display: grid; grid-template-columns: 1fr 1fr;
      gap: var(--sp-8); align-items: center; margin: var(--sp-10) 0;
    }
    .process-row--image-right .process-visual { order: 2; }
    .process-visual { border-radius: var(--r-lg); overflow: hidden; box-shadow: var(--shadow-md); background: #fff; }
    .process-visual img { width: 100%; display: block; }

    /* === Stat Card === */
    .stat-grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: var(--sp-4); padding: var(--sp-6) 0;
    }
    .stat-card { text-align: center; padding: var(--sp-5); background: #fff; border-radius: var(--r-lg); border: 1px solid var(--cream-200); }
    .stat-value { font-family: var(--font-serif); font-size: clamp(2rem, 4vw, 3rem); font-weight: 700; line-height: 1; display: block; margin-bottom: var(--sp-2); }
    .stat-label { font-size: 0.8125rem; color: var(--ink-300); }

    /* === Pull Quote === */
    .case-quote {
      position: relative; padding: var(--sp-8) var(--sp-6); margin: var(--sp-10) 0;
      text-align: center; background: var(--cream-100); border-radius: var(--r-xl);
    }
    .case-quote::before {
      content: '"'; font-family: var(--font-display); font-size: 5rem;
      color: var(--gold); opacity: 0.3; position: absolute;
      top: -0.1em; left: 50%; transform: translateX(-50%); line-height: 1;
    }
    .case-quote p {
      font-family: var(--font-display); font-size: clamp(1.25rem, 2.5vw, 1.75rem);
      font-style: italic; color: var(--royal); line-height: 1.5; max-width: 600px; margin: 0 auto;
    }
    .case-quote cite { display: block; font-size: 0.8125rem; font-style: normal; color: var(--ink-300); margin-top: var(--sp-3); }

    /* === Bleed Image (L16) === */
    .bleed-image { width: 100vw; margin-left: calc(-50vw + 50%); overflow: hidden; }
    .bleed-image img { width: 100%; display: block; }

    /* === Dark Panel (L13 反思) === */
    .dark-panel {
      background: linear-gradient(135deg, var(--royal), #061540);
      color: #fff; padding: var(--sp-10) var(--sp-4); margin: var(--sp-10) 0;
    }
    .dark-panel h2 { color: #fff; }
    .dark-panel .phase-label { color: var(--gold); }
    .learning-item { margin-bottom: var(--sp-6); padding-left: var(--sp-8); position: relative; }
    .learning-num {
      font-family: var(--font-display); font-size: 2rem; font-style: italic;
      color: var(--gold); position: absolute; left: 0; top: -0.3em;
    }
    .learning-item p { color: rgba(255,255,255,0.8); font-size: 1rem; line-height: 1.7; }

    /* === Post Nav === */
    .post-nav { display: flex; justify-content: space-between; padding: var(--sp-8) 0; border-top: 1px solid var(--cream-200); }
    .post-nav a { font-family: var(--font-serif); font-size: 1.1rem; color: var(--royal); text-decoration: none; }
    .post-nav a:hover { color: var(--wine); }

    /* === Responsive === */
    @media (max-width: 768px) {
      .process-row { grid-template-columns: 1fr; gap: var(--sp-4); }
      .process-row--image-right .process-visual { order: 0; }
      .hero-l4 { height: 75vh; }
      .breadcrumb { display: none; }
    }
    @media (prefers-reduced-motion: reduce) { html { scroll-behavior: auto; } }
  </style>
</head>
<body>
  <!-- Navbar -->
  <nav class="navbar">
    <a href="index.html" class="nav-logo">飞鸿<span class="gold-dot">.</span></a>
    <div class="breadcrumb"><a href="index.html#works">作品</a><span class="breadcrumb-sep">/</span><span>项目名称</span></div>
    <a href="index.html#contact" class="btn btn-cta btn-sm">联系我</a>
  </nav>

  <!-- ① Hero L4 全屏视觉 -->
  <section class="hero-l4">
    <img src="assets/case-hero.jpg" alt="项目封面">
    <div class="hero-overlay"></div>
    <div class="hero-content">
      <span class="hero-eyebrow">Client: 某科技公司 · 2025 · Brand Identity</span>
      <h1 class="hero-title">品牌重塑项目</h1>
      <p class="hero-sub">从传统到现代的品牌视觉升级</p>
    </div>
  </section>

  <!-- ② 项目概览 -->
  <section>
    <div class="container">
      <div class="reading">
        <p>项目摘要：简述项目背景、你的角色和核心成果。1-3句话讲清楚"做了什么"。</p>
      </div>
      <div class="meta-grid">
        <div class="meta-item"><span class="meta-label">Client</span><span class="meta-value">某科技公司</span></div>
        <div class="meta-item"><span class="meta-label">Role</span><span class="meta-value">品牌设计主导</span></div>
        <div class="meta-item"><span class="meta-label">Duration</span><span class="meta-value">2024.09 — 2025.01</span></div>
        <div class="meta-item"><span class="meta-label">Team</span><span class="meta-value">3人设计团队</span></div>
        <div class="meta-item"><span class="meta-label">Deliverables</span><span class="meta-value">Logo/VI/网站/包装</span></div>
      </div>
    </div>
  </section>

  <!-- ③ 背景与挑战 -->
  <section style="background:var(--cream-100);">
    <div class="container">
      <div class="reading">
        <span class="phase-label">Background</span>
        <h2>背景与挑战</h2>
        <p>详细描述项目背景：客户是谁、行业现状、为什么需要这个项目。</p>
        <p>核心挑战：1-3个关键设计挑战是什么？</p>
        <p style="color:var(--wine);font-weight:500;">核心挑战：如何在保留品牌10年积累的认知资产的同时，实现面向年轻用户的现代化转型？</p>
      </div>
    </div>
  </section>

  <!-- ④ 设计过程 -->
  <section>
    <div class="container">
      <span class="phase-label" style="text-align:center;display:block;">Process</span>
      <h2 style="text-align:center;">设计过程</h2>

      <div class="process-row process-row--image-left">
        <div class="process-visual"><img src="assets/case-sketch.jpg" alt="草图"></div>
        <div class="process-text">
          <span class="phase-label">Phase 01 · Research</span>
          <h3>研究与洞察</h3>
          <p>描述研究过程和发现的关键洞察。</p>
        </div>
      </div>

      <div class="process-row process-row--image-right">
        <div class="process-visual"><img src="assets/case-wireframe.jpg" alt="线框图"></div>
        <div class="process-text">
          <span class="phase-label">Phase 02 · Concept</span>
          <h3>概念探索</h3>
          <p>描述概念发散过程和方向选择。</p>
          <p style="color:var(--wine);font-weight:500;">方向C因与竞品过于相似被否决。</p>
        </div>
      </div>

      <div class="process-row process-row--image-left">
        <div class="process-visual"><img src="assets/case-iterate.jpg" alt="迭代"></div>
        <div class="process-text">
          <span class="phase-label">Phase 03 · Iteration</span>
          <h3>迭代与决策</h3>
          <p>描述迭代过程和关键设计决策。</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ⑤ 最终方案 (L16 画册溢出) -->
  <div class="bleed-image">
    <img src="assets/case-final.jpg" alt="最终方案">
  </div>

  <!-- ⑥ 结果与数据 -->
  <section>
    <div class="container">
      <span class="phase-label" style="text-align:center;display:block;">Result</span>
      <h2 style="text-align:center;">结果与数据</h2>

      <div class="case-quote">
        <p>"新版品牌上线后，我们的品牌认知度调研得分提升了23个百分点。"</p>
        <cite>—— 市场总监，某科技公司</cite>
      </div>

      <div class="stat-grid">
        <div class="stat-card"><span class="stat-value" style="color:var(--wine)">+47%</span><span class="stat-label">转化率提升</span></div>
        <div class="stat-card"><span class="stat-value" style="color:var(--gold)">NPS 58</span><span class="stat-label">用户净推荐值（原32）</span></div>
        <div class="stat-card"><span class="stat-value">20w+</span><span class="stat-label">首周访问量</span></div>
        <div class="stat-card"><span class="stat-value">-40%</span><span class="stat-label">客服咨询量下降</span></div>
      </div>
    </div>
  </section>

  <!-- ⑦ 反思 (L13 深色面板) -->
  <section class="dark-panel">
    <div class="container">
      <div class="reading">
        <span class="phase-label">Learnings</span>
        <h2>反思与收获</h2>
        <div class="learning-item">
          <span class="learning-num">01</span>
          <p>具体的反思内容。诚实面对做得不够好的地方，说明如果重来会怎么做。</p>
        </div>
        <div class="learning-item">
          <span class="learning-num">02</span>
          <p>第二条反思。从项目中学到的关键lesson，有具体事件支撑。</p>
        </div>
        <div class="learning-item">
          <span class="learning-num">03</span>
          <p>第三条反思。可以是关于设计流程、团队协作或客户沟通的insight。</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ⑧ 导航 -->
  <section style="padding-top:0;">
    <div class="container">
      <div class="post-nav">
        <a href="#">← 上一个项目</a>
        <a href="index.html#works">返回作品</a>
        <a href="#">下一个项目 →</a>
      </div>
    </div>
  </section>
</body>
</html>
```

---

## 场景定位

案例研究/项目复盘是以叙事方式完整呈现一个设计项目从问题到结果的深度内容页面，用于展示设计思考过程、解决问题的能力和专业深度。适用于：作品集项目详情页、设计博客案例复盘、客户提案案例展示、设计课程教学案例。不适用于：作品展示画廊（用Portfolio网格）、营销页面（用Landing）、教程文档（用Tutorial）。核心原则是"讲故事"——让读者跟随你的思路从背景走到结果，过程透明、数据可信、反思诚实，像翻一本设计画册。

## 推荐节奏（Section 序列）

### 方案 A：品牌设计案例型（10-12屏）
1. Hero（L4 全屏视觉）— 最终品牌主视觉全屏+项目名+客户标签，视觉冲击开场
2. 项目概览（L15双栏对比）— 左栏摘要+右栏元信息（客户/周期/角色/交付物）
3. 背景（L5左图右文 / L7单栏）— 客户背景、市场现状、旧品牌问题
4. 挑战与目标（L15双栏）— 左栏"挑战"酒红标注，右栏"目标"金色标注
5. 研究与洞察（L11交错瀑布流）— 用户研究、竞品分析、关键发现
6. 概念探索（L11交错）— 草图、情绪板、方向探索（展示被否方案）
7. 设计迭代（L12时间线 / L11交错）— 版本演进、关键决策点
8. 最终方案（L16画册溢出 + L10 Bento网格）— 主视觉溢出+应用场景mockup
9. 结果与数据（L14数据条 + L8引文）— 数据成果+客户评价
10. 反思（L13深色面板）— Learnings金色序号，深蓝底白字
11. 导航（上下篇+返回作品集）

### 方案 B：UI/UX产品案例型（12屏，过程更重）
1. Hero（L4全屏视觉）— 产品最终界面全屏
2. 概览+数据预览（L15+L14）— 元信息+核心数据预告
3. 用户痛点（L7单栏长文+数据支撑）— 首字下沉可选
4. 挑战vs目标（L15双栏）
5. 用户研究（L11交错）— 用户画像、旅程图、访谈洞察
6. 信息架构（L9全宽图+文字）— IA图、流程图
7. 设计探索（L11交错）— Wireframe多方案对比
8. 迭代过程（L12时间线）— 版本→测试→版本循环
9. 最终设计（L16溢出+L10 Bento）— 核心界面+设计系统
10. 成果数据（L14数据条+L8用户引言）— 转化率/满意度/任务完成率
11. 反思（L13深色面板）
12. 导航+相关案例

### 方案 C：精简案例型（6-8屏，适合作品集中快速浏览）
1. Hero（L4全屏视觉）
2. 概览（L7简短摘要+元信息）
3. 挑战（L8引文深色，一句话核心问题）
4. 过程精华（L11交错3-4组）— 精选最关键的过程图
5. 最终方案（L16画册溢出+L10网格精简版）
6. 结果（L14数据条3-4个数字）
7. 反思（简短L7段落）
8. 导航

### 方案 D：技术实现案例型（含代码，10屏+）
1. Hero（L4/L2）— 项目名+技术栈标签
2. 概览（L15双栏）— 摘要+技术元信息
3. 问题背景（L7单栏长文）— 技术挑战描述
4. 架构方案（L5图文）— 架构图+技术选型理由
5. 实现过程（L11交错+代码块）— 图文+#06 Terminal Code Block
6. 关键代码（L7长文+多代码块）— 核心代码片段讲解
7. 性能/结果（L14数据条）— 性能指标对比
8. 踩坑记录（L9三列/L7列表）— 酒红标注问题+解决方案
9. 反思（L13深色面板）
10. 导航+源码链接

## 专属装饰手法（Signature Touches）

- **#21 Drop Cap 首字下沉**：背景章节第一段可使用首字下沉，增加画册和书卷气
- **#20 Numbered Index 编号索引**：过程阶段用金色等宽序号（01/02/03）标注，图注用金色等宽数字标记
- **#04 Pull Quote 金句引用**：客户评价用Cormorant斜体引文块，可浅可深，必须标注客户姓名+职位
- **#15 Divider 分隔线**：大章节之间用金色渐变细线分隔，不要使用hr默认样式
- **#06 Terminal Code Block 终端代码块**：技术案例中代码块使用墨黑底+金色左边框+JetBrains Mono
- **#16 Alert Box 提示框**：过程中可用金色WARNING框标注决策点，酒红IMPORTANT框标注失败教训
- **#14 Section Marker 章节标记**：每个大阶段（Research/Concept/Iterate/Final）用大号phase-label（金色全大写小字）
- **#09 Fleuron 花饰**：章节过渡处可用❦装饰，但比教程场景更克制
- **#03 Image Frame 图片画框**：过程图加白色背景+圆角+柔和阴影，最终效果图可加1px金色边框
- **#11 Ornamental Corner 角饰**：Hero区域和最终方案展示区可用金色角饰增强正式感
- **#05 Highlight 荧光笔高亮**：正文中的关键决策点、核心数据可用金色荧光笔标记
- **图注编号**：每张重要图片配caption，用JetBrains Mono金色序号（如"01"）+斜体说明文字

## 推荐布局组合

| 布局 | 名称 | 适用位置 | 说明 |
|------|------|----------|------|
| **L4** | 全屏视觉Hero | 首屏（必选） | 最终方案大图全屏+渐变遮罩+白色项目名 |
| **L15** | 双栏对比 | 概览/挑战vs目标 | 左右对比结构，信息密度高 |
| **L5/L6** | 左图右文/左文右图 | 过程区核心 | L11交错瀑布流的基本单元 |
| **L11** | 交错瀑布流 | 设计过程区（必选） | 图文左右交替，叙事节奏的核心布局 |
| **L12** | 时间线 | 迭代过程/里程碑 | 皇家蓝连线+金色节点，展示时间序列 |
| **L16** | 画册溢出式 | 最终方案主视觉 | 关键大图突破容器宽度，画册感高潮 |
| **L10** | Bento网格 | 最终方案多场景展示 | 大小错落的mockup网格 |
| **L14** | 数据统计条 | 结果区（必选） | 3-4个大数字横排展示成果 |
| **L8** | 引文全屏 | 客户评价/关键洞察 | Cormorant斜体金句，视觉停顿 |
| **L13** | 深色面板CTA | 反思区Learnings（必选） | 深蓝底+金色序号+白色文字 |
| **L7** | 单栏长文 | 背景叙述/总结 | 680px行宽，长文阅读舒适 |

## 色彩策略

Case Study场景三色分配，核心原则：色彩服务于叙事节奏，金色用于标记信息，酒红用于标注关键/问题，皇家蓝为主色。

**皇家蓝 #0A2463（55%）—— 主色，专业信任**
- h1/h2/h3所有标题文字颜色
- 过程时间线连线
- 浅色版pull-quote文字颜色
- 导航栏背景
- 数据卡片默认数字颜色
- 图片边框/阴影中的蓝色成分
- 深色面板背景（渐变起始色）
- 正文链接颜色

**复古金 #F4D35E（30%）—— 信息标记与装饰**
- 阶段标签（RESEARCH/CONCEPT等金色全大写）
- 过程序号01/02/03（Cormorant斜体或等宽字体）
- 图注编号（等宽金色）
- 分隔线、装饰线
- 金色大引号（pull-quote的::before）
- 时间线节点圆点
- Hero区eyebrow标签（深色底上）
- 反思区序号（深色面板上的金色数字）
- 数据中最亮眼的数字（如营收数字）
- 高亮关键词（荧光笔效果）
- **白底上金色仅用于标签/序号/线条/短词，不用于大段文字**

**酒红 #D8315B（15%）—— 关键问题与成果**
- 核心挑战标记（"挑战"标签/酒红文字段落）
- 被否决方案的标记
- 关键错误/踩坑标注
- 最重要的成果数据（如+47%转化率）
- Before-After中的After强调
- 核心洞察的高亮
- **酒红在Case Study中标记"需要注意"和"最重要的成果"，克制使用才有力量**

**深色面板节奏**：Hero深色（L4图片遮罩）→ 概览浅色 → 背景浅暖色 → 过程区浅色 → 最终方案大图（自然深色） → 结果浅色 → 反思深色（L13必用）。反思区是全文字唯一的深色面板，形成叙事的视觉收束。数据结果区不用深色，让数据自己说话。

## 场景禁忌（Don'ts）

1. **只有最终效果图没有过程图**：过程图数量不少于最终效果图，否则只是作品展示不是Case Study
2. **结果无数据**："好评如潮""效果显著"是空话，必须有具体数字（转化率提升X%、NPS从Y到Z）
3. **反思写成自夸**："这次合作很愉快学到了很多"不是反思，反思必须诚实面对不足
4. **所有图片整齐等大排列**：必须有尺寸变化——全宽出血图+普通图+小图交替，形成节奏
5. **过程区每步都一样长**：重点步骤详细展开（大图+多段文字），次要步骤一笔带过
6. **酒红和金色滥用**：一屏超过3处酒红或5处金色就太多了，色彩用于标记不是填色
7. **正文宽度超过700px**：长文阅读必须控制在680px内
8. **CTA按钮频繁出现**：Case Study是叙事不是营销，CTA只在结尾出现1-2次
9. **忽略失败的尝试**：展示被否决的方案和错误的决策，这是专业深度的体现
10. **数据放在过程区开头**：数据应集中在结果区，过早展示数据会破坏叙事悬念

## 场景专属Checklist

- [ ] 叙事结构完整：背景→挑战→过程→结果→反思五个环节清晰
- [ ] 过程图数量≥最终效果图数量，包含草图/wireframe/探索稿/迭代图
- [ ] 结果区有2-3个以上可量化数据点（具体数字+单位+before/after对比）
- [ ] 反思区有2-3条具体诚实的Learnings，用L13深色面板+金色序号
- [ ] 至少1张L16画册溢出式大图（最终主视觉/关键过程图）
- [ ] 设计过程区使用L11交错瀑布流，图文左右交替不单调
- [ ] 有客户pull-quote，标注真实姓名+职位（非匿名）
- [ ] 元信息完整：客户/周期/角色/团队/交付物清晰可见
- [ ] 每张重要图片有图注（金色序号+说明文字）
- [ ] 展示了至少1个被否决的方向及其原因
- [ ] 正文宽度≤680px，行高1.8，长阅读舒适
- [ ] 首屏使用L4全屏视觉Hero，以项目最终效果为背景
- [ ] 底部有上一/下一项目导航+"返回作品集"链接
- [ ] 面包屑导航显示当前位置（首页>作品>项目名）
- [ ] 酒红色仅用于核心挑战/关键成果/错误标注，克制使用
- [ ] 金色用于标签/序号/装饰线/高亮，白底上无大段金色文字
- [ ] 移动端L11交错改为单列（图上文下），出血图保持全宽
- [ ] 代码块使用墨黑背景+金色左边框+JetBrains Mono（技术案例）
- [ ] 打印样式友好（@media print隐藏导航/CTA，保留正文和图片）
- [ ] 选中文本背景为金色，无bounce/弹性动画干扰阅读

---

*Scene: Case Study v1.0 · Feihong Design System*
*基于 brand-dna.md v2.0 · 最后更新：2026-07-08*
