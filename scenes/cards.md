# Feihong Design System · Scene: Cards (小红书图文卡片)
# 飞鸿品牌设计系统 · 场景规范：图文卡片 / 小红书场景

> 本规范定义飞鸿品牌设计系统在「小红书图文卡片 / 社交分享卡片 / 竖版分页图」场景中的具体应用方式。
> 所有规则建立在 `DNA.md`、`components/14-layouts.md`、`components/` 基础之上，场景专属规则以本文件为准。

---

## 1. 场景定义

### 适用内容形态

小红书图文卡片场景适用于以下内容形态：

| 类型 | 说明 | 典型页数 |
|------|------|----------|
| **小红书图文笔记** | 3:4 竖版分页图，小红书 feed 流展示 | 6-9 页 |
| **社交卡片分享** | 微信朋友圈/社群分享的竖版知识卡片 | 1-多页 |
| **文章转卡片** | 将长文/教程拆分为竖版卡片分页阅读 | 5-10 页 |
| **竖版信息图** | 单页或多页竖版知识图解/清单卡片 | 1-多页 |

### 核心尺寸约束

| 参数 | 规范值 | 说明 |
|------|--------|------|
| **画布比例** | **3:4 竖版** | 小红书最佳展示比例 |
| **画布尺寸** | **1080 × 1440 px** | 导出图片的标准尺寸 |
| **CSS 模拟尺寸** | `width: 540px; height: 720px;` (0.5x) 或 `1080px × 1440px` | HTML 开发时用缩放预览 |
| **导出格式** | PNG / JPG | 通过 html2canvas 导出 |
| **分页结构** | 每页一个独立 `div.cards-page` | 支持逐页导出 |

### 场景核心气质

- **一眼抓人**：封面页必须在小红书 feed 流中脱颖而出，0.5 秒内抓住注意力
- **大字可读**：手机端单手持握阅读，字号必须足够大，不眯眼
- **节奏明快**：每页只讲一个核心点，信息不堆砌，翻页有新鲜感
- **品质感**：衬线标题+金色细节传递高级感，不廉价不模板

### 场景核心约束

- **3:4 竖版比例，1080×1440px**，不可变形
- **白底/浅底为主**，不使用深色背景（影响小红书 feed 流吸引力和缩略图识别度）
- **字号要大**：手机阅读友好，标题 ≥ 36px，正文 ≥ 20px
- **每页排版手法必须不同**，避免千篇一律
- **支持 html2canvas 导出为图片**，需确保字体加载完毕后再导出
- **不使用 hover / 复杂交互**，最终产物是静态图片

---

## 2. 典型页面结构

小红书图文卡片采用 **封面页 → 内容页（多页）→ 金句页 → 结尾页** 的四阶段分页结构：

```
┌─────────────────┐
│  ① 封面页        │ ← 大字标题 + 标签 + 视觉冲击
│  (Cover)        │
├─────────────────┤
│  ② 内容页 ×N    │ ← 图文混排，每页一个核心点
│  (Content)      │    每页排版手法不同
├─────────────────┤
│  ③ 金句页        │ ← 大字居中 + 金色引号，情绪高点
│  (Pull Quote)   │
├─────────────────┤
│  ④ 结尾页        │ ← CTA / 联系方式 / 品牌标识
│  (CTA/End)      │
└─────────────────┘
```

### 各页功能说明

| 页码类型 | 功能 | 核心元素 | 排版手法 |
|----------|------|----------|----------|
| **封面页** | 吸引点击，传达主题 | 大标题(衬线) + 标签(badge) + 装饰元素 | 大标题居中或偏左，强视觉焦点 |
| **内容页** | 传递核心信息 | 小标题 + 正文/列表 + 配图/图标 | 交替使用上图下文/左图右文/全幅图/要点列表 |
| **金句页** | 制造情绪高点和记忆点 | 超大金句文字 + 金色引号 | 大字居中，极简单页，留足呼吸空间 |
| **结尾页** | 引导行动，建立品牌记忆 | CTA 文案 + 酒红按钮 + 联系方式/二维码 | 简洁有力，品牌标识小水印 |

### 页数建议

- **最低 4 页**：封面 + 1 内容 + 金句 + 结尾
- **推荐 6-8 页**：封面 + 3-5 内容页（含不同排版）+ 金句 + 结尾
- **最多不超过 10 页**：避免信息过载，小红书用户翻页耐心有限

---

## 3. 色彩使用指南

小红书卡片场景遵循品牌 55-30-15 色彩比例，但因白底为主，色彩使用方式有特殊约束：

### 3.1 背景色规则（最高优先级约束）

> **铁律：卡片背景以白色/暖米白为主，禁止使用深色背景。**

| 背景类型 | 色值 | 使用场景 |
|----------|------|----------|
| **卡片主背景** | `#FFFFFF`（纯白）或 `#FDFBF6`（暖米白） | 所有页面默认背景，白底在小红书 feed 流中最醒目 |
| **内容块背景** | `#FDFBF6`（暖米白）或 `#F0F4FA`（极浅蓝） | 卡片内的引用块、要点列表区域 |
| **深色背景** | **禁止使用** | 小红书深色模式是系统级，卡片本身始终为浅色 |

**为什么不能用深色背景？**
- 小红书 feed 流以白色/浅色为主，深色卡片缩略图显得暗沉，点击率低
- 手机端在明亮环境下深色卡片阅读体验差
- 品牌色在白底上对比度最佳（皇家蓝白底对比度 > 12:1）

### 3.2 皇家蓝 `#0A2463`（55%）— 标题与重点

| 用途 | 具体应用 | 备注 |
|------|----------|------|
| **标题文字** | 封面页大标题、内容页小标题 | 衬线字体，皇家蓝色 |
| **重点文字** | 正文中需要强调的关键词 | 可加粗 + 皇家蓝色 |
| **装饰元素** | 页码指示、小装饰线、品牌Logo | 克制使用，不抢标题焦点 |
| **分隔线** | 内容页的细线分隔 | 1px 皇家蓝，透明度 0.15 |

### 3.3 复古金 `#F4D35E`（30%）— 装饰与签名

| 用途 | 具体应用 | 备注 |
|------|----------|------|
| **装饰线** | 封面标题下方金色短线、内容分隔线 | 品牌签名细节 |
| **标签/徽章** | 分类标签(badge)的金色背景 | 金色底+皇家蓝字 |
| **金色圆点** | 要点列表的金色圆点标记 | 直径 10-12px（比网页版大，手机可见） |
| **引号装饰** | 金句页的大号金色衬线引号 | 80-120px 金色引号 |
| **装饰色块** | 页码旁边的金色小方块/圆点 | 小面积点缀 |
| **金色文字** | **禁止在白底上用金色做正文** | 对比度不足！仅在深色块内可用 |

> **注意**：金色 `#F4D35E` 在白底上对比度不足，**不能用作正文文字色**。白底上需要金色文字时，使用深金色阶 `#B8951F`（金色700）。

### 3.4 酒红 `#D8315B`（15%）— 强调与CTA

| 用途 | 具体应用 | 备注 |
|------|----------|------|
| **CTA 按钮** | 结尾页的行动按钮（btn-cta） | 酒红底+白字，最醒目的行动焦点 |
| **重点强调** | 正文中的核心关键词/数字 | 可加粗+酒红色，每页不超过2处 |
| **标签强调** | "重点"/"必看"等强调标签 | 酒红底+白字 badge |
| **装饰点缀** | 极少量的酒红色小装饰 | 一个小圆点或短线，制造色彩节奏 |

### 3.5 文字色规范

| 文字类型 | 色值 | 说明 |
|----------|------|------|
| **标题** | `#0A2463`（皇家蓝） | 衬线大标题 |
| **正文** | `#0D1225`（墨黑）或 `#3D4358`（正文灰） | 保证可读性 |
| **辅助说明** | `#6B7288`（辅助灰） | 小字说明、时间、来源 |
| **金色文字** | `#B8951F`（深金，白底）/ `#F4D35E`（深色块上） | 白底必须用深金 |

---

## 4. 排版规范

### 4.1 字号规范（手机阅读优先）

> **核心原则：字号要大！手机上不眯眼！** 卡片在手机屏幕上宽度只有约 360px，字号必须比网页大得多。

| 元素 | 字号（1080px画布） | 字号（CSS模拟 540px） | 字体 | 行高 | 字重 |
|------|-------------------|----------------------|------|------|------|
| **封面主标题** | 64-80px | 32-40px | Playfair Display / Noto Serif SC | 1.1-1.2 | 700/900 |
| **内容页标题** | 40-48px | 20-24px | Playfair Display / Noto Serif SC | 1.3 | 700 |
| **金句大字** | 56-72px | 28-36px | Cormorant Garamond italic / Noto Serif SC | 1.4 | 400/600 italic |
| **正文** | **≥ 28px** | **≥ 14px**（对应28px@1080）→ 实际建议 ≥ 20px CSS | Inter / Noto Sans SC | **1.6-1.8** | 400 |
| **列表项** | 28-32px | 14-16px | Inter / Noto Sans SC | 1.7 | 400 |
| **标签/徽章** | 20-24px | 10-12px | Inter / Noto Sans SC | 1.4 | 500/600 |
| **辅助小字** | 20-24px | 10-12px | Inter / Noto Sans SC | 1.5 | 400 |
| **页码** | 18-20px | 9-10px | Inter / JetBrains Mono | 1 | 400 |

> **换算关系**：html2canvas 导出时如果画布是 540×720 CSS像素，导出 scale: 2 得到 1080×1440 图片。字号按 540px 宽设置即可。

### 4.2 间距与边距

| 参数 | 规范值（CSS 540px画布） | 1080px导出 |
|------|------------------------|-----------|
| **页面外边距** | 40-48px（左右） | 80-96px |
| **标题下方间距** | 20-24px | 40-48px |
| **段落间距** | 16-20px | 32-40px |
| **列表项间距** | 12-16px | 24-32px |
| **元素组间距** | 32-40px | 64-80px |
| **行距（正文）** | **1.6-1.8** | 同左 |
| **行距（标题）** | 1.1-1.3 | 同左 |

### 4.3 字体策略

| 用途 | 字体栈 | 说明 |
|------|--------|------|
| **标题（中英混排）** | `'Playfair Display', 'Noto Serif SC', 'Source Han Serif SC', 'Songti SC', serif` | 衬线标题，传递品质感 |
| **金句/引言** | `'Cormorant Garamond', 'Noto Serif SC', 'Source Han Serif SC', serif` | 衬线斜体，有人文温度 |
| **正文（中英混排）** | `'Inter', 'Noto Sans SC', 'PingFang SC', 'Microsoft YaHei', sans-serif` | 无衬线正文，清晰易读 |
| **数字/标签** | `'Inter', 'JetBrains Mono', sans-serif` | 数字用等宽或Inter |

> **字体加载注意**：使用 Google Fonts 时，必须等待字体加载完毕（`document.fonts.ready`）再调用 html2canvas，否则导出图片字体会回退到系统字体。

### 4.4 排版铁律

1. **每页只讲一个核心点**：信息精简，不堆砌。一页说不清就拆成两页
2. **每页排版手法必须不同**：不能所有页都是上图下文，必须交替变换
3. **衬线标题 + 无衬线正文**：严格混搭，不能全用一种字体
4. **留白要充足**：四周留白 ≥ 40px（CSS），内容不要贴边
5. **文字不压图片重要区域**：图片叠加文字时，加半透明遮罩或选纯色区域
6. **中英文混排加空格**：遵循中文排版规范
7. **对齐有纪律**：同一区域内文字对齐方式统一，不随意居中/左切

---

## 5. 推荐布局（每页不同排版手法）

### 5.1 封面页布局

#### 封面-A：大标题居中（经典款）

```
┌──────────────────────┐
│                      │ ← 48px 留白
│     [badge 标签]     │
│                      │
│   大标题第一行        │
│   大标题第二行        │ ← Playfair 衬线 700
│   大标题第三行        │
│                      │
│   ─── 金色短线 ───    │ ← 60px 金色装饰线
│                      │
│   副标题/一句话说明    │
│                      │
│                      │
│              页码 ●  │
└──────────────────────┘
```
- 标题居中，皇家蓝衬线大字
- 顶部可有小标签（badge-gold）
- 标题下方金色短线装饰
- 底部可加极小号品牌水印

#### 封面-B：大标题偏左（杂志款）

```
┌──────────────────────┐
│                      │
│ [badge]              │
│                      │
│ 大标题第一行          │ ← 左对齐，大字号
│ 大标题第二行          │
│ 大标题第三行          │
│ ──金色线──            │ ← 左对齐金色短线
│                      │
│ 副标题说明文字        │ ← 左对齐
│                      │
│               ● 页码  │
└──────────────────────┘
```
- 标题左对齐，制造杂志编辑感
- 右侧可留空或加装饰数字/图案
- 金色线从标题下方开始，长度约标题宽度的1/3

### 5.2 内容页布局（必须交替使用！）

#### 内容-A：上图下文

```
┌──────────────────────┐
│  ┌────────────────┐  │
│  │                │  │
│  │     配图       │  │ ← 图片宽度约 80%，圆角 8-12px
│  │                │  │
│  └────────────────┘  │
│                      │
│  ■ 小标题             │ ← 皇家蓝衬线，金色圆点前缀
│                      │
│  正文内容第一行...     │
│  正文内容第二行...     │ ← 墨黑/深灰，Inter 无衬线
│  正文内容第三行...     │
└──────────────────────┘
```
- 图片在上，文字在下
- 图片宽度约为卡片宽度的 75-85%，居中或左对齐
- 图片下方是小标题+正文

#### 内容-B：左图右文

```
┌──────────────────────┐
│                      │
│ ┌──────┐ 小标题      │
│ │      │             │
│ │ 配图 │ 正文第一行   │
│ │      │ 正文第二行   │
│ │      │ 正文第三行   │
│ └──────┘             │
│                      │
│ ● 要点一             │
│ ● 要点二             │
└──────────────────────┘
```
- 左侧图片/图标（约 40% 宽度），右侧文字
- 适合产品展示、人物介绍、对比说明
- 右图左文也可作为变换（交替使用）

#### 内容-C：全幅图+文字叠加

```
┌──────────────────────┐
│┌────────────────────┐│
││                    ││
││   (半透明遮罩)      ││ ← 图片全幅 bleeding
││                    ││    叠加渐变遮罩
││   小标题            ││    从上到下 透明→深色
││                    ││
││   正文文字叠加      ││    或从下到上
││   在图片上          ││
││                    ││
│└────────────────────┘│
└──────────────────────┘
```
- 图片全幅（bleed 到边缘或留 24px 边距）
- 叠加半透明黑色/蓝色渐变遮罩（opacity 0.4-0.6）保证文字可读
- 文字为白色或浅色，放在图片暗部区域
- **注意**：这类页面不要连续使用，节奏上间隔安排

#### 内容-D：要点列表（无图）

```
┌──────────────────────┐
│                      │
│ ■ 核心要点标题        │ ← 皇家蓝衬线
│ ────金色线────        │
│                      │
│ ● 第一个要点内容      │
│   详细说明文字...      │ ← 金色圆点列表
│                      │
│ ● 第二个要点内容      │
│   详细说明文字...      │
│                      │
│ ● 第三个要点内容      │
│   详细说明文字...      │
│                      │
└──────────────────────┘
```
- 纯文字要点列表页，无配图
- 使用金色圆点列表（gold-dot list）
- 适合清单、步骤、方法论总结
- 要点之间间距宽松，不拥挤

#### 内容-E：数字/数据突出

```
┌──────────────────────┐
│                      │
│      80%             │ ← 超大皇家蓝数字（Playfair）
│    的人不知道          │
│                      │
│ ────金色线────        │
│                      │
│ 正文解释这个数据       │
│ 的含义和来源...        │
│                      │
│ [badge 数据来源]      │
└──────────────────────┘
```
- 一个超大数字/百分比作为视觉焦点
- 数字用 Playfair Display 衬线，60-80px
- 下方简短解释
- 适合数据类、统计类内容

### 5.3 金句页布局

```
┌──────────────────────┐
│                      │
│                      │ ← 大量留白
│     "                │ ← 80-120px 金色衬线引号
│                      │
│   金句文字第一行      │
│   金句文字第二行      │ ← Cormorant Garamond italic
│   金句文字第三行      │    或 Noto Serif SC 斜体
│                      │
│           —— 出处    │
│                      │
│                      │
│              ● 页码  │
└──────────────────────┘
```
- 极简单页，大量留白
- 金色大号引号装饰（开口方向朝文字）
- 金句文字居中，Cormorant Garamond italic 或中文衬线斜体
- 字号大（56-72px @1080），行距宽松（1.4）
- 出处/署名小字在右下
- **金句页是情绪高点**，文字必须精炼有力量

### 5.4 结尾页布局

```
┌──────────────────────┐
│                      │
│   关注/行动引导标题    │ ← 皇家蓝衬线
│                      │
│   ┌──────────────┐   │
│   │  CTA 按钮     │   │ ← 酒红背景+白字
│   │  立即关注/咨询 │   │    圆角 8px
│   └──────────────┘   │
│                      │
│   微信/小红书/联系方式 │
│   （可用二维码占位）   │
│                      │
│   [Logo/品牌名]       │ ← 小水印，底部居中
└──────────────────────┘
```
- CTA 按钮用酒红色，是整个卡片组中唯一的酒红大面积色块
- 联系方式简洁清晰
- 底部可有极小号品牌标识水印
- 不堆砌信息，简洁有力收尾

---

## 6. 组件选用

### 6.1 必用组件（每张卡片组必须包含）

| 组件 | 组件名 | 使用页 | 说明 |
|------|--------|--------|------|
| **金句引用块** | `pull-quote` | 金句页 | 大字居中+金色引号，Cormorant italic |
| **金色圆点列表** | `gold-dot-list` | 内容页 | 要点列举，金色圆点直径 10-12px |
| **标签徽章** | `badge` | 封面+内容页 | 分类标签、强调标签 |
| **CTA 按钮** | `btn-cta` | 结尾页 | 酒红底+白字，卡片组唯一酒红大面积色块 |

### 6.2 推荐组件（按需使用）

| 组件 | 使用场景 |
|------|----------|
| `gold-divider`（金色分隔线） | 标题下方、段落之间的装饰线 |
| `number-highlight`（数字突出） | 数据页的超大数字展示 |
| `quote-inline`（行内金句） | 内容页中的小引用，不单独成页 |
| `icon-label`（图标标签） | 带小图标的标签/特性说明 |
| `watermark`（品牌水印） | 每页右下角极小品牌名/Logo |

### 6.3 不使用/不推荐

| 组件/效果 | 原因 |
|-----------|------|
| **hover 效果** | 最终导出为图片，hover 无效 |
| **复杂动画/JS 交互** | 静态图片不需要交互 |
| **深色背景** | 影响 feed 流缩略图吸引力 |
| **渐变文字（background-clip: text）** | html2canvas 对渐变文字支持不好 |
| **backdrop-filter 毛玻璃** | html2canvas 不支持 |
| **固定定位 position: fixed** | 导出时定位异常 |
| **外部图片URL（未CORS）** | html2canvas 导出会因跨域失败，图片需用base64或同源 |
| **web字体未加载就导出** | 字体会回退，必须等待 fonts.ready |

---

## 7. 特殊注意事项

### 7.1 html2canvas 导出功能

每张卡片组 HTML 页面必须包含导出按钮，使用 html2canvas 将每页 `div.cards-page` 导出为图片：

**必须引入 html2canvas**：
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
```

**关键注意事项**：

1. **等待字体加载完毕**再导出：
```javascript
async function exportAllPages() {
  await document.fonts.ready; // 等待所有字体加载
  // 再开始导出
}
```

2. **使用 scale: 2 保证清晰度**：
```javascript
html2canvas(pageElement, {
  scale: 2,           // 540px → 1080px 导出
  useCORS: true,      // 允许跨域图片
  backgroundColor: '#FFFFFF',
  logging: false
});
```

3. **每页使用独立的 `div.cards-page` 容器**：
```html
<div class="cards-container">
  <div class="cards-page" id="page-1">...</div>
  <div class="cards-page" id="page-2">...</div>
  <div class="cards-page" id="page-3">...</div>
</div>
```

4. **卡片页面 CSS 必须固定尺寸**：
```css
.cards-page {
  width: 540px;
  height: 720px;
  background: #FFFFFF;
  position: relative;
  overflow: hidden;
  flex-shrink: 0;
  /* 不使用 transform/margin 导致偏移 */
}
```

5. **图片跨域处理**：使用本地图片或 base64 编码图片，或设置 `useCORS: true` 并确保图片服务器有 CORS 头。

### 7.2 字体加载保障

由于导出图片对字体要求极高，必须做好字体加载保障：

1. **使用 `<link rel="preload">` 预加载关键字体**
2. **使用 `document.fonts.ready` 等待所有字体加载完成**
3. **设置字体加载超时回退**：如果 Google Fonts 加载失败（如国内网络），使用系统字体回退栈（`font-family` 中必须包含系统字体）
4. **导出前可显示"字体加载中"提示**，加载完毕再显示导出按钮
5. **中文字体 Noto Serif SC / Noto Sans SC 文件较大**，考虑使用 `font-display: swap` 并在导出前确认加载

### 7.3 每页排版必须不同

这是小红书卡片场景的核心质量门槛：

- 封面页：封面布局（A居中或B偏左）
- 第1内容页：上图下文
- 第2内容页：左图右文（或右图左文）
- 第3内容页：要点列表
- 第4内容页：全幅图+文字叠加
- ...（更多内容页继续交替）
- 金句页：大字居中
- 结尾页：CTA

**禁止**：
- 所有内容页都用同一种布局
- 连续两页都是全幅图+文字叠加
- 连续两页都是纯文字列表

### 7.4 预览模式

开发时建议提供两种预览模式：
1. **单页预览**：显示一页 540×720 的卡片，方便调试
2. **分页预览**：所有页面横向排列或纵向排列，模拟小红书滑动
3. **导出按钮**：固定在页面右上角，可逐页导出或一键导出全部

### 7.5 其他注意事项

1. **页码指示**：每页右下角或底部居中显示 `1/8` 格式页码，用 Inter/JetBrains Mono，辅助灰色
2. **品牌水印**：可选，每页右下角极小字号品牌名 "Feihong" 或 "飞鸿"，透明度 0.3
3. **安全区域**：内容距离边缘至少 40px（CSS 540px画布），避免被小红书UI遮挡
4. **不使用圆角卡片**：导出为矩形图片即可，小红书 App 内会自动处理
5. **文件大小**：导出 JPG 质量 0.85 即可，单张图片控制在 500KB 以内利于上传

---

## 8. 场景专属 Checklist

在交付任何小红书图文卡片之前，必须通过以下检查：

### P0 — 必须通过（缺一不可）

- [ ] **画布比例为 3:4（1080×1440px 或 CSS 540×720px + scale:2导出）**
- [ ] **正文字号 ≥ 20px（CSS）/ 28px（@1080导出）**，手机上不眯眼
- [ ] **每页排版手法不同**，不千篇一律
- [ ] **html2canvas 导出功能正常工作**，导出图片清晰无字体回退
- [ ] **背景为白色/暖米白浅色底**，不使用深色背景
- [ ] **三种品牌色严格为 `#0A2463` / `#F4D35E` / `#D8315B`**
- [ ] **衬线标题（Playfair Display/Noto Serif SC）+ 无衬线正文（Inter/Noto Sans SC）** 混搭
- [ ] **行距 1.6-1.8（正文）**，阅读舒适
- [ ] **每页独立 `div.cards-page`** 容器，固定尺寸 540×720
- [ ] **字体加载完毕后再导出**（`document.fonts.ready`）
- [ ] **金色不在白底上用做正文文字**（对比度不足时用深金 `#B8951F`）
- [ ] **每页信息精简**，一个核心点/页，不堆砌
- [ ] **四周留白 ≥ 40px**（CSS），内容不贴边

### P1 — 应该通过（尽量满足）

- [ ] **封面页有强吸引力**：大标题+标签+视觉焦点，feed 流中能抓人
- [ ] **金句页存在**：至少有一页大字居中金句，金色引号装饰
- [ ] **结尾页有明确 CTA**：酒红按钮引导关注/行动
- [ ] **内容页交替使用不同布局**：上图下文/左图右文/全幅图/列表交替
- [ ] **金色装饰线/圆点/标签**成为品牌签名细节
- [ ] **封面有分类标签 badge**（金色底+皇家蓝字）
- [ ] **行距宽松不拥挤**，信息层次清晰
- [ ] **酒红色仅用于 CTA 按钮和极少数强调**，不大面积使用
- [ ] **标题使用皇家蓝 `#0A2463`**，正文使用墨黑/深灰

### P2 — 加分项（锦上添花）

- [ ] **页码指示**：每页显示 "X/N" 页码
- [ ] **品牌标识小水印**：每页右下角极小号品牌名，低透明度
- [ ] **有一页超大数字/数据突出页**，制造视觉冲击
- [ ] **图片风格统一**：色调偏暖、有质感、非AI假图
- [ ] **中英文混排规范**：中英文之间有空格
- [ ] **可一键导出全部页面为 ZIP**
- [ ] **国内网络环境下字体能正常加载**（有系统字体回退或使用国内CDN）

---

## 附录：html2canvas 导出按钮 JS 代码示例

```javascript
// 等待字体加载 + 逐页导出
async function exportCards() {
  const btn = document.getElementById('export-btn');
  btn.textContent = '字体加载中...';
  btn.disabled = true;

  try {
    // 1. 等待所有字体加载完毕
    await document.fonts.ready;
    btn.textContent = '导出中...';

    // 2. 获取所有页面
    const pages = document.querySelectorAll('.cards-page');
    const zip = new JSZip(); // 可选：使用 JSZip 打包

    for (let i = 0; i < pages.length; i++) {
      const page = pages[i];
      const pageNum = String(i + 1).padStart(2, '0');

      // 3. 逐页截图
      const canvas = await html2canvas(page, {
        scale: 2,                    // 540→1080, 720→1440
        useCORS: true,               // 允许跨域图片
        allowTaint: false,           // 不允许污染画布
        backgroundColor: '#FFFFFF',  // 白底
        logging: false,
        onclone: (clonedDoc) => {
          // 克隆文档中可做特殊处理
          const clonedPage = clonedDoc.getElementById(page.id);
          if (clonedPage) {
            clonedPage.style.transform = 'none';
            clonedPage.style.margin = '0';
          }
        }
      });

      // 4. 下载单张
      const link = document.createElement('a');
      link.download = `page-${pageNum}.png`;
      link.href = canvas.toDataURL('image/png');
      link.click();

      // 等待一下避免浏览器阻止多次下载
      await new Promise(r => setTimeout(r, 300));
    }

    btn.textContent = '导出完成！';
    setTimeout(() => {
      btn.textContent = '导出全部图片';
      btn.disabled = false;
    }, 2000);

  } catch (err) {
    console.error('导出失败:', err);
    btn.textContent = '导出失败，请重试';
    btn.disabled = false;
  }
}

// 绑定按钮事件
document.getElementById('export-btn').addEventListener('click', exportCards);
```

### HTML 骨架示例

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>小红书卡片 · 飞鸿</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Cormorant+Garamond:ital,wght@0,400;1,400;1,600&family=Inter:wght@400;500;600;700&family=Noto+Serif+SC:wght@400;700&family=Noto+Sans+SC:wght@400;500;700&display=swap" rel="stylesheet">
  <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
  <style>
    :root {
      --royal: #0A2463; --gold: #F4D35E; --wine: #D8315B;
      --cream: #FDFBF6; --ink: #0D1225; --body: #3D4358;
      --muted: #6B7288; --gold-dark: #B8951F;
      --font-serif: 'Playfair Display', 'Noto Serif SC', 'Songti SC', serif;
      --font-sans: 'Inter', 'Noto Sans SC', 'PingFang SC', 'Microsoft YaHei', sans-serif;
      --font-italic: 'Cormorant Garamond', 'Noto Serif SC', serif;
    }
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: var(--font-sans);
      background: #E8EAF0;
      padding: 2rem;
      display: flex; flex-direction: column; align-items: center; gap: 2rem;
    }
    .export-bar {
      position: fixed; top: 1rem; right: 1rem; z-index: 100;
    }
    #export-btn {
      padding: 0.75rem 1.5rem; background: var(--royal); color: #fff;
      border: none; border-radius: 8px; font-size: 14px; cursor: pointer;
      font-family: var(--font-sans); font-weight: 500;
    }
    #export-btn:hover { background: var(--wine); }
    #export-btn:disabled { opacity: 0.6; cursor: wait; }
    .cards-container { display: flex; flex-direction: column; gap: 1.5rem; }
    .cards-page {
      width: 540px; height: 720px; background: #fff;
      position: relative; overflow: hidden; flex-shrink: 0;
      padding: 48px 44px; display: flex; flex-direction: column;
    }
    /* 封面页 */
    .page-cover { justify-content: center; align-items: center; text-align: center; }
    .page-cover .badge {
      display: inline-block; background: var(--gold); color: var(--royal);
      font-size: 11px; font-weight: 600; padding: 4px 14px;
      border-radius: 4px; letter-spacing: 0.1em; text-transform: uppercase;
      margin-bottom: 24px;
    }
    .page-cover h1 {
      font-family: var(--font-serif); font-size: 38px; font-weight: 900;
      color: var(--royal); line-height: 1.15; margin-bottom: 20px;
    }
    .page-cover .gold-line {
      width: 50px; height: 2px; background: var(--gold); margin: 0 auto 20px;
    }
    .page-cover .subtitle {
      font-size: 14px; color: var(--muted); line-height: 1.6;
    }
    .page-number {
      position: absolute; bottom: 24px; right: 44px;
      font-size: 10px; color: var(--muted); font-family: 'Inter', monospace;
    }
    /* 金句页 */
    .page-quote { justify-content: center; align-items: center; text-align: center; }
    .page-quote .q-mark {
      font-family: var(--font-serif); font-size: 80px; color: var(--gold);
      line-height: 0.8; margin-bottom: 16px;
    }
    .page-quote blockquote {
      font-family: var(--font-italic); font-size: 30px; font-style: italic;
      color: var(--royal); line-height: 1.4; font-weight: 400;
    }
    .page-quote cite {
      display: block; margin-top: 20px; font-size: 12px;
      color: var(--muted); font-style: normal; font-family: var(--font-sans);
    }
    /* CTA按钮 */
    .btn-cta {
      display: inline-block; background: var(--wine); color: #fff;
      font-family: var(--font-sans); font-size: 15px; font-weight: 500;
      padding: 14px 36px; border-radius: 8px; text-decoration: none;
      box-shadow: 0 4px 16px rgba(216,49,91,0.25);
    }
    /* 金色圆点列表 */
    .gold-dot-list { list-style: none; padding: 0; }
    .gold-dot-list li {
      font-size: 15px; line-height: 1.7; color: var(--body);
      padding-left: 22px; position: relative; margin-bottom: 14px;
    }
    .gold-dot-list li::before {
      content: ''; position: absolute; left: 0; top: 9px;
      width: 10px; height: 10px; background: var(--gold); border-radius: 50%;
    }
  </style>
</head>
<body>
  <div class="export-bar">
    <button id="export-btn">导出全部图片</button>
  </div>

  <div class="cards-container">
    <!-- 封面页 -->
    <div class="cards-page page-cover" id="page-1">
      <span class="badge">干货分享</span>
      <h1>卡片主标题<br>第二行文字</h1>
      <div class="gold-line"></div>
      <p class="subtitle">一句话说明这组卡片的核心价值</p>
      <span class="page-number">1 / 6</span>
    </div>

    <!-- 内容页-要点列表 -->
    <div class="cards-page" id="page-2">
      <h2 style="font-family:var(--font-serif);font-size:22px;color:var(--royal);margin-bottom:8px;">核心要点</h2>
      <div style="width:40px;height:2px;background:var(--gold);margin-bottom:28px;"></div>
      <ul class="gold-dot-list">
        <li>第一个要点：详细说明文字...</li>
        <li>第二个要点：详细说明文字...</li>
        <li>第三个要点：详细说明文字...</li>
      </ul>
      <span class="page-number">2 / 6</span>
    </div>

    <!-- 金句页 -->
    <div class="cards-page page-quote" id="page-3">
      <span class="q-mark">&ldquo;</span>
      <blockquote>真正的品质<br>藏在看不见的细节里</blockquote>
      <cite>—— 飞鸿</cite>
      <span class="page-number">3 / 6</span>
    </div>

    <!-- 结尾页 -->
    <div class="cards-page" style="justify-content:center;align-items:center;text-align:center;">
      <h2 style="font-family:var(--font-serif);font-size:24px;color:var(--royal);margin-bottom:28px;">关注我，获取更多干货</h2>
      <a href="#" class="btn-cta">立即关注</a>
      <p style="margin-top:28px;font-size:12px;color:var(--muted);">小红书 @飞鸿</p>
      <span class="page-number">6 / 6</span>
    </div>
  </div>

  <script>
    // 导出代码（参见上方 exportCards 函数）
    document.getElementById('export-btn').addEventListener('click', async () => {
      const btn = document.getElementById('export-btn');
      btn.textContent = '等待字体加载...'; btn.disabled = true;
      await document.fonts.ready;
      btn.textContent = '导出中...';
      const pages = document.querySelectorAll('.cards-page');
      for (let i = 0; i < pages.length; i++) {
        const canvas = await html2canvas(pages[i], {
          scale: 2, useCORS: true, backgroundColor: '#FFFFFF', logging: false
        });
        const a = document.createElement('a');
        a.download = `page-${String(i+1).padStart(2,'0')}.png`;
        a.href = canvas.toDataURL('image/png');
        a.click();
        await new Promise(r => setTimeout(r, 300));
      }
      btn.textContent = '导出完成';
      setTimeout(() => { btn.textContent = '导出全部图片'; btn.disabled = false; }, 2000);
    });
  </script>
</body>
</html>
```

---

## 场景定位

图文卡片/小红书3:4卡片是以竖版图片序列形式在小红书/Instagram/公众号等平台传播的图文内容，用于知识分享、干货总结、金句卡片、教程步骤、产品种草等需要在手机feed流中滑动浏览的内容。适用于：小红书图文笔记、Instagram Carousel、公众号配图、知识卡片、课程讲义卡片、产品介绍卡片。不适用于：网页设计（用Portfolio/Landing）、PPT演示（用Deck）、长文阅读（用Tutorial）。核心原则是"一卡一观点、手机可读、3秒抓人"——每张卡片独立传达一个信息点，封面决定点击率，排版在手机屏幕上清晰不眯眼，html2canvas导出PNG清晰无模糊。

## 推荐节奏（Section 序列，即卡片页序列）

一组卡片通常5-10页（540×720px CSS / 1080×1440px 导出），结构如下：

### 方案 A：干货教程型（6-8页，最常用）
1. 封面（封面A居中大字 / 封面B偏左）— 大标题+标签+视觉焦点，feed流中抓人
2. 要点列表（内容D：要点列表）— 3-5个核心要点金色圆点列表，快速预览价值
3. 要点展开1（内容A：上图下文 / 内容B：左图右文）— 第一个要点详细说明
4. 要点展开2（内容B/C：左图右文/全幅图）— 第二个要点，换布局
5. 金句页（金句页布局）— Cormorant斜体大字+金色引号，情绪高点
6. 要点展开3（内容A/D交替）— 第三个要点
7. 行动/总结（内容D或E）— 总结清单或数据
8. 结尾页（结尾页CTA）— 酒红按钮+关注引导+联系方式

### 方案 B：金句/观点型（4-5页，适合观点类内容）
1. 封面（大字标题+人物/场景图）
2. 观点展开1（上图下文+小标题）
3. 金句页（核心金句大字居中）
4. 观点展开2（左图右文）
5. 结尾（CTA+二维码）

### 方案 C：清单/步骤型（7-10页，方法论/教程）
1. 封面
2. 目录/总览（要点列表：你将学到X个方法）
3. 步骤1（上图下文，带编号01）
4. 步骤2（左图右文，带编号02）
5. 金句/数据页（大数字突出）
6. 步骤3（全幅图+文字叠加）
7. 步骤4（要点列表）
8. 总结清单（金色圆点列表回顾）
9. 金句页
10. 结尾CTA

### 方案 D：产品种草型（5-7页）
1. 封面（产品大图+核心卖点）
2. 痛点引入（要点列表：你是不是也...）
3. 产品展示1（全幅图+卖点标注）
4. 产品展示2（左图右文：使用场景）
5. 对比/优势（要点列表：为什么选它）
6. 用户证言/数据（金句格式）
7. 结尾（购买引导/优惠信息+二维码）

## 专属装饰手法（Signature Touches）

卡片场景装饰比网页更密集，因为每一页都是独立画面：

- **#09 Fleuron 花饰**：封面标题旁或结尾页可用❦装饰，但比网页场景更克制
- **#07 Decorative Rule 装饰线**：标题下方的金色短线（40-60px），是卡片最稳定的装饰签名
- **#20 Numbered Index 编号索引**：步骤/要点用金色大号数字（01/02/03）标注，Playfair衬线
- **#04 Pull Quote 金句引用**：金句页用Cormorant斜体大字+金色大号引号（80-120px）
- **#18 Badge & Stamp 徽章标签**：封面分类标签用金色底皇家蓝字胶囊（"干货分享"/"原创"/"NEW"）
- **#15 Divider 分隔线**：标题和正文之间、要点之间用金色细线分隔
- **#05 Highlight 荧光笔高亮**：正文中的关键词用金色荧光笔效果标记（黄色半透明背景）
- **#11 Ornamental Corner 角饰**：封面四角可用金色角饰线，增加正式感
- **#03 Image Frame 图片画框**：配图加1px金色细边框或白色边框+柔和阴影
- **#19 Handwritten Note 手写注**：可用手写体标注（如"亲测有效！"/"重点！"），增加人味
- **页码装饰**：每页右下角"X/N"页码，Inter/JetBrains Mono小字灰色
- **品牌水印**：每页右下角极小字号品牌名，透明度0.3

## 推荐布局组合

卡片场景的"布局"是每页的排版方式，从5种内容页布局+封面+金句+结尾中选择：

| 布局 | 名称 | 适用页 | 说明 |
|------|------|--------|------|
| **封面A** | 居中大字封面 | 第1页（首选） | 标题居中+标签+金色线，最通用最抓人 |
| **封面B** | 偏左封面 | 第1页（备选） | 标题偏左+右侧配图，杂志感 |
| **内容A** | 上图下文 | 内容页 | 图片居中(75-85%宽)+小标题+正文，最常用内容布局 |
| **内容B** | 左图右文 | 内容页 | 左侧图(40%)+右侧文字，适合产品/人物介绍 |
| **内容C** | 全幅图+文字叠加 | 内容页（间隔用） | 图片全幅+渐变遮罩+白色文字，视觉冲击强但不连续用 |
| **内容D** | 要点列表 | 内容页/总结页 | 金色圆点列表，纯文字信息密度高 |
| **内容E** | 数字突出 | 数据页 | 超大Playfair数字(60-80px)+简短解释 |
| **金句页** | 大字居中金句 | 情绪高点页 | 大量留白+Cormorant斜体+金色大引号 |
| **结尾页** | CTA收尾 | 最后1页（必选） | 酒红按钮+关注引导+联系方式/二维码 |

## 色彩策略

卡片场景色彩策略核心：白底为主（feed流缩略图吸引力），皇家蓝标题，金色装饰，酒红仅CTA。

**皇家蓝 #0A2463（标题色，55%视觉权重）**
- 所有标题文字（封面h1、内容页h2、金句文字）
- 分类标签badge上的文字（金色底皇家蓝字）
- 数据/数字突出（内容E）
- 小标题前缀方块

**复古金 #F4D35E（装饰色，30%）**
- 封面分类标签badge背景色
- 标题下方的金色装饰短线
- 金色圆点列表（10-12px直径圆点）
- 金句页的大号引号
- 步骤/要点编号（01/02/03）
- 荧光笔高亮（半透明金色背景标记关键词）
- 分隔线、花饰、角饰
- 图片边框
- **白底上金色仅用于装饰线/圆点/标签背景/短数字，不用于大段正文**
- **注意**：白底上金色文字对比度不足，需要用深金`#B8951F`加粗（font-weight 700+）或仅在金色背景上放皇家蓝字

**酒红 #D8315B（行动色，15%）**
- 结尾页CTA按钮（整个卡片组唯一的酒红大面积色块）
- 极少数需要极强强调的词（封面中每卡最多1个酒红色词）
- **酒红在卡片组中克制到极致——只有CTA按钮是酒红大面积，其他位置基本不用**

**背景策略**：
- 封面/内容页/金句页/结尾页：白色底`#FFFFFF`或暖米白`#FDFBF6`
- 不使用深色背景（影响feed流缩略图效果，与周围白色卡片不协调）
- 全幅图页的图片本身可以暗，但卡片容器背景保持浅色
- 金句页可使用极浅暖米白（`#FEFCF0`）增加层次感但仍保持浅色

## 场景禁忌（Don'ts）

1. **深色背景做卡片**：小红书feed流是白色/浅色背景，深色卡片缩略图会显得压抑，点击率低
2. **每页排版一样**：连续两页相同布局=划走，必须交替上图下文/左图右文/列表/全幅图
3. **正文字号小于20px（CSS）**：手机上眯眼=划走，正文底线20px（推荐22-24px CSS），标题≥28px
4. **渐变文字/background-clip:text**：html2canvas对渐变文字渲染支持差，导出会模糊或失效
5. **backdrop-filter毛玻璃效果**：html2canvas完全不支持，导出无效果
6. **position:fixed定位**：导出时定位异常，所有元素用relative/absolute在卡片容器内
7. **外部图片未CORS配置**：会导出空白或跨域错误，图片用base64或同源
8. **未等字体加载就导出**：字体会回退为系统字体，必须等`document.fonts.ready`
9. **酒红色多用**：卡片组里酒红只在结尾CTA按钮出现，内容页不用酒红背景
10. **内容贴边**：内容距卡片边缘至少40px（CSS 540px画布），否则被小红书UI遮挡

## 场景专属Checklist

- [ ] 画布比例严格3:4（CSS 540×720px，html2canvas scale:2导出1080×1440px）
- [ ] 导出PNG文字不模糊：scale:2，等待document.fonts.ready后再导出
- [ ] 正文字号≥20px CSS（≈28px @1080），标题≥28px CSS（≈40px @1080）
- [ ] 每页排版不同，不连续两页相同布局
- [ ] 封面有金色badge标签+大标题+金色装饰线，feed流中3秒抓人
- [ ] 至少1页金句页：Cormorant斜体+金色大引号+大量留白
- [ ] 结尾页有酒红CTA按钮+关注引导+联系方式/二维码
- [ ] 内容距卡片边缘≥40px（CSS），不贴边
- [ ] 金色仅用于装饰线/圆点/标签/编号/引号，白底上无大段金色文字
- [ ] 酒红仅用于结尾CTA按钮（唯一大面积酒红色块）
- [ ] 每页右下角有"X/N"页码
- [ ] 列表用金色圆点（10-12px直径），不用默认disc
- [ ] 标题下方有金色短线装饰
- [ ] 不使用渐变文字、backdrop-filter毛玻璃、position:fixed
- [ ] 图片使用base64或同源/CORS配置，导出无跨域错误
- [ ] 所有图片有alt，配图风格统一（暖色调/有质感/非AI感假图）
- [ ] 行距1.6-1.8，段落间距宽松不拥挤
- [ ] 每页一个核心信息点，不堆砌文字
- [ ] 衬线标题(Playfair/Noto Serif SC)+无衬线正文(Inter/Noto Sans SC)混搭
- [ ] 导出JPG/PNG单张≤500KB，利于上传小红书

---

*Scene: Cards (小红书图文卡片) v1.0 · Feihong Design System*
*基于 DNA.md v2.0 · 最后更新：2026-07-08*
