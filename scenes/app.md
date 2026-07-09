# Feihong Design System · Scene: App
# 飞鸿品牌设计系统 · 场景规范：App型 / 功能型页面

> 本规范定义飞鸿品牌设计系统在「App型页面 / 功能型工具页 / 看板 / 仪表盘 / Canvas工具」中的具体应用方式。
> 所有规则建立在 `DNA.md`、`components/14-layouts.md`、`components/` 基础之上，场景专属规则以本文件为准。
> App场景的核心使命是**可用**——每一个交互都应为"让用户高效完成任务"服务。

---

## 1. 场景定义

### 适用页面类型

App场景适用于以下以**功能交互为核心目标**的产品形态：

| 类型 | 说明 | 典型特征 | 核心任务 |
|------|------|----------|---------|
| **工具页/功能页** | 编辑器、转换器、计算器、配置器 | 单功能聚焦，操作密集 | 完成一次操作 |
| **看板/仪表盘** | 数据看板、管理后台、监控面板 | 信息密度高，多组件组合 | 浏览数据+快速操作 |
| **App界面** | Web应用、SaaS产品、内部工具 | 多页面导航，状态持久 | 持续使用 |
| **Canvas工具** | 绘图工具、可视化编辑器、白板 | 画布+工具栏+属性面板 | 创作/编辑 |
| **管理后台** | CMS、CRM、数据管理系统 | 表格+表单+侧边栏 | CRUD操作 |

### 场景核心气质

- **高效可靠**：界面克制有序，让用户专注于任务本身，而非装饰
- **清晰反馈**：每一次操作都有即时、明确的状态响应
- **品牌融入**：在导航、主操作、关键状态点体现品牌色，UI承载面用中性色
- **密度适中**：信息密度高于Landing页，但不拥挤，留白用于分区而非装饰

### 场景核心约束

1. **功能优先于装饰**：所有设计决策服务于"让用户完成任务"，不以牺牲可用性换取视觉效果
2. **交互元素必须有完整状态**：hover / active / disabled / focus 四态缺一不可
3. **品牌色克制使用**：UI密度高时三色要"点到为止"，用中性色（暖米白、灰白）承载大部分界面
4. **表单必须有验证反馈**：输入错误/成功/警告状态必须有清晰的视觉提示
5. **响应式不可省略**：功能型页面必须适配至少桌面端+平板端，有移动端需求时需专门适配

---

## 2. 典型页面结构

App型页面通常采用**导航区 + 工作区**的经典功能布局，根据页面复杂度有三种典型结构：

```
┌─────────────────────────────────────────────────────────┐
│  结构 A：侧边栏 + 主内容区（最常用，适合多模块App）         │
├──────────┬──────────────────────────────────────────────┤
│          │  顶部栏（面包屑 + 全局操作 + 用户头像）          │
│          ├──────────────────────────────────────────────┤
│  侧边栏   │                                              │
│  (导航)   │  主内容区（功能界面 / 看板 / 表格 / 画布）      │
│          │                                              │
│          │                                              │
│          │                                              │
└──────────┴──────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│  结构 B：顶部导航 + 内容区（适合工具页、单功能应用）        │
├─────────────────────────────────────────────────────────┤
│  顶部导航栏（Logo + 导航链接 + 操作按钮 + 用户）           │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  主内容区（功能界面）                                     │
│                                                         │
│                                                         │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│  结构 C：全屏工具布局（适合Canvas工具、编辑器）             │
├──────────┬───────────────────────────────┬──────────────┤
│          │  顶部工具栏                     │              │
│  左侧    ├───────────────────────────────┤  右侧        │
│  工具面板 │                               │  属性面板     │
│          │                               │              │
│          │        画布 / 工作区            │              │
│          │                               │              │
└──────────┴───────────────────────────────┴──────────────┘
```

### 结构要点

1. **导航区承载品牌色**：侧边栏使用皇家蓝深色系，顶部栏使用暖米白/白色，建立清晰的品牌识别
2. **主内容区以中性色为主**：背景用暖米白或极浅灰白，让功能内容成为视觉焦点
3. **顶部栏包含全局操作**：面包屑导航、搜索、通知、用户头像、设置入口
4. **侧边栏折叠态**：宽≥64px（仅图标），展开态200-260px（图标+文字）
5. **工具栏固定位置**：Canvas工具的工具栏固定在边缘，不随内容滚动
6. **不使用Landing页的section结构**：App页不是纵向滚动的营销页，是功能分区的工作界面

---

## 3. 色彩使用指南

App场景中三色的使用原则与Landing页截然不同——**克制、精准、语义化**。界面的80%以上面积应由中性色承载，品牌色仅承担导航、主操作和状态语义。

### 3.1 皇家蓝 `#0A2463` — 导航与主操作色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **侧边栏背景** | 深色侧边栏用皇家蓝系（`#081C4F` ~ `#0A2463`） | 深色导航，品牌感强，与浅色内容区形成对比 |
| **主操作按钮** | `btn-primary`（皇家蓝按钮） | 表单提交、主要操作、确认按钮 |
| **导航选中态** | 侧边栏/顶部导航的当前页高亮 | 皇家蓝文字+左侧金色指示条或皇家蓝背景+白色文字 |
| **链接文字** | 界面内链接、表格内操作链接 | 皇家蓝默认色 |
| **品牌Logo** | 侧边栏顶部Logo、页面标题旁品牌标识 | Playfair Display衬线Logo |
| **选中/激活状态** | 菜单选中、Tab激活、单选选中 | 皇家蓝作为active语义色 |
| **焦点环** | 表单元素focus时的外发光 | `box-shadow: 0 0 0 3px rgba(10,36,99,0.15)` |

### 3.2 复古金 `#F4D35E` — 成功状态与高亮色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **成功状态** | 成功提示图标、操作成功反馈 | 金色对勾/圆点，配合文字提示 |
| **重点数据高亮** | 仪表盘关键数字、KPI指标 | 金色衬线数字，在数据看板中突出核心指标 |
| **通知/提醒标记** | 小红点替代方案、未读标记 | 金色圆点，比酒红更温和 |
| **标签/Tag** | `tag-gold` 状态标签（"已完成"/"在线"/"活跃"） | 金色背景+皇家蓝文字 |
| **进度条** | progress组件的填充色 | 金色填充，皇家蓝轨道 |
| **选中指示条** | 侧边栏/导航选中时的左侧指示条 | 3px宽金色竖条，精致不突兀 |
| **星级/评分** | 评分组件的星星 | 金色实心星 |

### 3.3 酒红 `#D8315B` — 错误与危险操作色

| 用途 | 具体应用 | 说明 |
|------|----------|------|
| **错误状态** | 表单验证失败、输入错误提示 | 酒红边框+酒红错误文字 |
| **危险操作** | 删除按钮、撤销不可逆操作的按钮 | `btn-danger`酒红描边按钮，非实心 |
| **警告/告警** | 系统告警、异常状态提示 | `alert-wine` 酒红左边框警告条 |
| **负面指标** | 下降趋势、异常数据、超阈值 | 酒红数字/箭头，配合向下图标 |
| **必填标记** | 表单必填字段的星号 `*` | 酒红色星号，传统表单语义 |
| **离线/错误状态** | 连接断开、同步失败图标 | 酒红小图标 |

> **铁律**：酒红在App场景中是**语义色**而非装饰色，绝不能用于非错误/危险场景的大面积着色。

### 3.4 背景与中性色（App场景主力色）

| 元素 | 色值 | 说明 |
|------|------|------|
| **页面主背景** | `#FDFBF6` (`var(--cream)`) | 暖米白，长时间使用不刺眼 |
| **卡片/面板背景** | `#FFFFFF` | 纯白卡片，与暖米白形成微妙层次 |
| **侧边栏背景（深色）** | `#081C4F` ~ `#0A2463` | 皇家蓝深蓝，白字为主 |
| **侧边栏文字** | `rgba(255,255,255,0.7)` | 非选中项用70%白，选中项纯白 |
| **顶部栏背景** | `#FFFFFF` | 白色顶栏，底部1px暖灰边框 |
| **正文文字** | `var(--ink-100)` (`#2C3347`) | 深灰，非纯黑，长阅读舒适 |
| **标题文字** | `var(--ink)` (`#0D1225`) | 墨黑，标题对比强 |
| **辅助文字** | `var(--ink-300)` (`#6D7487`) | 说明文字、placeholder、时间戳 |
| **禁用文字** | `var(--ink-400)` (`#9CA1B3`) | disabled状态文字 |
| **边框/分隔线** | `#F0EAD9` (`var(--cream-200)`) | 暖调边框，卡片、表格、输入框 |
| **输入框背景** | `#FAFAF7` | 极浅暖灰，与白色卡片区分 |
| **hover背景** | `#F8F4EB` (`var(--cream-100)`) | 行hover、菜单项hover |
| **终端/代码区背景** | `#0D1225` (墨黑) | 终端区域深色背景，终端绿文字 |

### 3.5 终端/代码区域专属色

| 元素 | 色值 | 说明 |
|------|------|------|
| 终端背景 | `#0D1225` (墨黑) | 深色，降低视觉疲劳 |
| 终端文字 | `#E2E8F0` | 浅灰白主文字 |
| **终端绿** | **`#4ADE80`** | 命令提示符、成功输出、关键字高亮 |
| 终端注释 | `#6D7487` | 灰色注释文字 |
| 终端错误 | `#D8315B` (酒红) | 错误输出复用品牌酒红 |
| 终端选择 | `rgba(74,222,128,0.15)` | 选中文字背景用终端绿透明 |

### 色彩使用铁律（App场景）

1. **三色总面积不超过界面的20%**：80%以上面积应由暖米白、白、暖灰等中性色承载
2. **皇家蓝做主操作，金色做成功/高亮，酒红做错误/危险**：三色语义不混淆
3. **侧边栏是品牌色唯一大面积使用区域**：主内容区保持中性
4. **同一屏内酒红色元素不超过2处**：错误提示+删除按钮，避免焦虑感
5. **终端绿仅用于终端/代码区域**：其他场景不使用此色
6. **不用彩色背景卡片**：卡片一律白底暖边框，不使用皇家蓝/金色/酒红填充的大色块卡片
7. **数据看板中金色仅用于1-2个核心KPI**：其余数字用皇家蓝或墨黑，避免满屏金色

---

## 4. 排版规范

App场景的排版以**清晰、高效、易扫读**为核心，字号偏小但层次分明，不使用Landing页的极端字号对比。

### 4.1 UI文字规范

| 元素 | 字号 | 行高 | 字体 | 颜色 | 说明 |
|------|------|------|------|------|------|
| **页面大标题** | `1.5rem` - `1.75rem`（24-28px） | 1.3 | Playfair Display 700 | `var(--ink)` | 仅页面顶部h1，仅此一处用衬线 |
| **面板/卡片标题** | `1rem` - `1.125rem`（16-18px） | 1.4 | Inter 600 | `var(--ink)` | 卡片标题、面板标题 |
| **正文/内容文字** | **`1rem`（16px）** | 1.5 | Inter 400 | `var(--ink-100)` | 主内容文字、表格内容 |
| **辅助/说明文字** | **`0.875rem`（14px）** | 1.5 | Inter 400 | `var(--ink-300)` | 辅助描述、表单帮助文字 |
| **小标签/元信息** | `0.75rem`（12px） | 1.4 | Inter 500 | `var(--ink-300)` | 时间戳、状态标记、breadcrumb |
| **表单标签** | `0.875rem`（14px） | 1.4 | Inter 500 | `var(--ink)` | 输入框上方标签，清晰可辨 |
| **按钮文字** | `0.875rem` - `0.9375rem`（14-15px） | 1 | Inter 500 | #fff / 品牌色 | 无衬线，不斜体 |
| **侧边栏导航文字** | `0.875rem`（14px） | 1 | Inter 500 | rgba(255,255,255,0.7) / #fff | 选中态纯白加粗 |
| **表格表头** | `0.8125rem`（13px） | 1 | Inter 600 | `var(--ink-300)` | 全大写或正常，加字距0.05em |
| **数据数字** | `1rem`（16px） | 1 | JetBrains Mono / Inter | `var(--ink)` | 等宽或tabular-nums，对齐整齐 |
| **KPI大数字** | `1.75rem` - `2.25rem`（28-36px） | 1.1 | Playfair Display 700 | `var(--gold)` / `var(--royal)` | 仪表盘核心指标，金色或皇家蓝 |
| **终端/代码文字** | `0.875rem`（14px） | 1.6 | JetBrains Mono | `#E2E8F0` | 等宽字体，终端绿点缀关键字 |

### 4.2 字体使用规则

| 字体 | 使用场景 | 禁用场景 |
|------|----------|---------|
| **Playfair Display（衬线）** | 页面大标题h1、品牌Logo、KPI大数字 | 界面内任何正文、按钮、表单标签、导航文字 |
| **Inter（无衬线）** | 所有UI文字（正文、标签、按钮、导航、表格） | 大标题（用衬线）、代码/终端（用等宽） |
| **Cormorant Garamond（斜体）** | 极少使用，仅偶尔用于欢迎语/引言 | 功能界面内完全不用 |
| **JetBrains Mono（等宽）** | 代码块、终端、数据表格数字、ID/序列号 | 正文段落、标题 |

> **铁律**：界面内95%以上的文字使用Inter。Playfair Display仅出现在页面顶部Logo和大标题位置，不深入工作区。

### 4.3 排版特殊规则

1. **数字对齐**：
   - 表格中的数字列使用 `font-variant-numeric: tabular-nums` 或 JetBrains Mono
   - 金额、百分比、数量右对齐，方便比较
   - KPI大数字可使用Playfair Display衬线增强权威感

2. **表单排版**：
   - 标签在输入框上方（非左侧），减少水平跳动
   - 必填标记用酒红星号 `*`，放在标签文字后
   - 错误提示在输入框下方，酒红色12px文字
   - 帮助文字在输入框下方，灰色12px文字

3. **表格排版**：
   - 表头灰色小字号，正文14-16px
   - 行高44-48px，给够点击区域
   - 操作列固定宽度，文字链接用皇家蓝
   - 数字列右对齐，文本列左对齐

4. **终端/代码排版**：
   ```css
   .terminal {
     font-family: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
     font-size: 0.875rem;
     line-height: 1.6;
     background: var(--ink);
     color: #E2E8F0;
     padding: 1rem 1.25rem;
     border-radius: 8px;
   }
   .terminal .prompt { color: var(--terminal-green); } /* #4ADE80 */
   .terminal .error { color: var(--wine); }
   .terminal .comment { color: #6D7487; }
   ```

---

## 5. 推荐布局

App场景使用功能型布局，从layouts中选取以下组合，**不使用L8/L16等艺术化布局**。

### 5.1 全局框架布局

| 布局 | 适用场景 | 结构 |
|------|----------|------|
| **侧边栏+主内容区** | 多模块SaaS、管理后台、仪表盘 | 左侧固定深色侧边栏 + 右侧顶部栏+内容区 |
| **顶部导航+内容** | 单功能工具、轻量App、配置器 | 顶部固定导航栏 + 下方全宽内容区 |
| **全屏工具布局** | Canvas编辑器、绘图工具、IDE | 四周工具栏/面板 + 中央画布区 |

### 5.2 内容区布局模式

| 模式 | 适用场景 | 说明 |
|------|----------|------|
| **卡片网格** | 仪表盘、功能入口 | 等宽卡片网格（2-4列），每个卡片一个功能模块 |
| **数据表格** | 列表页、管理页 | 全宽表格+筛选栏+分页 |
| **表单布局** | 配置页、设置页 | 单列表单（宽≤600px）或双列表单 |
| **分栏面板** | 详情页、编辑器 | 左侧列表25-30% + 右侧详情70-75% |
| **Tab切换** | 多视图切换 | 顶部Tab栏+下方内容区，Tab用皇家蓝下划线激活 |

### 5.3 经典App布局配方

#### 配方 A：仪表盘/看板

```
┌────────┬─────────────────────────────────────┐
│        │  顶部栏：页面标题 + 日期筛选 + 导出    │
│ 侧边栏  ├─────────────────────────────────────┤
│        │  KPI卡片行（4个stat-card横排）         │
│  ● 首页  │  ┌──────┬──────┬──────┬──────┐     │
│  ○ 数据  │  │ KPI  │ KPI  │ KPI  │ KPI  │     │
│  ○ 用户  │  └──────┴──────┴──────┴──────┘     │
│  ○ 设置  ├─────────────────────────────────────┤
│        │  图表区（2列：折线图+饼图）            │
│        │  ┌─────────────┬─────────────┐       │
│        │  │  趋势图表    │  分布图表    │       │
│        │  └─────────────┴─────────────┘       │
│        ├─────────────────────────────────────┤
│        │  最近活动列表（timeline）              │
└────────┴─────────────────────────────────────┘
```

#### 配方 B：数据管理后台

```
┌────────┬─────────────────────────────────────┐
│        │  顶部栏：面包屑 + 搜索 + 新建按钮      │
│ 侧边栏  ├─────────────────────────────────────┤
│        │  筛选栏：筛选条件+搜索框              │
│  ● 用户  ├─────────────────────────────────────┤
│  ○ 订单  │                                     │
│  ○ 商品  │  数据表格（全宽）                    │
│  ○ 数据  │  ┌─────────────────────────────┐   │
│        │  │ ID  名称  状态  时间  操作     │   │
│        │  │ ...                           │   │
│        │  └─────────────────────────────┘   │
│        │  分页器                             │
└────────┴─────────────────────────────────────┘
```

#### 配方 C：全屏工具/编辑器

```
┌────────┬───────────────────────────────┬────────┐
│ 工具栏  │  顶部：工具选项                │  面板  │
│        ├───────────────────────────────┤        │
│ 工具图标│                               │ 属性   │
│ 图标    │                               │ 设置   │
│ 图标    │      画布 / 工作区              │ 选项   │
│ 图标    │                               │        │
│        │                               │        │
└────────┴───────────────────────────────┴────────┘
```

### 5.4 布局使用禁忌

| 布局/做法 | App场景不推荐原因 |
|-----------|------------------|
| **L8 引文全屏/L16 画册溢出** | 艺术化布局打断工作流，不适合功能界面 |
| **Landing式纵向section** | App页不是营销页，不需要"英雄区→功能区→CTA"结构 |
| **极端字号对比** | 大标题80px+副标题20px的对比在功能界面中过于突兀 |
| **彩色背景大色块** | 皇家蓝/金色/酒红的大面积背景会干扰内容阅读 |
| **全宽英雄图/背景图** | 功能界面不放装饰性大图，影响信息密度 |
| **多列不对称瀑布流** | 功能区需要对齐和秩序感，瀑布流太随意 |

---

## 6. 组件选用指南

### 6.1 必用组件（App场景核心组件）

| 组件 | 组件名 | 使用场景 | 状态要求 |
|------|--------|----------|---------|
| **表单输入** | `form-input` | 所有输入场景（文本、数字、密码、搜索） | hover / focus / error / disabled 四态 |
| **下拉选择** | `form-select` | 选项选择、筛选器 | hover / focus / open / disabled 四态 |
| **按钮系列** | `btn-primary` / `btn-outline` / `btn-danger` / `btn-ghost` | 各类操作（提交/取消/删除/次要操作） | hover / active / disabled / loading 四态 |
| **标签** | `tag` / `badge` | 状态标记、分类标签、属性标记 | 默认/hover/可关闭 |
| **进度条** | `progress` | 加载进度、完成度、技能/配额 | 0%/中间/100%，动画可选 |
| **提示框** | `alert` | 成功/错误/警告/信息提示 | success(gold) / error(wine) / warning / info(royal) |
| **表格** | `data-table` | 数据列表、管理列表 | 行hover/选中/排序/分页/空状态 |
| **徽章** | `badge` | 数字标记、未读计数、状态小圆点 | gold/wine/royal/gray |
| **时间线** | `timeline` | 活动日志、操作历史、流程步骤 | 完成(gold)/进行中(royal)/待办(gray) |

### 6.2 组件完整状态规范

所有交互组件必须包含以下状态，不允许只有默认样式：

#### 按钮状态示例

```css
.btn { /* 默认样式 */ }
.btn:hover { /* 悬停：上移1px或加深背景色 */ }
.btn:active { /* 按下：下移1px或更深色 */ }
.btn:disabled, .btn[disabled] { /* 禁用：opacity 0.5，cursor: not-allowed，无hover效果 */ }
.btn:focus-visible { /* 键盘焦点：皇家蓝3px光晕 outline */ }
.btn.loading { /* 加载中：显示spinner，禁止点击 */ }
```

#### 表单输入状态示例

```css
.form-input {
  border: 1px solid #F0EAD9;
  background: #FAFAF7;
  border-radius: 8px;
  padding: 0.625rem 0.875rem;
  font-size: 0.9375rem;
  transition: border-color 0.2s, box-shadow 0.2s;
}
.form-input:hover { border-color: #D4CCB8; }
.form-input:focus {
  outline: none;
  border-color: var(--royal);
  box-shadow: 0 0 0 3px rgba(10,36,99,0.12);
}
.form-input.error {
  border-color: var(--wine);
  box-shadow: 0 0 0 3px rgba(216,49,91,0.1);
}
.form-input.success {
  border-color: var(--gold);
}
.form-input:disabled {
  background: #F0EAD9;
  color: #9CA1B3;
  cursor: not-allowed;
}
```

#### 标签/Tag颜色语义

```css
.tag-gold    { background: #FEFCF0; color: var(--royal); border: 1px solid #FAEBA3; }  /* 成功/完成/活跃 */
.tag-royal   { background: #EEF1FA; color: var(--royal); border: 1px solid #D4DCF0; }  /* 进行中/信息 */
.tag-wine    { background: #FDF0F3; color: var(--wine); border: 1px solid #F5C2CE; }   /* 错误/危险/告警 */
.tag-gray    { background: #F5F3ED; color: #6D7487; border: 1px solid #E8E3D4; }       /* 默认/待办/关闭 */
```

#### Alert提示框

```css
.alert {
  display: flex; align-items: flex-start; gap: 0.75rem;
  padding: 1rem 1.25rem; border-radius: 8px; border-left: 3px solid;
}
.alert-success { background: #FEFCF0; border-color: var(--gold); }
.alert-success .alert-icon { color: var(--gold); }
.alert-error   { background: #FDF0F3; border-color: var(--wine); }
.alert-error .alert-icon { color: var(--wine); }
.alert-info    { background: #EEF1FA; border-color: var(--royal); }
.alert-info .alert-icon { color: var(--royal); }
.alert-warning { background: #FEF9E7; border-color: #E5B80B; } /* 辅助金色，非品牌复古金 */
```

### 6.3 推荐组件（按需使用）

| 组件 | 使用场景 |
|------|----------|
| `sidebar`（侧边栏导航） | 多模块App必备，含折叠/展开态 |
| `navbar`（顶部栏） | 所有App页必备，含面包屑/搜索/用户 |
| `breadcrumb`（面包屑） | 深层级页面必备，显示当前位置 |
| `pagination`（分页器） | 数据表格、长列表 |
| `modal/dialog`（弹窗） | 确认操作、详情查看、表单弹窗 |
| `toast`（轻提示） | 操作成功/失败的短暂反馈 |
| `dropdown`（下拉菜单） | 更多操作、用户菜单 |
| `tooltip`（文字提示） | 图标按钮的功能说明 |
| `switch/toggle`（开关） | 设置项的开/关切换 |
| `checkbox/radio`（复选/单选） | 多选/单选项 |
| `date-picker`（日期选择） | 日期筛选、日期输入 |
| `code-block/terminal`（代码/终端） | 开发者工具、日志查看 |
| `stat-card`（数据统计卡） | 仪表盘KPI卡片（金色/皇家蓝数字） |
| `search-input`（搜索框） | 全局搜索、表格筛选搜索 |
| `avatar`（头像） | 用户列表、评论、操作人 |
| `empty-state`（空状态） | 无数据时的引导提示 |

### 6.4 深色侧边栏组件模式

```css
.sidebar {
  width: 240px;
  background: linear-gradient(180deg, #081C4F 0%, #0A2463 100%);
  color: rgba(255,255,255,0.7);
  min-height: 100vh;
  display: flex; flex-direction: column;
}
.sidebar-logo {
  padding: 1.25rem 1.5rem;
  font-family: 'Playfair Display', serif;
  font-size: 1.35rem; font-weight: 700; color: #fff;
  border-bottom: 1px solid rgba(255,255,255,0.08);
}
.sidebar-logo span { color: var(--gold); }
.sidebar-nav { flex: 1; padding: 1rem 0; }
.sidebar-item {
  display: flex; align-items: center; gap: 0.75rem;
  padding: 0.625rem 1.5rem;
  font-size: 0.875rem; color: rgba(255,255,255,0.65);
  text-decoration: none; transition: all 0.2s;
  position: relative;
}
.sidebar-item:hover { background: rgba(255,255,255,0.06); color: #fff; }
.sidebar-item.active {
  color: #fff; font-weight: 600;
  background: rgba(255,255,255,0.08);
}
.sidebar-item.active::before {
  content: ''; position: absolute; left: 0; top: 20%; height: 60%;
  width: 3px; background: var(--gold); border-radius: 0 2px 2px 0;
}
.sidebar-icon { font-size: 1.125rem; width: 20px; text-align: center; }
```

### 6.5 不推荐组件

| 组件 | 不推荐原因 |
|------|-----------|
| `card-feature`（Landing功能卡） | 带大图标+装饰的卡片，在功能界面中太花哨 |
| `dark-panel`（L13深色CTA面板） | 营销型强转化面板，不适合功能界面 |
| `card-testimonial`（口碑卡片） | 斜体衬线引用风格，不属于功能界面 |
| `btn-cta`（酒红CTA按钮） | 酒红在App中仅用于危险/错误，做主按钮会引发焦虑 |
| `pull-quote`（大型引用块） | 无功能场景使用 |

---

## 7. 特殊注意事项

### 7.1 交互反馈必须即时明确

每一次用户操作都必须有视觉反馈，不允许"点击了但不知道有没有反应"的情况：

| 操作类型 | 反馈方式 | 时效要求 |
|----------|---------|---------|
| 按钮点击 | active状态（按下效果）→ loading → 成功toast/失败alert | <100ms响应 |
| 表单提交 | 按钮loading态 → 成功跳转/提示 或 字段级错误标注 | 提交后立即loading |
| 行内操作（删除/编辑） | 确认弹窗 → 执行 → toast反馈 + 表格行更新 | 操作后toast 3秒内消失 |
| 开关/切换 | 即时切换动画（200ms），必要时toast保存成功 | 即时 |
| 数据加载 | 骨架屏/loading spinner，不用空白页面 | 200ms内显示loading |

### 7.2 表单验证规范

```
表单验证三层次：
1. 即时验证（blur时）：离开输入框即验证格式（邮箱、手机号、必填）
2. 提交验证（submit时）：全表单验证，第一个错误字段自动scroll到视野并focus
3. 后端错误：在对应字段下方显示后端返回的错误信息
```

- **错误样式**：输入框酒红边框 + 下方酒红色12px错误文字 + 可选酒红感叹号图标
- **成功样式**：输入框金色边框（可选）+ 右侧金色对勾图标
- **不使用浏览器默认的alert()弹窗**，统一用toast或alert组件
- **提交按钮在验证通过前**可保持可用（点击后提示错误），或禁用（opacity 0.6）

### 7.3 终端/代码区域规范

- 背景使用墨黑 `#0D1225`，不使用纯黑 `#000`
- 字体使用 JetBra Mono，14px，1.6行高
- 终端绿 `#4ADE80` 用于：
  - 命令提示符（`$`、`>`、`#`）
  - 成功输出信息
  - 语法高亮中的关键字/字符串（可按语法高亮方案扩展）
- 酒红 `#D8315B` 用于错误输出信息
- 灰色 `#6D7487` 用于注释
- 代码块圆角8px，与其他组件统一
- 可加复制按钮（右上角，hover时显示）

### 7.4 深色侧边栏规范

- 使用皇家蓝深色渐变（`#081C4F` → `#0A2463`），不使用纯黑
- 菜单项默认色为 `rgba(255,255,255,0.65)`，选中态纯白
- 选中项左侧有3px金色指示条（`var(--gold)`），这是品牌签名细节
- 侧边栏底部可放用户信息区域，顶部放Logo
- 折叠态（64px宽）只显示图标，hover时显示tooltip
- 侧边栏与内容区之间不加重阴影，用自然的色彩对比分隔

### 7.5 功能优先于装饰

在App场景中，以下元素应避免或极少量使用：

| 避免元素 | 原因 | 替代方案 |
|----------|------|---------|
| 大段装饰性文字 | 占用空间，干扰操作 | 用tooltip/帮助链接 |
| 复杂动画/转场 | 影响操作效率 | 仅用200ms以内的微交互 |
| 彩色渐变背景 | 影响数据可读性 | 用白色/暖米白纯色背景 |
| 装饰性插图/IP形象 | 分散注意力 | 仅在空状态页使用 |
| 衬线字体深入工作区 | 降低信息扫描效率 | 工作区全部Inter |
| 多重阴影/悬浮效果 | 增加视觉噪音 | 卡片用单层轻阴影或仅边框 |

### 7.6 响应式适配

| 断点 | 适配策略 |
|------|---------|
| **桌面端 >1200px** | 侧边栏展开+内容区多列布局 |
| **平板 768-1200px** | 侧边栏可折叠（默认折叠为图标态），内容区双列→单列 |
| **移动端 <768px** | 侧边栏隐藏为抽屉（汉堡菜单触发），表格可横滑，按钮全宽，表单单列 |

移动端特殊处理：
- 所有触摸目标 ≥ 44×44px
- 表格外层包裹 `overflow-x: auto` 容器
- 底部Tab栏替代侧边栏（如果移动端是重要使用场景）
- 弹窗全屏显示（非桌面端居中小弹窗）

### 7.7 加载与空状态

- **加载状态**：使用骨架屏（skeleton）优于spinner，骨架屏形状匹配实际内容布局
- **空状态**：必须有图标+说明文字+操作引导按钮，不放空白页
  ```html
  <div class="empty-state">
    <div class="empty-icon">📋</div>
    <p class="empty-title">暂无数据</p>
    <p class="empty-desc">还没有创建任何内容，点击下方按钮开始</p>
    <button class="btn btn-primary">新建</button>
  </div>
  ```

---

## 8. 场景专属 Checklist

在交付任何App/功能型页面之前，必须通过以下检查：

### P0 — 必须通过（缺一不可，直接影响可用性）

- [ ] **所有交互元素有完整状态**：按钮/链接/输入框有 hover / active / focus / disabled 样式
- [ ] **表单有focus样式**：输入框聚焦时有皇家蓝边框+光晕，错误时有酒红边框+错误提示
- [ ] **功能清晰可用**：用户进入页面3秒内知道"这是什么、我能做什么、该点哪里"
- [ ] **主操作按钮明确**：每个页面/面板有且仅有一个主操作按钮（`btn-primary`皇家蓝）
- [ ] **侧边栏/导航有选中态**：当前页面在导航中有高亮标记
- [ ] **三种品牌色严格为 `#0A2463` / `#F4D35E` / `#D8315B`**
- [ ] **三色语义正确**：皇家蓝=导航/主操作，金色=成功/高亮，酒红=错误/危险
- [ ] **界面80%以上面积为中性色**（暖米白/白/暖灰），品牌色不泛滥
- [ ] **页面大标题/Logo用Playfair Display，其余界面文字一律Inter**
- [ ] **表单验证有品牌化样式**：错误酒红，焦点皇家蓝，成功金色
- [ ] **所有触摸/点击目标 ≥ 44×44px**
- [ ] **响应式适配**：移动端可正常使用（或明确声明仅桌面端）
- [ ] **无浏览器默认样式残留**：按钮、输入框、表格、链接均经过品牌化处理
- [ ] **页面背景为暖米白 `#FDFBF6`**，不使用冷灰或纯白大面积背景

### P1 — 应该通过（影响体验完整度）

- [ ] **有操作反馈toast/alert**：提交、删除、保存等操作后有成功/失败提示
- [ ] **删除/危险操作有二次确认**：弹窗确认，确认按钮用酒红描边
- [ ] **加载状态有反馈**：骨架屏或spinner，不显示空白
- [ ] **空状态有引导**：无数据时显示空状态插图+文字+操作按钮
- [ ] **表格行有hover状态**：鼠标悬停时行背景变浅暖灰
- [ ] **响应式适配移动端**：表格可横滑、按钮全宽、导航抽屉化
- [ ] **终端/代码区域使用深色背景+JetBrains Mono+终端绿点缀**（如有代码展示）
- [ ] **数字使用tabular-nums或等宽字体**：金额/数量右对齐
- [ ] **深色侧边栏使用皇家蓝系+金色指示条**（如有侧边栏）
- [ ] **面包屑导航显示当前位置**（深层级页面）

### P2 — 加分项（提升专业度）

- [ ] **深色模式支持**：提供暗色主题切换（背景用墨黑/深蓝，文字反白）
- [ ] **快捷键提示**：常用操作在tooltip中显示快捷键（⌘S保存、⌘N新建等）
- [ ] **操作可撤销**：删除/修改操作后toast中提供"撤销"选项
- [ ] **骨架屏加载**：首次加载时使用与内容布局匹配的骨架屏
- [ ] **表格列可排序/筛选**：数据表格支持列头点击排序
- [ ] **分页/虚拟滚动**：大数据量时不卡顿
- [ ] **键盘导航支持**：Tab键可遍历所有交互元素，Enter提交
- [ ] **操作历史/时间线**：关键操作有日志记录
- [ ] **自动保存草稿**：表单/编辑器自动保存，防止数据丢失
- [ ] **离线提示**：网络断开时酒红提示条提醒

### 交付前自检三问

1. **新用户能否在无指导下完成核心操作**：如果我是第一次使用，我知道该点哪里、下一步做什么吗？
2. **操作失误能否恢复**：点错了按钮能否撤销？删除了数据能否找回？错误提示是否告诉我怎么改？
3. **长时间使用是否舒适**：颜色是否刺眼？文字是否清晰？信息密度是否让我感到焦虑？

---

## 附录：App页面快速模板骨架

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>控制台 · 飞鸿</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  <style>
    :root {
      --royal: #0A2463; --gold: #F4D35E; --wine: #D8315B;
      --cream: #FDFBF6; --ink: #0D1225;
      --terminal-green: #4ADE80;
      --font-serif: 'Playfair Display', 'Noto Serif SC', Georgia, serif;
      --font-sans: 'Inter', 'Noto Sans SC', -apple-system, sans-serif;
      --font-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
      --r-md: 8px; --r-lg: 12px;
      --sp-2: 0.5rem; --sp-3: 0.75rem; --sp-4: 1rem; --sp-5: 1.5rem; --sp-6: 2rem;
      --shadow-sm: 0 1px 3px rgba(10,36,99,0.06);
      --shadow-md: 0 4px 12px rgba(10,36,99,0.08);
      --sidebar-w: 240px;
      --topbar-h: 56px;
    }
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: var(--font-sans);
      background: var(--cream);
      color: var(--ink);
      line-height: 1.5;
      -webkit-font-smoothing: antialiased;
      font-size: 14px;
    }
    ::selection { background: var(--gold); color: var(--royal); }

    /* Layout */
    .app-layout { display: flex; min-height: 100vh; }

    /* Sidebar */
    .sidebar {
      width: var(--sidebar-w); flex-shrink: 0;
      background: linear-gradient(180deg, #081C4F 0%, var(--royal) 100%);
      color: rgba(255,255,255,0.65);
      display: flex; flex-direction: column;
      position: fixed; top: 0; left: 0; bottom: 0; z-index: 50;
    }
    .sidebar-logo {
      padding: var(--sp-4) var(--sp-5);
      font-family: var(--font-serif); font-size: 1.35rem; font-weight: 700;
      color: #fff; border-bottom: 1px solid rgba(255,255,255,0.08);
    }
    .sidebar-logo span { color: var(--gold); }
    .sidebar-nav { flex: 1; padding: var(--sp-3) 0; overflow-y: auto; }
    .sidebar-item {
      display: flex; align-items: center; gap: var(--sp-3);
      padding: var(--sp-3) var(--sp-5);
      font-size: 0.875rem; color: rgba(255,255,255,0.65);
      text-decoration: none; transition: all 0.2s; position: relative;
    }
    .sidebar-item:hover { background: rgba(255,255,255,0.06); color: #fff; }
    .sidebar-item.active { color: #fff; font-weight: 600; background: rgba(255,255,255,0.08); }
    .sidebar-item.active::before {
      content: ''; position: absolute; left: 0; top: 20%; height: 60%;
      width: 3px; background: var(--gold); border-radius: 0 2px 2px 0;
    }
    .sidebar-icon { font-size: 1.125rem; width: 20px; text-align: center; }

    /* Main */
    .main { flex: 1; margin-left: var(--sidebar-w); display: flex; flex-direction: column; }

    /* Topbar */
    .topbar {
      height: var(--topbar-h); background: #fff;
      border-bottom: 1px solid #F0EAD9;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 var(--sp-6); position: sticky; top: 0; z-index: 40;
    }
    .breadcrumb { font-size: 0.8125rem; color: #6D7487; }
    .breadcrumb span { color: var(--ink); font-weight: 500; }
    .topbar-actions { display: flex; align-items: center; gap: var(--sp-3); }
    .avatar {
      width: 32px; height: 32px; border-radius: 50%;
      background: var(--royal); color: #fff;
      display: flex; align-items: center; justify-content: center;
      font-size: 0.8125rem; font-weight: 600; cursor: pointer;
    }

    /* Content */
    .content { flex: 1; padding: var(--sp-6); }
    .page-header { margin-bottom: var(--sp-6); display: flex; justify-content: space-between; align-items: flex-start; }
    .page-title { font-family: var(--font-serif); font-size: 1.5rem; font-weight: 700; color: var(--ink); margin: 0; }
    .page-desc { font-size: 0.875rem; color: #6D7487; margin-top: var(--sp-2); }

    /* Buttons */
    .btn {
      display: inline-flex; align-items: center; justify-content: center; gap: 0.375rem;
      font-family: var(--font-sans); font-size: 0.875rem; font-weight: 500;
      padding: 0.5rem 1rem; border-radius: var(--r-md); border: none;
      cursor: pointer; text-decoration: none; transition: all 0.2s; white-space: nowrap;
    }
    .btn-primary { background: var(--royal); color: #fff; }
    .btn-primary:hover { background: #081D52; }
    .btn-primary:active { background: #061640; }
    .btn-primary:focus-visible { outline: none; box-shadow: 0 0 0 3px rgba(10,36,99,0.2); }
    .btn-primary:disabled { opacity: 0.5; cursor: not-allowed; }
    .btn-outline { background: transparent; color: var(--royal); border: 1px solid #D4DCF0; }
    .btn-outline:hover { background: #EEF1FA; }
    .btn-danger { background: transparent; color: var(--wine); border: 1px solid #F5C2CE; }
    .btn-danger:hover { background: #FDF0F3; }

    /* Cards */
    .card {
      background: #fff; border: 1px solid #F0EAD9; border-radius: var(--r-lg);
      padding: var(--sp-5);
    }
    .card-title { font-size: 1rem; font-weight: 600; color: var(--ink); margin: 0 0 var(--sp-4); }

    /* Form */
    .form-group { margin-bottom: var(--sp-4); }
    .form-label { display: block; font-size: 0.875rem; font-weight: 500; color: var(--ink); margin-bottom: var(--sp-2); }
    .form-label .required { color: var(--wine); margin-left: 2px; }
    .form-input {
      width: 100%; padding: 0.625rem 0.875rem; font-size: 0.9375rem;
      border: 1px solid #F0EAD9; border-radius: var(--r-md);
      background: #FAFAF7; font-family: var(--font-sans);
      transition: border-color 0.2s, box-shadow 0.2s;
    }
    .form-input:hover { border-color: #D4CCB8; }
    .form-input:focus { outline: none; border-color: var(--royal); box-shadow: 0 0 0 3px rgba(10,36,99,0.12); }
    .form-input.error { border-color: var(--wine); box-shadow: 0 0 0 3px rgba(216,49,91,0.1); }
    .form-input::placeholder { color: #9CA1B3; }
    .form-error { font-size: 0.75rem; color: var(--wine); margin-top: var(--sp-2); }
    .form-help { font-size: 0.75rem; color: #6D7487; margin-top: var(--sp-2); }

    /* Alert */
    .alert {
      display: flex; align-items: flex-start; gap: var(--sp-3);
      padding: var(--sp-4) var(--sp-5); border-radius: var(--r-md);
      border-left: 3px solid; margin-bottom: var(--sp-5);
    }
    .alert-success { background: #FEFCF0; border-color: var(--gold); }
    .alert-error { background: #FDF0F3; border-color: var(--wine); }
    .alert-info { background: #EEF1FA; border-color: var(--royal); }

    /* Tag */
    .tag {
      display: inline-flex; align-items: center;
      font-size: 0.75rem; font-weight: 500;
      padding: 0.125rem 0.5rem; border-radius: 4px;
      border: 1px solid;
    }
    .tag-gold { background: #FEFCF0; color: var(--royal); border-color: #FAEBA3; }

    /* Stats Grid */
    .stats-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: var(--sp-4); margin-bottom: var(--sp-6); }
    .stat-card { background: #fff; border: 1px solid #F0EAD9; border-radius: var(--r-lg); padding: var(--sp-5); }
    .stat-label { font-size: 0.8125rem; color: #6D7487; margin-bottom: var(--sp-2); }
    .stat-value { font-family: var(--font-serif); font-size: 1.75rem; font-weight: 700; color: var(--ink); line-height: 1.1; }
    .stat-value.highlight { color: var(--gold); }
    .stat-change { font-size: 0.75rem; margin-top: var(--sp-2); }
    .stat-change.up { color: var(--gold); }
    .stat-change.down { color: var(--wine); }

    /* Table */
    .table-wrap { background: #fff; border: 1px solid #F0EAD9; border-radius: var(--r-lg); overflow: hidden; }
    .data-table { width: 100%; border-collapse: collapse; }
    .data-table th {
      padding: var(--sp-3) var(--sp-5); font-size: 0.8125rem; font-weight: 600;
      text-align: left; color: #6D7487; background: #FAFAF7;
      border-bottom: 1px solid #F0EAD9;
    }
    .data-table td {
      padding: var(--sp-3) var(--sp-5); font-size: 0.875rem; color: #2C3347;
      border-bottom: 1px solid #F5F2E8;
    }
    .data-table tr:hover td { background: #F8F4EB; }
    .data-table tr:last-child td { border-bottom: none; }
    .table-link { color: var(--royal); text-decoration: none; font-size: 0.8125rem; }
    .table-link:hover { text-decoration: underline; }
    .table-link.danger { color: var(--wine); }

    /* Terminal */
    .terminal {
      background: var(--ink); color: #E2E8F0;
      font-family: var(--font-mono); font-size: 0.875rem; line-height: 1.6;
      padding: var(--sp-4) var(--sp-5); border-radius: var(--r-md);
    }
    .terminal .prompt { color: var(--terminal-green); }
    .terminal .comment { color: #6D7487; }
    .terminal .error-text { color: var(--wine); }

    /* Responsive */
    @media (max-width: 1024px) {
      .stats-grid { grid-template-columns: repeat(2, 1fr); }
    }
    @media (max-width: 768px) {
      .sidebar { transform: translateX(-100%); transition: transform 0.3s; }
      .sidebar.open { transform: translateX(0); }
      .main { margin-left: 0; }
      .stats-grid { grid-template-columns: 1fr; }
      .page-header { flex-direction: column; gap: var(--sp-3); }
      .btn { width: 100%; }
    }
    @media (prefers-reduced-motion: reduce) {
      * { transition: none !important; animation: none !important; }
    }
  </style>
</head>
<body>
  <div class="app-layout">
    <!-- Sidebar -->
    <aside class="sidebar">
      <div class="sidebar-logo">Feihong<span>.</span></div>
      <nav class="sidebar-nav">
        <a href="#" class="sidebar-item active">
          <span class="sidebar-icon">◈</span> 控制台
        </a>
        <a href="#" class="sidebar-item">
          <span class="sidebar-icon">◇</span> 数据
        </a>
        <a href="#" class="sidebar-item">
          <span class="sidebar-icon">◉</span> 用户
        </a>
        <a href="#" class="sidebar-item">
          <span class="sidebar-icon">⚙</span> 设置
        </a>
      </nav>
    </aside>

    <!-- Main -->
    <div class="main">
      <!-- Topbar -->
      <header class="topbar">
        <div class="breadcrumb">首页 / <span>控制台</span></div>
        <div class="topbar-actions">
          <button class="btn btn-outline">导出</button>
          <div class="avatar">F</div>
        </div>
      </header>

      <!-- Content -->
      <main class="content">
        <!-- Page Header -->
        <div class="page-header">
          <div>
            <h1 class="page-title">控制台</h1>
            <p class="page-desc">欢迎回来，这里是你的数据概览</p>
          </div>
          <button class="btn btn-primary">+ 新建</button>
        </div>

        <!-- Alert Example -->
        <div class="alert alert-success">
          <span>✓</span>
          <div>操作成功，数据已保存。</div>
        </div>

        <!-- Stats Cards -->
        <div class="stats-grid">
          <div class="stat-card">
            <div class="stat-label">总用户数</div>
            <div class="stat-value highlight">12,847</div>
            <div class="stat-change up">↑ 12.5% 较上月</div>
          </div>
          <div class="stat-card">
            <div class="stat-label">活跃用户</div>
            <div class="stat-value">8,392</div>
            <div class="stat-change up">↑ 8.2% 较上月</div>
          </div>
          <div class="stat-card">
            <div class="stat-label">转化率</div>
            <div class="stat-value">24.6%</div>
            <div class="stat-change down">↓ 2.1% 较上月</div>
          </div>
          <div class="stat-card">
            <div class="stat-label">收入</div>
            <div class="stat-value">¥89.2K</div>
            <div class="stat-change up">↑ 18.7% 较上月</div>
          </div>
        </div>

        <!-- Form Example -->
        <div class="card" style="max-width:480px;margin-bottom:var(--sp-6);">
          <h3 class="card-title">快捷设置</h3>
          <div class="form-group">
            <label class="form-label">项目名称 <span class="required">*</span></label>
            <input type="text" class="form-input" value="我的项目">
          </div>
          <div class="form-group">
            <label class="form-label">邮箱</label>
            <input type="email" class="form-input error" placeholder="请输入邮箱">
            <div class="form-error">请输入有效的邮箱地址</div>
          </div>
          <button class="btn btn-primary">保存设置</button>
        </div>

        <!-- Table Example -->
        <div class="table-wrap">
          <table class="data-table">
            <thead>
              <tr>
                <th>ID</th><th>名称</th><th>状态</th><th>创建时间</th><th>操作</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td style="font-family:var(--font-mono);">#001</td>
                <td>项目A</td>
                <td><span class="tag tag-gold">已完成</span></td>
                <td style="color:#6D7487;">2026-07-01</td>
                <td><a href="#" class="table-link">编辑</a> · <a href="#" class="table-link danger">删除</a></td>
              </tr>
              <tr>
                <td style="font-family:var(--font-mono);">#002</td>
                <td>项目B</td>
                <td><span class="tag" style="background:#EEF1FA;color:var(--royal);border-color:#D4DCF0;">进行中</span></td>
                <td style="color:#6D7487;">2026-07-05</td>
                <td><a href="#" class="table-link">编辑</a> · <a href="#" class="table-link danger">删除</a></td>
              </tr>
            </tbody>
          </table>
        </div>

        <!-- Terminal Example -->
        <div class="card" style="margin-top:var(--sp-6);">
          <h3 class="card-title">日志输出</h3>
          <div class="terminal">
            <div><span class="prompt">$</span> npm run build</div>
            <div class="comment">// 正在构建项目...</div>
            <div>✓ 编译完成</div>
            <div class="error-text">✗ 发现1个警告：未使用的变量</div>
            <div><span class="prompt">$</span> <span style="color:var(--terminal-green);">构建成功</span></div>
          </div>
        </div>
      </main>
    </div>
  </div>
</body>
</html>
```

---

## 场景定位

App/功能页/仪表盘是以任务完成和功能操作为核心的功能型界面，用于数据看板、管理后台、工具型产品、开发者工具、SaaS产品等用户需要频繁操作和高效完成任务的场景。适用于：数据仪表盘、CMS管理后台、开发者工具、项目管理工具、表单密集型应用、内部工具。不适用于：营销宣传页（用Landing）、内容阅读（用Tutorial）、作品展示（用Portfolio）。核心原则是"功能优先、效率至上"——品牌色克制使用（80%中性色），信息密度高但不混乱，交互反馈即时明确，长时间使用不疲劳。

## 推荐节奏（Section 序列）

App场景的"节奏"不是上下滚动的section，而是固定布局框架下的信息层级和模块组织：

### 方案 A：经典侧边栏+仪表盘型（最常用，数据/管理类App）
1. 顶部Sticky导航栏（面包屑+搜索+用户+操作）
2. 左侧固定深色侧边栏（Logo+导航+金色选中条）
3. 内容区：页面标题+主操作按钮
4. KPI数据卡片行（4个stat-card横排，金色/皇家蓝数字）
5. 图表/数据可视化区（1-2个主要图表）
6. 数据表格（最近项目/活动列表）
7. 次要模块（快捷操作/最近活动/终端日志）

### 方案 B：表单/工具型（设置/编辑器/配置工具）
1. 顶部Sticky导航栏
2. 左侧深色侧边栏（或无侧边栏用顶部Tab）
3. 内容区：页面标题+描述
4. 表单区（分组卡片式form-group）
5. 操作栏（底部sticky或右上固定：保存/取消/提交）
6. 预览/结果区（如有实时预览，左右分栏）

### 方案 C：开发者工具型（终端/日志/代码密集）
1. 顶部Sticky栏（项目名+环境标识+运行状态）
2. 左侧深色侧边栏（文件/模块导航）
3. 主工作区：编辑器/配置区（白底）
4. 底部终端面板（墨黑底+终端绿+酒红错误）
5. 右侧辅助面板（可选：属性/大纲/检查器）
6. 状态栏（底部固定：git分支/错误数/光标位置）

### 方案 D：列表/资源管理型（CRM/项目/内容管理）
1. 顶部Sticky栏
2. 左侧深色侧边栏
3. 内容区：页面标题+主操作按钮
4. 筛选/搜索栏
5. 数据表格（占主要空间，可排序/筛选/分页）
6. 分页器
7. 详情面板（点击行后右侧滑出或弹窗）

## 专属装饰手法（Signature Touches）

App场景装饰极度克制，仅在以下位置使用品牌元素：

- **#06 Terminal Code Block 终端代码块**：开发者工具/日志区域使用墨黑底+JetBrains Mono+终端绿#4ADE80+酒红错误文字，这是App场景最有辨识度的元素
- **#14 Section Marker 金色选中条**：侧边栏当前选中项左侧3px金色指示条（`width:3px; background:var(--gold)`），是App场景最核心的品牌签名
- **#18 Badge & Stamp 徽章标签**：状态标签用金色(成功)/皇家蓝(进行中)/酒红(错误)/灰色(默认)四种语义色
- **#15 Divider 分隔线**：卡片/模块之间用1px极浅暖色线（#F0EAD9）分隔，不用粗线
- **#16 Alert Box 提示框**：操作反馈用左侧3px色条的alert（成功金色/错误酒红/信息皇家蓝）
- **#03 Image Frame（空状态专用）**：空状态页面可用简洁线描风格插图或IP形象，增加人味
- **#20 Numbered Index 等宽数字**：数据表格中的ID、金额、数量用JetBrains Mono等宽数字（`font-variant-numeric: tabular-nums`）
- **金色Logo句号**：侧边栏Logo名字后的金色句号，延续品牌签名
- **#05 Highlight 荧光笔高亮（仅特殊场景）**：搜索结果高亮匹配关键词时可用金色背景标记
- **微交互状态色**：按钮hover/active/focus/disabled状态完整，焦点环用皇家蓝光晕
- **骨架屏**：加载状态用与内容布局匹配的骨架屏，不用旋转spinner占满屏幕
- **Toast反馈**：操作成功/失败用右上角短暂toast，成功金色、错误酒红、信息皇家蓝

## 推荐布局组合

| 布局 | 名称 | 适用位置 | 说明 |
|------|------|----------|------|
| **Sticky Sidebar + Header** | 固定侧边栏+顶栏 | 全局框架（必选） | 左侧240px皇家蓝深蓝侧边栏+顶部56px白色导航栏 |
| **L3** | 三列/四列等分 | KPI数据卡片行 | 3-4个stat-card横排展示关键指标 |
| **L9** | 卡片网格 | 功能入口/模块导航 | 等宽卡片排列功能模块入口 |
| **L7** | 单栏 | 表单/详情页 | 居中单栏表单，max-width 680-800px |
| **L5** | 左右分栏 | 编辑器+预览/列表+详情 | 左侧编辑/列表，右侧预览/详情 |
| **L15** | 双栏对比 | Before/After数据对比 | 不常用，仅在特定对比场景 |
| **L12** | 时间线 | 操作日志/活动流 | 活动记录、操作历史 |
| **L14** | 数据统计条 | 概览页顶部（可选） | 比KPI卡片更紧凑的数据展示 |

## 色彩策略

App场景色彩策略核心：80%面积为中性色（暖米白/白/浅暖灰），品牌色仅用于交互和状态标记，功能界面不搞"视觉冲击"。

**皇家蓝 #0A2463（主色，导航与主操作）**
- 侧边栏深色渐变背景（`linear-gradient(180deg, #081C4F, #0A2463)`）
- 主按钮（btn-primary）背景色
- 链接文字颜色
- 聚焦光晕（`box-shadow: 0 0 0 3px rgba(10,36,99,0.12)`）
- 信息标签/Info提示框左边框
- 页面标题/大标题文字
- 表格表头文字

**复古金 #F4D35E（成功与高亮）**
- 侧边栏选中项左侧3px指示条（最核心的品牌签名）
- 成功状态（alert-success边框、tag-gold、成功toast）
- KPI数据卡片中需要强调的数字（如总收入、总用户数）
- Logo中的金色句号
- 数据上升趋势箭头/数字
- 表单成功验证边框
- 搜索结果关键词高亮
- **金色不用于大面积背景，仅用于指示条、状态色、强调数字**

**酒红 #D8315B（危险与错误）**
- 危险/删除按钮（btn-danger文字+边框）
- 错误状态（alert-error边框、错误提示文字、错误toast）
- 表单验证错误边框和文字
- 终端中的错误输出文字
- 数据下降趋势箭头/数字
- 危险操作二次确认的确认按钮
- **酒红在App中=警告/危险/错误，绝不用于正常主按钮（会引发焦虑）**

**中性色策略（80%面积）**：
- 页面背景：暖米白`#FDFBF6`
- 卡片/内容区背景：白色`#FFFFFF`
- 侧边栏：皇家蓝深色渐变
- 顶栏：白色底+1px底边框
- 边框/分割线：暖灰`#F0EAD9`
- 正文：深墨灰`#2C3347`（不是纯黑）
- 次要文字：中灰`#6D7487`
- 占位符/禁用：浅灰`#9CA1B3`
- 终端/代码区：墨黑`#0D1225`

**终端绿 #4ADE80（特殊色）**：仅用于代码/终端区域的命令提示符和成功输出，不属于品牌三色但为App场景专用。

## 场景禁忌（Don'ts）

1. **酒红作为主按钮颜色**：App中酒红=危险/删除，主按钮用皇家蓝，否则用户会对正常操作产生焦虑
2. **大面积金色/酒红背景**：功能界面中金色和酒红只做状态色和指示色，不用做section背景
3. **装饰性元素过多**：不要放pull-quote、大段Cormorant斜体、花饰Fleuron等营销/内容类装饰
4. **衬线字体进入工作区**：只有Logo和页面大标题可用Playfair Display，所有工作区文字（表单/表格/按钮/导航）必须用Inter
5. **没有hover/active/disabled状态**：功能界面中每个交互元素必须有完整状态，否则用户不知道能否点击
6. **表格没有hover状态**：鼠标悬停行必须有背景色变化，帮助用户定位行
7. **侧边栏用纯黑背景**：必须用皇家蓝深蓝渐变（#081C4F→#0A2463），纯黑与品牌无关且刺眼
8. **操作无反馈**：每次点击必须有即时反馈（loading/toast/状态变化），不能让用户猜测是否成功
9. **弹窗关闭按钮不明显**：必须有明确的X按钮或取消按钮，不能只靠点击遮罩关闭
10. **冷灰色系**：所有灰色必须偏暖（带黄/棕调），禁止使用`#F5F5F5`/`#CCCCCC`/`#999999`等冷灰

## 场景专属Checklist

- [ ] 侧边栏为皇家蓝深蓝渐变（非纯黑），选中项有3px金色左侧指示条
- [ ] 主按钮为皇家蓝（非酒红），删除/危险操作为酒红描边按钮
- [ ] 所有交互元素有完整状态：hover/active/focus-visible/disabled/loading
- [ ] 表单focus时有皇家蓝光晕（box-shadow 3px），错误时有酒红边框+错误文字
- [ ] 页面背景为暖米白`#FDFBF6`，卡片白底+1px暖灰边框`#F0EAD9`
- [ ] 表格行hover时背景变为`#F8F4EB`，表头用`#FAFAF7`
- [ ] 终端/代码区墨黑底`#0D1225`+JetBrains Mono+终端绿`#4ADE80`+酒红错误
- [ ] 所有状态标签语义正确：金色=成功/完成，皇家蓝=信息/进行中，酒红=错误/危险，灰色=默认
- [ ] 数字用等宽字体（tabular-nums或JetBrains Mono），金额右对齐
- [ ] 顶部导航栏sticky固定，面包屑显示当前位置
- [ ] 删除/危险操作有二次确认弹窗，确认按钮用酒红
- [ ] 操作后有toast反馈（成功金色/错误酒红/信息皇家蓝），3秒内自动消失
- [ ] 空状态有图标+说明文字+操作引导按钮，不是空白页
- [ ] 加载状态用骨架屏（形状匹配内容布局），不是空白或全屏spinner
- [ ] 所有触摸/点击目标≥44px
- [ ] 移动端侧边栏变抽屉（hamburger触发），表格可横滑，按钮全宽
- [ ] 选中文本背景为金色，无bounce/弹性/无限循环动画
- [ ] 工作区文字全部Inter，仅Logo和页面标题用Playfair Display
- [ ] 品牌色面积控制在20%以内，80%为暖色中性色

---

*Scene: App v1.0 · Feihong Design System*
*基于 DNA.md v2.0 · 最后更新：2026-07-08*
