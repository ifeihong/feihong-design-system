# Feihong Design System · Scene: Deck
# 飞鸿品牌设计系统 · 场景规范：演示文稿 / 分享页 / Deck

> 本规范定义飞鸿品牌设计系统在「演讲 Slides / 分享 Deck / 在线演示文稿」中的具体应用方式。
> 所有规则建立在 `DNA.md`、`components/14-layouts.md`、`components/` 基础之上，场景专属规则以本文件为准。
> Deck 场景的核心使命是**全屏翻页、一页一观点、投影可读**——不是网页的缩小版，而是为投影和共享屏幕优化的全屏叙事体验。每一页都应该像一张独立的海报，3秒内传递核心信息。

---

## 1. 场景定义

### 适用页面类型

Deck 场景适用于以下以**全屏演示/翻页叙事为核心目标**的内容形态：

| 类型 | 说明 | 典型页数 | 核心目标 |
|------|------|----------|---------|
| **演讲/分享Slides** | 线下/线上会议演讲、设计分享、技术Talk | 20-60页 | 辅助演讲、传递观点、视觉支撑 |
| **在线演示文稿** | 网页版Deck、可分享链接的演示页面 | 10-40页 | 自传播、无需演讲者也能读懂 |
| **项目提案Deck** | 客户提案、Pitch Deck、方案汇报 | 10-30页 | 说服客户、展示方案专业度 |
| **工作坊/培训材料** | 内部培训、设计工作坊引导页 | 15-50页 | 引导流程、辅助教学 |
| **产品发布/发布会** | 产品发布演示、Keynote级展示页 | 15-40页 | 视觉冲击力、记忆点、品牌调性 |

### 场景核心气质

- **全屏沉浸**：16:9全屏展示，无浏览器边框感，像PPT一样翻页
- **一页一观点**：每页只有一个核心信息，不堆砌、不拥挤
- **字号大、对比强**：投影环境光线复杂，文字必须足够大、对比度足够高
- **节奏明快**：每页布局不同，金句页/数据页/图文页交替出现，保持观众注意力
- **品牌感强烈**：皇家蓝深色背景变体是Deck的标志性视觉语言，比网页更大胆

### 场景核心约束

1. **16:9比例固定**：1280x720或1920x1080，所有页面按此比例设计
2. **必须支持键盘翻页**：←/→方向键、空格键翻页，这是Deck的基本交互
3. **字号要大**：标题≥48px，正文≥24px——投影到两米外仍能看清
4. **一页一观点**：每页只传达一个核心信息，宁可多一页也不挤一页
5. **每页布局必须不同**：连续两页相同布局=视觉疲劳=观众走神

---

## 2. 典型页面结构

Deck 采用 **封面页 → 目录/议程 → 内容页（交替布局）→ 金句页 → 数据页 → 总结 → 感谢页/Q&A** 的经典演示结构：

```
┌─────────────────────────────────────────────────────────┐
│  ① 封面页（L2 居中大字 — 首选）                           │
│     - 16:9全屏                                           │
│     - 演讲标题（超大衬线，皇家蓝背景白色文字 或 米白背景）  │
│     - 演讲者名字+身份（金色小字）                         │
│     - 日期/场合（辅助文字）                               │
│     - 可选：品牌Logo/IP形象                               │
│     * 作用：第一印象，定调整场演讲                        │
├─────────────────────────────────────────────────────────┤
│  ② 目录/议程页（L9三列要点 或 L2居中列表）                │
│     - "Agenda" 或 "今天聊什么" 标题                       │
│     - 3-5个议程要点（编号列表）                           │
│     - progress-bar 可选，标记当前进度                     │
│     - 大装饰数字（01/02/03金色）                          │
│     * 作用：让观众知道接下来的节奏                        │
├─────────────────────────────────────────────────────────┤
│  ③ 内容页（交替布局，核心主体，占总页数60-70%）           │
│     - 布局交替使用：                                      │
│       · 左标题右内容（L5变体）                            │
│       · 全图背景+文字叠加（L4变体）                       │
│       · 大引言/金句（L8全屏引文）                         │
│       · 三列要点（L9卡片）                                │
│       · 数据展示（L14数据条变体）                         │
│       · 双栏对比（L15）                                   │
│     - 每页标题在固定位置（左上或顶部居中）                │
│     - 页码在右下角                                       │
│     * 作用：演讲主体内容，一页一观点                      │
├─────────────────────────────────────────────────────────┤
│  ④ 金句页（L8 全屏引文 — 穿插使用）                       │
│     - 整页只有一句话                                      │
│     - Cormorant斜体超大字                                 │
│     - 皇家蓝深色背景+白色/金色文字 或 米白背景+皇家蓝文字  │
│     - 金色大引号装饰                                      │
│     - 每10-15页出现一次，给观众"呼吸"和"拍照"的机会       │
│     * 作用：强调核心观点、制造记忆点、打破节奏            │
├─────────────────────────────────────────────────────────┤
│  ⑤ 数据页（L14 数据条 / stat-card 大字）                  │
│     - 1-3个核心数据超大展示                               │
│     - 数字用Playfair Display 72-120px                    │
│     - 数据标签用Inter小字说明                              │
│     - 酒红/金色标注关键数字                               │
│     * 作用：用数据说话，最有说服力的页面类型              │
├─────────────────────────────────────────────────────────┤
│  ⑥ 总结页（L9 三列要点 或 L2 居中）                       │
│     - "Key Takeaways" / "总结"                           │
│     - 3个核心要点回顾                                     │
│     - 大编号+简短文字                                     │
│     * 作用：强化记忆，收束内容                            │
├─────────────────────────────────────────────────────────┤
│  ⑦ 感谢页/Q&A（L2 居中大字）                              │
│     - "Thank You" / "谢谢" / "Q&A" 超大字                │
│     - 联系方式（邮箱/社交/二维码）                        │
│     - 可选：IP形象/品牌签名                               │
│     * 作用：优雅收尾，促成后续联系                        │
└─────────────────────────────────────────────────────────┘
```

### 结构要点

1. **封面和感谢页首尾呼应**：可使用相似的视觉元素（如相同背景、相同排版），形成闭环
2. **每10-15页插入一个金句页**：这是观众的"呼吸点"，也是最常被拍照分享的页面
3. **议程页可在每个大章节前重复**：高亮当前章节，给观众进度感（类似progress-bar）
4. **内容页布局必须交替**：左图右文 → 全图 → 三列 → 大引文 → 左文右图 → 数据 → ...
5. **结尾Q&A页放联系方式**：这是观众最后看到的页面，确保联系方式清晰可见
6. **总页数控制**：演讲按每页1-2分钟估算，30分钟演讲=15-30页

---

## 3. 色彩使用指南

Deck 场景是飞鸿品牌色最大胆的应用场景——**皇家蓝深色背景是Deck的标志性变体**，金色承担比网页更重要的装饰和强调职能，酒红用于关键数据和重点标注。

### 3.1 皇家蓝 `#0A2463`（50%）— 主导色与深色背景

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **深色页面背景** | 封面、金句页、数据页、感谢页的背景 | **Deck最具辨识度的特征**，皇家蓝深蓝径向渐变 |
| **标题文字**（浅色页） | 米白页面上的标题文字 | Playfair Display 皇家蓝粗体 |
| **装饰线/边框** | 内容分隔线、卡片边框、图片边框 | 皇家蓝细线 |
| **页码装饰** | 页码数字旁的装饰线/方块 | 皇家蓝小方块+金色页码 |
| **导航指示** | 翻页提示、进度指示 | 皇家蓝半透明元素 |
| **章节标记** | 大章节扉页的皇家蓝底色块 | 整页或半页皇家蓝 |

> **Deck场景特殊规则**：与网页场景不同，Deck允许并鼓励大面积使用皇家蓝作为页面背景（深色变体），这是Deck场景的标志性视觉语言。深色背景上的文字必须用白色或金色，确保投影对比度。

### 3.2 复古金 `#F4D35E`（30%）— 强调、页码、装饰

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **页码** | 右下角页码数字 | Cormorant斜体金色，是每页必现的品牌签名 |
| **装饰数字** | 议程编号、要点编号、章节序号 | 超大金色数字（01/02/03），Cormorant斜体 |
| **强调文字** | 金句中的关键词、数据中的核心数字 | 金色关键词在深蓝背景上最醒目 |
| **装饰元素** | 大引号、装饰线、角落装饰、分隔符 | 金色细节提升品质感 |
| **标题点缀** | 标题后的金色句号/装饰点 | 品牌签名细节 |
| **进度条** | progress-bar填充色 | 金色进度在皇家蓝底上 |
| **高亮关键词** | 正文中需要强调的1-2个词 | 金色加粗，不超过每页2处 |
| **CTA/联系方式** | 感谢页的邮箱/社交链接 | 金色文字在深蓝背景上清晰可见 |

### 3.3 酒红 `#D8315B`（20%）— 重点标注与关键数据

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **关键数据** | 数据页中最重要的1个数字 | 酒红色超大数字，比金色更有"冲击力" |
| **重点标注** | 要点列表中最重要的1条 | 酒红文字或酒红圆点标记 |
| **警示/强调** | "注意"/"核心"/"关键"标签 | 酒红badge |
| **对比数据** | Before/After中"After"的提升数字 | 酒红标注增长/改善 |
| **章节过渡标记** | 章节扉页上的章节号色块 | 小面积酒红色块 |

### 3.4 背景色系统（Deck特有双模式）

Deck场景有两套背景系统，在演示中交替使用以制造节奏：

#### 浅色页面（暖米白底）

| 元素 | 色值 | 说明 |
|------|------|------|
| 页面背景 | `#FDFBF6` (`var(--cream)`) | 暖米白，适合内容密集页、文字较多的页面 |
| 卡片/区块背景 | `#FFFFFF` | 白色卡片在米白上形成层次 |
| 标题文字 | `var(--ink)` (`#0D1225`) 或 `var(--royal)` | 墨黑或皇家蓝 |
| 正文文字 | `var(--ink-100)` (`#2C3347`) | 深灰，投影可读 |
| 辅助文字 | `var(--ink-200)` (`#4C546A`) | 中灰，标签和说明 |

#### 深色页面（皇家蓝底）— Deck标志性变体

| 元素 | 色值 | 说明 |
|------|------|------|
| 页面背景 | `linear-gradient(135deg, #0A2463 0%, #061540 100%)` | 皇家蓝深蓝径向/线性渐变 |
| 标题文字 | `#FFFFFF` | 白色，投影高对比 |
| 正文文字 | `rgba(255,255,255,0.85)` | 85%白色，不刺眼 |
| 辅助文字 | `rgba(255,255,255,0.5)` | 50%白色 |
| 金色装饰 | `var(--gold)` (`#F4D35E`) | 在深蓝底上金色非常醒目，是核心装饰色 |
| 酒红强调 | `var(--wine)` (`#D8315B`) | 关键数据和标注 |
| 卡片/区块背景 | `rgba(255,255,255,0.06)` | 6%透明白色卡片，深色模式下的"白色卡片"等价物 |

> **深浅交替原则**：不要连续3页以上使用同一种背景色。理想节奏：深→浅→浅→深→浅→深（金句页/数据页）→浅→深...

### 色彩使用铁律（Deck 场景）

1. **深色背景是Deck的特色**：至少40%的页面使用皇家蓝深色背景，这是Deck区别于网页的核心视觉特征
2. **深色背景上禁用纯黑文字**：深色页面上的文字只能是白色、金色或酒红色
3. **金色用于页码是铁律**：每页右下角必须有金色页码，这是品牌签名的持续性元素
4. **酒红一页最多1处大面积**：酒红冲击力强，一页中只用酒红标注1个最关键元素
5. **对比度必须足够高**：投影环境光线复杂，文字与背景对比度至少7:1（WCAG AAA）
6. **不用浅灰文字在浅色背景上**：投影会让浅灰文字"消失"，正文必须用深灰或皇家蓝

---

## 4. 排版规范

Deck排版与网页排版最大的区别是**字号极大、字距更宽、行距更松**——因为投影场景下文字是给"3米外坐着的人"看的，不是给"30厘米外盯着屏幕的人"看的。

### 4.1 字号规范（核心约束）

| 元素 | 最小字号 | 推荐字号 | 字体 | 说明 |
|------|---------|---------|------|------|
| **封面主标题** | 64px | `clamp(48px, 8vw, 120px)` | Playfair Display 900 | 超大，封面第一视觉 |
| **页面标题** | 36px | 48-64px | Playfair Display 700/900 | 每页标题必须大 |
| **金句/引言** | 36px | `clamp(32px, 5vw, 72px)` | Cormorant Garamond italic | 金句页的文字要尽可能大 |
| **数据数字** | 64px | 96-144px | Playfair Display 700/900 | 数据页的数字是主角 |
| **副标题/小标题** | 24px | 28-36px | Inter 600 或 Playfair 600 | 标题下方的说明 |
| **正文/要点** | **20px** | 24-28px | Inter 400/500 | 投影可读的最小正文字号 |
| **标签/eyebrow** | 14px | 16-18px | Inter 600 全大写 | 章节标签、分类标签 |
| **页码** | 16px | 20px | Cormorant Garamond italic | 金色，右下角 |
| **注释/来源** | 14px | 14-16px | Inter 400 | 数据来源、图片来源 |

> **铁律**：投影场景下，正文字号绝对不能小于20px。如果你觉得20px太大，那说明你放了太多文字——应该删减文字或拆成多页，而不是缩小字号。

### 4.2 字号对比要极端

Deck排版鼓励**极端字号对比**，大的极大、小的极小，制造视觉张力：

```
封面标题:  96px  ●●●●●●●●●●●●●●●●●●●●●●●● （极大，Playfair黑）
数据数字:  120px ●●●●●●●●●●●●●●●●●●●●●●●●●●●●●● （极大最大）
页面标题:  56px  ●●●●●●●●●●●●●● （大）
正文/要点: 26px  ●●●●●● （中）
副标题:    32px  ●●●●●●●● （中大）
页码:      20px  ●●●● （小，金色）
标签:      16px  ●●● （极小）
```

标题与正文的字号比应至少 **2:1**（如56px标题 vs 26px正文），数据数字与标签的字号比可达 **6:1** 以上。

### 4.3 文字密度控制（一页一观点）

| 页面类型 | 最大文字量 | 理想状态 |
|---------|-----------|---------|
| 封面页 | 标题+名字+日期，不超过20字 | 只有标题+名字 |
| 金句页 | 1-2句话，不超过20字 | 一句话 |
| 数据页 | 1个数字+1个标签，每个数据不超过10字说明 | 数字本身说话 |
| 内容页（要点） | 3-5个要点，每个要点不超过15字 | 关键词式要点 |
| 内容页（图文） | 标题+3-5行正文 | 图为主文为辅 |
| 总结页 | 3个要点，每个不超过10字 | 极简 |
| 感谢页 | 谢谢+联系方式 | 只有"Thank You" |

> **删减原则**：写完一页后，删掉一半文字。如果删掉后意思不变，说明你本来就放多了。演讲者说的话不需要全部写在slides上。

### 4.4 排版特殊规则

1. **标题位置固定**：
   - 左上对齐（最常用）：距左边10%，距上边8%
   - 居中对齐（封面/金句/感谢页）：水平垂直居中
   - 不要每页标题位置都不同，保持一致性

2. **安全边距**：
   ```css
   .slide {
     width: 1280px; height: 720px; /* 或 1920x1080 */
     padding: 72px 100px; /* 上下72px 左右100px的安全区域 */
   }
   ```
   - 所有重要内容放在安全边距内（左右各10%、上下各8%）
   - 投影可能会裁切边缘，不要把文字放在紧贴边缘的位置

3. **页码位置固定**：
   - 右下角，距右边100px，距底边48px
   - Cormorant Garamond italic，金色，20px
   - 格式：`01 / 25` 或 `01` 或 `01.`
   - 封面页和感谢页可以隐藏页码

4. **行高与字距**：
   ```css
   .slide-title { line-height: 1.1; letter-spacing: -0.02em; }
   .slide-body { line-height: 1.6; letter-spacing: 0; }
   .slide-quote { line-height: 1.3; letter-spacing: -0.01em; }
   .slide-number { line-height: 1; letter-spacing: -0.03em; }
   ```
   - 大标题行高要紧（1.1），不要让多行大标题松散
   - 正文行高1.6（比网页稍紧，因为字号大）
   - 数据数字行高1.0，紧凑有力

5. **要点列表不使用默认圆点**：
   ```css
   .slide-list { list-style: none; padding: 0; }
   .slide-list li {
     padding-left: 28px; position: relative;
     margin-bottom: 0.8em;
     font-size: 26px;
   }
   .slide-list li::before {
     content: ''; position: absolute; left: 0; top: 0.55em;
     width: 10px; height: 10px; border-radius: 50%;
     background: var(--gold); /* 金色圆点 */
   }
   .slide-list li.highlight::before { background: var(--wine); } /* 酒红重点 */
   ```
   - 用金色小圆点替代默认的"•"
   - 最重要的要点用酒红圆点
   - 不要使用数字列表（除非是有序步骤），用装饰性金色数字做编号页

---

## 5. 推荐布局组合

Deck场景的布局是从L1-L16中选取适合**全屏单页展示**的变体，每页布局必须不同。

### 5.1 封面页布局（1个首选）

| 布局 | 适用场景 | 视觉特点 |
|------|----------|---------|
| **L2 居中大字** | **Deck封面首选** | 标题居中，皇家蓝深色背景+白色/金色文字，极简大气 |

**封面页配置**：
- 背景：皇家蓝深蓝径向渐变（首选）或 暖米白+大幅图片
- 标题：Playfair Display 900，白色，96-120px，居中
- 副标题/演讲者名：Cormorant italic 金色，28-36px，标题下方
- 装饰：可选金色大引号/装饰线/IP形象在角落
- 不放页码

### 5.2 目录/议程页布局

| 布局 | 配置要点 |
|------|---------|
| **L9 三列要点** | 3个议程项横排，每项有金色大数字(01/02/03)+标题+简短说明 |
| **L2 居中列表** | 议程项居中垂直排列，每项前有金色序号，简洁正式 |

### 5.3 内容页布局（必须交替使用）

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **L5变体 左标题右内容** | 文字+图表/图片/要点 | 左侧1/3放标题（顶部对齐），右侧2/3放内容区 |
| **L6变体 左文右图** | 大段说明+配图 | 左侧2/3文字，右侧1/3图片，与L5交替 |
| **L4变体 全图背景+文字** | 视觉冲击页、章节过渡页 | 全屏图片（加深色遮罩）+ 白色文字叠加 |
| **L9 三列要点** | 3个并列观点/3个feature | 3列等宽，每列金色图标/数字+标题+说明 |
| **L8 全屏引文（金句页）** | 核心观点、章节总结 | 一句话居中，Cormorant斜体超大字，金色引号 |
| **L14变体 数据大字** | 关键数据展示 | 1-3个超大数字（96-144px）+ 简短标签，数字为主角 |
| **L15 双栏对比** | Before/After、方案对比 | 左右两栏，可用酒红vs金色对比标注优劣 |
| **L7变体 单栏居中** | 纯文字观点、引言说明 | 少量文字居中排列，周围大量留白 |

### 5.4 金句页布局（L8全屏引文）

金句页是Deck的"呼吸点"，配置：
- 背景：皇家蓝深蓝渐变（首选）或暖米白
- 文字：Cormorant Garamond italic，白色/皇家蓝，56-96px
- 装饰：左上角和右下角金色大引号（`"`），Cormorant 200px+，10-15%透明度
- 可选：右下角小字标注出处/作者
- 不放多余内容，整页就一句话

### 5.5 数据页布局

| 布局 | 配置要点 |
|------|---------|
| **L14变体 单数据大字** | 整页1个超大数字(120-144px)+1行标签，最有冲击力 |
| **L14变体 三数据横排** | 3个stat-card横排，中间的数字最大或用酒红标注 |
| **L15双栏对比** | Before vs After 两个数字对比，中间箭头/vs符号 |

- 数据页背景用深色（皇家蓝渐变）效果最好
- 最重要的数字用酒红，其余用白色或金色
- 数据标签必须简短（不超过10字）
- 数据来源用14px灰色小字放在角落

### 5.6 章节过渡页

| 布局 | 配置要点 |
|------|---------|
| **L2居中大字（深色）** | 章节编号(金色超大) + 章节标题(白色大) + 一句话说明 |
| **L4全图+遮罩** | 章节相关图片做全屏背景+深色遮罩+白色章节标题 |

- 每3-5页内容后可用一个章节过渡页给观众节奏信号
- 章节过渡页是"迷你封面"，视觉上要和正文页有明显区别

### 5.7 总结页布局

| 布局 | 配置要点 |
|------|---------|
| **L9三列要点** | 3个Key Takeaways，每列金色大数字(01/02/03)+一句话 |
| **L2居中列表** | 3个要点居中排列，极简风格 |

### 5.8 感谢页/Q&A布局

| 布局 | 配置要点 |
|------|---------|
| **L2居中大字** | "Thank You" / "Q&A" 超大字居中，联系方式在下方 |
| **与封面呼应** | 使用与封面相同的背景/配色/排版元素，形成闭环 |

- "Thank You" 或 "谢谢" 用Playfair Display超大字
- 联系方式（邮箱/微信/LinkedIn/个人网站）用金色或白色24-28px
- 可放二维码（200x200px以上）方便观众扫码联系
- IP形象可在角落出现，增加温度

### 5.9 经典 Deck 布局配方（30分钟演讲 = 20页）

| 页码 | 布局 | 页面类型 | 背景 |
|------|------|---------|------|
| 01 | **L2居中大字** | 封面 | 深色（皇家蓝） |
| 02 | **L9三列 / L2列表** | 议程/Agenda | 浅色（米白） |
| 03 | **L5左标题右内容** | 背景介绍 | 浅色 |
| 04 | **L6左文右图** | 问题/痛点 | 浅色 |
| 05 | **L8全屏引文** | **金句页**（核心观点） | 深色 |
| 06 | **L9三列要点** | 3个核心发现 | 浅色 |
| 07 | **L4全图+文字** | 视觉冲击/案例引入 | 深色（图片） |
| 08 | **L5左标题右内容** | 方法/框架 | 浅色 |
| 09 | **L15双栏对比** | Before/After对比 | 浅色 |
| 10 | **L8全屏引文** | **金句页**（章节总结） | 深色 |
| 11 | **L14单数据大字** | **数据页**（核心数据） | 深色 |
| 12 | **L6左文右图** | 案例详解 | 浅色 |
| 13 | **L9三列要点** | 关键洞察 | 浅色 |
| 14 | **L4全图+文字** | 视觉佐证 | 深色（图片） |
| 15 | **L14三数据横排** | **数据页**（成果数据） | 深色 |
| 16 | **L5左标题右内容** | 实践建议 | 浅色 |
| 17 | **L8全屏引文** | **金句页**（行动号召） | 深色 |
| 18 | **L9三列要点** | 总结/Takeaways | 浅色 |
| 19 | **L2居中大字** | 感谢/Q&A | 深色 |
| 20 | **（可选）** | 联系方式/二维码 | 深色 |

**节奏规律**：每3-4页浅色内容后插入1页深色（金句/数据/全图），形成"明-暗-明-暗"的呼吸节奏。

### 5.10 布局使用禁忌

| 布局/做法 | Deck 场景不推荐原因 |
|----------|------------------|
| L1非对称图文Hero | 网页首屏布局，不适合16:9单页展示 |
| L7单栏长文 | Deck不放长文，文字多就拆页 |
| L10/L11网格/瀑布流 | 网页浏览布局，Deck每页只有一个焦点 |
| L12/L13时间线/深色面板 | 时间线太长拆成多页，深色面板就是深色背景页 |
| L16画册溢出 | Deck本身就是全屏，不需要"溢出"概念 |
| **连续两页相同布局** | 视觉疲劳，观众走神，必须交替 |
| **连续3页以上同背景色** | 深浅交替是Deck的节奏核心 |
| **文字过小（<20px）** | 投影看不清，是最常见的Deck错误 |
| **一页超过5个要点** | 观众记不住，拆成两页 |

---

## 6. 组件选用指南

### 6.1 必用组件（Deck 场景核心组件，缺一不可）

| 组件 | 组件名 | 使用场景 | 使用频率 |
|------|--------|----------|----------|
| **大装饰数字** | `decorative-number` | 页码、议程编号、要点编号、数据数字 | 每页 |
| **大引文** | `pull-quote` | 金句页、章节总结页 | 每10页至少1次 |
| **数据卡片** | `stat-card` | 数据页、成果展示 | 2-5次 |
| **进度条** | `progress-bar` | 议程页顶部进度指示 | 章节页可选 |

#### 大装饰数字（`decorative-number`）使用规范

大装饰数字是Deck场景最具标志性的视觉元素，用于页码、编号、数据：

```html
<!-- 页码（每页右下角） -->
<span class="slide-page-num">08 / 25</span>

<!-- 议程编号 -->
<div class="agenda-item">
  <span class="decor-num">01</span>
  <h3 class="agenda-title">设计的本质</h3>
  <p class="agenda-desc">为什么好设计不是装饰</p>
</div>

<!-- 数据数字 -->
<div class="big-number" style="color:var(--wine)">96%</div>
<span class="big-number-label">用户完成率</span>
```

```css
/* 页码 */
.slide-page-num {
  position: absolute; right: 100px; bottom: 48px;
  font-family: var(--font-display);
  font-size: 20px;
  font-style: italic;
  color: var(--gold);
  opacity: 0.7;
}
/* 深色页页码 */
.slide.dark .slide-page-num { color: var(--gold); opacity: 0.8; }
.slide.light .slide-page-num { color: var(--royal); opacity: 0.5; }

/* 大装饰数字（议程/编号） */
.decor-num {
  font-family: var(--font-display);
  font-size: clamp(60px, 8vw, 96px);
  font-style: italic;
  font-weight: 600;
  color: var(--gold);
  line-height: 1;
  display: block;
  margin-bottom: var(--sp-3);
  opacity: 0.9;
}

/* 超大数据数字 */
.big-number {
  font-family: var(--font-serif);
  font-size: clamp(80px, 12vw, 144px);
  font-weight: 900;
  color: var(--gold);
  line-height: 1;
  letter-spacing: -0.03em;
}
.big-number-label {
  font-family: var(--font-sans);
  font-size: 24px;
  color: rgba(255,255,255,0.7);
  margin-top: var(--sp-3);
  display: block;
}
```

- **页码是铁律**：每页右下角必须有金色Cormorant斜体页码（封面/感谢页可隐藏）
- 议程编号用Cormorant斜体金色大数字（60-96px）
- 数据数字用Playfair Display黑粗体（80-144px），是页面最大元素
- 数字与文字的字号对比要极端

#### 大引文（`pull-quote`）Deck全屏变体

Deck的金句页pull-quote比网页更大胆——整页只有一句话：

```html
<!-- 金句页（深色背景） -->
<div class="slide slide-quote dark">
  <span class="quote-mark quote-mark--tl">"</span>
  <blockquote class="slide-quote-text">
    好的设计是<span style="color:var(--gold)">显而易见</span>的，<br>
    伟大的设计是<span style="color:var(--wine)">透明</span>的。
  </blockquote>
  <cite class="slide-quote-cite">—— Joe Sparano</cite>
  <span class="slide-page-num">05</span>
</div>
```

```css
.slide-quote {
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  text-align: center; position: relative;
}
.slide-quote-text {
  font-family: var(--font-display);
  font-size: clamp(36px, 5.5vw, 72px);
  font-style: italic; font-weight: 400;
  line-height: 1.3; color: #fff;
  max-width: 900px;
}
.slide-quote.dark .slide-quote-text { color: #fff; }
.slide-quote.light .slide-quote-text { color: var(--royal); }
.quote-mark {
  font-family: var(--font-display);
  font-size: 280px; color: var(--gold);
  opacity: 0.12; position: absolute; line-height: 1;
}
.quote-mark--tl { top: 40px; left: 80px; }
.quote-mark--br { bottom: 40px; right: 80px; transform: rotate(180deg); }
.slide-quote-cite {
  font-family: var(--font-sans); font-size: 20px;
  font-style: normal; color: rgba(255,255,255,0.5);
  margin-top: var(--sp-6);
}
.slide-quote.light .slide-quote-cite { color: var(--ink-300); }
.slide-quote.light .quote-mark { opacity: 0.08; }
```

- 金句页整页就一句话，不加多余装饰
- 金色大引号在对角（左上+右下），透明度10-15%
- 关键词可用金色或酒红标注（一句中最多2个变色词）
- 出处在文字下方，小字灰色

#### 数据卡片（`stat-card`）Deck大字变体

```html
<!-- 单数据大字页 -->
<div class="slide slide-data dark">
  <p class="slide-eyebrow">RESULT</p>
  <div class="big-number" style="color:var(--wine)">+47%</div>
  <span class="big-number-label">用户转化率提升</span>
  <span class="slide-page-num">11</span>
</div>

<!-- 三数据横排 -->
<div class="slide slide-data-triple light">
  <p class="slide-title">项目成果</p>
  <div class="data-triple">
    <div class="data-item">
      <span class="big-number" style="font-size:80px;color:var(--royal)">+47%</span>
      <span class="big-number-label" style="color:var(--ink-200)">转化率</span>
    </div>
    <div class="data-item data-item--highlight">
      <span class="big-number" style="font-size:96px;color:var(--wine)">NPS 58</span>
      <span class="big-number-label" style="color:var(--ink-200)">用户推荐值</span>
    </div>
    <div class="data-item">
      <span class="big-number" style="font-size:80px;color:var(--royal)">-40%</span>
      <span class="big-number-label" style="color:var(--ink-200)">客服咨询</span>
    </div>
  </div>
  <span class="slide-page-num" style="color:var(--royal);opacity:0.5">15</span>
</div>
```

```css
.slide-data {
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  text-align: center;
}
.data-triple {
  display: grid; grid-template-columns: repeat(3, 1fr);
  gap: 60px; margin-top: var(--sp-8); width: 100%;
}
.data-item { text-align: center; }
.data-item--highlight { transform: scale(1.1); }
```

- 单数据页：数字居中，极大，是页面唯一主角
- 三数据页：中间的数据略大或用酒红标注为重点
- 深色背景效果最好，数字用金色或酒红

#### 进度条（`progress-bar`）使用规范

```html
<!-- 议程进度条（顶部） -->
<div class="deck-progress">
  <div class="deck-progress-fill" style="width: 33%;"></div>
</div>
```

```css
.deck-progress {
  position: absolute; top: 0; left: 0; right: 0;
  height: 3px; background: rgba(255,255,255,0.1);
}
.slide.light .deck-progress { background: rgba(10,36,99,0.08); }
.deck-progress-fill {
  height: 100%; background: var(--gold);
  transition: width 0.5s var(--ease);
}
```

- 顶部3px高的金色进度条，显示当前演讲进度
- P2功能，推荐但非强制
- 进度条在深色和浅色页面上都要可见

### 6.2 推荐组件（按需使用）

| 组件 | 使用场景 |
|------|----------|
| `badge-gold` / `badge-wine` | 标签、重点标注、章节标签 |
| `card-project`（大图模式） | 案例展示页，全宽或半宽图片 |
| `code-block`（大字版） | 技术分享中的代码展示，字号≥20px，JetBrains Mono |
| `icon-feature`（金色图标） | 三列要点中的金色图标装饰 |
| `divider-gold` | 标题下方的金色短装饰线 |
| `nav-dots`（侧边导航点） | 右侧小圆点导航，显示当前位置和总页数（P2） |

### 6.3 Deck 场景专属组件模式

#### Slide 基础容器

```html
<div class="deck-container">
  <!-- 所有slides -->
  <div class="slide dark" data-slide="1">
    <div class="slide-inner">
      <!-- 封面内容 -->
    </div>
    <span class="slide-page-num">01</span>
  </div>
  <div class="slide light" data-slide="2">
    <div class="slide-inner">
      <!-- 内容 -->
    </div>
    <span class="slide-page-num">02</span>
  </div>
  <!-- ...更多slides -->
</div>
```

```css
.deck-container {
  width: 100vw; height: 100vh;
  overflow: hidden; position: relative;
  background: var(--ink);
}
.slide {
  position: absolute; inset: 0;
  width: 100%; height: 100%;
  display: none; /* JS控制显示 */
  overflow: hidden;
}
.slide.active { display: flex; }
.slide-inner {
  width: 100%; height: 100%;
  padding: 72px 100px;
  position: relative;
}
/* 深色slide */
.slide.dark {
  background: linear-gradient(135deg, var(--royal) 0%, #061540 100%);
  color: #fff;
}
/* 浅色slide */
.slide.light {
  background: var(--cream);
  color: var(--ink-100);
}
/* 全图slide */
.slide.image { background: var(--ink); }
.slide.image .slide-bg {
  position: absolute; inset: 0;
  width: 100%; height: 100%; object-fit: cover;
  opacity: 0.4;
}
```

#### 要点列表（Deck风格）

```html
<ul class="slide-list">
  <li>用户研究：12场深度访谈</li>
  <li>竞品分析：对标5款头部产品</li>
  <li class="highlight">核心发现：信息架构是最大痛点</li>
  <li>设计目标：核心任务完成时间降低50%</li>
</ul>
```

```css
.slide-list { list-style: none; padding: 0; margin: var(--sp-6) 0; }
.slide-list li {
  padding-left: 32px; position: relative;
  font-family: var(--font-sans);
  font-size: 26px; line-height: 1.6;
  margin-bottom: 0.7em; color: rgba(255,255,255,0.85);
}
.slide.light .slide-list li { color: var(--ink-100); }
.slide-list li::before {
  content: ''; position: absolute; left: 0; top: 0.6em;
  width: 12px; height: 12px; border-radius: 50%;
  background: var(--gold);
}
.slide-list li.highlight { color: var(--gold); font-weight: 500; }
.slide-list li.highlight::before { background: var(--wine); }
.slide.light .slide-list li.highlight { color: var(--wine); }
```

- 金色小圆点替代默认列表符号
- 最重要的一条用 `class="highlight"`，酒红圆点+金色/酒红文字
- 每条不超过20字，用短语不用完整句子
- 每页不超过5条

### 6.4 不推荐组件

| 组件 | 不推荐原因 |
|------|-----------|
| `navbar`（传统导航栏） | Deck是全屏翻页，不需要网页导航栏 |
| `social-links`（社交链接图标组） | 只在感谢页放联系方式，不需要每页都有 |
| `form-input` / 表单 | Deck不收集表单输入 |
| `countdown` | 与演讲场景无关 |
| `filter-tabs` | 无筛选场景 |
| `btn-*` 系列（多个按钮） | Deck几乎不需要按钮，翻页用键盘 |
| `card-testimonial` | 推荐语用pull-quote更大气 |
| `timeline`（长版） | 长timeline拆成多页或简化为要点 |
| `alert-*` | 提示框不需要 |

---

## 7. 特殊注意事项

### 7.1 16:9比例固定（铁律）

```css
/* Deck容器固定16:9比例 */
.deck-container {
  width: 100vw; height: 100vh;
  /* 但设计基准为 1280x720 或 1920x1080 */
}
/* 使用aspect-ratio确保比例 */
@supports (aspect-ratio: 16/9) {
  .deck-container {
    width: min(100vw, calc(100vh * 16 / 9));
    height: min(100vh, calc(100vw * 9 / 16));
    aspect-ratio: 16/9;
    margin: auto; position: absolute;
    top: 0; bottom: 0; left: 0; right: 0;
  }
}
```

- 设计基准：1280x720（720p）或1920x1080（1080p）
- 使用CSS `aspect-ratio: 16/9` 确保在任何屏幕上保持比例
- 在非16:9的屏幕上（如4:3投影仪、超宽屏），Deck居中，两侧/上下留黑边
- **所有字号、间距使用px基准或clamp基于vw**，按1280px宽度设计

### 7.2 键盘翻页JS（铁律）

Deck必须支持键盘翻页，这是基本交互：

```javascript
class DeckController {
  constructor() {
    this.slides = document.querySelectorAll('.slide');
    this.current = 0;
    this.total = this.slides.length;
    this.init();
  }
  init() {
    this.show(0);
    document.addEventListener('keydown', (e) => {
      if (e.key === 'ArrowRight' || e.key === ' ' || e.key === 'PageDown') {
        e.preventDefault(); this.next();
      } else if (e.key === 'ArrowLeft' || e.key === 'PageUp') {
        e.preventDefault(); this.prev();
      } else if (e.key === 'Home') {
        e.preventDefault(); this.show(0);
      } else if (e.key === 'End') {
        e.preventDefault(); this.show(this.total - 1);
      }
    });
    // 点击翻页（可选）
    document.addEventListener('click', (e) => {
      if (e.target.closest('a') || e.target.closest('button')) return;
      const x = e.clientX / window.innerWidth;
      if (x > 0.7) this.next();
      else if (x < 0.3) this.prev();
    });
    // 触摸滑动（移动端）
    let touchStartX = 0;
    document.addEventListener('touchstart', (e) => { touchStartX = e.touches[0].clientX; });
    document.addEventListener('touchend', (e) => {
      const diff = touchStartX - e.changedTouches[0].clientX;
      if (Math.abs(diff) > 50) { diff > 0 ? this.next() : this.prev(); }
    });
  }
  show(index) {
    if (index < 0 || index >= this.total) return;
    this.slides.forEach((s, i) => s.classList.toggle('active', i === index));
    this.current = index;
    // 更新URL hash
    history.replaceState(null, '', `#${index + 1}`);
    // 更新进度条
    const progress = document.querySelector('.deck-progress-fill');
    if (progress) progress.style.width = `${((index + 1) / this.total) * 100}%`;
  }
  next() { this.show(Math.min(this.current + 1, this.total - 1)); }
  prev() { this.show(Math.max(this.current - 1, 0)); }
}
// 初始化
document.addEventListener('DOMContentLoaded', () => new DeckController());
```

**必须支持的快捷键**：
- `→` 右箭头 / `Space` 空格 / `PageDown`：下一页
- `←` 左箭头 / `PageUp`：上一页
- `Home`：第一页
- `End`：最后一页

**可选交互**：
- 点击屏幕右侧70%区域下一页，左侧30%区域上一页
- 触摸滑动翻页（移动端支持）
- 鼠标滚轮翻页（可选，容易误触）
- URL hash记录当前页码（`#5` 表示第5页）

### 7.3 全屏JS

```javascript
// 双击进入/退出全屏
document.addEventListener('dblclick', () => {
  if (!document.fullscreenElement) {
    document.documentElement.requestFullscreen().catch(() => {});
  } else {
    document.exitFullscreen();
  }
});
// F键切换全屏
document.addEventListener('keydown', (e) => {
  if (e.key === 'f' || e.key === 'F') {
    if (!document.fullscreenElement) {
      document.documentElement.requestFullscreen().catch(() => {});
    } else {
      document.exitFullscreen();
    }
  }
});
```

- 支持 `F` 键和双击切换全屏
- 进入全屏后Deck自动填满屏幕
- 全屏模式下隐藏浏览器UI，获得最佳投影效果

### 7.4 每页信息不拥挤（铁律）

Deck设计的第一原则是**留白**。如果一页看起来"满了"，那就是太多了。

**拥挤信号**：
- 一页超过5个要点
- 正文字号小于20px
- 图片和文字各占一半且都很多
- 同时出现3种以上颜色
- 你需要眯起眼睛才能看清某个元素

**解决方法**：
1. 删文字：把要点从10个删到3个
2. 拆页：1页拆成2-3页
3. 升字号：如果删不了文字，就增大字号减少每行字数
4. 用图代替：能用图/图表说的就不用文字

> **Carmack法则**：一页slide的信息量应该和一条Twitter/X推文差不多——不是让你写140字，而是"扫一眼就能理解"。

### 7.5 底部页码/品牌标识

- **页码**：右下角，金色Cormorant斜体20px，格式 `08 / 25`
- **品牌标识**（可选）：左下角可放极小的品牌签名/Logo（16-20px），如"飞鸿."
- 品牌标识不要太大，不能干扰内容
- 封面页和感谢页可隐藏页码和品牌标识（或极淡化）

```css
.slide-brand {
  position: absolute; left: 100px; bottom: 48px;
  font-family: var(--font-serif); font-size: 16px;
  color: var(--gold); opacity: 0.4;
}
.slide.light .slide-brand { color: var(--royal); opacity: 0.3; }
```

### 7.6 字体要大、不使用小字号文字

这是最常见的Deck设计错误——设计师在自己的显示器上觉得字号合适，但投影到3米外就看不清了。

**自检方法**：
1. 把你的Deck在屏幕上缩放到实际投影大小（如果投影是100寸，在27寸屏幕上缩小到约1/4大小）
2. 站在离屏幕2-3米远的地方看
3. 如果你看不清任何文字，那个文字就太小了

**字号底线**：
- 任何情况下不小于14px（只有数据来源/图片版权可使用14px）
- 正文不小于20px
- 标题不小于36px
- 数据数字不小于64px

### 7.7 对比度要求（投影环境光线复杂）

投影环境的光线条件远比屏幕复杂——可能有窗户光、灯光、投影仪亮度不足等因素。对比度必须比网页更高：

```css
/* 深色页面上的文字对比度 */
.slide.dark h2 { color: #FFFFFF; } /* 对比度 15:1 ✅ */
.slide.dark p { color: rgba(255,255,255,0.85); } /* 对比度 ~10:1 ✅ */
.slide.dark .muted { color: rgba(255,255,255,0.5); } /* 仅用于非关键信息 */

/* 浅色页面上的文字对比度 */
.slide.light h2 { color: var(--ink); } /* 对比度 14:1 ✅ */
.slide.light p { color: var(--ink-100); } /* 对比度 10:1 ✅ */
.slide.light .muted { color: var(--ink-200); } /* 辅助信息最低限 */
```

- 正文文字对比度至少 7:1（WCAG AAA）
- 标题文字对比度至少 10:1
- 深色页面上不用 `rgba(255,255,255,0.3)` 以下的白色放正文
- 浅色页面上不用 `var(--ink-300)` 以下的灰色放正文
- 金色和酒红在白色背景上要加粗，否则细字投影可能看不清

### 7.8 翻页过渡动效（P2推荐）

```css
/* 翻页过渡 - 推荐淡入淡出（最专业） */
.slide {
  opacity: 0;
  transform: translateX(20px);
  transition: opacity 400ms var(--ease), transform 400ms var(--ease);
  pointer-events: none;
}
.slide.active {
  opacity: 1;
  transform: translateX(0);
  pointer-events: auto;
}
.slide.prev {
  transform: translateX(-20px);
}
```

- **推荐**：淡入淡出（opacity 400ms），最专业最不分散注意力
- **可选**：轻微水平位移（20px），像翻书一样
- **不推荐**：3D翻转、缩放弹跳、旋转等花哨效果
- 过渡时间控制在300-500ms，太快太突兀，太慢拖节奏
- 尊重 `prefers-reduced-motion`：
  ```css
  @media (prefers-reduced-motion: reduce) {
    .slide { transition: none; transform: none; }
  }
  ```

### 7.9 演讲者模式备注（P2）

如果Deck需要支持演讲者模式，可在每页添加备注：

```html
<div class="slide dark" data-slide="5">
  <div class="slide-inner">
    <!-- 可见内容 -->
    <blockquote class="slide-quote-text">好的设计是显而易见的...</blockquote>
  </div>
  <!-- 演讲者备注（演示时不可见，仅在演讲者模式显示） -->
  <aside class="speaker-notes">
    这里可以展开讲这个观点的背景：Joe Sparano是...
    停顿2秒，让观众读完这句话。
    然后问观众：你们见过哪些"透明"的设计？
  </aside>
  <span class="slide-page-num">05</span>
</div>
```

```css
.speaker-notes { display: none; }
/* 演讲者模式下显示（通过JS添加.speaker-mode类到body） */
body.speaker-mode .speaker-notes {
  display: block;
  position: fixed; bottom: 0; left: 0; right: 0;
  height: 200px; background: var(--ink);
  color: rgba(255,255,255,0.8); padding: var(--sp-4);
  font-size: 18px; line-height: 1.6; overflow-y: auto;
  z-index: 200;
}
body.speaker-mode .slide { height: calc(100vh - 200px); }
```

- 演讲者备注在正常演示模式下不可见
- 按 `S` 键可切换演讲者模式（需要JS实现）
- 备注内容只有演讲者能看到，用于提示自己该讲什么

---

## 8. 场景专属 Checklist

在交付任何 Deck / 演示文稿页面之前，必须通过以下检查：

### P0 — 必须通过（缺一不可，直接影响演示效果）

- [ ] **16:9比例固定**：容器使用aspect-ratio 16/9，设计基准1280x720或1920x1080
- [ ] **键盘翻页JS正常工作**：→/空格/PageDown下一页，←/PageUp上一页，Home/End跳首尾
- [ ] **字号足够大**：标题≥36px（推荐48px+），正文≥20px（推荐24px+），数据数字≥64px
- [ ] **一页一观点**：每页只有一个核心信息，不堆砌文字
- [ ] **页码可见**：右下角金色Cormorant斜体页码（封面/感谢页可隐藏）
- [ ] **三种品牌色严格为 `#0A2463` / `#F4D35E` / `#D8315B`**
- [ ] **全屏JS支持**：F键或双击可切换全屏模式
- [ ] **安全边距**：重要内容在左右100px、上下72px安全区内
- [ ] **文字对比度足够**：正文对比度≥7:1，标题≥10:1，投影可读
- [ ] **不使用小于14px的文字**（数据来源除外）
- [ ] **内容页标题位置一致**：左上对齐或居中，不随意变动
- [ ] **深色背景变体存在**：至少40%页面使用皇家蓝深色背景
- [ ] **衬线+无衬线混搭**：标题Playfair Display，正文Inter，金句Cormorant Garamond italic，代码JetBrains Mono
- [ ] **响应式/适配**：在不同屏幕尺寸下16:9比例保持，不裁切内容
- [ ] **翻页交互流畅**：无JS错误，翻页无卡顿

### P1 — 应该通过（尽量满足，影响质感和节奏）

- [ ] **每页布局不同**：不连续两页使用相同布局（左图右文→全图→三列→引文...交替）
- [ ] **有金句页**：每10-15页有一个L8全屏引文金句页，整页一句话
- [ ] **有视觉惊喜**：全图背景页、超大数字页、深色金句页等打破节奏的页面
- [ ] **深浅背景交替**：不连续3页以上使用相同背景色
- [ ] **要点列表使用金色圆点**：不用默认的"•"符号，重点项用酒红圆点
- [ ] **数据页有超大数字**：数字是页面最大元素（96px+），用金色或酒红
- [ ] **封面和感谢页视觉呼应**：使用相同/相似背景或排版元素形成闭环
- [ ] **大装饰数字使用Cormorant斜体**：页码、编号、序号统一字体
- [ ] **议程页有章节进度感**：章节过渡页高亮当前位置，或顶部progress-bar
- [ ] **感谢页有联系方式**：邮箱/社交/二维码清晰可见
- [ ] **关键词用金色或酒红标注**：金句/正文中的核心词变色强调（每页不超过2个）
- [ ] **有封面→议程→内容→总结→感谢的完整结构**
- [ ] **选中文本背景为金色**：`::selection { background: var(--gold); color: var(--royal); }`
- [ ] **触摸滑动支持**：移动端可左右滑动翻页
- [ ] **图片遮罩合适**：全图背景页的图片加深色遮罩确保文字可读

### P2 — 加分项（锦上添花，提升专业度）

- [ ] **翻页过渡动效**：淡入淡出300-500ms，克制优雅，不花哨
- [ ] **演讲者模式备注**：按S键显示演讲者备注（speaker-notes）
- [ ] **进度条**：顶部3px金色进度条显示演讲进度
- [ ] **侧边导航点**：右侧小圆点显示总页数和当前位置，可点击跳转
- [ ] **URL hash记录页码**：刷新或分享链接可定位到特定页
- [ ] **代码块使用JetBrains Mono**：技术分享中代码字号≥20px，语法高亮
- [ ] **IP形象自然出现**：封面或感谢页角落出现IP形象，增加温度
- [ ] **打印/PDF导出优化**：`@media print` 样式优化，可导出为PDF
- [ ] **品牌标识在左下角**：极淡的品牌签名，不干扰内容
- [ ] **点击翻页**：点击屏幕右侧下一页，左侧上一页
- [ ] **章节过渡页**：大章节之间有独立的过渡扉页
- [ ] **二维码在感谢页**：200px+尺寸，方便扫码

### 交付前自检三问

1. **站在3米外能看清吗？**：把slide缩小到投影比例，退后3米——所有文字都能看清吗？
2. **每页3秒能理解吗？**：快速翻页，每页只看3秒——你能说出每页的核心观点吗？
3. **有没有连续两页看起来一样？**：翻页节奏有变化吗？金句页和数据页穿插了吗？

---

## 附录：Deck 快速模板骨架

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>演讲标题 · 飞鸿</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400;1,600&family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  <style>
    :root {
      --royal: #0A2463; --gold: #F4D35E; --wine: #D8315B;
      --cream: #FDFBF6; --ink: #0D1225;
      --font-serif: 'Playfair Display', 'Noto Serif SC', Georgia, serif;
      --font-sans: 'Inter', 'Noto Sans SC', -apple-system, sans-serif;
      --font-display: 'Cormorant Garamond', 'Noto Serif SC', Georgia, serif;
      --font-mono: 'JetBrains Mono', 'Fira Code', monospace;
      --ease: cubic-bezier(0.16, 1, 0.3, 1);
    }
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
    html, body { width: 100%; height: 100%; overflow: hidden; background: var(--ink); }
    body { font-family: var(--font-sans); -webkit-font-smoothing: antialiased; }
    ::selection { background: var(--gold); color: var(--royal); }

    /* Deck Container - 16:9 */
    .deck {
      position: absolute; inset: 0;
      width: 100vw; height: 100vh;
      display: flex; align-items: center; justify-content: center;
    }
    @supports (aspect-ratio: 16/9) {
      .deck {
        width: min(100vw, calc(100vh * 16 / 9));
        height: min(100vh, calc(100vw * 9 / 16));
        aspect-ratio: 16/9;
        margin: auto;
        position: absolute;
        top: 0; bottom: 0; left: 0; right: 0;
      }
    }

    /* Slide Base */
    .slide {
      position: absolute; inset: 0;
      width: 100%; height: 100%;
      display: none;
      opacity: 0;
      transition: opacity 400ms var(--ease);
      overflow: hidden;
    }
    .slide.active { display: flex; opacity: 1; }
    .slide-inner {
      width: 100%; height: 100%;
      padding: 72px 100px;
      position: relative;
      display: flex; flex-direction: column;
    }

    /* Dark/Light/Image variants */
    .slide.dark {
      background: linear-gradient(135deg, var(--royal) 0%, #061540 100%);
      color: #fff;
    }
    .slide.light { background: var(--cream); color: var(--ink); }
    .slide.image .slide-bg {
      position: absolute; inset: 0;
      width: 100%; height: 100%; object-fit: cover;
    }
    .slide.image .slide-overlay {
      position: absolute; inset: 0;
      background: linear-gradient(135deg, rgba(10,36,99,0.85), rgba(6,21,64,0.75));
    }
    .slide.image .slide-inner { position: relative; z-index: 1; }

    /* Typography */
    .slide-eyebrow {
      font-size: 16px; font-weight: 600; letter-spacing: 0.2em;
      text-transform: uppercase; color: var(--gold);
      margin-bottom: 24px; display: block;
    }
    .slide-title {
      font-family: var(--font-serif);
      font-size: clamp(36px, 4.5vw, 56px);
      font-weight: 700; line-height: 1.1; letter-spacing: -0.02em;
      color: var(--ink); margin-bottom: 32px;
    }
    .slide.dark .slide-title { color: #fff; }
    .slide.image .slide-title { color: #fff; }

    /* Page Number */
    .slide-page-num {
      position: absolute; right: 100px; bottom: 48px;
      font-family: var(--font-display);
      font-size: 20px; font-style: italic;
      color: var(--gold); opacity: 0.7;
    }
    .slide.light .slide-page-num { color: var(--royal); opacity: 0.5; }

    /* Cover Slide (L2 居中) */
    .slide-cover { align-items: center; justify-content: center; text-align: center; }
    .cover-title {
      font-family: var(--font-serif);
      font-size: clamp(48px, 8vw, 96px);
      font-weight: 900; line-height: 1.05; letter-spacing: -0.02em;
      color: #fff; margin-bottom: 24px;
    }
    .cover-sub {
      font-family: var(--font-display);
      font-size: clamp(20px, 2.5vw, 32px);
      font-style: italic; color: var(--gold);
    }
    .cover-meta {
      font-size: 16px; color: rgba(255,255,255,0.5);
      margin-top: 48px;
    }

    /* Quote Slide */
    .slide-quote-page { align-items: center; justify-content: center; text-align: center; }
    .quote-mark {
      font-family: var(--font-display);
      font-size: 200px; color: var(--gold); opacity: 0.12;
      position: absolute; line-height: 1;
    }
    .quote-mark--tl { top: 30px; left: 80px; }
    .quote-mark--br { bottom: 30px; right: 80px; transform: rotate(180deg); }
    .quote-text {
      font-family: var(--font-display);
      font-size: clamp(32px, 5vw, 64px);
      font-style: italic; line-height: 1.3; color: #fff;
      max-width: 900px;
    }
    .quote-cite {
      font-size: 18px; color: rgba(255,255,255,0.5);
      margin-top: 32px; font-style: normal;
    }

    /* Big Number */
    .slide-data-page { align-items: center; justify-content: center; text-align: center; }
    .big-number {
      font-family: var(--font-serif);
      font-size: clamp(80px, 12vw, 144px);
      font-weight: 900; line-height: 1;
      color: var(--gold); letter-spacing: -0.03em;
    }
    .big-number.wine { color: var(--wine); }
    .big-number-label {
      font-size: 24px; color: rgba(255,255,255,0.7);
      margin-top: 16px; display: block;
    }

    /* Content List */
    .slide-list { list-style: none; padding: 0; }
    .slide-list li {
      padding-left: 32px; position: relative;
      font-size: 26px; line-height: 1.6;
      margin-bottom: 0.7em; color: rgba(255,255,255,0.85);
    }
    .slide.light .slide-list li { color: var(--ink); }
    .slide-list li::before {
      content: ''; position: absolute; left: 0; top: 0.6em;
      width: 12px; height: 12px; border-radius: 50%;
      background: var(--gold);
    }
    .slide-list li.highlight::before { background: var(--wine); }
    .slide-list li.highlight { color: var(--gold); font-weight: 500; }
    .slide.light .slide-list li.highlight { color: var(--wine); }

    /* Thank You */
    .slide-thanks { align-items: center; justify-content: center; text-align: center; }
    .thanks-text {
      font-family: var(--font-serif);
      font-size: clamp(56px, 10vw, 120px);
      font-weight: 900; color: #fff; line-height: 1;
    }
    .thanks-contact {
      font-size: 24px; color: var(--gold);
      margin-top: 40px;
    }

    /* Progress Bar (P2) */
    .deck-progress {
      position: absolute; top: 0; left: 0; right: 0;
      height: 3px; background: rgba(255,255,255,0.1);
      z-index: 10;
    }
    .slide.light .deck-progress { background: rgba(10,36,99,0.08); }
    .deck-progress-fill {
      height: 100%; background: var(--gold);
      transition: width 0.5s var(--ease);
    }

    @media (prefers-reduced-motion: reduce) {
      .slide { transition: none; }
      .deck-progress-fill { transition: none; }
    }
  </style>
</head>
<body>
  <div class="deck" id="deck">

    <!-- ① 封面 (L2 深色居中) -->
    <div class="slide dark active" data-slide="1">
      <div class="deck-progress"><div class="deck-progress-fill" style="width:10%"></div></div>
      <div class="slide-inner slide-cover">
        <span class="slide-eyebrow">Design Talk · 2025</span>
        <h1 class="cover-title">设计的<span style="color:var(--gold)">本质</span></h1>
        <p class="cover-sub">当AI可以生成一切，什么才是设计师的核心价值</p>
        <p class="cover-meta">飞鸿 · 品牌设计师</p>
      </div>
    </div>

    <!-- ② 议程 -->
    <div class="slide light" data-slide="2">
      <div class="deck-progress"><div class="deck-progress-fill" style="width:20%"></div></div>
      <div class="slide-inner">
        <span class="slide-eyebrow" style="color:var(--royal);background:transparent;padding:0;">Agenda</span>
        <h2 class="slide-title">今天聊什么</h2>
        <ul class="slide-list" style="max-width:600px">
          <li>AI时代设计师面临的挑战</li>
          <li class="highlight">审美判断是最稀缺的能力</li>
          <li>从"做图"到"做决策"</li>
          <li>三个可以立即开始的实践</li>
        </ul>
      </div>
      <span class="slide-page-num">02</span>
    </div>

    <!-- ③ 金句页示例 (L8 深色) -->
    <div class="slide dark slide-quote-page" data-slide="3">
      <div class="deck-progress"><div class="deck-progress-fill" style="width:30%"></div></div>
      <span class="quote-mark quote-mark--tl">"</span>
      <div class="slide-inner" style="align-items:center;justify-content:center;text-align:center;">
        <p class="quote-text">
          当工具人人可用，<br>
          <span style="color:var(--gold)">品味</span>和<span style="color:var(--wine)">判断</span>才是壁垒。
        </p>
        <cite class="quote-cite">—— 设计沉思录</cite>
      </div>
      <span class="quote-mark quote-mark--br">"</span>
      <span class="slide-page-num">03</span>
    </div>

    <!-- ④ 数据页示例 -->
    <div class="slide dark slide-data-page" data-slide="4">
      <div class="deck-progress"><div class="deck-progress-fill" style="width:50%"></div></div>
      <div class="slide-inner" style="align-items:center;justify-content:center;text-align:center;">
        <span class="slide-eyebrow">By The Numbers</span>
        <div class="big-number wine">87%</div>
        <span class="big-number-label">的设计师认为AI改变了他们的工作方式</span>
      </div>
      <span class="slide-page-num">04</span>
    </div>

    <!-- ⑤ 内容页示例 (左标题右要点) -->
    <div class="slide light" data-slide="5">
      <div class="deck-progress"><div class="deck-progress-fill" style="width:70%"></div></div>
      <div class="slide-inner" style="flex-direction:row;gap:60px;">
        <div style="flex:0 0 35%;">
          <span class="slide-eyebrow" style="color:var(--royal);background:transparent;padding:0;">Practice</span>
          <h2 class="slide-title">三个<br>实践</h2>
        </div>
        <div style="flex:1;">
          <ul class="slide-list">
            <li>每天花15分钟"看"好设计</li>
            <li>做设计决策时写下"为什么"</li>
            <li class="highlight">建立自己的审美参照系</li>
          </ul>
        </div>
      </div>
      <span class="slide-page-num">05</span>
    </div>

    <!-- ⑥ 感谢页 -->
    <div class="slide dark slide-thanks" data-slide="6">
      <div class="deck-progress"><div class="deck-progress-fill" style="width:100%"></div></div>
      <div class="slide-inner" style="align-items:center;justify-content:center;text-align:center;">
        <h2 class="thanks-text">Thank <span style="color:var(--gold)">You</span></h2>
        <p class="thanks-contact">hello@Feihong.art · @Feihong_design</p>
      </div>
    </div>

  </div>

  <script>
    // === Deck Controller ===
    class Deck {
      constructor() {
        this.slides = document.querySelectorAll('.slide');
        this.total = this.slides.length;
        this.cur = 0;
        this.go(0);
        this.bind();
      }
      bind() {
        document.addEventListener('keydown', e => {
          if (['ArrowRight',' ','PageDown'].includes(e.key)) { e.preventDefault(); this.next(); }
          else if (['ArrowLeft','PageUp'].includes(e.key)) { e.preventDefault(); this.prev(); }
          else if (e.key === 'Home') { e.preventDefault(); this.go(0); }
          else if (e.key === 'End') { e.preventDefault(); this.go(this.total-1); }
          else if (e.key === 'f' || e.key === 'F') { this.toggleFullscreen(); }
        });
        let sx = 0;
        document.addEventListener('touchstart', e => { sx = e.touches[0].clientX; });
        document.addEventListener('touchend', e => {
          const d = sx - e.changedTouches[0].clientX;
          if (Math.abs(d) > 50) d > 0 ? this.next() : this.prev();
        });
        document.addEventListener('dblclick', () => this.toggleFullscreen());
      }
      go(i) {
        if (i < 0 || i >= this.total) return;
        this.slides.forEach((s, j) => s.classList.toggle('active', j === i));
        this.cur = i;
        history.replaceState(null, '', `#${i+1}`);
      }
      next() { this.go(Math.min(this.cur + 1, this.total - 1)); }
      prev() { this.go(Math.max(this.cur - 1, 0)); }
      toggleFullscreen() {
        if (!document.fullscreenElement) document.documentElement.requestFullscreen().catch(()=>{});
        else document.exitFullscreen();
      }
    }
    document.addEventListener('DOMContentLoaded', () => new Deck());
  </script>
</body>
</html>
```

---

## 场景定位

演示文稿/Slides/Deck是用于线下演讲、线上分享、会议提案、项目汇报的全屏翻页式HTML演示。适用于：会议演讲、工作坊分享、项目提案汇报、课程授课、产品发布会、TED式演讲。不适用于：网页浏览（应该用普通页面）、文档阅读（应该用PDF/长文）、互动应用（应该用App）。核心原则是"少即是多"——大字少字、一页一观点、3秒读懂、投影可读，是面向观众的视觉辅助而非演讲稿。

## 推荐节奏（Section 序列，即Slide序列）

### 方案 A：经典演讲型（20-25页，15-30分钟演讲）
1. 封面（L2 居中大字，深色）— 标题+演讲者+场合，第一印象
2. 议程/目录（L3 三列或L7列表，浅色）— 告诉观众你要讲什么
3. 开场钩子（L8 引文全屏 / 数据大字，深色）— 一个惊人数据或金句抓住注意力
4. 背景/问题（L5 左图右文 / L7列表）— 为什么这个话题重要
5. 核心观点1（L3 三列 / L5图文）— 第一个论点+论据
6. 金句停顿（L8 引文全屏，深色）— 核心金句整页
7. 核心观点2+3（交替布局）— 深浅交替，图文交替
8. 案例/数据（大字数据页/全图页）— 用数据和案例证明观点
9. 总结（L7 列表 / L3三列，浅色）— 3个takeaway
10. 行动号召（L8引文或L13深色CTA）— 希望观众做什么
11. Q&A/感谢页（L2居中，深色）— Thank You + 联系方式

### 方案 B：项目汇报型（15-20页）
1. 封面（深色）— 项目名+团队+日期
2. 目录（浅色）— 议程
3. 背景与目标（L5图文）— 为什么做这个项目
4. 问题定义（L8引文深色 / 数据大字）— 核心问题
5. 方案探索（L3三列或L9卡片）— 多个方案对比
6. 最终方案（L5左图右文 / L16全图）— 选中方案详解
7. 执行过程（L12时间线）— 关键里程碑
8. 成果数据（大字数据页，深色）— 数据说话
9. 反思/收获（L7列表）— 经验教训
10. 下一步（L3三列）— 未来计划
11. 感谢/Q&A（深色）

### 方案 C：闪电演讲型（10页以内，5分钟）
1. 封面（深色）
2. 一个震撼数据/问题（L8深色大字）
3. 3个核心论点（每页一个，L2/L3交替）
4. 一个核心金句（L8深色）
5. 结论+行动（L8/L13深色）
6. 感谢（深色）

### 方案 D：工作坊/教学型（30-50页）
1. 封面+欢迎（深色）
2. 自我介绍（L5左图右文）
3. 议程（浅色列表）
4. 第一部分：概念讲解（文字+图表+金句穿插）
5. 中场金句/互动环节（L8深色引文/问题页）
6. 第二部分：实操演示（截图+代码+步骤）
7. 案例分析（L5图文+全图页）
8. 要点总结（L3三列takeaway）
9. Q&A+资源（感谢页+二维码+链接）

## 专属装饰手法（Signature Touches）

- **#11 Ornamental Corner 角饰**：封面和感谢页四角加金色角饰线，增加仪式感和正式感
- **#09 Fleuron 花饰**：章节过渡页标题两侧用❦装饰，标记新章节开始
- **#20 Numbered Index 编号索引**：议程页用金色大号Cormorant斜体数字（01/02/03），装饰感强
- **#04 Pull Quote 金句引用**：每10-15页必须有一个整页金句，Cormorant斜体大字+金色大引号对角
- **#07 Decorative Rule 装饰线**：标题下方加金色短装饰线（60px宽），增加排版精致度
- **#15 Divider 分隔线**：议程页章节之间用金色细线分隔
- **#14 Section Marker 章节标记**：章节过渡页用大号罗马数字（I, II, III...）金色，扉页感
- **#18 Badge & Stamp 徽章标签**：数据来源标签、"NEW"/"核心"等小标签用金色/酒红胶囊
- **#03 Image Frame 图片画框**：截图/照片加1px金色细边框或白色边框+阴影，避免图片和背景糊在一起
- **#22 Publication Header 刊头标题**：封面可用报纸刊头式排版，演讲标题大写衬线居中
- **#13 Red Thread 红线**：进度条用金色，关键节点可用酒红点标记
- **页码装饰**：右下角页码用金色Cormorant斜体，格式"08 / 25"，是Deck最稳定的品牌标识

## 推荐布局组合

| 布局 | 名称 | 适用Slide类型 | 说明 |
|------|------|--------------|------|
| **L2** | 居中大字 | 封面/感谢/Q&A/金句 | 最经典的Slide布局，标题居中，适合情绪性页面 |
| **L8** | 引文全屏 | 金句页/数据页/钩子页 | 整页一句话或一个数字，深色背景最佳，节奏停顿点 |
| **L3** | 分屏/三列 | 议程/三点总结/对比 | 3个要点并列，最常用的内容页布局 |
| **L5** | 左图右文 | 案例展示/方案讲解 | 一侧图一侧文，信息密度适中 |
| **L4** | 全屏视觉 | 全图背景页 | 大幅图片+半透明遮罩+白色文字，情绪渲染 |
| **L9** | 三列卡片 | 方案探索/功能介绍 | 3-4个卡片并排展示选项或功能 |
| **L12** | 时间线 | 项目历程/执行过程 | 皇家蓝连线+金色节点，展示时间序列 |
| **L15** | 双栏对比 | 方案对比/Before-After | 左右对比两个方案或前后效果 |
| **L14** | 数据统计条 | 成果展示 | 3-4个大数字横排展示关键指标 |

## 色彩策略

Deck场景色彩策略核心：深色为主（40-60%页面用深色），浅色做呼吸，金色做装饰，酒红做强调。投影环境下对比度要高。

**皇家蓝 #0A2463（55%）—— 主色，深邃权威**
- 深色页面背景（渐变`linear-gradient(135deg, #0A2463, #061540)`）
- 浅色页面标题文字颜色
- 议程/目录编号底色
- 数据连线、图表主色
- 封面/感谢页主背景

**复古金 #F4D35E（30%）—— 装饰，品质与聚焦**
- 页码（右下角Cormorant斜体金色）
- 大引号（金句页的对角金色引号，opacity 0.12）
- 关键词高亮（金句/标题中的核心词）
- 装饰线、角饰、Fleuron花饰
- 列表金色圆点
- 进度条颜色
- 章节编号数字
- Eyebrow标签文字颜色（深色页上）
- 数据数字（深色页上的金色大数字）
- **白底上金色仅用于线条/装饰/短词，不用大段金色文字**

**酒红 #D8315B（15%）—— 强调与关键数据**
- 最重要的数据数字（如+47%转化率提升）
- 列表中最关键的一条（highlight类）
- 标题中需要极强强调的词（每页最多1个）
- Before-After对比中After的标注
- 核心发现/结论标签
- **酒红在Deck中是"重音符号"，偶尔出现才有力，每页最多1处酒红**

**深浅交替节奏**：封面深色 → 议程浅色 → 钩子深色 → 内容浅色 → 金句深色 → 内容浅色 → 总结浅色 → 感谢深色。绝不能连续3页以上相同背景色。金色在深色和浅色页面上都要可见（深色页金色彩色，浅色页金色做装饰线）。

## 场景禁忌（Don'ts）

1. **一页超过5个要点**：超过5个就拆页或删减，每点不超过20字
2. **字号小于20px**：投影3米外20px是底线，推荐24px+正文，36px+标题
3. **全文字无图片**：连续3页纯文字是催眠剂，必须穿插图/数据/金句
4. **花哨翻页动画**：3D翻转、旋转、弹跳都不专业，用淡入淡出即可
5. **把演讲稿放上去**：Slide是视觉辅助不是提词器，你要说的话不要写在slide上
6. **图表无标题无结论**：放了图表必须有一句结论告诉观众看什么
7. **深色页上用低透明白色文字**：`rgba(255,255,255,0.5)`以下的白色投影看不清
8. **每页布局都一样**：连续两页相同布局=节奏单调，必须交替
9. **忘记页码**：页码是观众定位和提问引用的基础，除封面/感谢页外必须有
10. **全屏播放无键盘控制**：→/空格/PageDown必须能翻页，F键全屏是基本要求

## 场景专属Checklist

- [ ] 按F键能进入全屏模式，双击也能切换全屏
- [ ] 键盘翻页正常：→/空格/PageDown下一页，←/PageUp上一页，Home/End跳首尾
- [ ] 16:9比例固定（aspect-ratio: 16/9），在非16:9屏幕上居中留黑边
- [ ] 正文字号≥20px（推荐24px+），标题≥36px，数据数字≥64px
- [ ] 每页不超过5个要点，每点不超过20字短语（非完整句子）
- [ ] 除封面/感谢页外，每页右下角有金色Cormorant斜体页码
- [ ] 深色页面占比40-60%，深浅交替，不连续3页同色
- [ ] 每10-15页有一个整页金句（L8引文全屏），Cormorant斜体+金色大引号
- [ ] 重要内容在安全边距内（左右100px、上下72px），不贴边
- [ ] 全图背景页有深色遮罩（rgba(10,36,99,0.75+)）确保白色文字可读
- [ ] 文字对比度达标：正文≥7:1，标题≥10:1
- [ ] 关键词高亮克制：每页变色词不超过2个（金色或酒红）
- [ ] 翻页过渡为淡入淡出300-500ms，无花哨3D/弹跳效果
- [ ] 触摸滑动翻页支持（移动端）
- [ ] 感谢页有联系方式（邮箱/社交/二维码）
- [ ] 顶部有金色进度条（P2），显示演讲进度
- [ ] URL hash记录页码（如#5），刷新可定位
- [ ] 投影测试：站在3米外能看清所有文字
- [ ] 尊重prefers-reduced-motion，无动画干扰
- [ ] 无JS报错，翻页流畅无卡顿

---

*Scene: Deck v1.0 · Feihong Design System*
*基于 DNA.md v2.0 · 最后更新：2026-07-08*
