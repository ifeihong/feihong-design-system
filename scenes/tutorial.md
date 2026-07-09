# Feihong Design System · Scene: Tutorial
# 飞鸿品牌设计系统 · 场景规范：教程型页面

> 本规范定义飞鸿品牌设计系统在「教程/科普/知识分享」类长文页面中的具体应用方式。
> 所有规则建立在 `DNA.md`、`components/14-layouts.md`、`components/` 基础之上，场景专属规则以本文件为准。

---

## 1. 场景定义

### 适用页面类型

教程型页面场景适用于以下内容形态：

| 类型 | 说明 | 典型长度 |
|------|------|----------|
| **技术教程** | 步骤式教学、操作指南、代码教程 | 1500-5000字 |
| **科普文章** | 知识科普、概念解析、原理解读 | 1500-4000字 |
| **博客长文** | 深度思考、经验总结、观点论述 | 2000-5000字 |
| **知识分享** | 方法论、最佳实践、学习笔记 | 1500-4000字 |
| **介绍型长文** | 产品深度介绍、设计理念阐述、案例研究 | 2000-4000字 |

### 场景核心气质

- **专注阅读**：页面第一使命是让读者舒适地读完内容，所有设计为阅读体验服务
- **权威可信**：皇家蓝主导的视觉基调传递专业感和可信赖感
- **温润有节奏**：金色装饰和衬线字体营造人文气息，避免技术文档的冰冷感
- **层次清晰**：通过排版和色彩构建清晰的信息层级，长文不显得冗长

### 场景核心约束

- 阅读体验优先于视觉冲击
- 装饰元素服务于信息结构，不做无意义装饰
- 代码、引用、步骤等功能性组件必须有明确的视觉区分
- 长文必须提供导航辅助（TOC目录、进度条）

---

## 2. 典型页面结构

教程型页面采用 **Hero标题区 + TOC目录 + 正文多章节 + 结语/CTA** 的四阶段结构：

```
┌─────────────────────────────────────────────┐
│  ① Hero 标题区（L2 居中大字 / L7 阅读首屏）    │
│     - eyebrow 标签（教程/博客/科普）            │
│     - h1 衬线大标题                            │
│     - 元信息行（日期 · 阅读时长 · 作者）         │
│     - 金色装饰分隔线                           │
├─────────────────────────────────────────────┤
│  ② TOC 目录（固定侧边 / 顶部内嵌）              │
│     - 章节目录列表，可点击锚点跳转               │
│     - 当前章节高亮标记                          │
├─────────────────────────────────────────────┤
│  ③ 正文多章节（L7 单栏阅读 + 穿插组件）          │
│     ├─ 章节A：h2 子标题 + 正文段落              │
│     ├─ 代码块（金色左边框）                      │
│     ├─ [L8 引文全屏] 节奏打破（可选）            │
│     ├─ 章节B：h2 + 正文 + gold-dot 列表         │
│     ├─ [L12 步骤列表] 教程步骤                  │
│     ├─ 章节C：h3 子标题 + pull-quote 引用       │
│     ├─ 提示框（WARNING/INFO）                   │
│     └─ ...更多章节                              │
├─────────────────────────────────────────────┤
│  ④ 结语 / CTA（L13 深色面板）                   │
│     - 总结段落                                  │
│     - 行动号召按钮（酒红CTA）                    │
│     - 相关推荐 / 作者信息                        │
└─────────────────────────────────────────────┘
```

### 结构要点

1. **Hero 区**：不使用高冲击力的 L1/L3/L4 全屏 Hero，保持克制、聚焦标题本身
2. **TOC 目录**：文章超过 3 个章节必须提供目录；桌面端固定侧边，移动端折叠为顶部抽屉
3. **正文章节**：每个章节之间用金色装饰线（`divider-gold`）分隔，形成呼吸节奏
4. **节奏变化**：每 2-3 个章节穿插一次 L8 引文全屏或 L12 步骤列表，打破单栏长文的单调
5. **CTA 区**：文章结尾使用 L13 深色面板做收束，CTA 按钮用酒红色制造行动焦点

---

## 3. 色彩使用指南

教程场景严格遵循品牌 55-30-15 色彩比例，三色在教程场景的具体分配如下：

### 3.1 皇家蓝 `#0A2463`（55%）— 结构主导色

| 用途 | 具体应用 | CSS 变量 |
|------|----------|----------|
| **标题层级** | h1 页面标题、h2 章节标题、h3 子标题 | `var(--royal)` / `var(--ink)` |
| **导航系统** | 顶部导航栏文字、侧边 TOC 目录文字、面包屑 | `var(--royal)` |
| **超链接** | 正文内链接、章节跳转链接、相关推荐链接 | `var(--royal-600)` hover 到 `var(--royal-700)` |
| **信息提示** | INFO 级别提示框（`alert-info`） | `var(--royal)` 左边框 + `var(--royal-50)` 背景 |
| **引用块文字** | pull-quote 中的引言文字颜色 | `var(--royal)` |
| **装饰数字** | 衬线数字列表的编号、章节序号 | `var(--royal)`（浅透明度装饰） |

### 3.2 复古金 `#F4D35E`（30%）— 装饰与节奏色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **装饰线** | 标题下方金色线、章节分隔线（`divider-gold`） | 品牌签名细节 |
| **引用标记** | pull-quote 中的大号金色引号 `"` | 80px 金色衬线引号 |
| **列表圆点** | `list-gold-dot` 的金色圆点标记 | 直径 8px |
| **标签徽章** | 文章分类标签（`badge-gold`）、"New"/"更新"标记 | 金色背景+皇家蓝文字 |
| **代码框边框** | 代码块左侧 3px 金色边框 | `border-left: 3px solid var(--gold)` |
| **关键词高亮** | 正文中的关键词荧光笔效果 | `background: linear-gradient(transparent 60%, var(--gold-200) 60%)` |
| **时间线节点** | L12 步骤列表的金色圆点和连线 | `var(--gold)` 圆点 + 渐变连线 |
| **衬线数字** | `list-serif-number` 的编号颜色 | `var(--gold)` 斜体衬线数字 |
| **TOC 当前项** | 侧边目录当前章节的指示标记 | 左侧金色竖线 + 金色圆点 |

### 3.3 酒红 `#D8315B`（15%）— 强调与行动色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **重点强调** | 正文中需要特别注意的关键词 | 可使用 `text-wine` 或酒红色下划线 |
| **WARNING 提示** | 警告级别提示框（`alert-wine`） | 酒红左边框 + 极浅酒红背景 |
| **CTA 按钮** | 结尾行动号召主按钮（`btn-cta`） | 酒红背景+白色文字+酒红阴影 |
| **链接悬停** | 正文链接 hover 状态可转为酒红色 | `color: var(--wine)` on hover |
| **错误提示** | 代码中的错误标注、重要警示 | `var(--wine)` 语义色复用 |
| **精选标记** | "重要"/"必读"等标签（`badge-wine`） | 酒红背景+白色文字 |

### 3.4 背景与中性色

| 元素 | 色值 | 说明 |
|------|------|------|
| 页面背景 | `#FDFBF6` (`var(--cream)`) | 暖米白，长时间阅读不刺眼 |
| 卡片/代码块背景 | `#0D1225` (`var(--ink)`) | 墨黑深色背景，仅用于代码块和深色面板 |
| 正文文字 | `#0D1225` (`var(--ink)`) → 实际用 `var(--ink-100)` (#2C3347) | 正文用深灰而非纯墨黑，阅读更舒适 |
| 辅助文字 | `var(--ink-300)` (#6D7487) | 元信息、时间戳、说明文字 |
| 分隔线 | `var(--cream-200)` (#F0EAD9) | 暖调分隔线，不用冷灰 |

### 色彩使用铁律（教程场景）

1. **金色永远不做正文文字色**（对比度不足），仅用于装饰、标记和深色背景上的文字
2. **酒红不大面积使用**，仅在需要读者停下来注意的地方出现
3. **代码块必须是深色背景+金色左边框**，不使用浅色代码块
4. **链接默认皇家蓝，hover 可转酒红**，形成清晰的交互反馈
5. **提示框按语义分级**：INFO=皇家蓝、WARNING=金色/酒红、ERROR=酒红

---

## 4. 排版规范

### 4.1 阅读行宽（核心约束）

| 指标 | 规范值 | 说明 |
|------|--------|------|
| **正文最佳行宽** | **65ch**（约 680px） | 最舒适的中文+英文混排行宽 |
| 行宽范围 | 60ch — 75ch（约 620px — 760px） | 不窄于60ch（太碎），不宽于75ch（跨行困难） |
| 代码块行宽 | 与正文同宽，允许横向滚动 | 不做全出血代码块，保持阅读节奏统一 |
| 引文行宽 | 可放宽至 800px | L8 全屏引文可以更宽，形成节奏对比 |

```css
.L7-container {
  max-width: 680px;  /* ≈ 65ch */
  margin: 0 auto;
  padding: 0 1.5rem;
}
```

### 4.2 标题层级（h1-h3）

| 层级 | 字体 | 字号 (clamp) | 行高 | 字重 | 颜色 | 间距 |
|------|------|-------------|------|------|------|------|
| **h1** 页面标题 | Playfair Display 衬线 | `clamp(1.75rem, 4vw, 2.75rem)` | 1.2 | 700 | `var(--ink)` | 下方 0.75rem 到元信息 |
| **h2** 章节标题 | Playfair Display 衬线 | `clamp(1.5rem, 2.5vw, 2rem)` | 1.25 | 700 | `var(--ink)` | 上方 3rem，下方 1rem |
| **h3** 子标题 | Playfair Display 衬线 | `clamp(1.25rem, 2vw, 1.5rem)` | 1.35 | 600 | `var(--ink)` | 上方 2rem，下方 0.75rem |
| **h4** 小标题 | Inter 无衬线 | `1.1rem` | 1.4 | 600 | `var(--royal)` | 上方 1.5rem，下方 0.5rem |

#### 标题装饰规则

- **h1**：下方元信息行后有金色装饰线（`divider-gold`），长度约 60px 渐变消失
- **h2**：每个 h2 章节前必须有 `divider-gold` 金色分隔线（第一个 h2 除外）
- **h3**：不加装饰线，通过字号和字重区分层级
- **不使用 section-number 大数字**（那是 Landing 页风格），教程页保持简洁

### 4.3 正文字号与行高

| 元素 | 字号 | 行高 | 字体 | 颜色 | 段间距 |
|------|------|------|------|------|--------|
| **正文段落** | `1rem`（16px）→ `clamp(1rem, 1.2vw, 1.125rem)` | **1.75** | Inter | `var(--ink-100)` | 下方 1.5rem |
| **引言段落 Lead** | `clamp(1.05rem, 1.5vw, 1.2rem)` | 1.7 | Cormorant Garamond italic | `var(--ink-200)` | 下方 2rem |
| **列表项** | 1rem | 1.7 | Inter | `var(--ink-100)` | 下方 0.75rem |
| **代码块** | `0.875rem`（14px） | 1.7 | JetBrains Mono | `#E2E8F0` | 上下 1.5rem |
| **行内代码** | `0.875em` | 1.5 | JetBrains Mono | `var(--royal)` | 内联 |
| **辅助说明** | `0.875rem` | 1.6 | Inter | `var(--ink-300)` | — |
| **引用正文** | `clamp(1.1rem, 2vw, 1.35rem)` | 1.6 | Cormorant Garamond italic | `var(--royal)` | — |

### 4.4 段落排版细节

1. **首段不缩进**：所有段落不使用首行缩进（text-indent），通过段间距区分段落
2. **段落对齐**：左对齐（`text-align: left`），不使用两端对齐（justified）造成的字间距不均
3. **中英文混排**：中英文之间加半角空格，代码和文字之间加空格
4. **行内强调**：
   - 关键词：用 `<strong>`（皇家蓝色加粗）或金色荧光笔高亮
   - 术语：用行内代码 `<code class="inline-code">`
   - 金句/引用：用 `<em class="inline-quote">`（Cormorant 斜体，皇家蓝色）
5. **列表间距**：列表项之间 0.5rem，列表与正文之间 1.5rem

---

## 5. 推荐布局组合

从 L1-L16 中选取适合教程场景的布局组合，形成经典的教程页面布局配方：

### 5.1 推荐布局方案

#### 方案 A：经典阅读布局（推荐）

适用于大多数教程、博客文章、知识分享长文。

| 顺序 | 布局 | 作用 | 说明 |
|------|------|------|------|
| 1 | **L2 居中大字 Hero**（精简版） | 建立文章焦点 | 不用全屏100vh，精简为 60vh 左右，聚焦标题+元信息 |
| 2 | **L7 单栏长文** | 正文章节 | 主体内容，占页面 70% 以上篇幅 |
| — | *（穿插）* **L8 引文全屏** | 节奏打破 | 每 2-3 个章节插入一次，不超过 2 次 |
| — | *（穿插）* **L12 时间线/步骤列表** | 步骤展示 | 教程类内容在操作步骤处使用 |
| 3 | **L13 深色面板 CTA** | 收束转化 | 文章结尾的行动号召区 |

#### 方案 B：纯阅读布局

适用于纯文字类博客、深度长文、思想类文章。

| 顺序 | 布局 | 作用 |
|------|------|------|
| 1 | **L7 单栏长文**（从标题开始） | 全文使用单栏阅读布局，最纯粹的阅读体验 |
| — | *（穿插）* **L8 引文全屏** | 极少量节奏打破（1次以内） |
| 2 | **L13 深色面板 CTA** | 结尾收束 |

### 5.2 布局使用说明

- **L2（居中大字Hero）精简要点**：
  - 不使用装饰性英文大字（`decor-text`），保持简洁
  - 不使用全屏滚动提示动画
  - eyebrow 标签改为文章分类（如"教程"/"博客"/"科普"）
  - 副标题改为文章元信息行（日期 · 阅读时长）

- **L7（单栏长文）核心配置**：
  - 容器宽度固定为 680px（65ch）
  - 桌面端左侧或右侧可留出 TOC 目录空间（TOC 宽度约 200-240px）
  - 正文区和 TOC 之间保持 3-4rem 间距

- **L8（引文全屏）使用限制**：
  - 每篇文章不超过 2 个 L8 引文块
  - 引文内容必须是文章的核心金句，不做无意义装饰
  - 引文后紧跟正文继续，不额外加间距

- **L12（时间线/步骤列表）适配**：
  - 教程场景中用作"步骤列表"，标题改为"第 N 步：xxx"而非年份
  - 金色圆点+连线保持不变
  - 每个步骤可包含代码块和说明文字

- **L13（深色面板CTA）配置**：
  - 背景使用皇家蓝深蓝径向渐变
  - CTA 按钮使用酒红色（`btn-cta`），在深色面板上形成强对比
  - 可包含作者简介、相关文章链接、订阅表单等

### 5.3 不推荐在教程场景使用的布局

| 布局 | 不推荐原因 |
|------|-----------|
| L1 非对称图文 Hero | 过于个人化，分散阅读注意力 |
| L3 分屏 Hero | 冲击力过强，不适合阅读场景 |
| L4 全屏视觉 Hero | 图片为主，文字为次，不适合内容导向页面 |
| L5/L6 图文并排 | 打断单栏阅读节奏，仅在文章配图处可局部使用 |
| L9 三列卡片网格 | 信息密度过高，破坏阅读流 |
| L10 非对称网格 | 视觉导向，不适合文字内容 |
| L11 交错瀑布流 | 用于文章列表页，不用于文章正文页 |
| L14 数据统计条 | Landing 页信任建立用，教程页不需要 |
| L15 双栏对比 | 仅在教程内需要对比说明时局部使用 |
| L16 画册溢出式 | 视觉惊喜用，教程场景保持克制 |

---

## 6. 组件选用指南

### 6.1 必用组件（教程场景核心组件）

| 组件 | 组件名 | 使用场景 | 使用频率 |
|------|--------|----------|----------|
| **金色圆点列表** | `list-gold-dot` | 无序列表、要点列举、特性清单 | 高频，每篇必用 |
| **衬线数字列表** | `list-serif-number` | 有序步骤、教程步骤、方法论步骤 | 高频，教程类必用 |
| **代码块** | `code-block` | 代码示例、命令行、配置、技术标注 | 按需，技术教程必用 |
| **引用块** | `pull-quote` | 金句强调、核心观点引用、名人名言 | 中频，1-3次/篇 |
| **子章节标题** | `subsection-title` | h3 级小节标题、段落组标题 | 高频，每个小节必用 |

#### 金色圆点列表（`list-gold-dot`）

```html
<ul class="list list-gold-dot">
  <li>理解品牌三色的比例分配原则</li>
  <li>掌握标题层级的字号和行高规范</li>
  <li>学会在长文中穿插引文和步骤列表</li>
</ul>
```
- 金色圆点直径 8px，距文字 16px
- 用于无序列表，列表项顺序不重要时

#### 衬线数字列表（`list-serif-number`）

```html
<ol class="list list-serif-number">
  <li>
    <strong>安装依赖</strong>
    <p>首先安装设计系统的 npm 包，确保版本在 2.0 以上。</p>
  </li>
  <li>
    <strong>引入 CSS 变量</strong>
    <p>在全局样式中引入 brand-tokens，确保色彩和字体变量可用。</p>
  </li>
</ol>
```
- 金色 Playfair Display 斜体衬线数字（01, 02, 03...）
- 用于有序步骤、教程流程，数字大小 2.5rem
- 每个步骤包含加粗标题和说明文字

#### 代码块（`code-block`）

```html
<pre class="code-block"><code>:root {
  --royal: #0A2463;
  --gold: #F4D35E;
  --wine: #D8315B;
}</code></pre>
```
- 墨黑深色背景（`var(--ink)`），JetBrains Mono 等宽字体
- **左侧 3px 金色边框**（品牌签名细节）
- 圆角 12px，内边距 1.5rem
- 支持横向滚动，代码区域不换行
- 行内代码用 `<code class="inline-code">`

#### 引用块（`pull-quote`）

```html
<blockquote class="pull-quote">
  <span class="quote-mark">&ldquo;</span>
  <p>好的教程不是堆砌信息，而是引导读者完成一次思维的旅程。</p>
  <cite>— 飞鸿</cite>
</blockquote>
```
- 居中对齐，Cormorant Garamond 斜体
- 金色大号引号（5rem），皇家蓝引言文字
- 每篇文章不超过 2-3 个

#### 子章节标题（`subsection-title`）

```html
<h3 class="subsection-title">色彩比例的核心逻辑</h3>
```
- Playfair Display 衬线，1.25-1.75rem 流体字号
- 用于 h3 级别小节，不加分隔线
- 上方 2rem 间距，下方 0.75rem 间距

### 6.2 推荐组件（按需使用）

| 组件 | 使用场景 |
|------|----------|
| `alert-info`（皇家蓝信息框） | 补充说明、知识点提示、背景信息 |
| `alert-warning`（金色警告框） | 注意事项、常见误区、兼容性提醒 |
| `alert-wine`（酒红重要框） | 重要警告、必须遵守的规则、关键提醒 |
| `badge-gold` / `badge-royal` / `badge-wine` | 文章分类标签、难度标记、"重要"/"更新"标记 |
| `inline-code` | 行内代码、技术术语、API名称 |
| `inline-quote` | 行内金句、关键词斜体强调 |
| `divider-gold` | 章节之间的金色分隔线 |
| `table-wrap` + `brand-table` | 参数对比、数据展示、配置项列表 |
| `tag-group` + `tag` | 文章末尾的标签组（SEO + 分类） |

### 6.3 不推荐组件

| 组件 | 不推荐原因 |
|------|-----------|
| `card-feature` | 卡片网格用于 Landing，教程正文保持单栏 |
| `card-testimonial` | 推荐语用于个人主页，不适合教程场景 |
| `stat-card` | 数据统计用于首页，不用于文章内 |
| `L10-bento` 非对称网格 | 视觉展示布局，不适合阅读场景 |
| `progress`（技能进度条） | 用于 About 页，与教程无关 |

---

## 7. 特殊注意事项

### 7.1 代码块必须有金色左边框

这是教程场景的签名式细节，不可省略：

```css
.code-block {
  background: var(--ink);       /* 墨黑背景 */
  border-left: 3px solid var(--gold);  /* 金色左边框 */
  border-radius: 0 var(--r-lg) var(--r-lg) 0;  /* 左侧直角，右侧圆角 */
  font-family: var(--font-mono);
  font-size: 0.875rem;
  line-height: 1.7;
  padding: var(--sp-5);
  overflow-x: auto;
  margin: var(--sp-5) 0;
}
```

- 代码块不使用全圆角，左侧直角贴合金色边框线
- 可添加语言标记标签（如 `.code-lang`），位于代码块右上角，金色小字
- 代码块内的注释用 `#6B7288`（灰色），关键字可用皇家蓝或金色高亮

### 7.2 TOC 目录固定侧边

当文章超过 3 个章节时，桌面端必须提供固定侧边 TOC：

```
┌──────────────────────────────────────────────────┐
│  Navbar (顶部固定导航)                             │
├──────────┬───────────────────────────────────────┤
│          │                                       │
│  TOC     │  Hero 标题区                           │
│  (固定)   │  ─ 金色分隔线 ─                        │
│          │                                       │
│  ● 引言   │  正文章节...                            │
│  ○ 第一章  │  代码块...                             │
│  ○ 第二章  │  引用块...                             │
│  ○ 第三章  │  ...                                  │
│  ● 结语   │                                       │
│          │  L13 CTA                               │
│          │                                       │
└──────────┴───────────────────────────────────────┘
```

TOC 样式规范：
- 宽度：200-240px
- 位置：`position: sticky; top: 100px;`（距顶部导航栏下方）
- 对齐：右对齐，与正文间距 3-4rem
- 当前章节：金色圆点 + 皇家蓝加粗文字
- 非当前章节：灰色文字（`var(--ink-300)`），hover 变皇家蓝
- 移动端：TOC 折叠为顶部的"目录"按钮，点击展开抽屉

### 7.3 长文需要阅读进度条

文章长度超过 1500 字时，页面顶部应显示阅读进度条：

```css
.reading-progress {
  position: fixed;
  top: 0;
  left: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--royal), var(--gold), var(--wine));
  z-index: 200;
  transition: width 0.1s linear;
}
```

- 进度条位于页面最顶部，高度 3px
- 渐变色：皇家蓝 → 金色 → 酒红（品牌三色渐变）
- 使用 `position: fixed` 固定在顶部
- JavaScript 监听 scroll 事件实时更新宽度
- 尊重 `prefers-reduced-motion`，为晕动症用户提供关闭选项

### 7.4 金色装饰线分隔章节

每两个 h2 章节之间必须插入金色装饰分隔线：

```html
<div class="divider-gold"></div>
<h2 class="subsection-title">下一个章节</h2>
```

```css
.divider-gold {
  height: 1px;
  background: linear-gradient(90deg, transparent 0%, var(--gold) 30%, var(--gold) 70%, transparent 100%);
  margin: 3rem 0 2rem;
}
```

- 分隔线不是实线，是中间金色、两端渐隐的渐变线
- 长度约为正文宽度的 60%，居中渐变消失
- h1 下方的分隔线长度更短（约 60px），从左侧开始
- 不使用全宽分隔线，保持呼吸感

### 7.5 其他注意事项

1. **图片处理**：教程中的截图/配图宽度与正文同宽（680px），圆角 8px，有细微阴影（`var(--shadow-md)`）
2. **返回顶部按钮**：滚动超过 2 屏后显示，固定在右下角，皇家蓝圆形按钮+金色箭头
3. **作者信息**：正文结束后、CTA之前可插入作者信息卡片（头像+简介+链接），白色卡片+金色描边
4. **阅读时间**：Hero 区元信息显示预估阅读时间（按中文 500字/分钟 计算）
5. **锚点链接**：每个 h2/h3 都要有 id，支持 TOC 和外部链接直接跳转
6. **打印友好**：长文文章考虑打印样式，隐藏 TOC、进度条、CTA，代码块保留边框
7. **选中文本**：选中文本背景为金色（`::selection { background: var(--gold); color: var(--royal); }`）

---

## 8. 场景专属 Checklist

在交付任何教程型页面之前，必须通过以下检查：

### P0 — 必须通过（缺一不可）

- [ ] **代码块使用 JetBrains Mono 字体**（`var(--font-mono)`），不使用默认等宽字体
- [ ] **代码块有 3px 金色左边框**（`border-left: 3px solid var(--gold)`）
- [ ] **TOC 目录可点击跳转**，每个章节标题有对应 id 锚点
- [ ] **正文行宽为 65ch（约 680px）**，在 60-75ch 范围内，不超宽不超窄
- [ ] **标题层级清晰**：h1 使用 Playfair Display 衬线，h2/h3 层级分明
- [ ] **正文字号 ≥ 16px**，行高 1.75，中文阅读舒适
- [ ] **链接颜色为皇家蓝**，不使用浏览器默认蓝色
- [ ] **不保留任何浏览器默认样式**（列表、引用、代码、表格均经过品牌化处理）
- [ ] **页面背景为暖米白 `#FDFBF6`**，不使用纯白或冷灰背景
- [ ] **三种品牌色严格为 `#0A2463` / `#F4D35E` / `#D8315B`**
- [ ] **衬线+无衬线混搭策略**：标题 Playfair Display，正文 Inter，引言 Cormorant italic
- [ ] **响应式适配**：移动端 TOC 可折叠，代码块可横向滚动，字号不小于 14px
- [ ] **语义化 HTML**：使用 `<article>`、`<nav>`（TOC）、`<section>`、`<blockquote>`、`<pre><code>`

### P1 — 应该通过（尽量满足）

- [ ] **章节间有金色装饰线**（`divider-gold`），h2 之间有渐变金色分隔
- [ ] **引言块（pull-quote）不超过 2 个**，内容为文章核心金句
- [ ] **列表使用品牌样式**：无序列表用 `list-gold-dot`，有序步骤用 `list-serif-number`
- [ ] **提示框按语义分级**：INFO=皇家蓝、WARNING=金色、重要=酒红
- [ ] **正文中有金色荧光笔关键词高亮**（至少 2-3 处关键术语标记）
- [ ] **链接 hover 状态有反馈**（颜色变化或金色下划线动画）
- [ ] **桌面端 TOC 固定侧边**，当前章节有高亮标记
- [ ] **行内代码使用 `inline-code` 样式**（浅皇家蓝背景+皇家蓝文字）
- [ ] **章节节奏有变化**：不全是文字段落，穿插列表、代码块、引用等不同元素
- [ ] **Hero 区有元信息行**（日期 · 阅读时长 · 分类标签）

### P2 — 加分项（锦上添花）

- [ ] **页面顶部有阅读进度条**，三色渐变（皇家蓝→金色→酒红）
- [ ] **右下角有返回顶部按钮**，滚动 2 屏后出现
- [ ] **有作者信息卡片**，正文结束后、CTA 之前展示作者简介
- [ ] **文章末尾有标签组**（`tag-group`），方便分类检索
- [ ] **代码块有语言标记标签**（右上角金色小字显示"CSS"/"HTML"/"JS"）
- [ ] **有 Scroll Reveal 入场动画**，轻、慢、克制，不影响阅读
- [ ] **支持打印样式**，打印时隐藏导航/TOC/CTA，保留正文和代码
- [ ] **有相关文章推荐**，CTA 区域或侧边展示
- [ ] **IP 形象在合适位置自然出现**（如文章开头的引导角色，可选）
- [ ] **图片/截图有统一圆角和阴影**，视觉风格一致

---

## 附录：教程页面快速模板结构

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>教程标题 · 飞鸿</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Cormorant+Garamond:ital,wght@0,400;1,400&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  <style>
    /* === Brand Tokens === */
    :root {
      --royal: #0A2463; --gold: #F4D35E; --wine: #D8315B;
      --cream: #FDFBF6; --ink: #0D1225;
      --font-serif: 'Playfair Display', 'Noto Serif SC', Georgia, serif;
      --font-sans: 'Inter', 'Noto Sans SC', -apple-system, sans-serif;
      --font-display: 'Cormorant Garamond', 'Noto Serif SC', Georgia, serif;
      --font-mono: 'JetBrains Mono', Consolas, monospace;
      --r-lg: 12px; --sp-5: 1.5rem;
    }
    /* === Reset & Base === */
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

    /* === Reading Progress === */
    .reading-progress {
      position: fixed; top: 0; left: 0; height: 3px;
      background: linear-gradient(90deg, var(--royal), var(--gold), var(--wine));
      z-index: 200; transition: width 0.1s linear;
    }

    /* === Layout === */
    .tutorial-layout {
      display: grid;
      grid-template-columns: 240px 680px;
      gap: 4rem;
      max-width: 1000px;
      margin: 0 auto;
      padding: 6rem 1.5rem 4rem;
    }

    /* === TOC Sidebar === */
    .toc-sidebar {
      position: sticky; top: 100px;
      align-self: start;
      font-size: 0.875rem;
    }
    .toc-sidebar a {
      display: block;
      padding: 0.4rem 0 0.4rem 1rem;
      color: var(--ink-300, #6D7487);
      text-decoration: none;
      border-left: 2px solid transparent;
      transition: all 0.2s ease;
    }
    .toc-sidebar a:hover { color: var(--royal); }
    .toc-sidebar a.active {
      color: var(--royal);
      border-left-color: var(--gold);
      font-weight: 600;
    }

    /* === Article === */
    .tutorial-article { max-width: 680px; }
    .tutorial-article .eyebrow {
      display: inline-block;
      font-size: 0.75rem;
      font-weight: 500;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--royal);
      background: rgba(10,36,99,0.06);
      padding: 0.25rem 0.75rem;
      border-radius: 4px;
    }
    .tutorial-article h1 {
      font-family: var(--font-serif);
      font-size: clamp(1.75rem, 4vw, 2.75rem);
      font-weight: 700; line-height: 1.2;
      color: var(--ink); margin: 1rem 0 0.75rem;
    }
    .article-meta {
      font-size: 0.875rem; color: #6D7487;
      display: flex; gap: 0.5rem; margin-bottom: 1.5rem;
    }
    .divider-gold {
      height: 1px;
      background: linear-gradient(90deg, transparent 0%, var(--gold) 30%, var(--gold) 70%, transparent 100%);
      margin: 3rem 0 2rem;
    }
    .divider-gold.short {
      background: linear-gradient(90deg, var(--gold) 0%, transparent 100%);
      max-width: 60px; margin: 1.5rem 0;
    }
    .tutorial-article h2 {
      font-family: var(--font-serif);
      font-size: clamp(1.5rem, 2.5vw, 2rem);
      font-weight: 700; line-height: 1.25;
      color: var(--ink); margin: 0 0 1rem;
    }
    .tutorial-article h3 {
      font-family: var(--font-serif);
      font-size: clamp(1.25rem, 2vw, 1.5rem);
      font-weight: 600; color: var(--ink);
      margin: 2rem 0 0.75rem;
    }
    .tutorial-article p {
      font-size: clamp(1rem, 1.2vw, 1.125rem);
      line-height: 1.75; color: #2C3347;
      margin-bottom: 1.5rem;
    }

    /* === Code Block === */
    .code-block {
      background: var(--ink); color: #E2E8F0;
      font-family: var(--font-mono);
      font-size: 0.875rem; line-height: 1.7;
      padding: 1.5rem;
      border-radius: 0 var(--r-lg) var(--r-lg) 0;
      border-left: 3px solid var(--gold);
      overflow-x: auto; margin: 1.5rem 0;
    }
    .code-block code { font-family: inherit; }
    .inline-code {
      font-family: var(--font-mono);
      font-size: 0.875em;
      background: rgba(10,36,99,0.06);
      color: var(--royal);
      padding: 0.15em 0.4em;
      border-radius: 4px;
    }

    /* === Lists === */
    .list-gold-dot { list-style: none; padding: 0; margin: 0 0 1.5rem; }
    .list-gold-dot li {
      font-size: 1rem; line-height: 1.7; color: #2C3347;
      padding-left: 1.5rem; position: relative; margin-bottom: 0.75rem;
    }
    .list-gold-dot li::before {
      content: ''; position: absolute; left: 0; top: 0.7em;
      width: 8px; height: 8px; background: var(--gold); border-radius: 50%;
    }

    /* === Pull Quote === */
    .pull-quote {
      text-align: center; padding: 3rem 1.5rem; margin: 2.5rem 0;
      position: relative;
    }
    .pull-quote .quote-mark {
      font-family: var(--font-serif); font-size: 5rem;
      color: var(--gold); line-height: 1; display: block;
    }
    .pull-quote p {
      font-family: var(--font-display);
      font-size: clamp(1.25rem, 2.5vw, 1.75rem);
      font-style: italic; color: var(--royal);
      line-height: 1.5; margin: 1rem auto; max-width: 600px;
    }
    .pull-quote cite {
      font-family: var(--font-sans); font-size: 0.875rem;
      font-style: normal; color: #6D7487;
      letter-spacing: 0.1em; text-transform: uppercase;
    }

    /* === CTA Dark Panel === */
    .dark-panel {
      background: radial-gradient(ellipse at top left, #081C4F 0%, var(--ink) 70%);
      border-radius: 20px; padding: clamp(3rem, 6vw, 5rem);
      color: #fff; margin-top: 4rem; text-align: center;
    }
    .dark-panel h2 {
      font-family: var(--font-serif); color: #fff;
      font-size: clamp(1.75rem, 3.5vw, 2.5rem);
      margin: 1rem 0;
    }
    .dark-panel p { color: rgba(255,255,255,0.7); max-width: 500px; margin: 0 auto 2rem; }
    .btn-cta {
      display: inline-flex; align-items: center; gap: 0.5rem;
      font-family: var(--font-sans); font-size: 1rem; font-weight: 500;
      padding: 0.875rem 2rem; border-radius: 8px; border: none;
      background: var(--wine); color: #fff;
      box-shadow: 0 4px 20px rgba(216,49,91,0.25);
      cursor: pointer; text-decoration: none;
      transition: all 0.2s ease;
    }
    .btn-cta:hover { transform: translateY(-1px); box-shadow: 0 6px 24px rgba(216,49,91,0.35); }

    /* === Responsive === */
    @media (max-width: 960px) {
      .tutorial-layout { grid-template-columns: 1fr; }
      .toc-sidebar { display: none; } /* 移动端使用折叠抽屉 */
    }
    @media (prefers-reduced-motion: reduce) {
      .reading-progress { transition: none; }
      html { scroll-behavior: auto; }
    }
  </style>
</head>
<body>
  <div class="reading-progress" id="progress" style="width:0%"></div>

  <div class="tutorial-layout">
    <!-- TOC Sidebar -->
    <nav class="toc-sidebar" aria-label="目录">
      <a href="#intro" class="active">引言</a>
      <a href="#section-1">第一章</a>
      <a href="#section-2">第二章</a>
      <a href="#section-3">第三章</a>
      <a href="#conclusion">结语</a>
    </nav>

    <!-- Article -->
    <article class="tutorial-article">
      <span class="eyebrow">教程</span>
      <h1>文章标题</h1>
      <div class="article-meta">
        <span>2026年7月</span><span>·</span><span>阅读 8 分钟</span>
      </div>
      <div class="divider-gold short"></div>

      <section id="intro">
        <p>引言段落...</p>
      </section>

      <div class="divider-gold"></div>
      <section id="section-1">
        <h2>第一章标题</h2>
        <p>正文内容...</p>
        <pre class="code-block"><code>const example = "code here";</code></pre>
        <ul class="list-gold-dot">
          <li>要点一</li>
          <li>要点二</li>
        </ul>
      </section>

      <div class="divider-gold"></div>
      <section id="section-2">
        <h2>第二章标题</h2>
        <blockquote class="pull-quote">
          <span class="quote-mark">&ldquo;</span>
          <p>核心金句</p>
          <cite>— 飞鸿</cite>
        </blockquote>
        <h3>小节标题</h3>
        <p>正文内容...</p>
      </section>

      <div class="divider-gold"></div>
      <section id="section-3">
        <h2>第三章标题</h2>
        <p>正文内容，使用 <code class="inline-code">行内代码</code>...</p>
      </section>

      <div class="divider-gold"></div>
      <section id="conclusion">
        <h2>结语</h2>
        <p>总结段落...</p>
      </section>

      <!-- CTA -->
      <div class="dark-panel">
        <h2>准备好开始实践了吗？</h2>
        <p>将这些规范应用到你的下一篇教程文章中。</p>
        <a href="#" class="btn-cta">查看更多教程</a>
      </div>
    </article>
  </div>

  <script>
    // Reading progress bar
    window.addEventListener('scroll', () => {
      const h = document.documentElement;
      const pct = (h.scrollTop / (h.scrollHeight - h.clientHeight)) * 100;
      document.getElementById('progress').style.width = pct + '%';
    });
    // TOC active state
    const sections = document.querySelectorAll('section[id]');
    const tocLinks = document.querySelectorAll('.toc-sidebar a');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(e => {
        if (e.isIntersecting) {
          tocLinks.forEach(l => l.classList.remove('active'));
          const link = document.querySelector(`.toc-sidebar a[href="#${e.target.id}"]`);
          if (link) link.classList.add('active');
        }
      });
    }, { threshold: 0.3 });
    sections.forEach(s => observer.observe(s));
  </script>
</body>
</html>
```

---

## 场景定位

教程/文章/长文场景是以深度阅读为核心的内容页面，用于技术教程、设计指南、观点文章、知识长文等需要读者沉浸阅读10分钟以上的内容。适用于：技术博客文章、设计教程、深度分析、系列专栏、课程讲义、文档说明。不适用于：营销转化页（应用Landing）、作品集展示（视觉优先）、功能操作界面（应用App场景）。核心原则是"阅读舒适第一"——字号够大、行宽合理、节奏有变化、装饰服务于内容而非干扰内容。

## 推荐节奏（Section 序列）

### 方案 A：经典教程型（适合技术/操作教程）
1. Hero标题区（L2 居中大字 / L7 单栏长文头部）— 标题+元信息（日期/时长/分类）+首字下沉开头
2. 引言/概述（L7 单栏长文）— 为什么要学、能学到什么、前置知识
3. 第一步（L7 单栏长文+代码块）— 概念解释+代码/操作步骤
4. 旁注/提示（穿插alert-info/warning）— 注意事项和常见错误
5. 深入章节（L7 单栏长文+引用块+列表）— 多个h2章节循环
6. 金句停顿（L8 引文全屏）— 每3-4个章节插入一个pull-quote打破文字密度
7. 总结回顾（L7 单栏长文+金色圆点列表）— 要点回顾
8. CTA（L13/L14 深色面板）— 相关阅读/订阅/下载资源

### 方案 B：观点文章型（适合评论/随笔/观点文）
1. Hero（L2 居中大字）— 大标题+导语+Cormorant斜体副标题
2. 开篇（首字下沉+L7单栏长文）— 故事/场景引入，有温度
3. 论点一（L7 长文+旁注/sidenote）— 观点+论据
4. 金句引用（L8 引文全屏 / #04 Pull Quote）— 核心论点大字呈现
5. 论点二/三（L7 长文+引用块）— 继续论述
6. 反面论证（L6 深色面板可选）— 对立观点或注意事项
7. 结论（L7 长文）— 收束观点
8. 作者信息+CTA（作者卡片+深色面板）

### 方案 C：极简文档型（适合API文档/参考手册）
1. 标题（L7 单栏头部）— 简洁标题+简短描述
2. 目录（固定TOC侧边）— 快速跳转
3. 正文（L7 单栏长文）— 结构化内容，大量代码块/表格
4. 提示框穿插（alert系列）— 重要信息标注
5. 相关链接（L7 尾部）— 上一篇/下一篇导航

### 方案 D：系列专栏型（适合连载/系列教程）
1. 刊头式Hero（#22 Publication Header）— 专栏名+期号+本期标题
2. 上期回顾（L7 简短段落+链接）— 系列连贯性
3. 正文（L7 多章节，节奏变化丰富）— 首字下沉+旁注+代码+引用
4. 章节编号（#14 Section Marker + #20 Numbered Index）— 罗马数字/阿拉伯数字编号
5. 思考与练习（金色圆点列表）— 互动环节
6. 下集预告（L6 深色面板）— 预告下期内容
7. 订阅CTA（L13 深色面板）— 订阅专栏更新

## 专属装饰手法（Signature Touches）

- **#21 Drop Cap 首字下沉**：文章第一段第一个字母使用Playfair Display超大号下沉（3-4行高），金色或皇家蓝色，书卷气的标志手法
- **#04 Pull Quote 金句引用**：正文中每隔3-4个章节插入一个Cormorant斜体金句块，金色大引号装饰，打破文字密度
- **#01 sidenote 旁注/边注**：桌面端右侧margin区域放置补充说明、参考链接、术语解释，正文用金色编号标记
- **#15 Divider 分隔线**：h2章节之间使用金色渐变分隔线（中间金色两端透明），而非hr或大块留白
- **#09 Fleuron 花饰**：文章开头标题下方或章节分隔处使用❦花饰，增加印刷品质感
- **#20 Numbered Index 编号索引**：教程步骤用大号金色衬线数字编号（01/02/03），方便对照和回溯
- **#14 Section Marker 章节标记**：h2标题旁可加金色罗马数字（I, II, III...）作为章节标记
- **#06 Terminal Code Block 终端代码块**：技术教程中代码块使用深色背景（#0D1225墨黑）+金色左侧边框（3px），右上角可加语言标签
- **#05 Highlight 荧光笔高亮**：正文中的关键术语、核心概念用金色荧光笔效果标记（`::after`黄色半透明背景）
- **#16 Alert Box 提示框**：INFO用皇家蓝边框+浅蓝底，WARNING用金色边框+浅金底，IMPORTANT用酒红边框+浅红底
- **#08 Footnote 脚注/尾注**：学术性文章用脚注，正文用上标金色数字标记，底部集中列出注释
- **#19 Handwritten Note 手写注**：教程中可加手写体旁注（如"这里容易错！"/"亲测有效"），增加人味和亲和力

## 推荐布局组合

| 布局 | 名称 | 适用位置 | 说明 |
|------|------|----------|------|
| **L7** | 单栏长文 | 正文主体 | 650-700px行宽，阅读舒适区，是教程场景绝对主体 |
| **L2** | 居中大字Hero | 文章头部 | 大标题居中，元信息在下，简洁大气 |
| **L8** | 引文全屏 | 章节之间 | Pull-quote金句，打断长文节奏，Cormorant斜体 |
| **L6** | 深色面板 | 反面论证/预告/CTA | 深蓝色背景打断全文字，视觉停顿 |
| **L5** | 左图右文 | 文中需要配图说明处 | 截图/示意图+文字说明 |
| **L9** | 图片全宽 | 大图展示 | 截图/图表突破正文宽度展示 |
| **L3** | 三列等分（变体） | 步骤/要点并列 | 3个步骤或要点并排（桌面端），移动端折叠 |
| **L13** | 深色面板CTA | 文章结尾 | 订阅/下载/相关阅读引导 |
| **L14** | 双栏TOC+正文 | 整体页面骨架 | 左侧240px固定TOC+右侧680px正文，桌面端标准 |

## 色彩策略

教程场景三色分配，核心原则：色彩服务于阅读，不干扰文字。

**皇家蓝 #0A2463（55%）—— 标题与信任**
- h1/h2/h3所有标题文字颜色
- 文章元信息中的标签分类背景
- 链接文字颜色
- INFO提示框的边框和图标
- 旁注(sidenote)的标记数字
- 作者名字
- 代码块语言标签背景（可选）

**复古金 #F4D35E（30%）—— 装饰与高亮**
- 首字下沉(Drop Cap)颜色
- 章节分隔线（金色渐变线）
- 代码块左侧3px金色边框
- Pull-quote的大引号颜色
- 荧光笔高亮效果（半透明金色背景）
- 旁注编号标记颜色
- 列表金色圆点
- TOC当前章节的金色左边框
- Fleuron花饰颜色
- 章节编号数字颜色
- 阅读进度条的中间色
- **金色在白底上仅用于装饰/线条/高亮背景，不用于大段正文**

**酒红 #D8315B（15%）—— 警示与强调**
- IMPORTANT提示框的边框和标识
- 代码块中的错误/警告高亮
- 正文中需要极强提醒的文字
- 阅读进度条的终点色
- 标签中"更新"/"重要"等紧急标识
- **酒红在教程中使用最克制，仅用于真正需要注意的内容**

**背景处理**：整体暖米白`#FDFBF6`；代码块用墨黑`#0D1225`深色背景；pull-quote可用暖米白或极浅皇家蓝底（`#EEF1FA`）；深色面板仅在CTA和特殊警示处使用，正文中不插入深色面板打断阅读流。

## 场景禁忌（Don'ts）

1. **行宽过宽过窄**：正文行宽必须控制在650-700px，超过800px阅读疲劳，低于500px换行频繁
2. **正文字号小于16px**：长文阅读16px是底线，推荐17-18px（1rem=16px时用1.0625rem-1.125rem）
3. **行高低于1.6**：中文长文行高必须≥1.7，英文≥1.65，否则文字拥挤
4. **段落之间无间距**：段落间距至少1.5rem，不要紧贴在一起
5. **全文字墙无变化**：不能从头到尾都是p标签，必须穿插列表、引用、代码块、提示框、图片
6. **斜体正文大段使用**：Cormorant斜体仅用于引用、副标题、金句，不用于正文段落
7. **代码块无横向滚动**：长代码行必须`overflow-x:auto`，不能撑破布局
8. **TOC在移动端不处理**：桌面端固定侧边TOC，移动端必须折叠为抽屉或顶部锚点导航
9. **等宽字体用于正文**：JetBrains Mono仅用于代码和行内代码，正文必须用Inter
10. **深色背景上放大段正文**：深色面板只放标题+少量文字+CTA，不要在深蓝底上放长段落

## 场景专属Checklist

- [ ] 正文行宽650-700px，字号≥16px（推荐17-18px），行高≥1.7
- [ ] 文章第一段有首字下沉（Drop Cap），Playfair Display大字金色/皇家蓝
- [ ] 有固定TOC侧边栏（桌面端240px），当前章节金色左边框高亮，移动端折叠
- [ ] 顶部有阅读进度条（三色渐变皇家蓝→金色→酒红）
- [ ] h2章节之间有金色渐变分隔线
- [ ] 每3-4个文字章节有节奏变化：代码块/引用/列表/提示框/图片
- [ ] Pull-quote金句使用Cormorant Garamond italic，金色大引号，居中
- [ ] 代码块使用墨黑背景（#0D1225）+金色左侧3px边框，JetBrains Mono字体
- [ ] 行内代码使用浅皇家蓝背景+皇家蓝文字，等宽字体
- [ ] 提示框按语义分级：INFO=皇家蓝、WARNING=金色、IMPORTANT=酒红
- [ ] 关键术语有金色荧光笔高亮（至少2-3处）
- [ ] 无序列表使用金色圆点（list-gold-dot），不用默认disc
- [ ] 文章元信息行存在：日期·阅读时长·分类标签
- [ ] 页面顶部3px有阅读进度条，随滚动实时更新
- [ ] 移动端代码块可横向滚动，字号不小于14px
- [ ] 打印样式友好：@media print隐藏导航/TOC/CTA，保留正文
- [ ] 文章结尾有CTA或相关阅读引导，不让读者戛然而止
- [ ] 语义化HTML：article/nav/section/blockquote/pre/code标签正确使用
- [ ] 选中文本背景为金色，无bounce/弹性/无限循环动画干扰阅读

---

*Scene: Tutorial v1.0 · Feihong Design System*
*基于 DNA.md v2.0 · 最后更新：2026-07-08*
