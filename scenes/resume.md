# Feihong Design System · Scene: Resume
# 飞鸿品牌设计系统 · 场景规范：简历 / CV

> 本规范定义飞鸿品牌设计系统在「个人简历 / 履历 / CV」中的具体应用方式。
> 所有规则建立在 `DNA.md`、`components/14-layouts.md`、`components/` 基础之上，场景专属规则以本文件为准。
> 简历场景的核心使命是**专业呈现**——在一张A4纸上，让阅读者快速建立对你的专业信任。

---

## 1. 场景定义

### 适用页面类型

Resume场景适用于以下以**个人信息高效传达为核心目标**的文档形态：

| 类型 | 说明 | 典型长度 | 核心目标 |
|------|------|----------|---------|
| **求职简历** | 应聘岗位用的标准简历 | 1页A4 | 获得面试机会 |
| **学术CV** | 申请学术/研究职位 | 1-2页A4 | 展示学术成果 |
| **个人履历** | 自由职业者/顾问的个人介绍 | 1页A4 | 建立专业信任 |
| **在线简历页** | 个人网站上的简历页面 | 1屏~1.5屏 | 在线展示+PDF导出 |
| **简历PDF** | 用于投递/打印的PDF文件 | 1页A4 | 打印/邮件投递 |

### 场景核心气质

- **专业克制**：没有花哨装饰，排版服务于信息传达
- **信息密度高**：在有限空间内呈现最有价值的信息
- **品牌质感**：通过衬线姓名+金色细节点缀传递品味，不使用廉价模板感
- **打印友好**：黑白打印依然清晰可读，不依赖彩色背景传达信息

### 场景核心约束

1. **单页原则**：简历内容不超过1页A4纸（学术CV除外），不翻页
2. **打印友好**：必须有 `@media print` 样式，黑白打印效果可接受
3. **无动效无JS依赖**：简历是文档，不是网页应用，不需要交互动画
4. **经历倒序排列**：工作经历和教育背景按时间倒序（最近的在前）
5. **联系方式清晰可见**：姓名+职位+联系方式在头部区域一目了然
6. **极度克制用色**：大面积留白+墨黑文字，品牌色仅作为点缀

---

## 2. 典型页面结构

简历页面采用**头部信息 + 分栏/分块内容**的经典文档结构，根据布局风格有两种典型结构：

```
┌─────────────────────────────────────────────────────────┐
│  结构 A：单栏布局（经典、通用、最易维护）                   │
├─────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────┐  │
│  │  头部（Header）                                     │  │
│  │  姓名（大，衬线）| 职位头衔                           │  │
│  │  邮箱 · 手机 · 地点 · 网站/LinkedIn                  │  │
│  └───────────────────────────────────────────────────┘  │
│  ── 金色细线 ──────────────────────────────────────────  │
│                                                         │
│  SUMMARY / 个人简介                                     │
│  2-3句话概括核心能力与定位                                │
│                                                         │
│  ── 金色小圆点+章节标题（大写宽字距）────────────────────  │
│  EXPERIENCE / 工作经历                                   │
│  ● 职位 @ 公司 | 时间                      ◆            │
│    公司简介（一句话）                                    │
│    - 成就点1（量化数据）                                 │
│    - 成就点2（量化数据）                                 │
│    - 成就点3                                            │
│                                                         │
│  ● 职位 @ 公司 | 时间                                   │
│    - 成就点...                                          │
│                                                         │
│  ── 金色小圆点+章节标题 ──────────────────────────────   │
│  EDUCATION / 教育背景                                    │
│  ● 学位 @ 学校 | 时间                                   │
│                                                         │
│  ── 金色小圆点+章节标题 ──────────────────────────────   │
│  SKILLS / 技能                                           │
│  技能标签组 / 技能进度条                                  │
│                                                         │
│  ── 金色小圆点+章节标题 ──────────────────────────────   │
│  PROJECTS / 项目（可选）                                 │
│  ● 项目名 - 简介                                        │
│                                                         │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│  结构 B：双栏布局（左窄右宽，现代感强，信息密度高）         │
├──────────────────────┬──────────────────────────────────┤
│                      │  姓名（大，衬线）                   │
│   左侧栏（~30%）      │  职位头衔                          │
│                      │  联系方式                          │
│   联系方式            ├──────────────────────────────────┤
│   · email            │                                  │
│   · phone            │  SUMMARY / 个人简介                │
│   · location         │                                  │
│   · website          │  EXPERIENCE / 工作经历             │
│                      │  ● 职位 @ 公司 | 时间              │
│   ──细线──            │    - 成就点...                     │
│   SKILLS / 技能       │                                  │
│   [技能标签组]        │  ● 职位 @ 公司 | 时间              │
│   或进度条            │    - 成就点...                     │
│                      │                                  │
│   ──细线──            ├──────────────────────────────────┤
│   EDUCATION / 教育    │                                  │
│   ● 学位 @ 学校       │  PROJECTS / 项目（可选）           │
│   ● 学位 @ 学校       │  ● 项目名 - 简介                  │
│                      │                                  │
│   ──细线──            │                                  │
│   LANGUAGES / 语言    │                                  │
│   中文 ●●●●●          │                                  │
│   English ●●●●○       │                                  │
│                      │                                  │
└──────────────────────┴──────────────────────────────────┘
```

### 结构要点

1. **头部区域**占页面顶部约10-15%，包含姓名（最大字号）、职位头衔、联系方式
2. **个人简介/Summary**紧跟头部，2-3句话，不超过4行
3. **工作经历**是简历主体，占最大篇幅（约40-50%），倒序排列
4. **章节标题**统一格式：左侧金色小圆点 + 大写字母章节名 + 细线延伸（或全宽金色细线下划线）
5. **教育/技能**占15-20%，简洁罗列
6. **项目经历**可选，根据岗位需要决定是否包含
7. **不放图片**（除非岗位明确要求头像，如空乘/模特）
8. **不使用彩色背景卡片**分割内容，用细线和间距分区

---

## 3. 色彩使用指南

简历场景的色彩原则是**极度克制**——品牌色仅用于点缀和品牌识别，90%以上面积是白色背景+墨黑文字。打印时，即使在黑白模式下所有关键信息依然清晰可读。

### 3.1 皇家蓝 `#0A2463` — 姓名与标题色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **姓名** | 头部姓名用皇家蓝 | 唯一大面积使用品牌色的文字，建立品牌识别 |
| **章节标题** | EXPERIENCE/EDUCATION/SKILLS等标题 | 皇家蓝大写字母，字号小但字距宽 |
| **链接文字** | 邮箱、网站、LinkedIn链接 | 皇家蓝下划线或纯皇家蓝文字 |

> **铁律**：皇家蓝在简历中只用在**姓名和章节标题**两处，不用于正文、不用于背景、不用于装饰色块。

### 3.2 复古金 `#F4D35E` — 点缀与分割色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **分割线** | 章节之间的金色细线 | 0.5-1px，`#F4D35E` 或更淡的金色 `#FAEBA3` |
| **小圆点** | 章节标题前的金色圆点 | 6-8px直径的金色圆点 ● 代替数字序号 |
| **标签点缀** | 技能标签的边框/背景 | 极浅金色背景+皇家蓝文字，或金色边框 |
| **时间线圆点** | 工作经历条目旁的金色小圆点 | 标记每条经历的起始位置 |
| **技能进度条** | progress的填充色 | 金色填充，白色或浅灰轨道 |
| **星级评分** | 语言能力/技能水平的星标 | 金色实心星，灰色空心星 |

> **铁律**：金色仅用于**线、点、边框**等装饰细节，绝不做文字颜色或背景填充。金色的面积应该小而精致。

### 3.3 酒红 `#D8315B` — 几乎不用

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **亮点标签**（可选） | 1-2个亮点标签（如"Top 1%"、"获奖"） | 全页最多1-2处，极度克制 |
| **不使用** | 不用于分割线、标题、正文、背景 | 酒红在简历中容易显得突兀 |

> **铁律**：酒红在简历中**几乎不用**。如果一定要用，全页不超过2处，仅用于突出最亮眼的1-2个标签。

### 3.4 背景与文字色（简历主力色）

| 元素 | 色值 | 说明 |
|------|------|------|
| **页面背景** | `#FFFFFF`（纯白） | 打印友好，不用暖米白（打印时可能偏黄） |
| **姓名颜色** | `#0A2463`（皇家蓝） | 衬线大字号，页面视觉锚点 |
| **正文文字** | `#0D1225`（墨黑）或 `#1A1F36` | 接近纯黑，打印清晰 |
| **章节标题** | `#0A2463`（皇家蓝） | 大写字母，宽字距 |
| **辅助文字** | `#4A5066` | 时间、公司名、地点等元信息 |
| **弱化文字** | `#8A90A5` | 次要信息、标签内文字 |
| **分割线** | `#F4D35E`（金色，章节间）或 `#E8E3D4`（暖灰，条目间） | 两种层级的分割线 |
| **标签背景** | `#FEFCF0`（极浅金） | 技能标签等浅金色背景 |
| **进度条轨道** | `#F0EAD9` | 暖灰色轨道 |

### 3.5 打印色彩规则

1. **黑白打印必须可读**：将页面转为灰度后，姓名（黑底深字）、章节标题（深灰）、正文（黑）、分割线（浅灰）层次分明
2. **不用浅色文字**：不在白色背景上使用金色文字（打印时看不见）
3. **不用彩色背景**：任何区块都不使用彩色背景填充（打印时浪费墨水且可能发灰）
4. **链接打印不显示蓝色**：`@media print` 中将链接颜色设为黑色，去掉下划线
5. **分割线在打印时可见**：金色细线打印后应为浅灰色，仍然可辨

### 色彩使用铁律（Resume场景）

1. **皇家蓝仅用于姓名+章节标题**，全页不超过15%的文字着色
2. **金色仅用于线和点**，不做文字色、不做背景色
3. **酒红几乎不用**，全页不超过2处点缀标签
4. **正文一律墨黑**，不用灰色正文（灰色在打印时可能太浅）
5. **背景一律纯白**，不使用任何彩色背景或渐变
6. **技能标签用极浅金底+皇家蓝文字**，打印后为浅灰底+深灰字，依然清晰

---

## 4. 排版规范

简历排版以**紧凑、清晰、层次分明**为核心。A4纸尺寸严格控制，字号比网页小但必须可读。

### 4.1 页面尺寸

| 指标 | 规范值 | 说明 |
|------|--------|------|
| **页面尺寸** | 210mm × 297mm（A4） | 严格A4尺寸，不使用Letter |
| **页面边距** | 上下 15-20mm，左右 18-22mm | 打印不贴边，PDF导出不裁切 |
| **内容宽度** | 约170mm | A4宽度减去左右边距 |
| **单栏内容宽度** | 160-170mm | 适合阅读的单行长度 |
| **双栏左侧宽度** | 约55-65mm（约30%） | 放技能、联系方式等短信息 |
| **双栏右侧宽度** | 约100-110mm（约70%） | 放工作经历等长内容 |
| **栏间距** | 8-10mm | 双栏之间的间距 |

### 4.2 字号规范

| 元素 | 字号 | 行高 | 字体 | 颜色 | 说明 |
|------|------|------|------|------|------|
| **姓名** | 24-28px（1.5-1.75rem） | 1.2 | Playfair Display 700 | 皇家蓝 `#0A2463` | 页面最大字号，唯一衬线大字 |
| **职位头衔** | 13-15px | 1.4 | Inter 500 | 墨黑 | 姓名下方，一句话定位 |
| **联系方式** | 10-11px | 1.4 | Inter 400 | `#4A5066` | 邮箱/手机/地点/网站，用 `·` 或 `|` 分隔 |
| **章节标题** | 11-12px（0.7-0.75rem） | 1.2 | Inter 600/700 | 皇家蓝 | 全大写，字距 0.15-0.2em |
| **公司/学校名** | 12-13px | 1.3 | Inter 600 | 墨黑 | 加粗，与职位名同行或下行 |
| **职位名/学位** | 11-12px | 1.3 | Inter 600 | 墨黑 | 加粗 |
| **时间/地点** | 10-11px | 1.3 | Inter 400 | `#4A5066` | 右对齐或跟在公司名后 |
| **正文/描述** | 10-11px（0.625-0.6875rem） | **1.4-1.5** | Inter 400 | 墨黑 | 简历主体文字，必须清晰 |
| **技能标签** | 9-10px | 1 | Inter 500 | 皇家蓝/墨黑 | 小标签，浅金背景 |
| **成就列表** | 10-11px | 1.4 | Inter 400 | 墨黑 | `- ` 或 `● ` 开头的bullet point |
| **辅助说明** | 9-10px | 1.3 | Inter 400 | `#8A90A5` | 最弱化的文字 |

> **字号铁律**：简历最小字号不小于9px（屏幕）/ 7pt（打印），正文不小于10px。宁可精简内容也不要把字号缩到看不清。

### 4.3 字体使用规则

| 字体 | 使用场景 | 禁用场景 |
|------|----------|---------|
| **Playfair Display（衬线）** | **姓名**（仅此一处大字）、可选的个人简介首字母大写 | 正文、公司名、职位名、技能标签、联系方式 |
| **Inter（无衬线）** | **其余所有文字**（职位、公司、正文、标签、章节标题） | 姓名（用衬线）、代码相关（如有） |
| **Cormorant Garamond（斜体）** | 不使用 | 简历中不使用斜体衬线，显得不够正式 |
| **JetBrains Mono（等宽）** | 技术岗位的技能列表（可选）、GitHub链接 | 正文、标题 |

> **铁律**：全页只有**姓名**一处使用Playfair Display衬线字体，其他所有文字一律Inter。这是简历场景最严格的字体规则。

### 4.4 间距规范

| 间距类型 | 规范值 | 说明 |
|----------|--------|------|
| 姓名与职位间距 | 4-6px | 紧密相连，形成头部组 |
| 头部与第一条分割线间距 | 12-16px | 头部组与正文之间有明确间隔 |
| 章节间距 | 16-20px | 两个section之间的距离 |
| 章节标题与内容间距 | 6-8px | 标题和下方内容间距小 |
| 工作条目间距 | 12-16px | 两个工作/教育条目之间 |
| 条目内标题与描述间距 | 3-4px | 公司行与bullet point之间 |
| bullet point之间 | 2-3px | 成就列表行距紧凑 |
| 章节分割线粗细 | 0.5-1px | 金色细线，不粗重 |

### 4.5 排版特殊规则

1. **章节标题格式**：
   ```
   ● EXPERIENCE ──────────────────────────
   ```
   - 金色小圆点（6-8px）+ 空格 + 大写字母标题（皇家蓝，0.15em字距）+ 金色细线延伸至行尾
   - 或：大写标题下方一条金色细线（宽度40-60px，左对齐，不延伸至全宽）

2. **工作经历条目格式**：
   ```
   ● 高级产品经理  @  某某科技有限公司           2023.06 - 至今
     领先的企业级SaaS平台，服务500+企业客户
     - 主导XX产品从0到1设计，上线6个月获取10万+用户
     - 优化核心转化漏斗，将付费转化率提升37%
     - 带领5人设计团队，建立组件库和设计规范
   ```
   - 职位名加粗 + 公司名（常规或轻量加粗）+ 时间右对齐
   - 公司简介一行（可选，斜体或灰色）
   - 2-4条成就bullet point，动词开头+量化数据

3. **联系方式格式**：
   ```
   hong.fei@email.com  ·  138-0000-0000  ·  上海  ·  linkedin.com/in/feihong
   ```
   - 用 ` · `（中间点+空格）分隔各项
   - 邮箱不加 `mailto:` 下划线（打印后不好看）
   - 电话号码用 `-` 分隔，便于阅读

4. **技能标签格式**：
   ```css
   .skill-tag {
     display: inline-block;
     font-size: 0.625rem; /* 10px */
     padding: 2px 8px;
     background: #FEFCF0; /* 极浅金 */
     color: var(--royal);
     border-radius: 3px;
     margin: 2px 4px 2px 0;
   }
   ```

5. **数字排版**：
   - 所有数字使用 `font-variant-numeric: tabular-nums`，对齐整齐
   - 百分比、金额等量化数据可加粗，吸引目光
   - 日期格式统一：`2023.06 - 至今` 或 `2021.09 - 2023.06`

---

## 5. 推荐布局

简历场景使用文档型布局，**不使用L8/L16等艺术化布局，不使用彩色背景卡片**。

### 5.1 布局选择

| 布局 | 适用人群 | 优点 | 缺点 |
|------|----------|------|------|
| **单栏布局** | 通用/所有行业/应届生/经验丰富者 | 最经典、最易阅读、ATS友好 | 信息密度稍低 |
| **双栏布局（左窄右宽）** | 设计师/创意行业/技能密集型岗位 | 现代感强、信息密度高、技能突出 | ATS解析可能有问题、实现稍复杂 |

### 5.2 单栏布局模板

```css
.resume-single {
  width: 210mm;
  min-height: 297mm;
  padding: 18mm 20mm;
  background: #fff;
  font-family: 'Inter', sans-serif;
  font-size: 10.5px;
  line-height: 1.5;
  color: var(--ink);
}
```

内容流从上到下：Header → Summary → Experience → Education → Skills → Projects（可选）

### 5.3 双栏布局模板

```css
.resume-dual {
  width: 210mm;
  min-height: 297mm;
  padding: 15mm 18mm;
  background: #fff;
  display: grid;
  grid-template-columns: 58mm 1fr;
  gap: 8mm;
  font-family: 'Inter', sans-serif;
  font-size: 10.5px;
}
```

- **左侧栏**放：联系方式、技能、教育、语言、证书（短信息模块）
- **右侧栏**放：姓名+职位头部、Summary、Experience、Projects（长内容模块）
- 左侧栏可以有一条1px金色竖线分隔（可选，非常克制）
- 头部区域（姓名+职位+联系方式）可横跨两栏，也可放在右侧栏顶部

### 5.4 经典简历布局配方

#### 配方 A：单栏通用简历（最推荐，适合所有场景）

| 顺序 | 模块 | 占比 |
|------|------|------|
| 1 | Header（姓名+职位+联系方式） | 10% |
| 2 | Summary（2-3句话） | 8% |
| 3 | Experience（3-4个经历，倒序） | 50% |
| 4 | Education（1-2个学历） | 12% |
| 5 | Skills（技能标签组） | 12% |
| 6 | Projects / Awards（可选） | 8% |

#### 配方 B：双栏创意/设计简历

| 位置 | 模块 |
|------|------|
| **横跨头部** | 姓名（皇家蓝衬线）+ 职位头衔 + 金色细分割线 |
| 左栏 | 联系方式 · 技能（标签或进度条）· 教育 · 语言 · 证书 |
| 右栏 | Summary · Experience · Projects |

#### 配方 C：技术岗简历

| 顺序 | 模块 | 特殊处理 |
|------|------|---------|
| 1 | Header | 姓名+职位+"全栈工程师"等明确头衔 |
| 2 | 技术栈（Skills提前） | 编程语言/框架/工具用等宽字体标签 |
| 3 | Experience | 强调技术成果，量化性能指标 |
| 4 | Projects | 开源项目/GitHub项目，附链接 |
| 5 | Education | 简洁 |

### 5.5 布局使用禁忌

| 布局/做法 | Resume场景不推荐原因 |
|-----------|---------------------|
| **L8引文全屏/L16画册溢出** | 艺术化布局不适合正式简历 |
| **彩色背景卡片/色块** | 打印不友好，分散注意力，显得不专业 |
| **card阴影/hover效果** | 简历是打印文档，不需要悬浮交互效果 |
| **dark-panel深色面板** | 打印时浪费墨水，黑白打印可能发灰 |
| **多列瀑布流** | 阅读顺序不清晰，ATS无法正确解析 |
| **头像/照片** | 国内大多数岗位不需要照片，可能引入偏见（除非岗位要求） |
| **图标装饰** | 电话图标、邮件图标等——直接用文字即可，图标浪费空间且可能不专业 |
| **双栏以上的多栏布局** | 三栏及以上太拥挤，阅读跳跃 |

---

## 6. 组件选用指南

### 6.1 必用组件

| 组件 | 使用方式 | 说明 |
|------|---------|------|
| **金色圆点分隔** | `●` 章节标题前的金色圆点、时间线标记 | 8px圆形金色，统一章节视觉 |
| **细线分割** | 章节间金色细线、条目间暖灰细线 | 0.5-1px，不用粗线 |
| **技能标签组** | `skill-tag` 系列，浅金底+皇家蓝文字 | 小标签，圆角3px，inline-block排列 |
| **bullet point列表** | 成就列表用 `- ` 或小型圆点 | 不用大号图标，保持简洁 |

### 6.2 金色圆点组件模式

```css
.gold-dot {
  display: inline-block;
  width: 7px; height: 7px;
  background: var(--gold);
  border-radius: 50%;
  margin-right: 8px;
  vertical-align: middle;
}

/* 章节标题 */
.section-header {
  display: flex; align-items: center;
  margin-bottom: 8px;
}
.section-header .gold-dot { flex-shrink: 0; }
.section-title {
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--royal);
  margin-right: 10px;
  white-space: nowrap;
}
.section-line {
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, var(--gold) 0%, #F0EAD9 60%, transparent 100%);
}
```

```html
<div class="section-header">
  <span class="gold-dot"></span>
  <span class="section-title">Experience</span>
  <span class="section-line"></span>
</div>
```

### 6.3 技能进度条模式

```css
.skill-bar-wrap { margin-bottom: 6px; }
.skill-bar-label {
  display: flex; justify-content: space-between;
  font-size: 10px; margin-bottom: 3px;
}
.skill-bar-label span:first-child { font-weight: 500; }
.skill-bar-label span:last-child { color: #8A90A5; }
.skill-bar {
  height: 4px;
  background: #F0EAD9;
  border-radius: 2px;
  overflow: hidden;
}
.skill-bar-fill {
  height: 100%;
  background: var(--gold);
  border-radius: 2px;
}
```

```html
<div class="skill-bar-wrap">
  <div class="skill-bar-label"><span>产品设计</span><span>精通</span></div>
  <div class="skill-bar"><div class="skill-bar-fill" style="width:90%"></div></div>
</div>
```

### 6.4 技能标签组模式

```css
.skill-tags { display: flex; flex-wrap: wrap; gap: 4px 6px; margin-top: 4px; }
.skill-tag {
  display: inline-block;
  font-size: 9.5px;
  font-weight: 500;
  padding: 2px 7px;
  background: #FEFCF0;
  color: var(--royal);
  border-radius: 3px;
  letter-spacing: 0.02em;
}
```

```html
<div class="skill-tags">
  <span class="skill-tag">Figma</span>
  <span class="skill-tag">Sketch</span>
  <span class="skill-tag">用户研究</span>
  <span class="skill-tag">原型设计</span>
  <span class="skill-tag">设计系统</span>
</div>
```

### 6.5 工作条目模式

```css
.exp-item { margin-bottom: 14px; }
.exp-header {
  display: flex; justify-content: space-between; align-items: baseline;
  margin-bottom: 3px;
}
.exp-role {
  font-size: 11.5px; font-weight: 600; color: var(--ink);
}
.exp-company {
  font-size: 11px; font-weight: 400; color: #4A5066;
  margin-left: 6px;
}
.exp-date {
  font-size: 10px; color: #8A90A5; white-space: nowrap;
}
.exp-bullets {
  margin: 4px 0 0 0; padding: 0; list-style: none;
}
.exp-bullets li {
  font-size: 10.5px; line-height: 1.45; color: var(--ink);
  padding-left: 12px; position: relative; margin-bottom: 2px;
}
.exp-bullets li::before {
  content: '–';
  position: absolute; left: 0; color: var(--gold);
}
```

```html
<div class="exp-item">
  <div class="exp-header">
    <div><span class="exp-role">高级产品设计师</span><span class="exp-company">@ 某某科技</span></div>
    <div class="exp-date">2023.06 - 至今</div>
  </div>
  <ul class="exp-bullets">
    <li>主导企业级SaaS产品设计体系重构，组件库覆盖200+组件，设计效率提升40%</li>
    <li>优化核心用户流程，将用户完成任务时间从3分钟缩短至45秒</li>
  </ul>
</div>
```

### 6.6 不使用的组件

| 组件 | 不使用原因 |
|------|-----------|
| `card`（带阴影卡片） | 简历是文档，不需要卡片容器，用线和间距分区即可 |
| `btn`系列（按钮） | 简历中无可点击操作，不需要按钮样式 |
| `dark-panel` | 打印不友好，简历无CTA区域 |
| `card-feature`/`card-testimonial` | Landing页组件，不适用 |
| `alert`/`toast` | 无交互提示场景 |
| `form-input`/`form-select` | 无表单场景 |
| `hover`/`dark-panel`效果 | 打印文档无鼠标悬浮状态 |
| `progress`大尺寸进度条 | 用小号skill-bar即可 |
| `timeline`（大号时间线） | 用金色小圆点+文字即可，不使用带连线的大时间线组件 |

---

## 7. 特殊注意事项

### 7.1 必须有 @media print 样式（铁律）

简历必须为打印优化，这是与其他场景最根本的区别：

```css
@media print {
  /* 重置页面 */
  @page {
    size: A4;
    margin: 0;
  }
  * {
    -webkit-print-color-adjust: exact !important;
    print-color-adjust: exact !important;
    color-adjust: exact !important;
  }
  html, body {
    margin: 0; padding: 0;
    background: #fff !important;
    font-size: 10.5pt; /* 打印用pt单位 */
  }
  .resume {
    width: 210mm;
    min-height: 297mm;
    margin: 0; padding: 15mm 18mm;
    box-shadow: none !important;
    page-break-after: avoid;
  }
  /* 隐藏不应打印的元素 */
  .no-print, nav, .toolbar, .download-btn { display: none !important; }
  /* 链接不显示蓝色和下划线 */
  a { color: var(--ink) !important; text-decoration: none !important; }
  /* 避免分页断字/断条 */
  .exp-item, .edu-item, section {
    page-break-inside: avoid;
    break-inside: avoid;
  }
  h1, h2, h3, .section-header {
    page-break-after: avoid;
    break-after: avoid;
  }
  /* 移除阴影 */
  * { box-shadow: none !important; text-shadow: none !important; }
  /* 确保背景色打印（金色圆点、标签背景） */
  .gold-dot, .skill-tag, .skill-bar-fill {
    -webkit-print-color-adjust: exact;
    print-color-adjust: exact;
  }
}
```

### 7.2 单页原则（铁律）

- **内容必须控制在1页A4内**：如果内容超过1页，精简文字、调整间距、缩小边距（最小12mm）、减小正文字号（最小10px）
- **不要让第二个条目悬在第二页顶部**：要么全部放在第一页，要么整条移到第二页（但单页是目标）
- **使用 `page-break-inside: avoid`** 防止工作条目在分页处被切断
- **在线简历页**也应遵循"一屏半"原则，不需要无限滚动

### 7.3 无图片、无动效、无JS（铁律）

| 禁止项 | 原因 |
|--------|------|
| **个人头像/照片** | 大多数岗位不需要，可能引入视觉偏见，浪费空间（空乘/模特等要求照片的岗位除外） |
| **公司Logo图标** | 不一致、不专业、浪费空间，用文字即可 |
| **装饰性插图/图标** | 电话图标、邮件图标等——直接用文字更简洁专业 |
| **CSS动画/transition** | 简历是静态文档，不需要动画 |
| **JavaScript交互** | PDF导出后JS无效，打印时无效 |
| **hover效果** | 打印时不可见，鼠标悬浮在简历上无意义 |
| **滚动效果/parallax** | 简历是文档，不是网页 |

### 7.4 PDF导出友好

- 使用 `window.print()` 触发浏览器打印/另存为PDF
- 推荐浏览器：Chrome（打印效果最稳定）
- 打印设置：纸张尺寸A4、边距默认/无、背景图形**勾选**（确保金色和标签背景打印出来）
- 不使用Web Fonts的极端字重（如Playfair Display Black），可能在PDF中渲染异常
- 导出后检查：在PDF中打开检查是否有1页、所有元素完整、无空白页
- 提供下载按钮时，使用 `@media print` 隐藏按钮本身

```html
<button class="no-print download-btn" onclick="window.print()">下载PDF</button>
```

### 7.5 联系方式清晰

- **邮箱**放在最前面，是最正式的联系方式
- **手机号**使用易读格式：`138-0000-0000`
- **地点**精确到城市即可，不需要详细地址
- **在线链接**：LinkedIn、个人网站、GitHub（技术岗），不超过3个
- **不放入**：微信号（非商务场景）、QQ号、生日（除非要求）、身份证号
- 联系方式单行排列，用 `·` 分隔，不换行

### 7.6 内容写作规范

1. **成就用动词开头+量化数据**：
   - 好："主导设计系统重构，设计效率提升40%，覆盖200+组件"
   - 差："负责设计系统的重构工作"

2. **每段经历2-4个bullet point**：不超过4个，保持精炼
3. **个人简介2-3句话**：不超过4行，概括你的核心价值
4. **不用第一人称"我"**：直接陈述事实
5. **不用空洞形容词**："优秀的沟通能力"、"团队合作精神"——用事实证明
6. **时间格式统一**：`2023.06 - 至今` 或 `2023.06 - 2024.03`，全篇统一
7. **不写"简历""个人简历"等标题**：你的名字就是标题

### 7.7 在线简历页额外规范

如果简历作为个人网站的一个页面（非纯PDF导出），额外注意：

1. **页面居中**：简历纸张居中显示，最大宽度210mm（约794px），两侧留白
2. **纸张效果**（可选）：白色背景+轻微阴影模拟纸张，但打印时阴影必须去掉
3. **下载按钮**：固定在右上角或顶部，`class="no-print"`
4. **不使用网站导航**：简历页可以有简化的返回链接，但不要放完整导航栏
5. **字体加载**：确保Playfair Display和Inter字体正确加载，FOIT/FOUT处理

---

## 8. 场景专属 Checklist

在交付任何简历/CV之前，必须通过以下检查：

### P0 — 必须通过（缺一不可，直接影响专业度和投递效果）

- [ ] **A4单页**：内容不超过1页A4纸（210×297mm），打印/导出PDF后恰好1页
- [ ] **打印样式@media print存在**：隐藏导航/按钮、移除阴影、黑白友好、分页不断字
- [ ] **无动效**：没有CSS动画、transition、JS交互效果
- [ ] **经历倒序排列**：工作经历和教育背景最近的在最前面
- [ ] **联系方式清晰**：邮箱、手机、地点、必要链接一目了然，用·分隔
- [ ] **姓名使用Playfair Display衬线皇家蓝大字**：24-28px，是全页唯一衬线大字
- [ ] **其余文字一律Inter无衬线**：正文字号10-11px，墨黑色
- [ ] **三种品牌色严格为 `#0A2463` / `#F4D35E` / `#D8315B`**
- [ ] **色彩极度克制**：皇家蓝仅用于姓名+章节标题，金色仅用于线/点，酒红几乎不用
- [ ] **正文行高1.4-1.5**：紧凑但可读，不松散
- [ ] **背景纯白**：无彩色背景、无渐变、无图片
- [ ] **章节标题格式统一**：金色圆点+大写字母宽字距皇家蓝标题+金色细线
- [ ] **无浏览器默认样式残留**：链接样式、列表样式经过重置
- [ ] **黑白打印可读**：去色后所有信息层次分明
- [ ] **无头像/照片**（岗位明确要求除外）
- [ ] **PDF导出测试通过**：Chrome打印为PDF后检查，所有元素完整、无裁切、无空白第二页

### P1 — 应该通过（影响质感和专业度）

- [ ] **金色分割线点缀**：章节之间有金色细线，不粗重、不泛滥
- [ ] **衬线姓名品质感**：Playfair Display的姓名与其他文字形成优雅的字体对比
- [ ] **bullet point使用金色短横线或圆点**：不使用默认的大号黑色圆点
- [ ] **成就量化**：工作经历中有具体数字（百分比、金额、用户数等）
- [ ] **技能标签使用极浅金底+皇家蓝文字**：小标签，圆角精致
- [ ] **辅助文字（时间/公司名）使用灰色**：层次分明，但灰色不能太浅导致打印不清
- [ ] **日期格式统一**：全篇使用相同的日期格式
- [ ] **间距紧凑但不拥挤**：章节间16-20px，条目间12-16px，行距1.4-1.5
- [ ] **没有空洞形容词**："团队合作"、"沟通能力"等空话被具体事例替代
- [ ] **没有"个人简历"等多余标题**：名字就是标题
- [ ] **选中文本背景为金色**：`::selection { background: #F4D35E; color: #0A2463; }`

### P2 — 加分项（锦上添花）

- [ ] **可导出PDF**：页面有"下载PDF"按钮，点击触发window.print()
- [ ] **双栏布局**（适合设计/创意岗）：左窄右宽，左侧技能/联系方式，右侧经历
- [ ] **技能进度条**：用金色填充的细进度条展示技能水平
- [ ] **个人简介首字母大写装饰**：Summary第一个字母用Playfair Display稍大字号（可选，非必须）
- [ ] **在线链接可点击**：网页版简历中邮箱/LinkedIn/GitHub可点击（打印时自动转黑色无下划线）
- [ ] **字体优化**：使用 `font-variant-numeric: tabular-nums` 让数字对齐
- [ ] **打印设置提示**：在线简历页可加一行小字提示"打印时请勾选'背景图形'以确保最佳效果"

### 交付前自检三问

1. **10秒扫读测试**：拿到简历的人10秒内能否知道你是谁、做什么的、核心优势是什么？
2. **打印测试**：黑白打印出来后，名字是否清晰？章节层次是否分明？有没有模糊不清的灰色文字？
3. **冗余信息检查**：有没有可以删掉但不影响理解的内容？有没有"负责XX工作"而没有成果的描述？

---

## 附录：简历快速模板骨架

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>飞鸿 - 个人简历</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --royal: #0A2463;
      --gold: #F4D35E;
      --gold-light: #FAEBA3;
      --wine: #D8315B;
      --ink: #0D1225;
      --ink-2: #1A1F36;
      --muted: #4A5066;
      --faint: #8A90A5;
      --line: #E8E3D4;
      --tag-bg: #FEFCF0;
    }
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: 'Inter', 'Noto Sans SC', -apple-system, sans-serif;
      background: #F0EAD9;
      color: var(--ink);
      -webkit-font-smoothing: antialiased;
      padding: 30px 0;
    }
    ::selection { background: var(--gold); color: var(--royal); }

    /* 下载按钮（仅屏幕显示） */
    .toolbar {
      position: fixed; top: 20px; right: 20px; z-index: 100;
    }
    .btn-print {
      padding: 8px 18px; background: var(--royal); color: #fff;
      border: none; border-radius: 6px; font-size: 13px;
      font-family: inherit; cursor: pointer;
      box-shadow: 0 2px 8px rgba(10,36,99,0.2);
    }
    .btn-print:hover { background: #081D52; }

    /* 简历纸张 */
    .resume {
      width: 210mm;
      min-height: 297mm;
      margin: 0 auto;
      padding: 18mm 20mm;
      background: #fff;
      box-shadow: 0 2px 20px rgba(0,0,0,0.08);
      font-size: 10.5px;
      line-height: 1.5;
      font-variant-numeric: tabular-nums;
    }

    /* 头部 */
    .header { text-align: center; margin-bottom: 14px; }
    .name {
      font-family: 'Playfair Display', 'Noto Serif SC', Georgia, serif;
      font-size: 28px; font-weight: 700; color: var(--royal);
      letter-spacing: 0.02em; line-height: 1.2; margin-bottom: 4px;
    }
    .title {
      font-size: 13px; font-weight: 500; color: var(--ink);
      margin-bottom: 6px;
    }
    .contact {
      font-size: 10.5px; color: var(--muted);
      display: flex; justify-content: center; flex-wrap: wrap; gap: 0 10px;
    }
    .contact a { color: var(--muted); text-decoration: none; }
    .contact a:hover { color: var(--royal); }
    .contact .sep { color: var(--gold-light); }

    /* 分割线 */
    .divider-gold {
      height: 1px;
      background: var(--gold);
      margin: 12px 0 16px;
      border: none;
    }

    /* 章节 */
    .section { margin-bottom: 16px; }
    .section-header {
      display: flex; align-items: center; margin-bottom: 8px;
    }
    .gold-dot {
      display: inline-block; width: 7px; height: 7px;
      background: var(--gold); border-radius: 50%;
      margin-right: 8px; flex-shrink: 0;
    }
    .section-title {
      font-size: 11px; font-weight: 700; letter-spacing: 0.18em;
      text-transform: uppercase; color: var(--royal);
      margin-right: 10px; white-space: nowrap;
    }
    .section-line {
      flex: 1; height: 1px;
      background: linear-gradient(90deg, var(--gold) 0%, var(--line) 60%, transparent 100%);
    }

    /* Summary */
    .summary {
      font-size: 10.5px; line-height: 1.6; color: var(--ink-2);
      margin-bottom: 2px;
    }

    /* 经历条目 */
    .item { margin-bottom: 12px; }
    .item-header {
      display: flex; justify-content: space-between; align-items: baseline;
      margin-bottom: 2px;
    }
    .item-title { font-size: 11.5px; font-weight: 600; color: var(--ink); }
    .item-sub { font-size: 11px; font-weight: 400; color: var(--muted); margin-left: 6px; }
    .item-date { font-size: 10px; color: var(--faint); white-space: nowrap; }
    .item-bullets { list-style: none; margin: 3px 0 0; padding: 0; }
    .item-bullets li {
      font-size: 10.5px; line-height: 1.45; color: var(--ink);
      padding-left: 12px; position: relative; margin-bottom: 2px;
    }
    .item-bullets li::before {
      content: '–'; position: absolute; left: 0; color: var(--gold);
    }

    /* 技能标签 */
    .skill-tags { display: flex; flex-wrap: wrap; gap: 4px 6px; }
    .skill-tag {
      display: inline-block; font-size: 9.5px; font-weight: 500;
      padding: 2px 8px; background: var(--tag-bg); color: var(--royal);
      border-radius: 3px; letter-spacing: 0.02em;
    }

    /* 教育条目 */
    .edu-item { margin-bottom: 6px; }
    .edu-degree { font-size: 11px; font-weight: 600; color: var(--ink); }
    .edu-school { font-size: 10.5px; color: var(--muted); margin-left: 6px; }

    /* 打印样式 */
    @media print {
      @page { size: A4; margin: 0; }
      * {
        -webkit-print-color-adjust: exact !important;
        print-color-adjust: exact !important;
        color-adjust: exact !important;
      }
      body { background: #fff; padding: 0; font-size: 10.5pt; }
      .toolbar, .no-print { display: none !important; }
      .resume {
        width: 210mm; min-height: 297mm;
        margin: 0; padding: 15mm 18mm;
        box-shadow: none !important;
      }
      a { color: var(--ink) !important; text-decoration: none !important; }
      .item, .edu-item, .section {
        page-break-inside: avoid; break-inside: avoid;
      }
      .section-header { page-break-after: avoid; break-after: avoid; }
      * { box-shadow: none !important; text-shadow: none !important; }
    }

    /* 屏幕响应式 */
    @media (max-width: 850px) {
      body { padding: 0; }
      .resume { width: 100%; min-height: auto; padding: 24px 20px; box-shadow: none; }
      .toolbar { position: sticky; top: 0; right: auto; text-align: center; padding: 10px; background: #F0EAD9; }
    }
  </style>
</head>
<body>
  <!-- 下载按钮（打印时隐藏） -->
  <div class="toolbar no-print">
    <button class="btn-print" onclick="window.print()">下载 PDF</button>
  </div>

  <div class="resume">
    <!-- 头部 -->
    <header class="header">
      <h1 class="name">飞鸿</h1>
      <div class="title">高级产品设计师</div>
      <div class="contact">
        <a href="mailto:hong.fei@email.com">hong.fei@email.com</a>
        <span class="sep">·</span>
        <span>138-0000-0000</span>
        <span class="sep">·</span>
        <span>上海</span>
        <span class="sep">·</span>
        <a href="#">linkedin.com/in/feihong</a>
        <span class="sep">·</span>
        <a href="#">github.com/feihong</a>
      </div>
    </header>

    <hr class="divider-gold">

    <!-- Summary -->
    <section class="section">
      <div class="summary">
        7年B端产品设计经验，专注企业级SaaS设计系统与复杂数据可视化。主导过3个从0到1的产品设计，
        擅长通过系统化设计思维提升团队效率，优化用户核心流程转化率平均提升30%以上。
      </div>
    </section>

    <!-- Experience -->
    <section class="section">
      <div class="section-header">
        <span class="gold-dot"></span>
        <span class="section-title">Experience</span>
        <span class="section-line"></span>
      </div>

      <div class="item">
        <div class="item-header">
          <div>
            <span class="item-title">高级产品设计师</span>
            <span class="item-sub">@ 某某科技有限公司</span>
          </div>
          <div class="item-date">2023.06 - 至今</div>
        </div>
        <ul class="item-bullets">
          <li>主导企业级SaaS平台设计体系重构，建立包含200+组件的设计系统，设计交付效率提升40%</li>
          <li>优化核心用户转化漏斗，通过A/B测试将试用转付费率从2.1%提升至3.5%</li>
          <li>带领5人设计团队，建立设计评审流程和组件库治理机制，组件复用率达75%</li>
        </ul>
      </div>

      <div class="item">
        <div class="item-header">
          <div>
            <span class="item-title">产品设计师</span>
            <span class="item-sub">@ 某某互联网公司</span>
          </div>
          <div class="item-date">2020.03 - 2023.05</div>
        </div>
        <ul class="item-bullets">
          <li>负责数据看板产品的全链路设计，服务10万+活跃用户，NPS从32提升至58</li>
          <li>设计并落地企业级数据可视化组件库，被3个业务线采纳使用</li>
          <li>推动设计-开发协作流程优化，设计稿还原度从70%提升至95%</li>
        </ul>
      </div>

      <div class="item">
        <div class="item-header">
          <div>
            <span class="item-title">UI设计师</span>
            <span class="item-sub">@ 某某设计工作室</span>
          </div>
          <div class="item-date">2018.07 - 2020.02</div>
        </div>
        <ul class="item-bullets">
          <li>参与10+企业客户的品牌视觉与产品界面设计项目</li>
          <li>独立完成某金融App从视觉到交互的全套设计，上线3个月获取5万用户</li>
        </ul>
      </div>
    </section>

    <!-- Education -->
    <section class="section">
      <div class="section-header">
        <span class="gold-dot"></span>
        <span class="section-title">Education</span>
        <span class="section-line"></span>
      </div>
      <div class="edu-item">
        <div class="item-header">
          <div>
            <span class="edu-degree">设计学 硕士</span>
            <span class="edu-school">@ 某某大学</span>
          </div>
          <div class="item-date">2016.09 - 2018.06</div>
        </div>
      </div>
      <div class="edu-item">
        <div class="item-header">
          <div>
            <span class="edu-degree">视觉传达设计 学士</span>
            <span class="edu-school">@ 某某大学</span>
          </div>
          <div class="item-date">2012.09 - 2016.06</div>
        </div>
      </div>
    </section>

    <!-- Skills -->
    <section class="section">
      <div class="section-header">
        <span class="gold-dot"></span>
        <span class="section-title">Skills</span>
        <span class="section-line"></span>
      </div>
      <div class="skill-tags">
        <span class="skill-tag">Figma</span>
        <span class="skill-tag">Sketch</span>
        <span class="skill-tag">设计系统</span>
        <span class="skill-tag">B端设计</span>
        <span class="skill-tag">数据可视化</span>
        <span class="skill-tag">用户研究</span>
        <span class="skill-tag">交互原型</span>
        <span class="skill-tag">HTML/CSS</span>
        <span class="skill-tag">团队管理</span>
      </div>
    </section>

    <!-- Projects（可选） -->
    <section class="section">
      <div class="section-header">
        <span class="gold-dot"></span>
        <span class="section-title">Projects</span>
        <span class="section-line"></span>
      </div>
      <div class="item">
        <div class="item-header">
          <div>
            <span class="item-title">Feihong Design System</span>
          </div>
          <div class="item-date">2025</div>
        </div>
        <ul class="item-bullets">
          <li>开源个人品牌设计系统，包含完整的设计规范、组件库和多场景模板</li>
        </ul>
      </div>
    </section>
  </div>
</body>
</html>
```

---

## 场景定位

简历/CV是求职和职业展示的正式文档，用于求职投递、职位申请、个人职业介绍。适用于：求职简历、学术CV、职业介绍、个人简介文档。不适用于：作品集展示（视觉优先，用Portfolio）、个人主页（多屏叙事，用Portfolio）、营销页（用Landing）。核心原则是"专业、精简、A4一页"——Ctrl+P导出PDF打印友好，ATS（求职者追踪系统）可解析，黑白打印可读，10秒扫读能抓住核心信息，装饰极度克制。

## 推荐节奏（Section 序列）

简历场景的"节奏"是A4纸上从上到下的模块排列：

### 方案 A：单栏通用简历（最推荐，所有行业通用）
1. Header（居中/左对齐）— 姓名（Playfair皇家蓝大字）+职位头衔+联系方式
2. 金色分割线
3. Summary/个人简介（2-3句话）— 核心价值概括
4. Experience工作经历（倒序，占50%空间）— 公司+职位+日期+2-4条量化成果
5. Education教育背景（简洁，占12%）
6. Skills技能标签（占12%）— 浅金底皇家蓝字小标签
7. Projects/Awards（可选，占8%）

### 方案 B：双栏创意/设计简历
1. Header（横跨两栏）— 姓名+职位+金色分割线
2. 左窄栏（30%宽度）：联系方式·技能（标签或进度条）·教育·语言·证书
3. 右宽栏（70%宽度）：Summary·Experience（主要空间）·Projects
4. 左右栏之间可选1px金色竖线分隔

### 方案 C：技术岗简历
1. Header（姓名+职位+联系方式+GitHub/技术博客链接）
2. Skills技术栈（前置，因为HR/猎头先筛关键词）— 编程语言/框架/工具分类标签
3. Experience工作经历（强调技术成果和量化性能指标）
4. Projects开源/个人项目（附链接和技术栈）
5. Education（简洁）

### 方案 D：学术CV（多页可接受）
1. Header（姓名+学术头衔+机构+联系方式）
2. Research Interests研究方向
3. Education教育背景
4. Publications出版物（占主要空间，按引用格式）
5. Research/Teaching Experience研究/教学经历
6. Awards/Honors奖项荣誉
7. Skills/Languages技能语言
（学术CV可超过1页，与普通简历单页原则不同）

## 专属装饰手法（Signature Touches）

简历场景装饰极度克制——装饰仅用于信息层次划分，不用于"美化"：

- **#07 Decorative Rule 装饰线**：Header下方一条金色水平线（1px），分隔姓名和内容
- **#20 Numbered Index 金色圆点**：每个章节标题前有一个7px金色圆点（`border-radius:50%`），是简历最核心的装饰签名
- **#15 Divider 渐变分隔线**：章节标题右侧有金色到透明的渐变线（0→60%金色→透明）
- **金色短横线bullet**：工作成就列表用金色短横线"–"代替默认的"•"圆点
- **#18 Badge & Stamp 技能标签**：技能用极浅金底（#FEFCF0）+皇家蓝文字的小标签（padding 2px 7px, rounded 3px）
- **#14 Section Marker 章节标题**：全大写、宽字距（0.18em）、小字号（11px）、皇家蓝色，配合金色圆点
- **等宽数字**：日期、数字使用`font-variant-numeric: tabular-nums`对齐
- **金色进度条（可选）**：技能水平可用4px高金色填充进度条，但创意岗位慎用（可能显俗）

## 推荐布局组合

简历场景仅使用文档型布局，禁用艺术化布局：

| 布局 | 适用性 | 说明 |
|------|--------|------|
| **单栏文档流** | 所有岗位首选 | 从上到下线性阅读，ATS最友好，打印最安全 |
| **双栏（左窄右宽）** | 设计/创意岗 | 左侧短信息模块，右侧长内容模块，现代感强但ATS可能解析困难 |
| **Header居中** | 传统/正式岗位 | 姓名居中，联系方式一行排列居中，正式感强 |
| **Header左对齐** | 现代/科技岗 | 姓名左对齐，联系方式在名字下方或右侧 |
| ❌ L8引文全屏 | 禁用 | 艺术化布局不适合正式简历 |
| ❌ L16画册溢出 | 禁用 | 简历是文档不是画册 |
| ❌ L10/L11网格瀑布流 | 禁用 | 阅读顺序不清晰，ATS无法解析 |
| ❌ L13深色面板 | 禁用 | 打印费墨，黑白打印发灰 |
| ❌ 彩色背景卡片 | 禁用 | 不专业，打印不友好 |

## 色彩策略

简历场景色彩极度克制——白色背景，皇家蓝+金色做信息层次，酒红基本不用。

**皇家蓝 #0A2463（仅用于文字层次）**
- 姓名（24-28px Playfair Display，全页唯一大字）
- 章节标题（EXPERIENCE/EDUCATION/SKILLS等，全大写小字号）
- 技能标签文字（#FEFCF0浅金底上的皇家蓝字）
- 职位名称（工作条目的标题，11.5px semibold）

**复古金 #F4D35E（仅用于线条和点）**
- Header下方的金色水平线（1px）
- 章节标题前的7px金色圆点
- 章节标题右侧的金色渐变线
- 工作成就列表前的金色短横线"–"
- 技能进度条填充色（如果使用）
- **金色绝不用于文字（除了进度条/标签背景这种色块场景），仅用于点和线**
- **金色面积占比不超过页面5%**

**酒红 #D8315B（基本不用）**
- 简历中酒红几乎不使用
- 极特殊情况下可用于特别突出的成就标签（如"最佳员工"），但建议不用
- **酒红在简历中过于抢眼，会破坏专业稳重感**

**背景与中性色**：
- 页面背景：纯白`#FFFFFF`（打印友好）
- 正文：墨黑`#0D1225`或深墨灰`#1A1F36`
- 次要信息（公司名、日期）：中灰`#4A5066`、浅灰`#8A90A5`
- 分割线：暖灰`#E8E3D4`
- 技能标签背景：极浅金`#FEFCF0`
- **禁止使用暖米白#FDFBF6做简历背景**——简历必须纯白底，模拟真实纸张

## 场景禁忌（Don'ts）

1. **超过1页A4**：除非是学术CV，普通简历必须1页，超过就删减（10年经验也可以1页）
2. **放个人照片**：大多数岗位不需要，可能引入偏见（空乘/模特等要求照片的岗位除外）
3. **用图标装饰**：电话图标、邮件图标浪费空间且不专业，直接用文字
4. **公司Logo**：大小不一、风格混乱，直接用公司名文字
5. **彩色背景/深色面板**：打印费墨、黑白打印层次丢失、不专业
6. **CSS动画/JS交互/hover效果**：简历是静态文档，PDF后全部失效
7. **技能用大号进度条/雷达图**：俗套且不准确（"Photoshop 90%"谁评判的？），用标签或简短描述更好
8. **空洞形容词**："沟通能力强""团队合作精神""责任心强"——用事实和数据证明
9. **第一人称"我"**：直接陈述事实，"主导设计"而非"我主导了设计"
10. **写"个人简历"/"Resume"作标题**：你的名字就是标题
11. **虚假/夸大信息**：简历每个点都可能被追问
12. **冷灰色**：所有灰色必须偏暖（带棕/黄调），禁用`#999`/`#CCC`等冷灰

## 场景专属Checklist

- [ ] A4单页（210×297mm），Ctrl+P打印/导出PDF恰好1页无空白第二页
- [ ] @media print样式完整：隐藏按钮/导航、移除阴影、`print-color-adjust: exact`确保金色打印
- [ ] 姓名Playfair Display皇家蓝大字（24-28px），其余文字Inter无衬线
- [ ] 联系方式清晰：邮箱·手机·城市·必要链接（LinkedIn/GitHub/个人网站），用·分隔
- [ ] 工作经历倒序排列（最近的在最前），每段2-4个bullet point
- [ ] 成就以动词开头+量化数据（"提升X%"、"覆盖N个组件"、"服务N万用户"）
- [ ] 章节标题统一格式：金色圆点+全大写皇家蓝标题+金色渐变线
- [ ] bullet point用金色短横线"–"，不用默认黑色圆点
- [ ] 技能用浅金底皇家蓝字标签（9.5px, rounded 3px），不用大进度条
- [ ] 背景纯白`#FFFFFF`，无彩色块、无渐变、无阴影（打印时box-shadow:none）
- [ ] 无头像、无公司Logo、无装饰图标、无动画
- [ ] 日期格式统一（如"2023.06 - 至今"），全篇一致
- [ ] 黑白打印测试：去色后层次分明，金色圆点/线可见（灰度下应仍有区分度）
- [ ] PDF导出测试：Chrome打印为PDF，检查所有元素完整、无裁切、无断页
- [ ] 在线链接在网页版可点击，打印时自动转黑色无下划线
- [ ] "背景图形"勾选提示：建议用户打印时勾选"背景图形"确保金色元素可见
- [ ] 字体使用`font-variant-numeric: tabular-nums`让数字对齐
- [ ] 页面边距12-20mm，不小于12mm避免打印裁切
- [ ] 正文字号10-11px（打印10-11pt），不小于10px
- [ ] 选中文本背景为金色

---

*Scene: Resume v1.0 · Feihong Design System*
*基于 DNA.md v2.0 · 最后更新：2026-07-08*
