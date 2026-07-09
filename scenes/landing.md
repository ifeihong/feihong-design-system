# Feihong Design System · Scene: Landing
# 飞鸿品牌设计系统 · 场景规范：活动页 / Landing 页

> 本规范定义飞鸿品牌设计系统在「活动页 / Landing 落地页 / 转化型页面」中的具体应用方式。
> 所有规则建立在 `DNA.md`、`components/14-layouts.md`、`components/` 基础之上，场景专属规则以本文件为准。
> Landing 场景的核心使命是**转化**——每一个像素都应为"让访客采取行动"服务。

---

## 1. 场景定义

### 适用页面类型

Landing 场景适用于以下以**转化为核心目标**的内容形态：

| 类型 | 说明 | 典型长度 | 核心转化目标 |
|------|------|----------|-------------|
| **活动宣传页** | 线下/线上活动、分享会、沙龙、工作坊 | 5-8屏 | 报名 / 购票 |
| **产品落地页** | 新产品发布、功能介绍、App 下载页 | 6-10屏 | 注册 / 下载 / 试用 |
| **服务销售页** | 设计服务、咨询服务、课程售卖 | 5-9屏 | 咨询 / 预约 / 购买 |
| **报名/注册页** | 课程报名、会员注册、活动报名 | 3-5屏 | 填写表单 / 提交信息 |
| **分享/邀请页** | 邀请好友、裂变活动、限时优惠 | 4-6屏 | 分享 / 领取 / 参与 |

### 场景核心气质

- **权威可信**：皇家蓝主导的视觉基调传递专业感，让访客放心托付
- **紧迫有力**：酒红 CTA 和金色高亮制造行动焦点，不拖沓、不犹豫
- **品质高级**：衬线标题 + 精致细节传递品牌质感，拒绝廉价营销感
- **节奏明快**：每个 section 版式不同，信息密度有疏有密，引导访客顺畅向下阅读

### 场景核心约束

1. **转化优先于审美表达**：所有设计决策服务于"让访客行动"，但不以牺牲品牌质感为代价
2. **首屏必须回答三个问题**：这是什么？对我有什么价值？我该做什么？
3. **CTA 按钮至少出现 2 次**（首屏 + 结尾），长页面建议 3-4 次
4. **社会证明不可省略**：必须有客户评价、数据、合作品牌Logo等信任建立元素
5. **价值主张一句话说清**：首屏副标题不超过 25 个字，让访客 3 秒内理解核心价值

---

## 2. 典型页面结构

Landing 页面采用 **Hero 首屏 → 社会证明 → 价值/功能 → 案例/作品 → 价格/FAQ → 深色CTA** 的六段式经典转化结构：

```
┌─────────────────────────────────────────────────────────┐
│  ① Hero 首屏（L1/L2/L3/L4 — 根据内容类型选择）            │
│     - 导航栏（固定顶部，半透明毛玻璃）                      │
│     - eyebrow 标签（活动名称 / 产品定位）                   │
│     - h1 超大衬线标题（极端字号对比）                       │
│     - 一句话价值主张（Cormorant 斜体副标题）               │
│     - 主 CTA 按钮（酒红 btn-cta + btn-lg）                │
│     - 次要按钮（幽灵/描边）                                │
│     - 可选：背景装饰文字/大数字、视觉元素                   │
├─────────────────────────────────────────────────────────┤
│  ② 社会证明区（L14 数据统计条 / Logo墙 / 客户评价）         │
│     - 数据统计（stat-card × 3-4）                         │
│     - 或：合作品牌 Logo 展示                               │
│     - 或：用户评价卡片（testimonial-card × 2-3）          │
│     * 作用：首屏后立即建立信任，降低访客心理防线             │
├─────────────────────────────────────────────────────────┤
│  ③ 核心价值 / 功能介绍（L9 三列卡片 / L5/L6 图文并排）      │
│     - section-title 章节标题（金色序号+装饰线）            │
│     - 3-4 个核心价值点（card-feature）                    │
│     - 或：左图右文/左文右图交替详述功能                     │
│     * 作用：告诉访客"你能得到什么"                          │
├─────────────────────────────────────────────────────────┤
│  ④ 作品 / 案例展示（L10 非对称网格 / L11 交错瀑布流）       │
│     - 精选案例/作品（card-project 或 L10-bento）          │
│     - 或：客户成功故事（testimonial + 数据结果）           │
│     * 作用：用真实结果证明能力，进一步建立信任               │
├─────────────────────────────────────────────────────────┤
│  ⑤ 价格 / FAQ（L15 双栏对比 / FAQ折叠列表）                │
│     - 价格套餐对比（L15-compare，推荐套餐加金色高亮）       │
│     - 常见问题（FAQ手风琴列表，皇家蓝/金色）                │
│     - 或：活动日程/议程（时间线 L12 或列表）                │
│     * 作用：消除决策疑虑，推动行动                          │
├─────────────────────────────────────────────────────────┤
│  ⑥ 视觉惊喜（可选，L16 画册溢出式 / L8 引文全屏）           │
│     - 一张有冲击力的视觉/金句打破模板感                     │
│     * 作用：制造记忆点，避免千篇一律的 Landing 感           │
├─────────────────────────────────────────────────────────┤
│  ⑦ 结尾 CTA（L13 深色面板 — 必选，页面最强转化点）          │
│     - 深蓝径向渐变背景                                     │
│     - 大标题重申价值主张                                   │
│     - 酒红 CTA 大按钮（btn-cta + btn-xl）                 │
│     - 可选：内嵌简化表单（姓名+邮箱/手机）                  │
│     - 紧迫感文案（"限时"/"仅剩XX名额"/"立即行动"）          │
├─────────────────────────────────────────────────────────┤
│  ⑧ Footer（简洁版，不喧宾夺主）                            │
│     - 品牌Logo + 版权信息                                  │
│     - 必要链接（隐私政策、联系方式）                        │
│     - 社交链接（可选）                                     │
└─────────────────────────────────────────────────────────┘
```

### 结构要点

1. **首屏不超过 100vh**：访客不滚动就能看到完整标题、价值主张和 CTA 按钮
2. **社会证明紧随首屏**：在访客还没决定是否继续往下看时，先建立信任
3. **每个 section 都有不同版式**：交替使用网格/图文/卡片/深色面板，避免"卡片墙"的单调感
4. **CTA 按钮之间不超过 3 屏**：长页面在中段可插入小型 CTA 条或内联按钮
5. **结尾 CTA 必须是视觉最强点**：使用 L13 深色面板，酒红按钮在深蓝背景上形成最强对比
6. **表单尽量精简**：报名页字段不超过 4 个（姓名、手机/邮箱即可），降低行动门槛

---

## 3. 色彩使用指南

Landing 场景严格遵循品牌 55-30-15 色彩比例，但三色的使用侧重与其他场景不同——**酒红承担更重的转化引导职责**。

### 3.1 皇家蓝 `#0A2463`（55%）— 信任与结构色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **导航栏** | 顶部固定导航背景（半透明暖米白 + blur，文字皇家蓝） | 建立品牌识别 |
| **主标题** | h1 Hero大标题、h2 section 标题 | Playfair Display 衬线，墨黑/皇家蓝 |
| **功能卡片标题** | card-feature 的 card-title | 皇家蓝色，建立专业感 |
| **次要按钮** | btn-primary（皇家蓝按钮） | 非主要行动的按钮，如"了解更多" |
| **描边按钮** | btn-outline（皇家蓝描边） | 次要行动、辅助选项 |
| **链接文字** | 正文内链接、FAQ 问题文字 | 皇家蓝默认色，hover 转酒红 |
| **数据数字** | stat-card 的 stat-number | 皇家蓝衬线大数字，权威感 |
| **FAQ/列表图标** | 折叠箭头、列表标记 | 皇家蓝，统一交互色 |

### 3.2 复古金 `#F4D35E`（30%）— 高亮与装饰色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **标签徽章** | badge-gold（"限时"/"推荐"/"New"/"热门"） | 金色背景+皇家蓝文字，吸引目光 |
| **价格高亮** | 折扣价、优惠金额、"省¥XXX" | 金色荧光笔效果或金色文字 |
| **装饰线** | title-gold-line、divider-gold | 品牌签名细节，章节分隔 |
| **装饰序号** | section-number（01, 02, 03...） | Cormorant 斜体金色大数字 |
| **关键词高亮** | h1 中的核心关键词（荧光笔效果） | `linear-gradient(transparent 60%, var(--gold-200) 60%)` |
| **推荐套餐标记** | L15 双栏对比中"推荐"方案的金色边框+阴影 | 引导用户选择目标方案 |
| **星级评分** | testimonial-card 中的五角星 | 金色实心星，增强口碑可信度 |
| **倒计时数字** | 限时活动的倒计时数字（可选） | 金色衬线数字，制造紧迫感 |
| **图标背景** | card-feature 的 card-icon 背景 | 极浅金色 `var(--gold-50)` + 金色图标 |

### 3.3 酒红 `#D8315B`（15%）— 行动与强调色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **主 CTA 按钮** | btn-cta（酒红按钮） | **页面最高优先级按钮**，白色文字+酒红阴影 |
| **价格数字** | 套餐价格、售价 | 酒红色衬线大数字，突出决策关键信息 |
| **紧迫感标记** | "限时"/"仅剩XX名"/"即将截止" | badge-wine 酒红标签，制造紧迫感 |
| **关键强调文字** | 核心卖点中的关键词、痛点词 | 酒红色加粗，让目光停留 |
| **悬停状态** | 链接 hover、卡片 hover 的强调色 | 交互反馈从皇家蓝转酒红 |
| **表单错误提示** | 输入验证失败的提示文字和边框 | 复用酒红作为 error 语义色 |
| **选中状态** | 价格套餐中被选中的方案 | 酒红边框/酒红勾选标记 |
| **折扣标签** | "5折"/"早鸟价"等优惠标签 | 酒红底白字，强烈视觉吸引 |

### 3.4 背景与中性色

| 元素 | 色值 | 说明 |
|------|------|------|
| 页面主背景 | `#FDFBF6` (`var(--cream)`) | 暖米白，不刺眼、不冰冷 |
| 卡片背景 | `#FFFFFF` | 纯白卡片，与暖米白背景形成微妙层次 |
| 交替 section 背景 | `var(--cream-100)` (`#F8F4EB`) | 部分section用极浅暖米色，增加节奏 |
| 深色面板背景 | 皇家蓝深蓝径向渐变 | L13 CTA区、L3分屏Hero左侧 |
| 正文文字 | `var(--ink-100)` (`#2C3347`) | 深灰，非纯墨黑，长阅读舒适 |
| 标题文字 | `var(--ink)` (`#0D1225`) | 墨黑，标题对比强烈 |
| 辅助文字 | `var(--ink-300)` (`#6D7487`) | 说明文字、元信息 |
| 边框/分隔线 | `var(--cream-200)` (`#F0EAD9`) | 暖调边框，不用冷灰 |

### 色彩使用铁律（Landing 场景）

1. **酒红 CTA 是页面中最醒目的元素**：同一屏内不超过 1 个酒红 CTA 按钮，避免焦点分散
2. **金色不大面积使用**：仅用于标签、装饰、高亮，不做区块背景
3. **皇家蓝标题 + 酒红 CTA + 金色标签**是 Landing 的经典三色组合，不要调换角色
4. **价格数字必须用酒红或皇家蓝**（衬线大字号），不能用灰色——价格是决策关键
5. **深色面板（L13）上的 CTA 按钮用金色**：深蓝背景上金色按钮比酒红更醒目（例外情况）
6. **表单焦点状态用皇家蓝**：`box-shadow: 0 0 0 3px var(--royal-50)`，错误状态用酒红
7. **倒计时/紧迫感元素可用酒红+金色组合**：但全页仅 1 处，不能泛滥

---

## 4. 排版规范

### 4.1 Hero 大标题：极端字号对比（核心约束）

Landing 首屏的标题排版是整个页面最重要的排版决策，必须做到**极端字号对比**：

| 指标 | 规范值 | 说明 |
|------|--------|------|
| **h1 字号** | `clamp(2.8rem, 8vw, 5.5rem)` | 桌面端最大可达 88px，移动端不小于 44px |
| h1 字重 | 700/900 | Playfair Display 粗体 |
| h1 行高 | 1.05 | 紧凑，有力量感 |
| h1 字距 | -0.03em | 微缩字距，大标题更紧凑 |
| **副标题字号** | `clamp(1rem, 1.8vw, 1.35rem)` | 与 h1 形成强烈反差 |
| 副标题字体 | Cormorant Garamond italic | 斜体衬线，优雅有温度 |
| 副标题行高 | 1.6 | 舒适阅读 |
| **eyebrow 标签字号** | `0.75rem`（12px） | 全大写，0.15em 字距，极小 |
| CTA 按钮字号 | `1.0625rem` - `1.125rem`（btn-lg/btn-xl） | 足够大，易于点击 |

**字号对比示例**：
```
eyebrow:  12px  ●●● （极小，全大写）
h1:       80px  ●●●●●●●●●●●●●●●●●●●● （极大，衬线粗体）
subtitle: 20px  ●●●●● （中等，斜体衬线）
CTA:      18px  ●●●● （按钮文字，无衬线中粗）
```

> **铁律**：h1 和副标题的字号比例不小于 3:1，eyebrow 和 h1 的比例不小于 1:5。大的要足够大，小的要真的小。

### 4.2 正文排版规范

| 元素 | 字号 | 行高 | 字体 | 颜色 | 说明 |
|------|------|------|------|------|------|
| **正文段落** | `1rem`（16px） | **1.7** | Inter | `var(--ink-100)` | 行高严格 1.7，不小于 1.6 |
| **卡片描述** | `0.9375rem`（15px） | 1.65 | Inter | `var(--ink-200)` | 卡片内文字略小 |
| **引言/金句** | `clamp(1.25rem, 2.5vw, 2rem)` | 1.5 | Cormorant Garamond italic | `var(--royal)` | L8 引文区使用 |
| **价格数字** | `clamp(2rem, 4vw, 3rem)` | 1 | Playfair Display 700 | `var(--wine)` | 酒红色衬线大数字 |
| **数据数字** | `clamp(2rem, 4vw, 3.5rem)` | 1 | Playfair Display 700 | `var(--royal)` | stat-card 用 |
| **标签/徽章** | `0.75rem`（12px） | 1.4 | Inter 500/600 | 品牌色 | 全大写加字距 |
| **按钮文字** | `0.9375rem` - `1.125rem` | 1 | Inter 500 | #fff / 品牌色 | 不使用斜体 |
| **表单标签** | `0.875rem`（14px） | 1.4 | Inter 500 | `var(--ink)` | 表单上方标签 |
| **FAQ 问题** | `1.0625rem`（17px） | 1.5 | Inter 600 | `var(--royal)` | 问题文字加粗 |
| **FAQ 答案** | `0.9375rem`（15px） | 1.7 | Inter 400 | `var(--ink-200)` | 答案常规字重 |

### 4.3 标题层级（Landing 场景适配）

| 层级 | 字体 | 字号 (clamp) | 行高 | 字重 | 颜色 | 装饰 |
|------|------|-------------|------|------|------|------|
| **h1** Hero标题 | Playfair Display | `clamp(2.8rem, 8vw, 5.5rem)` | 1.05 | 700/900 | `var(--ink)` | 关键词金色荧光笔高亮 |
| **h2** Section标题 | Playfair Display | `clamp(1.75rem, 3.5vw, 2.75rem)` | 1.15 | 700 | `var(--ink)` | 金色序号 + title-gold-line |
| **h3** 卡片/子标题 | Playfair Display | `clamp(1.15rem, 2vw, 1.4rem)` | 1.3 | 600 | `var(--royal)` | 无装饰线 |
| **h4** 小标题 | Inter | `1rem` | 1.4 | 600 | `var(--ink)` | 无装饰 |

### 4.4 排版特殊规则

1. **h1 中的关键词使用金色荧光笔高亮**：
   ```css
   .hero-title .highlight {
     position: relative;
     color: var(--royal);
     font-style: italic;
   }
   .hero-title .highlight::after {
     content: '';
     position: absolute;
     bottom: 0.08em;
     left: 0;
     width: 100%;
     height: 0.25em;
     background: var(--gold);
     z-index: -1;
     border-radius: 2px;
   }
   ```

2. **价格排版规则**：
   - 货币符号（¥）字号为价格数字的 50%，垂直对齐顶部
   - 原价使用灰色删除线，字号为折扣价的 60%
   - "省¥XXX" 或折扣标签用金色 `badge-gold`
   - 价格单位（"起"/"/人"/"/月"）用辅助灰色小字

3. **CTA 按钮文字规则**：
   - 以动词开头："立即报名"、"免费试用"、"预约咨询"、"立即购买"
   - 不用"提交"、"确认"、"点击这里"等模糊文字
   - 不超过 6 个汉字，简洁有力
   - 可加箭头图标增强行动感："立即报名 →"

4. **正文段落宽度**：
   - 卡片内描述：不超过 350px
   - 独立说明段落：不超过 550px
   - FAQ 答案：不超过 600px
   - 不使用 L7 教程场景的 680px 窄单栏，Landing 需要更宽的视觉节奏

---

## 5. 推荐布局组合

从 L1-L16 中选取适合 Landing 转化场景的布局，按页面位置推荐如下：

### 5.1 首屏布局（4选1，根据内容类型）

| 布局 | 适用场景 | 视觉特点 | CTA 可见度 |
|------|----------|----------|-----------|
| **L1 非对称图文 Hero** | 个人品牌服务页、咨询服务 | 左侧文字+右侧头像/形象，有温度、个人化 | 高 |
| **L2 居中大字 Hero** | **活动页/分享会首选**、Slogan页 | 居中超大标题，大气权威，一句话价值主张 | 最高 |
| **L3 分屏 Hero** | 产品落地页、App下载页 | 50:50分屏，一侧深色+文字，一侧产品图 | 高 |
| **L4 全屏视觉 Hero** | 高端品牌活动、案例封面 | 全幅背景图+叠加文字，沉浸式画册感 | 中（需确保CTA在图上清晰可见）|

**首屏选择建议**：
- **活动/分享会/报名页** → 首选 **L2 居中大字Hero**（标题冲击力最强，CTA居中聚焦）
- **产品/App介绍** → 首选 **L3 分屏Hero**（展示产品截图）或 **L1 非对称**
- **个人服务页** → 首选 **L1 非对称图文Hero**（展示个人形象，建立信任）
- **高端品牌活动** → 可选 **L4 全屏视觉Hero**（需确保文字在图上对比度足够）

### 5.2 中段内容布局（按需组合）

| 布局 | 用途 | 使用位置 | 节奏密度 |
|------|------|----------|---------|
| **L14 数据统计条** | 社会证明、数据背书 | Hero 正下方 | 密 |
| **L9 三列卡片网格** | 功能特色、核心价值点 | 中段主体 | 密 |
| **L5/L6 图文并排** | 功能详述、服务介绍 | 卡片前后交替使用 | 中等 |
| **L10 非对称网格** | 作品展示、案例精选 | 功能区之后 | 中密 |
| **L15 双栏对比** | 价格套餐、服务对比、Before/After | 决策阶段（FAQ之前） | 中等 |
| **L12 时间线** | 活动日程/议程、课程大纲、活动流程 | 活动页/课程页专属 | 中等 |

### 5.3 视觉惊喜布局（P1加分项，2选1，不超过1个）

| 布局 | 效果 | 使用位置 |
|------|------|----------|
| **L16 画册溢出式** | 艺术感、画册感、专业设计水准，反AI模板感 | 中段靠后（案例展示前后） |
| **L8 引文全屏** | 呼吸感、金句停顿、价值主张强化 | 两段密内容之间，或价格区之前 |

> **重要**：Landing 页建议加入一个视觉惊喜区，避免全页都是规则的卡片和网格而显得像AI模板。

### 5.4 结尾布局（必选）

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **L13 深色面板 CTA** | 页面最终转化点，必选 | 深蓝径向渐变背景 + 白色标题 + 金色或酒红CTA按钮 + 可选内嵌表单 |

### 5.5 经典 Landing 布局配方

#### 配方 A：活动/分享会页（7屏，最常用）

| 顺序 | 布局 | 内容 |
|------|------|------|
| 1 | **L2 居中大字Hero** | 活动名称 + 一句话价值 + "立即报名"CTA |
| 2 | **L14 数据统计条** | 往届参与人数/嘉宾数量/好评率等 |
| 3 | **L5 左图右文** | 活动介绍/嘉宾介绍 |
| 4 | **L9 三列卡片** | 你将收获什么（3-4个核心价值点） |
| 5 | **L12 时间线** | 活动日程/议程安排 |
| 6 | **L8 引文全屏**（可选） | 嘉宾金句/活动主题金句 |
| 7 | **L13 深色面板CTA** | 报名表单 + "立即报名"按钮 |

#### 配方 B：产品/服务落地页（8屏）

| 顺序 | 布局 | 内容 |
|------|------|------|
| 1 | **L3 分屏Hero** 或 **L1 非对称** | 产品名+价值主张+CTA+产品图 |
| 2 | **L14 数据统计条** | 用户数/评分/效果数据 |
| 3 | **L9 三列卡片** | 核心功能特色（3个） |
| 4 | **L6 左文右图** | 功能详述（主要功能） |
| 5 | **L10 非对称网格** | 产品截图/案例展示 |
| 6 | **testimonial-card 区域** | 用户好评（2-3条） |
| 7 | **L15 双栏对比** | 价格套餐 |
| 8 | **L13 深色面板CTA** | 免费试用/注册CTA |

#### 配方 C：报名/注册短页（5屏，精简）

| 顺序 | 布局 | 内容 |
|------|------|------|
| 1 | **L2 居中大字Hero** | 标题+一句话价值+CTA |
| 2 | **L14 数据统计条** | 关键数字建立信任 |
| 3 | **L9 三列卡片**（精简为3个） | 核心价值点 |
| 4 | **testimonial-card**（1-2条） | 简短好评 |
| 5 | **L13 深色面板CTA** | 直接放报名表单+提交按钮 |

### 5.6 布局使用禁忌

| 布局 | Landing 场景不推荐原因 |
|------|----------------------|
| L7 单栏长文 | 过于阅读导向，信息密度低，转化路径长 |
| L11 交错瀑布流 | 适合作品列表页，Landing 中段太松散 |
| 连续两个 L9 网格 | 卡片墙+卡片墙=AI模板感，必须穿插非网格布局 |
| 多个 L13 深色面板 | 深色面板是强节奏元素，全页只在结尾用1次（L3分屏Hero除外） |

---

## 6. 组件选用指南

### 6.1 必用组件（Landing 场景核心组件，缺一不可）

| 组件 | 组件名 | 使用场景 | 使用频率 |
|------|--------|----------|----------|
| **CTA 按钮** | `btn-cta` | 首屏主按钮、结尾CTA、中段内联CTA | 至少2次，长页面3-4次 |
| **功能卡片** | `card-feature` | 核心价值点、功能特色、服务内容 | 3-6个 |
| **数据统计卡** | `stat-card` | Hero下方社会证明数据 | 3-4个 |
| **推荐/口碑卡片** | `card-testimonial` | 用户评价、客户好评、口碑展示 | 2-4个 |
| **深色面板** | `dark-panel` | 结尾CTA区（L13），页面最强转化点 | 1次（结尾必用） |

#### CTA 按钮（`btn-cta`）使用规范

```html
<!-- 首屏主CTA -->
<a href="#signup" class="btn btn-cta btn-lg">立即报名 →</a>

<!-- 结尾CTA（深色面板上用金色按钮） -->
<a href="#signup" class="btn btn-gold btn-xl">免费预约咨询</a>
```

- **btn-cta（酒红）**：浅色背景上的主行动按钮，首屏、中段CTA使用
- **btn-gold（金色）**：深色面板（L13）上的CTA按钮，深蓝背景上金色最醒目
- **按钮尺寸**：首屏用 `btn-lg`，结尾深色面板用 `btn-xl`，中段内联用默认大小
- **按钮宽度**：移动端 CTA 按钮宽度 100%（`width: 100%`），桌面端自适应内容宽度
- **CTA 按钮在同一屏内只出现 1 次**，避免用户决策犹豫

#### 功能卡片（`card-feature`）使用规范

```html
<div class="card card-feature reveal">
  <div class="card-icon">✦</div>
  <h3 class="card-title">系统化设计</h3>
  <p class="card-desc">从策略到落地的完整设计体系，不只是好看的界面。</p>
</div>
```

- 用于展示核心价值点，通常 3-4 个为一组（L9 三列网格）
- 每个卡片必须包含：图标（card-icon）+ 标题（card-title）+ 描述（card-desc）
- 图标使用简单几何符号（✦ ◆ ● ◇ ■）或线性图标，不使用emoji
- 卡片 hover 效果：上移 4px + 阴影加深 + 顶部三色渐变条显示
- **不要在卡片内放按钮**，卡片描述末尾可加 `card-link` 文字链接

#### 数据统计卡（`stat-card`）使用规范

```html
<section class="L14-stats">
  <div class="container">
    <div class="L14-grid">
      <div class="stat-card"><span class="stat-number">500+</span><span class="stat-label">参与者</span></div>
      <div class="stat-card"><span class="stat-number">12</span><span class="stat-label">位嘉宾</span></div>
      <div class="stat-card"><span class="stat-number">98%</span><span class="stat-label">好评率</span></div>
      <div class="stat-card"><span class="stat-number">5</span><span class="stat-label">届沉淀</span></div>
    </div>
  </div>
</section>
```

- 放置在 Hero 首屏正下方，第一时间建立信任
- 3-4 个数据为宜，不超过 4 个
- 数字必须具体、可信（"500+"优于"数千"，"98%"优于"很高"）
- 数字用 Playfair Display 衬线皇家蓝大字体
- L14 背景用白色（`#fff`），与暖米白页面背景形成层次区分

#### 推荐/口碑卡片（`card-testimonial`）使用规范

```html
<div class="card card-testimonial">
  <div class="testimonial-stars">★★★★★</div>
  <p class="testimonial-text">参加完分享会后，我对个人品牌有了全新的认识，当天晚上就重新梳理了自己的定位。</p>
  <div class="testimonial-author">
    <div class="author-avatar">李</div>
    <div>
      <div class="author-name">李女士</div>
      <div class="author-title">某互联网公司 · 产品经理</div>
    </div>
  </div>
</div>
```

- 用于社会证明区域，展示真实用户评价
- Cormorant Garamond 斜体引文字体，有人文温度
- 必须包含：星级 + 评价文字 + 头像/姓氏 + 姓名 + 身份/公司
- 2-4 条为宜，排列方式：桌面端 2-3 列，移动端单列
- 如果有客户头像照片，用真实头像替换字母头像效果更好
- 推荐语不超过 60 字，简短有力

#### 深色面板（`dark-panel`）使用规范

```html
<div class="dark-panel">
  <span class="eyebrow" style="background:rgba(244,211,94,0.15);color:var(--gold);">限时报名</span>
  <h2>准备好加入我们了吗？</h2>
  <p>早鸟票仅剩最后 20 个名额，立即锁定你的席位。</p>
  <!-- 可选：内嵌精简表单 -->
  <div class="cta-form">
    <input type="text" class="form-input" placeholder="您的姓名">
    <input type="tel" class="form-input" placeholder="手机号码">
    <button class="btn btn-gold btn-xl">立即报名</button>
  </div>
</div>
```

- 全页仅在结尾使用 1 次（L3分屏Hero的深色侧不算）
- 背景：皇家蓝深蓝径向渐变 + 右上角微弱金色光晕
- 标题白色，描述文字用 `rgba(255,255,255,0.7)`
- CTA 按钮用 **金色**（`btn-gold`），深蓝背景上金色比酒红更醒目
- 可内嵌精简表单（姓名+手机/邮箱，不超过3个字段），减少跳转流失
- 可加紧迫感文案："限时"/"仅剩XX名额"/"早鸟价即将截止"

### 6.2 推荐组件（按需使用）

| 组件 | 使用场景 |
|------|----------|
| `btn-primary`（皇家蓝主按钮） | 次要行动，如"了解更多"、"查看议程" |
| `btn-outline`（描边按钮） | 辅助选项，如"查看详情"（与btn-cta并列时使用） |
| `badge-gold` / `badge-wine` | "限时"/"推荐"/"New"/"热门"/"早鸟"等标签 |
| `list-check`（金色勾选列表） | 套餐包含内容、你将获得什么、权益清单 |
| `list-gold-dot`（金色圆点列表） | 要点列举、功能说明、议程条目 |
| `form-input` + `form-label` | 报名表单、预约表单、邮件订阅 |
| `section-title`（含金色序号） | 每个内容section的标题区 |
| `navbar`（固定导航） | 所有Landing页必备，含品牌Logo+导航链接+CTA按钮 |
| `divider-gold` | section之间的金色渐变分隔线 |
| `brand-table` | 套餐对比表格（比L15更复杂的对比场景） |

### 6.3 Landing 场景专属组件模式

#### 价格展示组合

```html
<div class="price-block">
  <span class="price-original"><s>¥599</s></span>
  <span class="price-current">¥<strong>299</strong></span>
  <span class="price-unit">/人</span>
  <span class="badge badge-gold">早鸟5折</span>
</div>
```
```css
.price-current {
  font-family: var(--font-serif);
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 700;
  color: var(--wine);
  line-height: 1;
}
.price-current strong { font-size: 1.4em; }
.price-original {
  font-size: 1rem;
  color: var(--ink-300);
  text-decoration: line-through;
  margin-right: var(--sp-2);
}
```

#### 简化内嵌表单（深色面板内）

```css
.cta-form {
  display: flex;
  gap: var(--sp-3);
  max-width: 480px;
  margin: var(--sp-6) auto 0;
  flex-wrap: wrap;
}
.cta-form .form-input {
  flex: 1;
  min-width: 140px;
  background: rgba(255,255,255,0.1);
  border-color: rgba(255,255,255,0.2);
  color: #fff;
}
.cta-form .form-input::placeholder { color: rgba(255,255,255,0.5); }
.cta-form .form-input:focus {
  border-color: var(--gold);
  box-shadow: 0 0 0 3px rgba(244,211,94,0.15);
}
```

#### Logo墙（社会证明补充）

```html
<div class="logo-wall">
  <p class="caption-text" style="text-align:center;margin-bottom:var(--sp-5);">他们都参加过</p>
  <div class="logo-grid">
    <div class="logo-item">某某科技</div>
    <div class="logo-item">某某集团</div>
    <div class="logo-item">某某工作室</div>
    <!-- 更多Logo -->
  </div>
</div>
```
```css
.logo-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  gap: var(--sp-8);
  opacity: 0.5;
}
.logo-item {
  font-family: var(--font-serif);
  font-size: 1.125rem;
  color: var(--ink-200);
  filter: grayscale(1);
}
```

### 6.4 不推荐组件

| 组件 | 不推荐原因 |
|------|-----------|
| `code-block` | Landing页无代码展示场景 |
| `progress`（技能进度条） | 个人About页用，Landing转化页不需要 |
| `alert-success`/`alert-info` | 提示框用于教程/后台，Landing用badge和卡片替代 |
| `pull-quote`（大型引用块） | 用 L8 引文全屏布局替代，更有冲击力 |

---

## 7. 特殊注意事项

### 7.1 CTA 按钮至少出现 2 次（铁律）

| 位置 | 按钮样式 | 文案建议 |
|------|----------|---------|
| **首屏 Hero 区** | `btn-cta btn-lg`（酒红大按钮） | "立即报名"、"免费试用"、"预约咨询" |
| **中段内联**（可选） | `btn-cta` 或 `btn-primary` | 卡片底部、FAQ之后、段落后内联 |
| **结尾深色面板** | `btn-gold btn-xl`（金色特大按钮） | 与首屏相同文案，或更强行动号召 |

**CTA 按钮文案公式**：
- 动词 + 明确行动 + 紧迫感（可选）
- 好："立即报名"、"免费预约咨询"、"锁定早鸟席位"
- 差："提交"、"确认"、"点击这里"、"开始"

### 7.2 首屏必须有明确价值主张

首屏在 3 秒内必须让访客明白：

1. **这是什么**（eyebrow 标签 + h1 标题）
   - 例：`<span class="eyebrow">2026 设计分享会</span>`
   - 例：`<h1>设计的温度</h1>`

2. **对我有什么价值**（副标题，一句话）
   - 例：`<p class="L2-subtitle">当AI可以生成一切，人的审美判断才是最稀缺的能力。</p>`
   - 不超过 25 个汉字，Cormorant Garamond 斜体
   - 回答"我为什么要参加/购买/注册"

3. **我该做什么**（CTA 按钮）
   - 例：`<a href="#signup" class="btn btn-cta btn-lg">立即报名 →</a>`
   - 按钮在首屏可见，不需要滚动就能看到

### 7.3 必须有社会证明区域

Landing 页不能只有"自卖自夸"，必须有第三方信任背书。可选择以下形式**至少一种**：

| 形式 | 适用场景 | 推荐度 |
|------|----------|--------|
| **数据统计（L14 stat-card）** | 所有Landing页通用 | ★★★★★ |
| **用户评价（testimonial-card）** | 课程/服务/活动 | ★★★★★ |
| **合作品牌Logo墙** | B2B服务、企业活动 | ★★★★ |
| **名人/专家推荐** | 高端活动、课程 | ★★★★ |
| **媒体报道引用** | 产品发布、品牌活动 | ★★★ |
| **真实数据结果** | 产品落地页（如"转化率提升37%"） | ★★★★ |

**社会证明放置位置**：首屏 Hero 下方（L14 数据条），以及案例展示之后（testimonial 卡片）。

### 7.4 导航栏规范

Landing 页导航栏应精简，不超过 5 个链接：

```html
<nav class="navbar">
  <a href="#" class="nav-logo">Feihong<span style="color:var(--gold)">.</span></a>
  <div class="nav-links">
    <a href="#about" class="nav-link">活动介绍</a>
    <a href="#speakers" class="nav-link">嘉宾</a>
    <a href="#schedule" class="nav-link">日程</a>
    <a href="#faq" class="nav-link">FAQ</a>
    <a href="#signup" class="btn btn-cta btn-sm">立即报名</a>
  </div>
</nav>
```

- 导航栏右侧始终放一个小型 CTA 按钮（`btn-cta btn-sm`），方便随时转化
- 固定顶部（`position: fixed`），滚动时加毛玻璃效果和底部边框
- 移动端收起为汉堡菜单，菜单底部放 CTA 按钮
- Logo 点击返回页面顶部

### 7.5 表单设计规范

Landing 页表单直接影响转化率，必须遵循：

1. **字段越少越好**：
   - 活动报名：姓名 + 手机（2个字段）
   - 产品注册：邮箱 + 密码（或仅邮箱）
   - 咨询预约：姓名 + 手机 + 需求描述（3个字段）
   - **绝对不要超过 4 个字段**

2. **表单验证品牌化**：
   - 输入框 focus 状态：皇家蓝边框 + 皇家蓝光晕
   - 错误状态：酒红边框 + 酒红色错误提示文字（不用浏览器默认提示）
   - 成功状态：金色边框/金色勾选标记
   - 不使用浏览器默认的 `alert()` 弹窗

3. **提交按钮状态**：
   - 默认：酒红 CTA 按钮
   - 提交中：按钮变灰 + "提交中..." 文字 + loading 动画（可选）
   - 成功：金色边框 + "提交成功 ✓" 文字
   - 提交按钮在表单验证通过前保持禁用状态（`opacity: 0.6`）

### 7.6 紧迫感营造（不廉价）

Landing 页可以适当营造紧迫感，但不能像微商甩卖：

**正确做法**：
- 金色"早鸟票"标签 + 价格对比（原价划掉+折扣价）
- "仅剩 XX 个名额"的小标签（用真实数据）
- 倒计时组件（仅在确实有限时活动时使用，数字用金色衬线字体）
- 深色面板中用金色 eyebrow 标签写"限时报名"

**错误做法**：
- 满屏闪烁的"仅剩最后3个！"
- 多个红色感叹号和爆炸贴效果
- 虚假倒计时（每次刷新重置）
- "不买就亏了"式的低俗营销文案

### 7.7 移动端适配要点

1. **首屏 CTA 按钮宽度 100%**，放在屏幕下半区，拇指热区内
2. **表单字段单列**，输入框高度 ≥ 48px（触摸友好）
3. **导航栏折叠**为汉堡菜单，菜单内包含 CTA 按钮
4. **L14 数据统计改为2列**，数字字号适当缩小
5. **卡片网格改为单列**，L9 三列→单列，L10 非对称网格→单列
6. **价格数字**不要缩小到看不清，移动端价格字号 `clamp(1.75rem, 8vw, 2.5rem)`
7. **所有触摸目标 ≥ 44×44px**，按钮内边距足够大
8. **首屏不使用 100vh**（移动端浏览器地址栏会导致溢出），改用 `min-height: 85vh`

---

## 8. 场景专属 Checklist

在交付任何 Landing/活动页之前，必须通过以下检查：

### P0 — 必须通过（缺一不可，直接影响转化）

- [ ] **首屏有 CTA 按钮**：访客不需要滚动就能看到行动按钮，按钮使用 `btn-cta`（酒红）
- [ ] **价值主张一句话说清**：首屏副标题不超过 25 个字，3 秒内让访客明白"这对我有什么用"
- [ ] **表单入口清晰**：报名/注册表单字段不超过 4 个，提交按钮醒目，表单验证有品牌化样式
- [ ] **CTA 按钮至少出现 2 次**：首屏 1 次 + 结尾深色面板 1 次，长页面 3-4 次
- [ ] **结尾使用 L13 深色面板**：深蓝径向渐变背景 + CTA 按钮，作为页面最强转化点
- [ ] **首屏标题使用极端字号对比**：h1 衬线超大字号（≥48px桌面端），与副标题/标签形成强烈反差
- [ ] **社会证明区域存在**：至少有一种信任背书（数据/评价/Logo墙），放置在首屏下方
- [ ] **三种品牌色严格为 `#0A2463` / `#F4D35E` / `#D8315B`**
- [ ] **酒红色仅用于 CTA 按钮、价格、紧迫感标记**，不大面积使用
- [ ] **页面背景为暖米白 `#FDFBF6`**，不使用纯白或冷灰背景
- [ ] **衬线+无衬线混搭策略**：标题 Playfair Display，正文 Inter，引言/副标题 Cormorant Garamond italic
- [ ] **正文行高 1.7**，卡片描述行高 1.65，标题行高 1.05-1.2
- [ ] **导航栏固定顶部**，右侧有小型 CTA 按钮，移动端有汉堡菜单
- [ ] **所有链接、按钮、表单经过品牌化处理**，不保留浏览器默认样式
- [ ] **响应式适配**：移动端单列布局，CTA 按钮全宽，触摸目标 ≥ 44px
- [ ] **价格数字使用酒红衬线大字体**，不是灰色小字
- [ ] **不出现禁忌清单中的元素**（纯黑/纯白大面积、冷灰、AI光效、bounce动画等）

### P1 — 应该通过（尽量满足，影响质感和转化）

- [ ] **社会证明区域内容真实可信**：数字具体（"500+"而非"数千"），评价有真实姓名和身份
- [ ] **至少一个视觉惊喜 section**：L16 画册溢出式或 L8 引文全屏，打破模板感
- [ ] **每个 section 使用不同布局**：不连续使用两个相同类型的网格/卡片布局
- [ ] **金色装饰线/序号形成品牌签名感**：section-title 有金色序号和装饰线
- [ ] **功能卡片有 hover 效果**：上移 + 阴影 + 顶部三色渐变条
- [ ] **CTA 按钮文案以动词开头**："立即报名"而非"提交"，"免费试用"而非"开始"
- [ ] **关键词有金色荧光笔高亮**：h1 中的核心词、正文内的重要术语
- [ ] **推荐/口碑卡片使用 Cormorant Garamond 斜体**，有人文温度
- [ ] **深色面板 CTA 使用金色按钮**（而非酒红），深蓝背景上金色最醒目
- [ ] **套餐对比中推荐方案有金色高亮**：金色边框 + `badge-gold`"推荐"标签
- [ ] **FAQ 区域存在**（长页面）：解答常见疑问，消除决策障碍
- [ ] **选中文本背景为金色**：`::selection { background: var(--gold); color: var(--royal); }`
- [ ] **有 Scroll Reveal 入场动画**，但轻、慢、克制（300-600ms，ease-out），不影响阅读

### P2 — 加分项（锦上添花，提升专业度）

- [ ] **动效克制优雅**：没有bounce/弹性动画，没有无限循环动画，尊重 `prefers-reduced-motion`
- [ ] **表单验证有实时反馈**：输入时即时验证，错误提示用酒红，成功用金色
- [ ] **有倒计时组件**（限时活动）：金色衬线数字，真实倒计时（非虚假刷新重置）
- [ ] **导航栏滚动时样式变化**：从透明变为毛玻璃+边框
- [ ] **CTA 按钮有微动画**：hover 时上移 1px + 阴影加深
- [ ] **价格有对比展示**：原价灰色删除线 + 折扣价酒红突出 + 金色折扣标签
- [ ] **深色面板内嵌精简表单**：减少跳转环节，直接在CTA区完成转化
- [ ] **有合作品牌 Logo 墙**：增强B2B信任度
- [ ] **页面加载性能良好**：图片压缩，字体预加载，首屏内容快速呈现
- [ ] **IP形象/头像在合适位置自然出现**，强化个人品牌感（个人Landing页）
- [ ] **有页面加载/过渡的细腻动效**：如内容渐入、按钮反馈，但不喧宾夺主

### 交付前自检三问

1. **转化路径是否清晰**：访客从进入页面到完成行动，需要几次点击？有没有任何分散注意力的元素？
2. **信任感是否足够**：如果我是第一次看到这个页面，我会放心填写手机号/付款吗？社会证明够不够？
3. **品牌气质是否到位**：看起来像一个有品质的品牌做的活动，还是像微商甩卖页？有没有廉价营销感？

---

## 附录：Landing 页面快速模板结构

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>活动名称 · 飞鸿</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400;1,600&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    /* === Brand Tokens === */
    :root {
      --royal: #0A2463; --gold: #F4D35E; --wine: #D8315B;
      --cream: #FDFBF6; --ink: #0D1225;
      --font-serif: 'Playfair Display', 'Noto Serif SC', Georgia, serif;
      --font-sans: 'Inter', 'Noto Sans SC', -apple-system, sans-serif;
      --font-display: 'Cormorant Garamond', 'Noto Serif SC', Georgia, serif;
      --r-lg: 12px; --r-xl: 20px;
      --sp-3: 0.75rem; --sp-4: 1rem; --sp-5: 1.5rem; --sp-6: 2rem; --sp-8: 3rem;
      --shadow-md: 0 4px 16px rgba(10,36,99,0.10);
      --shadow-lg: 0 8px 32px rgba(10,36,99,0.12);
      --shadow-wine: 0 4px 20px rgba(216,49,91,0.25);
      --ease: cubic-bezier(0.16, 1, 0.3, 1);
      --container: min(1200px, 92vw);
    }
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; -webkit-text-size-adjust: 100%; }
    body {
      font-family: var(--font-sans);
      background: var(--cream);
      color: var(--ink);
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
    }
    ::selection { background: var(--gold); color: var(--royal); }
    .container { max-width: var(--container); margin: 0 auto; padding: 0 var(--sp-4); }

    /* === Navbar === */
    .navbar {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: var(--sp-3) clamp(var(--sp-4), 4vw, var(--sp-8));
      background: rgba(253,251,246,0.85); backdrop-filter: blur(12px);
      transition: all 350ms var(--ease);
    }
    .navbar.scrolled { border-bottom: 1px solid #F0EAD9; box-shadow: 0 1px 8px rgba(10,36,99,0.06); }
    .nav-logo { font-family: var(--font-serif); font-size: 1.5rem; font-weight: 700; color: var(--royal); text-decoration: none; }
    .nav-links { display: flex; align-items: center; gap: var(--sp-6); }
    .nav-link { font-size: 0.9375rem; color: #2C3347; text-decoration: none; transition: color 0.2s; }
    .nav-link:hover { color: var(--royal); }

    /* === Buttons === */
    .btn {
      display: inline-flex; align-items: center; justify-content: center; gap: 0.5rem;
      font-family: var(--font-sans); font-size: 0.9375rem; font-weight: 500;
      padding: var(--sp-3) var(--sp-5); border-radius: 8px; border: none;
      cursor: pointer; text-decoration: none; transition: all 0.2s; white-space: nowrap;
    }
    .btn-cta { background: var(--wine); color: #fff; box-shadow: var(--shadow-wine); }
    .btn-cta:hover { background: #AD2749; transform: translateY(-1px); box-shadow: 0 6px 24px rgba(216,49,91,0.35); }
    .btn-gold { background: var(--gold); color: var(--royal); font-weight: 600; }
    .btn-gold:hover { background: #DDB52E; color: #fff; transform: translateY(-1px); }
    .btn-lg { padding: var(--sp-4) var(--sp-6); font-size: 1.0625rem; }
    .btn-xl { padding: var(--sp-5) var(--sp-8); font-size: 1.125rem; }
    .btn-sm { padding: 0.5rem var(--sp-4); font-size: 0.8125rem; }

    /* === Hero (L2 居中大字) === */
    .L2-hero {
      min-height: 85vh; display: flex; flex-direction: column;
      align-items: center; justify-content: center; text-align: center;
      padding: 6rem var(--sp-4) 4rem; position: relative;
    }
    .eyebrow {
      display: inline-block; font-size: 0.75rem; font-weight: 500;
      letter-spacing: 0.15em; text-transform: uppercase;
      color: var(--royal); background: #EEF1FA;
      padding: 0.25rem 0.75rem; border-radius: 4px; margin-bottom: var(--sp-3);
    }
    .L2-title {
      font-family: var(--font-serif); font-size: clamp(2.8rem, 8vw, 5.5rem);
      font-weight: 700; line-height: 1.05; color: var(--ink);
      margin: var(--sp-4) 0; letter-spacing: -0.03em;
    }
    .L2-title .highlight { position: relative; color: var(--royal); font-style: italic; }
    .L2-title .highlight::after {
      content: ''; position: absolute; bottom: 0.08em; left: 0;
      width: 100%; height: 0.25em; background: var(--gold);
      z-index: -1; border-radius: 2px;
    }
    .L2-subtitle {
      font-family: var(--font-display); font-size: clamp(1rem, 1.8vw, 1.35rem);
      font-style: italic; color: #4C546A; line-height: 1.6;
      max-width: 500px; margin: 0 0 var(--sp-8);
    }

    /* === Stats (L14) === */
    .L14-stats { padding: var(--sp-8) var(--sp-4); background: #fff; border-top: 1px solid #F0EAD9; border-bottom: 1px solid #F0EAD9; }
    .L14-grid { display: grid; grid-template-columns: repeat(4, 1fr); max-width: var(--container); margin: 0 auto; }
    .stat-card { text-align: center; padding: var(--sp-6) var(--sp-4); position: relative; }
    .stat-card::after { content: ''; position: absolute; right: 0; top: 20%; height: 60%; width: 1px; background: #F0EAD9; }
    .stat-card:last-child::after { display: none; }
    .stat-number { font-family: var(--font-serif); font-size: clamp(2rem, 4vw, 3.5rem); font-weight: 700; color: var(--royal); line-height: 1; display: block; }
    .stat-label { font-size: 0.875rem; color: #6D7487; margin-top: var(--sp-2); display: block; }

    /* === Section Title === */
    .section { padding: clamp(var(--sp-8), 8vw, 6rem) var(--sp-4); }
    .section-title { text-align: center; margin-bottom: var(--sp-8); }
    .section-number { font-family: var(--font-display); font-size: clamp(1.5rem, 3vw, 2.5rem); font-style: italic; color: var(--gold); display: block; margin-bottom: var(--sp-2); }
    .section-title h2 { font-family: var(--font-serif); font-size: clamp(1.75rem, 3.5vw, 2.75rem); font-weight: 700; color: var(--ink); margin: 0 0 var(--sp-3); }
    .title-gold-line { width: 60px; height: 2px; background: linear-gradient(90deg, var(--gold), transparent); margin: 0 auto; }

    /* === Feature Cards (L9) === */
    .L9-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; }
    .card { background: #fff; border-radius: var(--r-lg); padding: var(--sp-6); transition: all 350ms var(--ease); position: relative; overflow: hidden; border: 1px solid #F0EAD9; }
    .card-feature::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px; background: linear-gradient(90deg, var(--royal), var(--gold), var(--wine)); opacity: 0; transition: opacity 350ms var(--ease); }
    .card-feature:hover { transform: translateY(-4px); box-shadow: var(--shadow-lg); border-color: #FAEBA3; }
    .card-feature:hover::before { opacity: 1; }
    .card-icon { font-size: 1.75rem; color: var(--gold); margin-bottom: var(--sp-4); display: inline-flex; width: 48px; height: 48px; align-items: center; justify-content: center; background: #FEFCF0; border-radius: var(--r-lg); }
    .card-title { font-family: var(--font-serif); font-size: 1.25rem; font-weight: 600; color: var(--royal); margin: 0 0 var(--sp-2); }
    .card-desc { font-size: 0.9375rem; line-height: 1.65; color: #4C546A; margin: 0; }

    /* === Testimonials === */
    .testimonial-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; }
    .card-testimonial { background: var(--cream); }
    .testimonial-stars { color: var(--gold); font-size: 1rem; letter-spacing: 2px; margin-bottom: var(--sp-3); }
    .testimonial-text { font-family: var(--font-display); font-size: 1.0625rem; font-style: italic; line-height: 1.7; color: #2C3347; margin: 0 0 var(--sp-5); }
    .testimonial-author { display: flex; align-items: center; gap: var(--sp-3); }
    .author-avatar { width: 40px; height: 40px; border-radius: 50%; background: var(--royal); color: #fff; display: flex; align-items: center; justify-content: center; font-family: var(--font-serif); font-weight: 600; }
    .author-name { font-weight: 600; font-size: 0.9375rem; color: var(--ink); }
    .author-title { font-size: 0.8125rem; color: #6D7487; }

    /* === Dark Panel CTA (L13) === */
    .dark-panel {
      background: radial-gradient(ellipse at top left, #081C4F 0%, var(--ink) 70%);
      border-radius: var(--r-xl); padding: clamp(var(--sp-8), 8vw, 5rem);
      color: #fff; text-align: center; position: relative; overflow: hidden;
    }
    .dark-panel::before {
      content: ''; position: absolute; width: 400px; height: 400px; border-radius: 50%;
      background: radial-gradient(circle, rgba(244,211,94,0.08), transparent 70%);
      top: -100px; right: -100px;
    }
    .dark-panel > * { position: relative; z-index: 1; }
    .dark-panel .eyebrow { background: rgba(244,211,94,0.15); color: var(--gold); }
    .dark-panel h2 { font-family: var(--font-serif); font-size: clamp(1.75rem, 3.5vw, 2.75rem); color: #fff; margin: var(--sp-3) 0 var(--sp-4); }
    .dark-panel p { font-size: 1.0625rem; color: rgba(255,255,255,0.7); line-height: 1.7; max-width: 500px; margin: 0 auto var(--sp-6); }

    /* === Footer === */
    .footer { background: var(--ink); color: #fff; padding: var(--sp-8) var(--sp-4) var(--sp-6); margin-top: var(--sp-8); text-align: center; }
    .footer p { font-size: 0.8125rem; color: rgba(255,255,255,0.4); }

    /* === Reveal Animation === */
    .reveal { opacity: 0; transform: translateY(30px); transition: opacity 700ms var(--ease), transform 700ms var(--ease); }
    .reveal.visible { opacity: 1; transform: translateY(0); }
    .reveal-delay-1 { transition-delay: 100ms; }
    .reveal-delay-2 { transition-delay: 200ms; }

    /* === Responsive === */
    @media (max-width: 768px) {
      .nav-links .nav-link { display: none; }
      .L14-grid { grid-template-columns: repeat(2, 1fr); gap: var(--sp-6); }
      .stat-card::after { display: none; }
      .L9-grid, .testimonial-grid { grid-template-columns: 1fr; }
      .btn-cta, .btn-gold { width: 100%; }
    }
    @media (prefers-reduced-motion: reduce) {
      .reveal { opacity: 1; transform: none; }
      html { scroll-behavior: auto; }
    }
  </style>
</head>
<body>
  <!-- Navbar -->
  <nav class="navbar" id="navbar">
    <a href="#" class="nav-logo">Feihong<span style="color:var(--gold)">.</span></a>
    <div class="nav-links">
      <a href="#about" class="nav-link">介绍</a>
      <a href="#value" class="nav-link">收获</a>
      <a href="#reviews" class="nav-link">评价</a>
      <a href="#signup" class="btn btn-cta btn-sm">立即报名</a>
    </div>
  </nav>

  <!-- ① Hero (L2) -->
  <section class="L2-hero" id="hero">
    <span class="eyebrow">2026 设计分享会</span>
    <h1 class="L2-title">设计的<span class="highlight">温度</span></h1>
    <p class="L2-subtitle">当AI可以生成一切，<br>人的审美判断才是最稀缺的能力。</p>
    <a href="#signup" class="btn btn-cta btn-lg">立即报名 →</a>
  </section>

  <!-- ② 社会证明 (L14) -->
  <section class="L14-stats">
    <div class="L14-grid">
      <div class="stat-card"><span class="stat-number">500+</span><span class="stat-label">往届参与者</span></div>
      <div class="stat-card"><span class="stat-number">12</span><span class="stat-label">位行业嘉宾</span></div>
      <div class="stat-card"><span class="stat-number">98%</span><span class="stat-label">好评率</span></div>
      <div class="stat-card"><span class="stat-number">5</span><span class="stat-label">届沉淀</span></div>
    </div>
  </section>

  <!-- ③ 核心价值 (L9) -->
  <section class="section" id="value">
    <div class="container">
      <div class="section-title">
        <span class="section-number">01</span>
        <h2>你将收获什么</h2>
        <div class="title-gold-line"></div>
      </div>
      <div class="L9-grid">
        <div class="card card-feature reveal">
          <div class="card-icon">✦</div>
          <h3 class="card-title">系统化思维</h3>
          <p class="card-desc">从品牌策略到视觉落地的完整方法论，不只是零散的技巧。</p>
        </div>
        <div class="card card-feature reveal reveal-delay-1">
          <div class="card-icon">◆</div>
          <h3 class="card-title">实战案例解析</h3>
          <p class="card-desc">深度拆解5个真实品牌项目，理解决策背后的思考过程。</p>
        </div>
        <div class="card card-feature reveal reveal-delay-2">
          <div class="card-icon">●</div>
          <h3 class="card-title">高质量人脉</h3>
          <p class="card-desc">与12位行业嘉宾和500+设计师面对面交流，建立优质连接。</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ④ 用户评价 -->
  <section class="section" id="reviews" style="background:#F8F4EB;">
    <div class="container">
      <div class="section-title">
        <span class="section-number">02</span>
        <h2>往届参与者怎么说</h2>
        <div class="title-gold-line"></div>
      </div>
      <div class="testimonial-grid">
        <div class="card card-testimonial reveal">
          <div class="testimonial-stars">★★★★★</div>
          <p class="testimonial-text">参加完分享会，我对个人品牌有了全新认识，当晚就重新梳理了定位。</p>
          <div class="testimonial-author">
            <div class="author-avatar">李</div>
            <div><div class="author-name">李女士</div><div class="author-title">产品经理</div></div>
          </div>
        </div>
        <div class="card card-testimonial reveal reveal-delay-1">
          <div class="testimonial-stars">★★★★★</div>
          <p class="testimonial-text">飞鸿老师的分享既有理论高度又有实操价值，受益匪浅。</p>
          <div class="testimonial-author">
            <div class="author-avatar">张</div>
            <div><div class="author-name">张先生</div><div class="author-title">创业公司CEO</div></div>
          </div>
        </div>
        <div class="card card-testimonial reveal reveal-delay-2">
          <div class="testimonial-stars">★★★★★</div>
          <p class="testimonial-text">认识了很多优秀的同行，这本身就值回票价。</p>
          <div class="testimonial-author">
            <div class="author-avatar">王</div>
            <div><div class="author-name">王女士</div><div class="author-title">自由设计师</div></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ⑦ 结尾 CTA (L13) -->
  <section class="section" id="signup">
    <div class="container">
      <div class="dark-panel">
        <span class="eyebrow">限时早鸟票</span>
        <h2>准备好加入我们了吗？</h2>
        <p>早鸟票仅剩最后 20 个名额，立即锁定你的席位。</p>
        <a href="#" class="btn btn-gold btn-xl">立即报名 →</a>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="footer">
    <p>© 2026 Feihong Design. All rights reserved.</p>
  </footer>

  <script>
    // Navbar scroll effect
    window.addEventListener('scroll', () => {
      document.getElementById('navbar').classList.toggle('scrolled', window.scrollY > 20);
    });
    // Scroll reveal
    const revealEls = document.querySelectorAll('.reveal');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); }});
    }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });
    revealEls.forEach(el => observer.observe(el));
  </script>
</body>
</html>
```

---

## 场景定位

Landing Page/活动页/报名页是以单一转化目标为核心的营销页面，用于活动报名、产品发布、课程销售、预约咨询等需要访客立即行动的场景。适用于：线上/线下活动报名、新产品发布、课程/训练营招生、服务预约、限时优惠、众筹预热。不适用于：内容型网站（信息浏览为主）、企业官网（多入口多目标）、后台系统（功能操作）、作品集（作品展示为主）。核心原则是"一个页面，一个目标"——所有元素服务于转化，情绪层层递进，CTA贯穿始终。

## 推荐节奏（Section 序列）

### 方案 A：经典活动报名型（7-8屏，最常用）
1. Hero（L2 居中大字 / L3 分屏）— 一句话价值主张+主CTA，3秒说清"这是什么、对我有什么用"
2. 社会证明（L14 数据统计条）— 关键数字建立初步信任（人数/好评率/届数）
3. 核心价值（L9 三列卡片）— 3个收获点，说明"你能得到什么"
4. 内容/议程（L7 单栏长文 / L12 时间线）— 详细内容介绍，降低信息不对称
5. 用户评价（card-testimonial组）— 真实反馈，消除决策疑虑
6. 价格/套餐（L15 双栏对比，可选）— 如有付费，推荐方案金色高亮
7. FAQ（折叠面板，可选）— 解答最后疑虑
8. CTA收口（L13 深色面板）— 最强行动号召，酒红/金色按钮+紧迫感文案

### 方案 B：产品发布型（6屏）
1. Hero（L4 全屏视觉）— 产品大图+核心卖点，视觉冲击
2. 痛点共鸣（L7 单栏长文/L5左图右文）— 描述用户痛点，建立共情
3. 解决方案（L9 三列功能卡片）— 产品如何解决问题
4. 产品展示（L16 画册溢出式 / L8图文交错）— 产品细节/使用场景
5. 信任背书（L14 数据+Logo墙+评价）— 数据+客户Logo+用户证言
6. CTA（L13 深色面板）— 立即购买/预约/试用

### 方案 C：极简引流型（4-5屏，冷启动/预热）
1. Hero（L2 居中大字）— 悬念式标题+极简副标题
2. 痛点/机会（L6 深色面板）— 一句话戳中痛点或描述机会
3. 解决方案简述（L5 左图右文）— 简要说明提供什么
4. 早鸟/预约CTA（L13 深色面板）— 邮箱/手机号收集
5. Footer（社交链接）

### 方案 D：长文案销售型（10+屏，高客单价产品）
1. Hero（L2 居中大字）— 强情绪标题，引发好奇
2. 痛点放大（L6 深色面板）— 深入描述问题的严重性
3. 共鸣故事（L7 单栏长文）— 创始人/用户故事，建立信任
4. 方案提出（L5 左图右文）— 引出产品/服务
5. 价值拆解（L9 三列卡片×2组）— 详细价值点
6. 社会证明（评价+数据+Logo墙）— 多维度信任
7. 价格锚定（L15 对比+L14数据）— 价格展示+价值对比
8. 风险逆转（L6 深色面板）— 退款保证/无效退款
9. FAQ（折叠面板）— 消除最后疑虑
10. CTA（L13 深色面板）— 最终行动号召+紧迫感

## 专属装饰手法（Signature Touches）

- **#05 Highlight 荧光笔高亮**：Hero标题中的核心关键词用金色荧光笔下划线（`::after`伪元素实现），制造重点和人味
- **#18 Badge & Stamp 徽章标签**："限时早鸟"/"仅剩XX名"/"NEW"等标签用酒红底白字胶囊标签，制造紧迫感
- **#08 Countdown 倒计时**：限时活动放在Hero旁或CTA区上方，金色衬线数字+酒红冒号，真实倒计时
- **#15 Divider 分隔线**：Section之间用金色渐变细线分隔，或用Fleuron花饰分隔
- **#09 Fleuron 花饰**：FAQ或评价区标题两侧用❦装饰，增加排版精致感
- **#04 Pull Quote 金句引用**：在痛点段落后插入大字金句（Cormorant斜体），强化情绪共鸣
- **#07 Decorative Rule 装饰线**：价格数字上方加金色双线装饰，突出价格的仪式感
- **#20 Numbered Index 编号索引**：价值点/收获点用金色大号数字（01/02/03）标注，方便扫读
- **#11 Ornamental Corner 角饰**：深色CTA面板四角加金色角饰，增强画框聚焦感
- **#19 Handwritten Note 手写注**：在用户头像旁加手写体标注（如"第3期学员"），增加真实感
- **#03 Image Frame 图片画框**：产品/人物照片加1px金色细边框，提升品质感
- **#24 Wax Seal（可选用）**：高客单价/品牌活动可在CTA区旁加火漆印章，增强信任感和品质感

## 推荐布局组合

| 布局 | 名称 | 适用位置 | 说明 |
|------|------|----------|------|
| **L2** | 居中大字Hero | 首屏（首选） | 标题居中，价值主张清晰，最适合活动/课程报名 |
| **L3** | 分屏Hero | 首屏（备选） | 一侧文字+一侧产品/人物图，适合产品发布 |
| **L4** | 全屏视觉Hero | 首屏（备选） | 大图冲击，适合有强视觉素材的发布会 |
| **L14** | 数据统计条 | Hero下方 | 4个关键数字，快速建立社会证明 |
| **L9** | 三列卡片网格 | 核心价值/功能 | 3-4个价值点卡片，顶部三色渐变条hover效果 |
| **L5** | 左图右文 | 痛点/方案/故事 | 图文交错，适合叙述性内容 |
| **L8** | 引文全屏 | 情绪转折点 | 金句/痛点宣言，深色背景打断节奏 |
| **L12** | 时间线 | 议程/流程 | 活动日程/产品使用步骤 |
| **L15** | 双栏对比 | 价格/套餐对比 | 推荐方案金色边框+徽章 |
| **L6** | 深色面板 | 痛点/风险逆转 | 情绪强化，深蓝色背景聚焦注意力 |
| **L13** | 深色面板CTA | 结尾转化（必用） | 最强行动号召，金色按钮 |
| **L16** | 画册溢出式 | 产品展示（加分） | 突破容器宽度的大图，视觉惊喜 |

## 色彩策略

Landing场景三色分配，核心原则：酒红=行动，皇家蓝=信任，金色=品质/强调。

**皇家蓝 #0A2463（55%）—— 信任与专业**
- 所有标题文字（h1-h3）
- 卡片图标背景/图标颜色
- 功能卡片hover时的边框色
- 深色面板/深色Section背景
- 导航栏背景（滚动后）
- 数据统计区数字颜色
- 正文链接
- Footer背景

**复古金 #F4D35E（30%）—— 品质与高亮**
- Hero标题关键词的荧光笔高亮（下划线）
- Section序号（金色大号斜体数字）
- 装饰线、分隔线、Fleuron花饰
- 深色面板上的CTA按钮（金色按钮在深蓝底上最醒目）
- 推荐套餐的金色边框+"推荐"徽章
- 倒计时数字颜色
- 功能卡片顶部hover渐变条的中间色
- 价格斜线删除线旁的折扣标签
- 星级评分星星颜色
- 角饰、角线等装饰元素
- **白底上金色仅用于装饰/线条/标签，不用于大段文字**

**酒红 #D8315B（15%）—— 行动与紧迫感**
- Hero首屏主CTA按钮（"立即报名"/"立即购买"）
- 紧迫感标签（"限时"/"仅剩XX名"/"早鸟"）
- 价格数字（酒红衬线大字，最醒目）
- 折扣标签（如"-30%"）
- 表单错误提示
- 倒计时冒号闪烁元素
- 功能卡片顶部hover渐变条的一端
- **酒红绝不大面积使用，仅用于按钮、价格、标签**

**深浅面板交替节奏**：Hero浅色 → 数据条白色 → 价值卡片浅色 → 评价区浅暖色底 → 深色CTA。每3-4个浅色section后必须有一个深色面板打断节奏，结尾L13必为深色。

## 场景禁忌（Don'ts）

1. **多个转化目标**：一个Landing页只能有一个主CTA，不要同时放"报名""关注公众号""加微信""下载资料"
2. **CTA按钮文案模糊**："提交""确认""开始"是最差文案，必须用动词开头："立即报名""免费预约""锁定席位"
3. **首屏没有CTA**：访客不需要滚动就能看到行动按钮，首屏必须有CTA
4. **虚假社会证明**："数百万用户""好评如潮"等空话不如"527人已参加""4.9/5分（203条评价）"具体
5. **表单字段过多**：报名表单不超过4个字段（姓名+手机/邮箱即可），多一步流失30%
6. **倒计时做假**：刷新页面重置倒计时是最低级的错误，必须用真实服务器时间
7. **自动弹窗**：进入页面立即弹出的窗口/浮层转化率极低且体验差
8. **酒红大面积使用**：酒红只用于CTA和价格标签，不要做section背景或大面积色块
9. **导航链接过多**：Landing页导航精简到3-4个锚点链接+1个CTA按钮，不要放外跳链接
10. **底部没有CTA**：看完所有内容的访客是最高意向的，结尾必须有CTA，不能让他们滚回去找按钮

## 场景专属Checklist

- [ ] 首屏有且仅有一个主CTA按钮（酒红色），无需滚动即可看到
- [ ] 价值主张在副标题25字内说清，3秒内明白"这对我有什么用"
- [ ] CTA按钮在页面中出现至少2次（首屏1次+结尾深色面板1次），长页面3-4次
- [ ] CTA按钮文案以动词开头（"立即报名"/"免费预约"），不用"提交"/"确认"
- [ ] 结尾必用L13深色面板CTA，金色按钮（深蓝底上金色最醒目）
- [ ] Hero标题核心词有金色荧光笔高亮效果
- [ ] 社会证明区域存在（数据统计条/评价/Logo墙至少一种），数字具体不模糊
- [ ] 价格数字为酒红衬线大字体，非灰色小字；有折扣时原价灰色删除线+酒红现价
- [ ] 表单字段不超过4个，提交按钮为酒红CTA样式
- [ ] 表单验证有品牌化反馈：focus皇家蓝光晕，错误酒红提示，成功金色反馈
- [ ] 每个section使用不同布局，不连续两个相同网格
- [ ] 限时活动有真实倒计时（服务器时间），不刷新重置
- [ ] 深浅面板交替有节奏，不连续3个以上浅色或深色
- [ ] 移动端CTA按钮全宽、在拇指热区内，所有触摸目标≥44px
- [ ] 导航精简（3-4锚点+1CTA），固定顶部，滚动后毛玻璃效果
- [ ] 选中文本背景为金色，无bounce/弹性/无限循环动画
- [ ] 页面加载性能良好，首屏<3秒，图片压缩懒加载

---

*Scene: Landing v1.0 · Feihong Design System*
*基于 DNA.md v2.0 · 最后更新：2026-07-08*
