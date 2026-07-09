# Feihong Design System · Scene: Portfolio
# 飞鸿品牌设计系统 · 场景规范：作品集 / 个人主页

> 本规范定义飞鸿品牌设计系统在「个人主页 / Portfolio / 作品展示网站」中的具体应用方式。
> 所有规则建立在 `DNA.md`、`components/14-layouts.md`、`components/` 基础之上，场景专属规则以本文件为准。
> Portfolio 场景的核心使命是**展示作品 + 建立个人品牌认知 + 促成联系**——让访客记住"你是谁"，看到"你能做什么"，并主动找到你。

---

## 1. 场景定义

### 适用页面类型

Portfolio 场景适用于以下以**个人品牌展示为核心目标**的内容形态：

| 类型 | 说明 | 典型长度 | 核心目标 |
|------|------|----------|---------|
| **设计师/创意人作品集** | UI/UX设计师、品牌设计师、插画师、摄影师 | 6-10屏 | 展示作品实力 + 获取工作/合作机会 |
| **个人品牌主页** | 独立设计师、自由职业者、个人IP | 5-8屏 | 建立品牌认知 + 促成咨询/合作 |
| **创作者展示站** | 艺术家、写作者、导演、音乐人 | 5-9屏 | 呈现创作风格 + 吸引粉丝/委托 |
| **求职/面试作品集** | 用于求职投递、面试展示的精简作品集 | 4-6屏 | 快速展现专业能力 + 获取面试机会 |
| **工作室/小团队官网** | 2-5人小团队、独立工作室 | 6-9屏 | 展示团队实力 + 获取商业项目 |

### 场景核心气质

- **高级优雅**：皇家蓝主导的品牌基调 + 衬线大标题，传递专业品味与审美水准
- **个性鲜明**：金色签名装饰 + 个人金句 + IP形象，让访客记住"这个人"而非千篇一律的模板
- **作品为王**：作品卡片与展示区域占据页面最大视觉权重，一切设计为作品让路
- **有温度有人味**：头像、引言、个人故事打破"冰冷作品集"的距离感，建立真实连接

### 场景核心约束

1. **作品是绝对主角**：作品展示区域占页面视觉面积不低于 40%，文字介绍为作品服务
2. **首屏 3 秒建立个人认知**：访客打开页面立即看到你的名字、身份标签和视觉形象（头像/IP）
3. **联系方式永远触手可及**：CTA/联系按钮在导航栏常驻，结尾有明确联系区
4. **头像必须出现且有金色边框**：个人品牌的核心是"人"，没有头像的作品集缺乏信任感
5. **至少有一句个人金句/引言**：用一句话定义你的设计哲学或个人态度，建立品牌性格

---

## 2. 典型页面结构

Portfolio 页面采用 **Hero个人介绍 → About关于我 → Works作品网格 → Skills技能 → Testimonials推荐 → Contact联系** 的六段式经典个人品牌结构：

```
┌─────────────────────────────────────────────────────────┐
│  ① Hero 个人介绍（L1 非对称图文+头像 — 首选）             │
│     - 导航栏（固定顶部，含名字Logo+导航+联系CTA）           │
│     - eyebrow 职业标签（如"品牌设计师"/"独立创作者"）      │
│     - h1 名字（超大衬线斜体，页面最大字号）                │
│     - 一句话自我介绍（Cormorant 斜体副标题）               │
│     - 头像（金色边框+柔和阴影，右侧/圆形）                 │
│     - 社交链接（social-links）                            │
│     - 主 CTA 按钮（"查看作品"/"联系我"）                  │
│     - 可选：IP形象在头像附近自然出现                       │
├─────────────────────────────────────────────────────────┤
│  ② About 关于我（L5/L6 图文并排）                         │
│     - section-title 章节标题（金色序号+装饰线）            │
│     - 个人照片/IP形象（左或右）                           │
│     - 2-3段个人介绍文字（有故事感，非简历罗列）             │
│     - 个人金句/引言（Cormorant 斜体，可穿插L8引文）        │
│     - 关键数据（从业年限/项目数量/合作品牌数）             │
│     * 作用：让访客了解"你是怎样的人"，建立情感连接         │
├─────────────────────────────────────────────────────────┤
│  ③ Works 作品网格（L10 非对称bento / L11 交错瀑布流）      │
│     - 作品分类标签（可选筛选：全部/品牌/UI/插画）          │
│     - 精选作品大图（card-project，1-2个置顶大卡片）        │
│     - 作品网格（非对称排列，避免等大卡片墙）               │
│     - 卡片hover：皇家蓝遮罩+金色"查看案例"标签             │
│     - 精选作品标记（badge-wine "精选"标签）               │
│     * 作用：这是页面的核心，用作品说话                     │
├─────────────────────────────────────────────────────────┤
│  ④ Skills 技能展示（L9 三列卡片 / L12 时间线）             │
│     - 技能标签/能力卡片（card-feature 风格）              │
│     - 或：职业经历时间线（timeline，展示成长轨迹）         │
│     - 工具/软件图标（简洁展示，不堆砌）                    │
│     * 作用：证明专业能力，建立可信度                       │
├─────────────────────────────────────────────────────────┤
│  ⑤ 视觉穿插（可选，L8 引文全屏 / L16 画册式）              │
│     - 个人金句/设计哲学全屏引言                            │
│     - 或：一张有冲击力的代表作品做画册式溢出展示           │
│     * 作用：打破网格节奏，制造记忆点                       │
├─────────────────────────────────────────────────────────┤
│  ⑥ Testimonials 推荐/评价（card-testimonial × 2-4）      │
│     - 客户/合作方/前同事推荐语                            │
│     - 推荐人头像+姓名+身份                                │
│     - 金色五星评分                                       │
│     * 作用：第三方背书，增强信任                           │
├─────────────────────────────────────────────────────────┤
│  ⑦ Contact 联系（L13 深色面板 CTA — 必选）                │
│     - 深蓝径向渐变背景                                    │
│     - 邀请合作的标题（如"有好项目？聊聊。"）              │
│     - 联系方式（邮箱、微信、社交链接）                     │
│     - 可选：内嵌联系表单（姓名+邮箱+留言）                 │
│     - social-links 再次出现                              │
├─────────────────────────────────────────────────────────┤
│  ⑧ Footer（简洁，含品牌签名）                             │
│     - 名字Logo + 版权信息                                 │
│     - 社交链接（可选）                                    │
│     - 返回顶部按钮                                       │
└─────────────────────────────────────────────────────────┘
```

### 结构要点

1. **首屏必须出现头像**：个人主页的首屏不能只有文字，必须有带金色边框的头像建立"人"的认知
2. **Works 是视觉最重的 section**：作品区用最大的图片、最宽松的间距，不要被其他内容抢风头
3. **About 要有故事感**：不是简历的搬运，而是用 2-3 段有温度的文字让人了解你
4. **联系方式至少出现 3 次**：导航栏CTA + Hero区按钮 + 结尾Contact区，确保访客随时能找到你
5. **每个 section 版式不同**：图文/网格/时间线/深色面板交替，避免单调
6. **金句至少出现 1 次**：在About或L8引文中用一句Cormorant斜体金句定义你的品牌态度

---

## 3. 色彩使用指南

Portfolio 场景遵循品牌 55-30-15 色彩比例，但三色在个人品牌场景中的角色侧重有所不同——**金色承担更重要的签名装饰职能**，酒红用于精选标记和CTA强调。

### 3.1 皇家蓝 `#0A2463`（55%）— 品牌识别与作品交互色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **导航栏** | 顶部固定导航文字、Logo | 建立品牌识别第一印象 |
| **主标题** | h1 名字、h2 section 标题 | Playfair Display 衬线，皇家蓝/墨黑 |
| **作品卡片hover遮罩** | card-project hover 时的皇家蓝半透明遮罩 | 交互核心，作品查看的引导 |
| **正文标题** | h3 子标题、技能卡片标题 | 皇家蓝色，统一专业感 |
| **次要按钮** | btn-primary（皇家蓝按钮） | "了解更多"等非主要行动 |
| **描边按钮** | btn-outline（皇家蓝描边） | 辅助选项 |
| **链接文字** | 正文内链接 | 皇家蓝默认色，hover 转酒红 |
| **时间线** | timeline 的连线和节点 | 皇家蓝主色调 |
| **技能图标背景** | card-feature 的 card-icon 背景 | 极浅皇家蓝 `var(--royal-50)` |

### 3.2 复古金 `#F4D35E`（30%）— 签名装饰与高亮色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **头像边框** | avatar 组件的金色环形边框 | **Portfolio 最标志性的视觉元素** |
| **作品hover标签** | card-project hover 时的金色"查看案例"标签 | 引导点击查看作品详情 |
| **标签徽章** | badge-gold（职业标签、年份标签、技能标签） | 金色背景+皇家蓝文字 |
| **装饰线** | title-gold-line、divider-gold | 品牌签名细节，章节分隔 |
| **装饰序号** | section-number（01, 02, 03...） | Cormorant 斜体金色大数字 |
| **名字关键词** | h1 名字中的点/特殊符号（如名字后的金色句号） | 个人品牌签名细节 |
| **社交链接hover** | social-links 图标hover时的金色高亮 | 交互反馈 |
| **金色荧光笔高亮** | 引言/正文中的核心关键词 | `linear-gradient(transparent 60%, var(--gold-200) 60%)` |
| **精选标记（辅助）** | 与酒红配合，金色用于星级评分、数据数字 | 增强品质感 |
| **头像阴影** | 头像周围的金色柔和光晕阴影 | `box-shadow: 0 8px 32px rgba(244,211,94,0.2)` |

### 3.3 酒红 `#D8315B`（15%）— 精选强调与CTA色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **精选作品标签** | badge-wine（"精选"/"Featured"标签） | 标记代表作品，红色最吸引目光 |
| **联系CTA按钮** | btn-cta（酒红按钮） | "联系我"/"合作咨询"等主要行动 |
| **关键强调文字** | 核心能力关键词、个人标签 | 酒红色加粗，少量点缀 |
| **悬停状态** | 链接hover、按钮hover的强调色 | 交互反馈 |
| **联系信息高亮** | 邮箱地址、电话号码 | 酒红色衬线字体，便于识别 |
| **表单错误提示** | 输入验证失败的提示 | 复用酒红作为error语义色 |

### 3.4 背景与中性色

| 元素 | 色值 | 说明 |
|------|------|------|
| 页面主背景 | `#FDFBF6` (`var(--cream)`) | 暖米白，温润不刺眼，衬出作品色彩 |
| 卡片背景 | `#FFFFFF` | 纯白卡片，与暖米白形成微妙层次 |
| 交替 section 背景 | `var(--cream-100)` (`#F8F4EB`) | About/Skills区可用极浅暖米色，增加节奏 |
| 深色面板背景 | 皇家蓝深蓝径向渐变 | L13 Contact区、可选Hero深色侧 |
| 作品卡片背景 | `#FFFFFF` 或 皇家蓝深蓝（hover时） | 默认白色，hover时切换为皇家蓝遮罩 |
| 正文文字 | `var(--ink-100)` (`#2C3347`) | 深灰，长阅读舒适 |
| 标题文字 | `var(--ink)` (`#0D1225`) | 墨黑，名字和标题对比强烈 |
| 辅助文字 | `var(--ink-300)` (`#6D7487`) | 说明文字、元信息、日期 |
| 边框/分隔线 | `var(--cream-200)` (`#F0EAD9`) | 暖调边框，不用冷灰 |

### 色彩使用铁律（Portfolio 场景）

1. **头像必须有金色边框**：3-4px 金色实线/渐变边框 + 柔和金色阴影，这是Portfolio场景最具辨识度的品牌符号
2. **金色不大面积铺陈**：仅用于边框、标签、装饰线、hover标签、序号，不做区块背景
3. **作品hover必须是皇家蓝遮罩+金色标签**：这是作品区的标准交互范式，不可替换为其他颜色
4. **酒红仅用于精选标签和CTA按钮**：同一屏内酒红元素不超过2-3个，保持克制
5. **深色面板（L13）上的CTA按钮用金色**：深蓝背景上金色按钮比酒红更醒目
6. **作品图片本身的色彩不做品牌色覆盖**：作品图保持原貌，品牌色只出现在UI框架和交互层

---

## 4. 排版规范

### 4.1 名字排版：超大衬线斜体（核心约束）

Portfolio 首屏的名字排版是整个页面最重要的排版决策，必须使用**超大衬线斜体**，建立强烈的个人品牌签名感：

| 指标 | 规范值 | 说明 |
|------|--------|------|
| **h1 名字字号** | `clamp(3rem, 9vw, 6rem)` | 桌面端最大可达 96px，移动端不小于 48px |
| h1 名字字重 | 700/900 | Playfair Display 粗体 |
| h1 名字字式 | **italic 斜体** | 斜体衬线更具签名感和个人气质 |
| h1 行高 | 1.0 | 极紧凑，名字要有分量感 |
| h1 字距 | -0.02em | 微缩字距，大标题更紧凑 |
| **eyebrow 职业标签** | `0.75rem`（12px） | 全大写，0.2em字距，极小，金色或皇家蓝底色 |
| **副标题字号** | `clamp(1.1rem, 2vw, 1.5rem)` | 与h1形成强烈反差 |
| 副标题字体 | Cormorant Garamond italic | 斜体衬线，优雅有温度 |
| 副标题行高 | 1.6 | 舒适阅读 |

**字号对比示例**：
```
eyebrow:  12px  ●●● （极小，全大写，如"品牌设计师 · 独立创作者"）
h1 名字:  88px  ●●●●●●●●●●●●●●●●●●●●● （极大，衬线斜体粗体）
subtitle: 22px  ●●●●● （中等，斜体衬线，一句话介绍）
```

> **铁律**：名字h1必须是页面最大字号，与eyebrow标签形成至少1:6的字号比。名字用斜体（`font-style: italic`），这是Portfolio区别于Landing场景的关键排版特征。

### 4.2 职业标签 eyebrow 样式

职业标签是首屏的第一行文字，定义你的身份，使用标准 eyebrow 样式：

```css
.eyebrow {
  display: inline-block;
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--royal);
  background: rgba(10, 36, 99, 0.06);
  padding: 0.3rem 0.85rem;
  border-radius: 4px;
  margin-bottom: var(--sp-4);
}
/* 金色变体——用于强调身份 */
.eyebrow-gold {
  color: var(--royal);
  background: var(--gold);
}
```

- 内容示例："品牌设计师" / "UI/UX Designer" / "独立创作者 · 上海"
- 不超过 8 个汉字，简洁有力
- 可加金色分隔点："品牌设计 · 视觉策略 · 创意指导"

### 4.3 正文排版规范

| 元素 | 字号 | 行高 | 字体 | 颜色 | 说明 |
|------|------|------|------|------|------|
| **正文段落** | `1rem`（16px） | **1.7** | Inter | `var(--ink-100)` | 行高严格1.7，About区个人介绍 |
| **卡片描述** | `0.9375rem`（15px） | 1.65 | Inter | `var(--ink-200)` | 作品/技能卡片内文字 |
| **引言/金句** | `clamp(1.5rem, 3vw, 2.25rem)` | 1.4 | Cormorant Garamond italic | `var(--royal)` | L8引文区、About区pull-quote |
| **数据数字** | `clamp(2rem, 4vw, 3rem)` | 1 | Playfair Display 700 | `var(--royal)` 或 `var(--gold)` | 从业年限、项目数 |
| **作品标题** | `clamp(1.15rem, 2vw, 1.4rem)` | 1.3 | Playfair Display 600 | `var(--ink)` | card-project标题 |
| **标签/徽章** | `0.75rem`（12px） | 1.4 | Inter 500/600 | 品牌色 | 全大写加字距 |
| **按钮文字** | `0.9375rem` - `1.0625rem` | 1 | Inter 500 | #fff / 品牌色 | 不使用斜体 |
| **推荐语** | `1.0625rem`（17px） | 1.7 | Cormorant Garamond italic | `var(--ink-100)` | testimonial引用文字 |
| **联系信息** | `1.125rem`（18px） | 1.5 | Inter/Playfair | `var(--wine)` 或 `var(--royal)` | 邮箱、电话等 |

### 4.4 标题层级（Portfolio 场景适配）

| 层级 | 字体 | 字号 (clamp) | 行高 | 字重 | 字式 | 颜色 | 装饰 |
|------|------|-------------|------|------|------|------|------|
| **h1** 名字 | Playfair Display | `clamp(3rem, 9vw, 6rem)` | 1.0 | 700/900 | **italic** | `var(--ink)` | 名字后可加金色句号 |
| **h2** Section标题 | Playfair Display | `clamp(1.75rem, 3.5vw, 2.75rem)` | 1.15 | 700 | normal | `var(--ink)` | 金色序号 + title-gold-line |
| **h3** 作品/技能标题 | Playfair Display | `clamp(1.15rem, 2vw, 1.4rem)` | 1.3 | 600 | normal | `var(--royal)` | 无装饰线 |
| **h4** 小标题 | Inter | `1rem` | 1.4 | 600 | normal | `var(--ink)` | 无装饰 |

### 4.5 排版特殊规则

1. **名字中的金色签名细节**：
   ```css
   .hero-name .gold-dot {
     color: var(--gold);
     font-style: normal; /* 句号不斜体 */
   }
   /* 用法：<h1 class="hero-name">飞鸿<span class="gold-dot">.</span></h1> */
   ```

2. **个人金句/引言排版**：
   ```css
   .personal-quote {
     font-family: var(--font-display);
     font-size: clamp(1.5rem, 3vw, 2.25rem);
     font-style: italic;
     font-weight: 400;
     line-height: 1.4;
     color: var(--royal);
     max-width: 700px;
     margin: 0 auto;
     text-align: center;
     position: relative;
   }
   .personal-quote::before {
     content: '"';
     font-family: var(--font-serif);
     font-size: 4em;
     color: var(--gold);
     opacity: 0.4;
     position: absolute;
     top: -0.3em;
     left: -0.2em;
     line-height: 1;
   }
   ```

3. **作品标题hover时的变化**：
   - 默认：墨黑/深灰色作品标题 + 辅助灰色分类标签
   - hover时：作品图片被皇家蓝遮罩覆盖，出现金色"查看案例 →"标签
   - 标题文字在遮罩上变为白色

4. **正文段落宽度**：
   - About区个人介绍：不超过 550px（有温度的阅读宽度）
   - 引言/金句：不超过 700px（居中，宽松呼吸感）
   - 卡片描述：不超过 350px
   - 推荐语：不超过 450px

---

## 5. 推荐布局组合

从 L1-L16 中选取适合 Portfolio 个人品牌展示的布局，按页面位置推荐如下：

### 5.1 首屏布局（1个首选 + 2个备选）

| 布局 | 适用场景 | 视觉特点 |
|------|----------|---------|
| **L1 非对称图文Hero** | **Portfolio首选**，设计师/创意人个人主页 | 左侧名字+介绍+CTA，右侧头像+IP形象，有温度、个人化 |
| L2 居中大字Hero | 极简风格作品集、艺术家主页 | 居中名字+副标题，头像可放在名字下方或省略 |
| L3 分屏Hero | 偏商业/服务导向的个人工作室 | 一侧深色+名字介绍，一侧大幅代表作品图 |

**首屏选择建议**：
- **设计师/创意人/个人IP** → 首选 **L1 非对称图文Hero**（头像+名字+介绍，个人感最强）
- **极简主义/艺术家/摄影师** → 可选 **L2 居中大字Hero**（名字居中，大气克制）
- **工作室/商业服务** → 可选 **L3 分屏Hero**（一侧放代表作品图）

### 5.2 About 区域布局

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **L5 左图右文** | About首选，个人照片+介绍文字 | 左侧圆形/方形头像或个人照片（金色边框），右侧文字 |
| **L6 左文右图** | 与L5交替使用或About区使用 | IP形象或工作照在右侧 |
| **L8 引文全屏** | About区内或之后穿插个人金句 | Cormorant斜体金句，皇家蓝色，金色大引号装饰 |

### 5.3 Works 作品区域布局（2选1或组合）

| 布局 | 视觉特点 | 适用场景 |
|------|---------|---------|
| **L10 非对称bento网格** | 大小卡片错落排列，1-2个大卡片置顶+小卡片网格 | **设计师作品集首选**，有设计感、不单调 |
| **L11 交错瀑布流** | 两列/三列不等高卡片交错排列 | 插画师/摄影师/内容创作者，作品数量多且尺寸不一 |

**Works 区布局要点**：
- 精选作品（1-2个）用大卡片尺寸置顶展示，加 `badge-wine` "精选"标签
- 其余作品用等大或略错落的卡片排列
- 绝对不要所有作品都用一样大的卡片排成整齐网格——这是AI模板的典型特征
- 卡片之间间距宽松（`gap: 1.5rem` 以上），让作品有呼吸空间

### 5.4 Skills/经历区域布局

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **L9 三列卡片网格** | 技能/能力/服务内容展示 | 3-4个技能卡片，card-feature风格，金色图标 |
| **L12 时间线** | 职业经历/成长轨迹/项目历程 | 皇家蓝连线+金色节点，左侧时间右侧内容 |

### 5.5 视觉惊喜布局（P1加分项，1-2个）

| 布局 | 效果 | 使用位置 |
|------|------|---------|
| **L8 引文全屏** | 个人金句/设计哲学全屏展示，呼吸感 | About和Works之间，或Skills之后 |
| **L16 画册溢出式** | 一张代表作品突破容器宽度溢出显示，画册感 | Works区域中穿插，或结尾CTA之前 |

### 5.6 结尾布局（必选）

| 布局 | 用途 | 配置要点 |
|------|------|---------|
| **L13 深色面板CTA** | 联系区，页面收尾，促成合作 | 深蓝径向渐变+白色邀请文字+金色CTA按钮+社交链接+联系方式 |

### 5.7 经典 Portfolio 布局配方

#### 配方 A：设计师/创意人标准作品集（7屏，最常用）

| 顺序 | 布局 | 内容 |
|------|------|------|
| 1 | **L1 非对称图文Hero** | 头像（金色边框）+ 名字（衬线斜体）+ 职业标签 + 一句话介绍 + CTA |
| 2 | **L5 左图右文（About）** | 个人照片/IP形象 + 2-3段个人介绍 + 数据数字 |
| 3 | **L8 引文全屏**（可选） | 个人金句/设计哲学 |
| 4 | **L10 非对称bento网格** | 精选作品1-2个大卡片 + 其余作品卡片网格 + 分类筛选 |
| 5 | **L9 三列卡片 或 L12时间线** | 技能/能力 或 职业经历 |
| 6 | **card-testimonial × 3** | 客户/合作方推荐评价 |
| 7 | **L13 深色面板CTA** | 联系邀请 + 邮箱/社交 + 联系按钮 |

#### 配方 B：极简艺术家/摄影师作品集（6屏）

| 顺序 | 布局 | 内容 |
|------|------|------|
| 1 | **L2 居中大字Hero** | 名字居中超大衬线斜体 + 一句副标题 |
| 2 | **L16 画册式**（可选） | 一张大幅代表作品开篇 |
| 3 | **L11 交错瀑布流** | 作品展示（视觉绝对主体） |
| 4 | **L6 左文右图（About）** | 简短个人介绍 + 工作照/肖像 |
| 5 | **L8 引文全屏** | 创作理念/艺术宣言金句 |
| 6 | **L13 深色面板CTA** | 联系/委托邀请 |

#### 配方 C：求职/面试精简作品集（5屏）

| 顺序 | 布局 | 内容 |
|------|------|------|
| 1 | **L1 非对称图文Hero** | 头像+名字+职位目标+核心技能标签+简历下载CTA |
| 2 | **L5 左图右文（About）** | 简短自我介绍（3-5句话）+ 关键数据 |
| 3 | **L10 非对称bento网格** | 3-5个精选项目（大卡片，含项目结果数据） |
| 4 | **L12 时间线** | 教育/工作经历 |
| 5 | **L13 深色面板CTA** | 联系方式（邮箱+微信+LinkedIn）+ "期待合作" |

### 5.8 布局使用禁忌

| 布局 | Portfolio 场景不推荐原因 |
|------|----------------------|
| L7 单栏长文 | 纯文字阅读导向，Portfolio应以作品视觉为主 |
| L14 数据统计条 | 适用于Landing页首屏下方建立信任，Portfolio用stat-card嵌入About区即可 |
| L15 双栏对比 | 适用于价格套餐对比，Portfolio无数价格对比场景 |
| 连续两个相同网格 | 连续两个L9或连续两个L10 = AI模板感，必须穿插不同布局 |
| 多个 L13 深色面板 | 深色面板仅在结尾Contact区使用1次 |

---

## 6. 组件选用指南

### 6.1 必用组件（Portfolio 场景核心组件，缺一不可）

| 组件 | 组件名 | 使用场景 | 使用频率 |
|------|--------|----------|----------|
| **头像** | `avatar` | Hero首屏右侧、About区、推荐人头像 | 首屏必用，推荐区复用 |
| **作品卡片** | `card-project` | Works作品展示区 | 6-12个，页面核心组件 |
| **社交链接** | `social-links` | Hero区、Contact区、Footer | 2-3次 |
| **时间线** | `timeline` | Skills/经历区展示职业轨迹 | 1次（L12） |
| **深色面板** | `dark-panel` | 结尾Contact联系区（L13） | 1次（结尾必用） |

#### 头像（`avatar`）使用规范

```html
<!-- Hero首屏头像（大尺寸） -->
<div class="avatar avatar-lg">
  <img src="assets/avatar.png" alt="飞鸿">
</div>

<!-- About区头像（中尺寸，可选） -->
<div class="avatar avatar-md">
  <img src="assets/avatar.png" alt="飞鸿">
</div>

<!-- 推荐人头像（小尺寸） -->
<div class="avatar avatar-sm">
  <img src="assets/client-avatar.jpg" alt="推荐人姓名">
</div>
```

```css
.avatar {
  border-radius: 50%;
  overflow: hidden;
  border: 3px solid var(--gold);
  box-shadow: 0 8px 32px rgba(244, 211, 94, 0.2), 0 4px 16px rgba(10, 36, 99, 0.1);
  position: relative;
}
.avatar::after {
  /* 金色光晕装饰 */
  content: '';
  position: absolute;
  inset: -6px;
  border-radius: 50%;
  border: 1px solid rgba(244, 211, 94, 0.3);
  pointer-events: none;
}
.avatar-lg { width: clamp(200px, 28vw, 320px); height: clamp(200px, 28vw, 320px); }
.avatar-md { width: 120px; height: 120px; }
.avatar-sm { width: 48px; height: 48px; border-width: 2px; }
.avatar img { width: 100%; height: 100%; object-fit: cover; display: block; }
```

- **金色边框是硬性要求**：3px（大/中尺寸）或2px（小尺寸）`var(--gold)` 实线边框
- **必须有柔和阴影**：金色光晕阴影 + 皇家蓝投影，让头像从背景中浮起
- **圆形为标准形态**：Portfolio头像默认圆形，方形头像需加圆角（`border-radius: 16px`）
- 头像图片路径：`assets/avatar.png`
- IP形象（`assets/character.png`）可在头像旁或About区自然出现，作为装饰/吉祥物

#### 作品卡片（`card-project`）使用规范

```html
<div class="card card-project">
  <div class="project-image">
    <img src="assets/project-1.jpg" alt="项目名称">
    <div class="project-overlay">
      <span class="project-view-label">查看案例 →</span>
    </div>
  </div>
  <div class="project-info">
    <span class="badge badge-wine">精选</span>
    <h3 class="project-title">品牌重塑项目</h3>
    <span class="project-category">品牌设计 / 2025</span>
  </div>
</div>
```

```css
.card-project {
  background: #fff;
  border-radius: var(--r-lg);
  overflow: hidden;
  transition: all 400ms var(--ease);
  border: 1px solid #F0EAD9;
}
.card-project:hover {
  transform: translateY(-6px);
  box-shadow: var(--shadow-lg);
  border-color: var(--royal);
}
.project-image {
  position: relative;
  aspect-ratio: 4/3;
  overflow: hidden;
}
.project-image img {
  width: 100%; height: 100%; object-fit: cover;
  transition: transform 500ms var(--ease);
}
.project-overlay {
  position: absolute; inset: 0;
  background: rgba(10, 36, 99, 0.85); /* 皇家蓝遮罩 */
  display: flex; align-items: center; justify-content: center;
  opacity: 0; transition: opacity 350ms var(--ease);
}
.project-view-label {
  font-family: var(--font-sans);
  font-size: 0.9375rem; font-weight: 500;
  color: var(--gold); /* 金色标签 */
  padding: 0.6rem 1.2rem;
  border: 1.5px solid var(--gold);
  border-radius: 100px;
  transform: translateY(8px);
  transition: transform 350ms var(--ease);
}
.card-project:hover .project-overlay { opacity: 1; }
.card-project:hover .project-view-label { transform: translateY(0); }
.card-project:hover .project-image img { transform: scale(1.05); }
.project-info { padding: var(--sp-4) var(--sp-5); }
.project-title { font-family: var(--font-serif); font-size: 1.15rem; font-weight: 600; color: var(--ink); margin: var(--sp-2) 0 var(--sp-1); }
.project-category { font-size: 0.8125rem; color: var(--ink-300); }
```

- **hover效果是核心交互**：皇家蓝半透明遮罩(`rgba(10,36,99,0.85)`)从上到下渐显 + 金色"查看案例 →"标签浮现
- 精选作品加 `badge-wine`（酒红底白字）"精选"标签
- 图片hover时轻微放大（`scale(1.05)`），增加层次感
- 项目信息区包含：标签（可选）+ 标题 + 分类/年份
- 大卡片（bento布局中的主卡片）可设 `aspect-ratio: 16/10` 或 `3/2`，比普通卡片更宽更高

#### 社交链接（`social-links`）使用规范

```html
<div class="social-links">
  <a href="#" class="social-link" aria-label="Email">
    <svg><!-- 邮箱图标 --></svg>
  </a>
  <a href="#" class="social-link" aria-label="Dribbble">
    <svg><!-- Dribbble图标 --></svg>
  </a>
  <a href="#" class="social-link" aria-label="Behance">
    <svg><!-- Behance图标 --></svg>
  </a>
  <a href="#" class="social-link" aria-label="WeChat">
    <svg><!-- 微信图标 --></svg>
  </a>
  <a href="#" class="social-link" aria-label="GitHub">
    <svg><!-- GitHub图标 --></svg>
  </a>
</div>
```

```css
.social-links { display: flex; gap: var(--sp-3); }
.social-link {
  width: 40px; height: 40px;
  display: flex; align-items: center; justify-content: center;
  border-radius: 50%;
  background: rgba(10, 36, 99, 0.06);
  color: var(--royal);
  transition: all 250ms var(--ease);
}
.social-link:hover {
  background: var(--gold);
  color: var(--royal);
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(244, 211, 94, 0.3);
}
.social-link svg { width: 18px; height: 18px; }
```

- Hero区放主要社交链接（3-5个），Contact区放完整联系方式
- 默认：浅皇家蓝底+皇家蓝图标；hover：金色底+皇家蓝图标+上移
- 使用SVG图标，不使用emoji或文字链接
- 每个链接必须有 `aria-label` 确保可访问性

#### 时间线（`timeline`）使用规范

```html
<div class="timeline">
  <div class="timeline-item">
    <div class="timeline-dot"></div>
    <div class="timeline-content">
      <span class="timeline-date">2024 — 至今</span>
      <h3 class="timeline-title">独立设计师</h3>
      <p class="timeline-desc">为品牌提供从策略到视觉的全链路设计服务。</p>
    </div>
  </div>
  <div class="timeline-item">
    <div class="timeline-dot"></div>
    <div class="timeline-content">
      <span class="timeline-date">2021 — 2024</span>
      <h3 class="timeline-title">某互联网公司 · 高级设计师</h3>
      <p class="timeline-desc">负责核心产品的UI/UX设计，主导3次重大改版。</p>
    </div>
  </div>
</div>
```

```css
.timeline { position: relative; padding-left: var(--sp-8); }
.timeline::before {
  content: ''; position: absolute;
  left: 7px; top: 8px; bottom: 8px;
  width: 2px; background: linear-gradient(180deg, var(--royal), rgba(10,36,99,0.15));
}
.timeline-item { position: relative; padding-bottom: var(--sp-6); }
.timeline-item:last-child { padding-bottom: 0; }
.timeline-dot {
  position: absolute; left: -25px; top: 6px;
  width: 16px; height: 16px; border-radius: 50%;
  background: var(--gold); border: 3px solid var(--cream);
  box-shadow: 0 0 0 2px var(--royal);
}
.timeline-date { font-size: 0.8125rem; color: var(--gold); font-weight: 500; letter-spacing: 0.05em; }
.timeline-title { font-family: var(--font-serif); font-size: 1.1rem; font-weight: 600; color: var(--royal); margin: var(--sp-1) 0; }
.timeline-desc { font-size: 0.9375rem; line-height: 1.65; color: var(--ink-200); }
```

- 连线使用皇家蓝渐变（深到浅），节点使用金色圆点+皇家蓝外环
- 日期文字用金色小字，标题用皇家蓝衬线，描述用深灰
- 适用于职业经历、项目历程、成长轨迹展示

#### 深色面板（`dark-panel`）使用规范

```html
<div class="dark-panel contact-panel">
  <span class="eyebrow" style="background:rgba(244,211,94,0.15);color:var(--gold);">Let's Talk</span>
  <h2>有好项目？<br>聊聊吧。</h2>
  <p>无论是品牌设计、UI设计还是创意合作，欢迎随时联系。</p>
  <div class="contact-info">
    <a href="mailto:hello@Feihong.art" class="contact-email">hello@Feihong.art</a>
  </div>
  <div class="social-links" style="justify-content:center;margin-top:var(--sp-6);">
    <!-- 社交链接 -->
  </div>
  <a href="mailto:hello@Feihong.art" class="btn btn-gold btn-xl" style="margin-top:var(--sp-6);">发送邮件 →</a>
</div>
```

- Portfolio场景的dark-panel用于Contact联系区，全页仅1次
- 背景：皇家蓝深蓝径向渐变 + 右上角微弱金色光晕
- 标题白色，Cormorant/Playfair衬线字号大
- CTA按钮用**金色**（`btn-gold`），深蓝背景上金色最醒目
- 联系邮箱用金色或白色衬线大字，易于识别
- 社交链接在深色面板上需调整样式（图标白色，hover金色）

### 6.2 推荐组件（按需使用）

| 组件 | 使用场景 |
|------|----------|
| `btn-cta`（酒红按钮） | Hero区"联系我"/"查看作品"主CTA，About区内联按钮 |
| `btn-primary`（皇家蓝主按钮） | 次要行动，如"下载简历" |
| `btn-outline`（描边按钮） | 辅助选项，如"了解更多" |
| `badge-gold` / `badge-wine` | 职业标签、"精选"标签、年份标签、分类标签 |
| `card-feature` | Skills技能展示区的能力卡片 |
| `card-testimonial` | 客户/合作方推荐评价 |
| `stat-card`（小型） | About区嵌入的关键数据（从业年限/项目数/客户数） |
| `section-title`（含金色序号） | 每个内容section的标题区 |
| `divider-gold` | section之间的金色渐变分隔线 |
| `filter-tabs`（筛选标签） | Works区作品分类筛选（全部/品牌/UI/插画...） |
| `navbar`（固定导航） | 所有Portfolio页必备，含名字Logo+导航链接+联系CTA |

### 6.3 Portfolio 场景专属组件模式

#### IP形象自然融入

```html
<!-- Hero区：头像旁边放置小尺寸IP形象 -->
<div class="hero-visual">
  <div class="avatar avatar-lg">
    <img src="assets/avatar.png" alt="飞鸿">
  </div>
  <img src="assets/character.png" alt="飞鸿IP形象" class="ip-mascot">
</div>
```

```css
.ip-mascot {
  position: absolute;
  width: 120px;
  bottom: -10px;
  right: -20px;
  z-index: 2;
  filter: drop-shadow(0 4px 12px rgba(10,36,99,0.15));
  animation: float 4s ease-in-out infinite;
}
@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-8px); }
}
@media (prefers-reduced-motion: reduce) {
  .ip-mascot { animation: none; }
}
```

- IP形象（`assets/character.png`）在Hero区可作为头像旁的装饰元素，带轻柔浮动动画
- 在About区可替换为更大尺寸，作为个人形象的补充
- 不要让IP形象喧宾夺主，尺寸不超过头像的 40%
- 浮动动画必须尊重 `prefers-reduced-motion`

#### 作品筛选标签

```html
<div class="filter-tabs">
  <button class="filter-tab active" data-filter="all">全部</button>
  <button class="filter-tab" data-filter="branding">品牌设计</button>
  <button class="filter-tab" data-filter="ui">UI/UX</button>
  <button class="filter-tab" data-filter="illustration">插画</button>
</div>
```

```css
.filter-tabs { display: flex; gap: var(--sp-2); flex-wrap: wrap; margin-bottom: var(--sp-6); }
.filter-tab {
  font-family: var(--font-sans); font-size: 0.875rem; font-weight: 500;
  padding: 0.4rem 1rem; border-radius: 100px;
  background: transparent; border: 1px solid #F0EAD9;
  color: var(--ink-200); cursor: pointer;
  transition: all 250ms var(--ease);
}
.filter-tab:hover { border-color: var(--royal); color: var(--royal); }
.filter-tab.active { background: var(--royal); color: #fff; border-color: var(--royal); }
```

- 筛选标签为胶囊形状，默认描边，激活态皇家蓝底白字
- 不使用金色或酒红作为激活态——筛选是导航行为不是强调行为
- P2功能，不强制要求

### 6.4 不推荐组件

| 组件 | 不推荐原因 |
|------|-----------|
| `form-input`（复杂表单） | Portfolio联系表单不超过3个字段，不需要复杂表单组件 |
| `price-table` / `brand-table` | 无数价格/对比场景 |
| `progress`（技能进度条） | 过于俗套，用卡片或标签展示技能更高级 |
| `alert-*` 系列 | 提示框用于产品/教程，作品集不需要 |
| `countdown`（倒计时） | Landing场景紧迫感组件，作品集不需要 |

---

## 7. 特殊注意事项

### 7.1 头像金色边框+阴影（铁律）

头像是Portfolio场景中最具辨识度的个人品牌元素，必须满足：

1. **金色边框**：3px `var(--gold)` 实线边框（小头像2px）
2. **多层阴影**：金色光晕阴影（`rgba(244,211,94,0.2)`）+ 皇家蓝投影（`rgba(10,36,99,0.1)`）
3. **可选外环**：1px 半透明金色外环（`::after`伪元素），增强精致感
4. **圆形为标准**：默认圆形（`border-radius: 50%`），方形需加大圆角（≥16px）
5. **图片质量**：头像图片清晰、光线好、专业，不用模糊/过度滤镜/卡通化过度的照片

### 7.2 IP形象自然出现

IP形象（`assets/character.png`）是飞鸿个人品牌的重要元素，在Portfolio中：

- **推荐位置**：Hero区头像旁（小尺寸，浮动动画）、About区文字旁（中尺寸）
- **出现次数**：1-2次即可，不要在每个section都出现
- **尺寸控制**：不超过所在区域主要视觉元素的 40%（头像旁的IP不超过头像的40%）
- **不要替代头像**：IP形象是辅助/吉祥物，不能替代真实头像——个人品牌需要真实人像建立信任
- **动画克制**：如有浮动动画，幅度小（±8px）、周期长（4s），尊重 `prefers-reduced-motion`

### 7.3 作品卡片hover交互规范

作品卡片的hover效果是Portfolio最重要的交互，必须统一：

| 状态 | 视觉表现 |
|------|---------|
| **默认** | 作品图片清晰可见，下方显示标题+分类，白色卡片背景 |
| **hover** | ① 卡片整体上移6px ② 阴影加深 ③ 图片上覆盖皇家蓝半透明遮罩(`rgba(10,36,99,0.85)`) ④ 遮罩中央浮现金色描边胶囊标签"查看案例 →" ⑤ 图片轻微放大(scale 1.05) |
| **点击/激活** | 标签缩放0.95，跳转至作品详情页 |

```css
/* 关键hover CSS汇总 */
.card-project:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 40px rgba(10,36,99,0.15);
}
.card-project:hover .project-overlay { opacity: 1; }
.card-project:hover .project-view-label {
  transform: translateY(0);
  border-color: var(--gold);
  color: var(--gold);
}
.card-project:hover .project-image img { transform: scale(1.05); }
```

- 遮罩必须是**皇家蓝**（不是酒红、不是纯黑、不是金色）
- "查看案例"标签必须是**金色描边+金色文字**（不是金色填充底）
- 标签用胶囊圆角（`border-radius: 100px`），带箭头"→"
- 移动端没有hover，可改为点击显示遮罩（首次点击显示遮罩，二次点击跳转）

### 7.4 个人金句/引言体现品牌性格

Portfolio必须至少有一句个人金句/引言，体现你的设计哲学或个人态度：

**金句位置建议**：
- L8引文全屏区（About和Works之间，最推荐）
- About区文字末尾作为pull-quote
- Hero区副标题（如果一句话自我介绍本身就是金句）

**金句写作原则**：
- 简短有力：不超过30个字
- 有个人态度：不是正确的废话（不用"设计让生活更美好"这种万能句）
- Cormorant Garamond italic 斜体，皇家蓝色
- 可配金色大引号装饰

**金句示例**：
- "当AI可以生成一切，人的审美判断才是最稀缺的能力。"
- "好设计不是让人注意到设计本身，而是让人注意到它要传达的信息。"
- "我不做千篇一律的美，我做有记忆点的对。"
- "克制是最高级的张扬。"

### 7.5 导航栏规范

Portfolio导航栏应精简，不超过5个链接：

```html
<nav class="navbar">
  <a href="#" class="nav-logo">飞鸿<span style="color:var(--gold)">.</span></a>
  <div class="nav-links">
    <a href="#about" class="nav-link">关于</a>
    <a href="#works" class="nav-link">作品</a>
    <a href="#skills" class="nav-link">技能</a>
    <a href="#contact" class="btn btn-cta btn-sm">联系我</a>
  </div>
</nav>
```

- Logo使用名字（中文或英文），名字后加金色句号作为品牌签名
- 导航链接不超过4个（不含CTA按钮）：关于/作品/技能/联系 足够
- 导航栏右侧始终放一个小型CTA按钮（"联系我"/"合作咨询"）
- 固定顶部（`position: fixed`），滚动时加毛玻璃效果
- 移动端收起为汉堡菜单，菜单底部放CTA按钮
- 当前所在section的导航链接加金色下划线高亮

### 7.6 移动端适配要点

1. **头像尺寸适当缩小**：移动端头像 `width: 180px; height: 180px`，仍然居中或右侧
2. **L1非对称Hero改为单列**：移动端文字在上、头像在下，居中对齐
3. **作品网格改为双列或单列**：L10 bento网格移动端改为双列等宽，L11瀑布流改为双列
4. **CTA按钮宽度100%**，放在屏幕下半区，拇指热区内
5. **导航栏折叠为汉堡菜单**，菜单内包含联系CTA
6. **时间线左侧间距缩小**：移动端padding-left适当减小
7. **名字字号**移动端不小于48px，保持视觉冲击力
8. **所有触摸目标 ≥ 44×44px**，社交链接图标≥40px
9. **IP形象**移动端适当缩小或隐藏，避免占用过多屏幕空间
10. **首屏不使用100vh**（移动端浏览器地址栏问题），改用 `min-height: 85vh`

### 7.7 暗色模式说明（P2加分项）

Portfolio可支持暗色模式作为加分项，但需注意：

- 背景色从暖米白 `#FDFBF6` 切换为墨黑 `#0D1225` 或深海军蓝 `#081537`
- 卡片背景从白色切换为 `#131B30`
- 正文文字从深灰切换为 `rgba(255,255,255,0.8)`
- 金色和酒红保持不变，皇家蓝可适当提亮为 `#2A44A3`
- 头像金色边框和阴影在暗色下更明显，可适当增强金色光晕
- 使用 `prefers-color-scheme: dark` 自动切换，或提供手动切换按钮
- **不强制要求**，P2优先级

---

## 8. 场景专属 Checklist

在交付任何 Portfolio / 个人主页之前，必须通过以下检查：

### P0 — 必须通过（缺一不可，直接影响个人品牌呈现）

- [ ] **头像正确显示且有金色边框**：头像图片加载正常，有3px金色边框（`var(--gold)`）+ 柔和金色阴影
- [ ] **作品卡片有hover交互**：hover时显示皇家蓝遮罩 + 金色"查看案例"标签，卡片上移+阴影
- [ ] **联系方式清晰可见**：导航栏有联系CTA，Hero区有联系/查看作品按钮，结尾Contact区有明确联系方式（邮箱/社交）
- [ ] **名字使用超大衬线斜体**：h1名字为Playfair Display italic，字号≥clamp(3rem,9vw,6rem)，是页面最大元素
- [ ] **职业标签使用eyebrow样式**：小字号、全大写、宽字距、背景色块，位于名字上方
- [ ] **三种品牌色严格为 `#0A2463` / `#F4D35E` / `#D8315B`**
- [ ] **作品区占页面最大视觉比重**：作品卡片数量≥6个，图片清晰，间距宽松
- [ ] **结尾使用L13深色面板**：深蓝径向渐变背景+金色CTA按钮+联系方式
- [ ] **衬线+无衬线混搭策略**：标题Playfair Display，正文Inter，引言/副标题Cormorant Garamond italic
- [ ] **页面背景为暖米白 `#FDFBF6`**，不使用纯白或冷灰背景
- [ ] **正文行高1.7**，名字行高1.0，标题行高1.05-1.2
- [ ] **导航栏固定顶部**，含名字Logo+导航链接+联系CTA按钮
- [ ] **社交链接存在**：Hero区和Contact区至少各出现一次
- [ ] **响应式适配**：移动端单列布局，头像和名字居中，CTA按钮全宽
- [ ] **所有链接、按钮经过品牌化处理**，不保留浏览器默认样式
- [ ] **不出现禁忌清单中的元素**（纯黑/纯白大面积、冷灰、AI光效、bounce动画、技能进度条等）

### P1 — 应该通过（尽量满足，影响质感和品牌完整度）

- [ ] **IP形象自然出现**：在Hero区头像旁或About区自然出现`assets/character.png`，尺寸克制，不替代真实头像
- [ ] **有个人金句/引言**：至少1处Cormorant Garamond斜体金句，体现个人设计哲学或品牌态度
- [ ] **作品使用非对称布局**：L10 bento网格或L11交错瀑布流，不是整齐的等大卡片墙
- [ ] **精选作品有酒红"精选"标签**：1-2个代表作品用`badge-wine`标记
- [ ] **section标题有金色序号+装饰线**：形成品牌签名感
- [ ] **有Scroll Reveal入场动画**，轻、慢、克制（300-600ms，ease-out），不影响阅读
- [ ] **每个section使用不同布局**：不连续使用两个相同类型的网格/卡片布局
- [ ] **社交链接有hover效果**：hover变金色底+上移
- [ ] **About区有故事感**：不是简历罗列，而是2-3段有温度的个人介绍
- [ ] **至少一个视觉惊喜section**：L8引文全屏或L16画册溢出式，打破模板感
- [ ] **选中文本背景为金色**：`::selection { background: var(--gold); color: var(--royal); }`
- [ ] **深色面板CTA使用金色按钮**（而非酒红），深蓝背景上金色最醒目
- [ ] **名字后有金色句号签名细节**：如"飞鸿."中的金色点

### P2 — 加分项（锦上添花，提升专业度）

- [ ] **作品可筛选**：filter-tabs按分类筛选作品（全部/品牌/UI/插画等）
- [ ] **有暗/亮模式切换**：暗色模式下品牌色保持识别度，背景切换为深色
- [ ] **作品卡片点击进入详情页**：有独立的作品详情页展示案例完整过程
- [ ] **时间线展示职业经历**：L12时间线，金色节点+皇家蓝连线
- [ ] **有下载简历按钮**：`btn-outline`样式，提供PDF简历下载
- [ ] **导航栏当前section高亮**：滚动时对应导航链接加金色下划线
- [ ] **IP形象有轻柔浮动动画**：幅度小（±8px）、周期长（4s），尊重`prefers-reduced-motion`
- [ ] **有客户评价/推荐**：2-4条card-testimonial，含真实头像+姓名+身份
- [ ] **动效克制优雅**：没有bounce/弹性动画，没有无限循环动画
- [ ] **页面加载性能良好**：图片懒加载+压缩，字体预加载，首屏内容快速呈现
- [ ] **联系表单有品牌化验证**：focus皇家蓝光晕，错误酒红提示，成功金色反馈
- [ ] **有回到顶部按钮**：滚动超过一屏后显示，点击平滑回到顶部

### 交付前自检三问

1. **这像一个"人"的主页还是模板？**：看到头像、金句、个人故事了吗？还是一堆卡片和网格的堆砌？
2. **作品足够突出吗？**：打开页面3秒内，访客的目光是否被作品吸引？作品图片是否清晰、有吸引力？
3. **想联系你方便吗？**：如果我是潜在客户/雇主，我能在3秒内找到你的联系方式吗？

---

## 附录：Portfolio Hero 首屏快速模板结构（L1 非对称图文）

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>飞鸿 · 品牌设计师</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700;1,900&family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400;1,600&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    /* === Brand Tokens === */
    :root {
      --royal: #0A2463; --gold: #F4D35E; --wine: #D8315B;
      --cream: #FDFBF6; --ink: #0D1225;
      --royal-50: #EEF1FA; --gold-200: #FAEBA3;
      --ink-100: #2C3347; --ink-200: #4C546A; --ink-300: #6D7487;
      --cream-100: #F8F4EB; --cream-200: #F0EAD9;
      --font-serif: 'Playfair Display', 'Noto Serif SC', Georgia, serif;
      --font-sans: 'Inter', 'Noto Sans SC', -apple-system, sans-serif;
      --font-display: 'Cormorant Garamond', 'Noto Serif SC', Georgia, serif;
      --r-lg: 12px; --r-xl: 20px;
      --sp-1: 0.25rem; --sp-2: 0.5rem; --sp-3: 0.75rem; --sp-4: 1rem;
      --sp-5: 1.5rem; --sp-6: 2rem; --sp-8: 3rem;
      --shadow-md: 0 4px 16px rgba(10,36,99,0.10);
      --shadow-lg: 0 8px 32px rgba(10,36,99,0.12);
      --shadow-gold: 0 8px 32px rgba(244,211,94,0.2), 0 4px 16px rgba(10,36,99,0.1);
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
    .navbar.scrolled { border-bottom: 1px solid var(--cream-200); box-shadow: 0 1px 8px rgba(10,36,99,0.06); }
    .nav-logo { font-family: var(--font-serif); font-size: 1.5rem; font-weight: 700; color: var(--royal); text-decoration: none; }
    .nav-logo .gold-dot { color: var(--gold); }
    .nav-links { display: flex; align-items: center; gap: var(--sp-6); }
    .nav-link { font-size: 0.9375rem; color: var(--ink-200); text-decoration: none; transition: color 0.2s; }
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
    .btn-gold:hover { background: #DDB52E; transform: translateY(-1px); }
    .btn-outline { background: transparent; color: var(--royal); border: 1.5px solid var(--royal); }
    .btn-outline:hover { background: var(--royal); color: #fff; }
    .btn-lg { padding: var(--sp-4) var(--sp-6); font-size: 1.0625rem; }
    .btn-xl { padding: var(--sp-5) var(--sp-8); font-size: 1.125rem; }
    .btn-sm { padding: 0.5rem var(--sp-4); font-size: 0.8125rem; }

    /* === Eyebrow === */
    .eyebrow {
      display: inline-block; font-size: 0.75rem; font-weight: 500;
      letter-spacing: 0.2em; text-transform: uppercase;
      color: var(--royal); background: var(--royal-50);
      padding: 0.3rem 0.85rem; border-radius: 4px; margin-bottom: var(--sp-4);
    }

    /* === Hero (L1 非对称图文) === */
    .L1-hero {
      min-height: 85vh; display: flex; align-items: center;
      padding: 6rem var(--sp-4) 4rem; position: relative;
    }
    .L1-hero .container {
      display: grid; grid-template-columns: 1.2fr 1fr;
      gap: var(--sp-8); align-items: center;
      width: 100%;
    }
    .hero-text { position: relative; z-index: 2; }
    .hero-name {
      font-family: var(--font-serif); font-size: clamp(3rem, 9vw, 6rem);
      font-weight: 900; font-style: italic; line-height: 1;
      color: var(--ink); margin: var(--sp-3) 0 var(--sp-4);
      letter-spacing: -0.02em;
    }
    .hero-name .gold-dot { color: var(--gold); font-style: normal; }
    .hero-subtitle {
      font-family: var(--font-display); font-size: clamp(1.1rem, 2vw, 1.5rem);
      font-style: italic; color: var(--ink-200); line-height: 1.6;
      max-width: 480px; margin-bottom: var(--sp-6);
    }
    .hero-actions { display: flex; gap: var(--sp-3); flex-wrap: wrap; margin-bottom: var(--sp-6); }

    /* === Social Links === */
    .social-links { display: flex; gap: var(--sp-3); }
    .social-link {
      width: 40px; height: 40px;
      display: flex; align-items: center; justify-content: center;
      border-radius: 50%; background: var(--royal-50); color: var(--royal);
      transition: all 250ms var(--ease); text-decoration: none;
    }
    .social-link:hover {
      background: var(--gold); color: var(--royal);
      transform: translateY(-2px); box-shadow: 0 4px 12px rgba(244,211,94,0.3);
    }
    .social-link svg { width: 18px; height: 18px; }

    /* === Avatar === */
    .hero-visual { position: relative; display: flex; justify-content: center; }
    .avatar {
      border-radius: 50%; overflow: hidden;
      border: 3px solid var(--gold);
      box-shadow: var(--shadow-gold);
      position: relative;
    }
    .avatar-lg { width: clamp(220px, 30vw, 340px); height: clamp(220px, 30vw, 340px); }
    .avatar img { width: 100%; height: 100%; object-fit: cover; display: block; }
    .ip-mascot {
      position: absolute; width: 120px; bottom: -10px; right: -10px;
      filter: drop-shadow(0 4px 12px rgba(10,36,99,0.15));
      animation: float 4s ease-in-out infinite; z-index: 2;
    }
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-8px); }
    }

    /* === Reveal Animation === */
    .reveal { opacity: 0; transform: translateY(30px); transition: opacity 700ms var(--ease), transform 700ms var(--ease); }
    .reveal.visible { opacity: 1; transform: translateY(0); }
    .reveal-delay-1 { transition-delay: 100ms; }
    .reveal-delay-2 { transition-delay: 200ms; }

    /* === Responsive === */
    @media (max-width: 768px) {
      .nav-links .nav-link { display: none; }
      .L1-hero .container { grid-template-columns: 1fr; text-align: center; gap: var(--sp-6); }
      .hero-visual { order: -1; }
      .avatar-lg { width: 200px; height: 200px; }
      .hero-subtitle { margin-left: auto; margin-right: auto; }
      .hero-actions { justify-content: center; }
      .social-links { justify-content: center; }
      .ip-mascot { width: 90px; right: 20px; }
      .btn-cta, .btn-gold, .btn-outline { width: 100%; }
    }
    @media (prefers-reduced-motion: reduce) {
      .reveal { opacity: 1; transform: none; }
      .ip-mascot { animation: none; }
      html { scroll-behavior: auto; }
    }
  </style>
</head>
<body>
  <!-- Navbar -->
  <nav class="navbar" id="navbar">
    <a href="#" class="nav-logo">飞鸿<span class="gold-dot">.</span></a>
    <div class="nav-links">
      <a href="#about" class="nav-link">关于</a>
      <a href="#works" class="nav-link">作品</a>
      <a href="#skills" class="nav-link">技能</a>
      <a href="#contact" class="btn btn-cta btn-sm">联系我</a>
    </div>
  </nav>

  <!-- ① Hero (L1 非对称图文) -->
  <section class="L1-hero" id="hero">
    <div class="container">
      <div class="hero-text">
        <span class="eyebrow reveal">品牌设计师 · 独立创作者</span>
        <h1 class="hero-name reveal reveal-delay-1">飞鸿<span class="gold-dot">.</span></h1>
        <p class="hero-subtitle reveal reveal-delay-2">用设计为品牌注入温度与记忆点。<br>相信好的设计不是装饰，而是沟通。</p>
        <div class="hero-actions reveal reveal-delay-2">
          <a href="#works" class="btn btn-cta btn-lg">查看作品 →</a>
          <a href="#contact" class="btn btn-outline btn-lg">联系我</a>
        </div>
        <div class="social-links reveal reveal-delay-2">
          <a href="mailto:hello@Feihong.art" class="social-link" aria-label="Email">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          </a>
          <a href="#" class="social-link" aria-label="Dribbble">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M8.56 2.75c4.37 6.03 6.02 9.42 8.03 17.72m2.54-15.38c-3.72 4.35-8.94 5.66-16.88 5.85m19.5 1.9c-3.5-.93-6.63-.82-8.94 0-2.58.92-5.01 2.86-7.44 6.32"/></svg>
          </a>
          <a href="#" class="social-link" aria-label="Behance">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M2 7h6a2.5 2.5 0 0 1 0 5H2zm0 5h7a2.5 2.5 0 0 1 0 5H2zM14 8h7M14 14h7a3 3 0 0 0-6 0c0 1.66 1.34 3 3 3h1"/></svg>
          </a>
        </div>
      </div>
      <div class="hero-visual reveal reveal-delay-1">
        <div class="avatar avatar-lg">
          <img src="assets/avatar.png" alt="飞鸿">
        </div>
        <img src="assets/character.png" alt="飞鸿IP形象" class="ip-mascot">
      </div>
    </div>
  </section>

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

作品集/个人主页是个人品牌的数字名片，用于展示作品、建立信任、促成联系。适用于设计师、艺术家、摄影师、开发者、创意从业者展示个人作品和职业经历。不适用于企业官网（应更商务正式）、电商转化页（应更功能导向）、纯博客内容站（应更阅读导向）。核心目标是让访客在30秒内记住你是谁、做什么、水平如何——视觉冲击优先，信息量克制，每屏有明确焦点。

## 推荐节奏（Section 序列）

### 方案 A：经典设计师型（7屏，最常用）
1. Hero（L1 非对称图文）— 头像+名字+一句话定位+CTA，3秒建立第一印象
2. About（L5 左图右文）— 人像照+个人故事+数据数字，建立信任与人味
3. 金句穿插（L8 引文全屏）— 衬线斜体金句，呼吸感与态度表达
4. 作品展示（L10 非对称Bento网格）— 1-2个大卡片精选+其余网格，视觉主体
5. 技能/经历（L9 三列卡片 / L12 时间线）— 能力背书与职业轨迹
6. 客户推荐（card-testimonial组）— 第三方信任证言
7. 联系（L13 深色面板CTA）— 深蓝底+金色按钮+社交链接，行动收口

### 方案 B：极简艺术家型（6屏）
1. Hero（L2 居中大字）— 超大衬线名字+副标题，克制大气
2. 画册开篇（L16 画册溢出式）— 一幅代表作全屏溢出，视觉震撼
3. 作品瀑布（L11 交错瀑布流）— 视觉绝对主体，作品本身说话
4. About（L6 左文右图）— 简短介绍+工作照/肖像
5. 艺术宣言（L8 引文全屏）— 金色大引号+创作理念
6. 联系（L13 深色面板CTA）— 委托/合作邀请

### 方案 C：求职精简型（5屏）
1. Hero（L1 非对称图文）— 头像+名字+职位目标+核心技能标签+简历下载
2. About（L5 左图右文）— 3-5句自我介绍+关键数据（年限/项目数/客户数）
3. 精选项目（L10 非对称Bento）— 3-5个大卡片，每个含项目结果数据
4. 经历（L12 时间线）— 教育+工作经历
5. 联系（L13 深色面板CTA）— 邮箱+微信+LinkedIn+"期待合作"

### 方案 D：豪华杂志型（10屏，资深创作者）
1. Hero（L4 全屏视觉）— 全屏代表作+衬线大字叠加
2. 卷首语（L6 深色面板）— 皇家蓝底+金色文字引言
3. 代表作深度（L8 图文交错）— 每件重点作品独占一屏+故事
4. 工作室（L5 左图右文 / L9 图片全宽）— 工作场景照
5. 完整作品（L10 Bento网格）— 分类展示
6. 履历/展览（L12 时间线）— 获奖/展览/出版物
7. 媒体评价（card-testimonial组）— 多条引用堆叠
8. 合作品牌（L9 三列）— Logo墙
9. 金句收束（L8 引文全屏）— 个人哲学
10. 联系（L13 深色面板CTA）— 豪华深色收尾

## 专属装饰手法（Signature Touches）

- **#10 Wax Seal 火漆印章**：放在About Me人像照片右下角（叠在照片上），作为个人签名感锚点；Footer品牌名旁放小号火漆
- **#07 Decorative Rule 装饰线**：作品网格与About之间用金色双线装饰线分隔，增加仪式感和版面节奏感
- **#04 Pull Quote 金句引用**：Hero下方或About前，大字引用自己的设计理念，Cormorant斜体金色在深蓝底或皇家蓝色在米白底
- **#20 Numbered Index 编号索引**：作品网格每件作品标注编号（No.01, No.02...），衬线小字金色，增加档案/目录感
- **#09 Fleuron 花饰**：Section标题两侧使用Fleuron（❦），如 "❦ 精选作品 ❦"，古典书卷气
- **#11 Ornamental Corner 角饰**：深色Hero面板四角加金色角饰线，营造古典画框感
- **#19 Handwritten Note 手写注**：About Me照片旁加手写体签名或日期（如"— 飞鸿，2026"），增加人味
- **#15 Divider 分隔线**：Section之间用金色细线+Fleuron分隔，而非大块留白
- **#03 Image Frame 图片画框**：作品展示图片加1px金色细边框（`border: 1px solid #F4D35E`），模拟画廊装裱
- **#13 Red Thread 红线**：页面左侧可加1px酒红竖线装饰，增加装订/书脊感
- **#14 Section Marker 章节标记**：每个Section左上角用罗马数字（I, II, III...）金色标注
- **#22 Publication Header 刊头标题**：Hero区域可用报纸刊头式排版，品牌名大写衬线居中，下方金色细线分隔

## 推荐布局组合

| 布局 | 名称 | 适用位置 | 说明 |
|------|------|----------|------|
| **L1** | 非对称图文Hero | 首屏（首选） | 头像+名字+介绍，个人感最强，设计师首选 |
| **L2** | 居中大字Hero | 首屏（备选） | 极简艺术家/摄影师风格，名字居中大气克制 |
| **L4** | 全屏视觉Hero | 首屏（备选） | 大幅代表作+文字叠加，视觉冲击最强 |
| **L5** | 左图右文 | About区 | 人像照+个人简介，经典人物介绍 |
| **L8** | 引文全屏 | Section之间 | 金句/宣言穿插，Cormorant斜体，呼吸停顿 |
| **L10** | 非对称Bento网格 | 作品展示 | 大小卡片错落，设计感强，作品集首选网格 |
| **L11** | 交错瀑布流 | 作品展示（备选） | 不等高两列/三列，适合插画/摄影作品尺寸不一时 |
| **L9** | 三列卡片网格 | 技能/服务区 | 等宽三列展示能力标签或服务项 |
| **L12** | 时间线 | 经历区 | 皇家蓝连线+金色节点，职业/项目历程 |
| **L13** | 深色面板CTA | 结尾联系区 | 深蓝径向渐变+金色CTA按钮，全页仅1次 |
| **L16** | 画册溢出式 | 视觉惊喜 | 代表作品突破容器宽度，画廊/画册感 |

## 色彩策略

作品集场景三色分配：

**皇家蓝 #0A2463（55%）—— 主色，沉稳权威**
- Hero深色背景（L13/L4深色模式）
- 所有标题文字（h1-h3）
- 作品卡片hover遮罩（`rgba(10,36,99,0.85)`）
- 导航栏背景（滚动后/深色模式）
- 深色面板（引言区可选、CTA区必用）
- 正文链接文字颜色
- 筛选标签激活态背景
- 时间线连线
- Footer背景

**复古金 #F4D35E（30%）—— 装饰，品质感**
- 头像3px金色边框（铁律）
- 装饰线、分隔线、角饰、Fleuron花饰
- 深色背景上的强调文字（金句、CTA按钮）
- 作品编号（No.01金色小字）
- 时间线节点圆点
- 名字后的金色句号签名
- 作品卡片hover时的"查看案例→"标签（金色描边+金色文字）
- 社交链接hover背景
- eyebrow标签可选金色背景
- **白底上绝不使用金色文字，仅用金色做线条/边框/小面积装饰**

**酒红 #D8315B（15%）—— 点缀，行动与激情**
- Hero主CTA按钮背景（"查看作品"/"联系我"）
- 作品卡片"精选"标签（badge-wine）
- 左侧红线装饰
- 导航当前页指示
- 重要数据数字高亮（如"50+"项目数）
- 表单错误提示
- 按钮hover深色态（#AD2749）

**深色面板节奏**：Hero可用深色开场；About和Works之间可用L8引文（可浅可深）；结尾L13必须深色。避免连续2个以上深色面板。深色面板内文字为白色+金色组合，绝不放酒红色文字在深蓝底上（对比度不足）。

## 场景禁忌（Don'ts）

1. **作品图片变形/压缩**：图片比例失调是作品集致命错误，必须用`object-fit:cover`且容器比例统一
2. **假数据/Lorem Ipsum占位**：个人网站每一个字都应真实，假文案立刻暴露模板感
3. **自动播放音视频**：打开网页突然出声是最差的第一印象
4. **技能进度条**：过于俗套的UI模式，用卡片或标签展示技能更高级
5. **所有作品等大整齐排列**：AI模板典型特征，必须用Bento错落或瀑布流
6. **IP形象替代真实头像**：个人品牌需要真实人像建立信任，IP只能辅助
7. **联系方式隐藏过深**：不要让访客点3次才能找到邮箱，Hero和Footer都要有
8. **过度鼠标跟随/光标特效**：干扰浏览作品本身，作品集的主角是作品不是特效
9. **Loading动画超过2秒**：作品集要快速展示作品，首屏加载<3秒
10. **多个深色面板堆砌**：深色面板全页最多2处（Hero可选+CTA必用），过多会压抑

## 场景专属Checklist

- [ ] Hero首屏在100vh（移动端85vh）内完整显示，无需滚动即可看到名字+定位+CTA
- [ ] 头像有3px金色边框（`#F4D35E`）+金色光晕阴影，图片清晰专业
- [ ] 名字为Playfair Display italic超大字号（clamp 3-6rem），是页面最大元素
- [ ] 作品卡片hover效果正常：皇家蓝遮罩+金色"查看案例→"标签+卡片上移6px
- [ ] 作品图片全部加载无变形，使用统一比例或Bento错落布局
- [ ] 作品数量≥6个，精选作品有酒红"精选"标签，1-2个大卡片置顶
- [ ] 联系方式清晰可见：导航栏CTA+Hero按钮+结尾Contact区+Footer
- [ ] 邮箱链接为可点击mailto链接，社交链接打开新标签页
- [ ] 导航固定顶部，滚动有毛玻璃效果，移动端汉堡菜单
- [ ] 深色面板与浅色面板交替，结尾必用L13深色CTA（金色按钮）
- [ ] 至少1处Cormorant Garamond斜体金句/引言，体现个人态度
- [ ] 衬线标题+无衬线正文+斜体引言的字体混搭策略执行到位
- [ ] 页面背景为暖米白`#FDFBF6`，无纯黑/纯白大面积/冷灰色块
- [ ] 移动端1280px/768px/375px三档宽度正常：单列+头像居中+CTA全宽
- [ ] 所有触摸目标≥44px，按钮和链接无浏览器默认样式
- [ ] 选中文本背景为金色（`::selection`），无bounce/弹性/无限循环动画

---

*Scene: Portfolio v1.0 · Feihong Design System*
*基于 DNA.md v2.0 · 最后更新：2026-07-08*
