# Feihong Design System · Scene: WeChat Official Account (公众号排版)
# 飞鸿品牌设计系统 · 场景规范：微信公众号排版

> 本规范定义飞鸿品牌设计系统在「微信公众号图文排版」场景中的具体应用方式。
> 公众号场景有极强的平台约束，所有规则以微信编辑器实际渲染效果为准。

---

## 1. 场景定义

### 适用内容形态

微信公众号排版场景适用于以下内容形态：

| 类型 | 说明 | 典型长度 |
|------|------|----------|
| **公众号推文** | 品牌公众号正式发布的图文内容 | 1500-4000字 |
| **知识长文** | 深度文章、行业观点、方法论 | 2000-5000字 |
| **产品/活动宣发** | 产品介绍、活动通知、品牌故事 | 800-2000字 |
| **周报/合集** | 定期内容汇总、资源推荐 | 1000-2500字 |

### 核心平台约束（最高优先级）

> **铁律：微信公众号不支持外部 CSS、不支持 class、不支持 JS。所有样式必须内联在标签的 style 属性中。**

| 约束项 | 具体限制 |
|--------|----------|
| **CSS** | 不支持 `<link>` 引入外部 CSS，不支持 `<style>` 标签中的 class 选择器（部分版本支持，但不可靠） |
| **样式写法** | 所有样式必须写在标签的 `style="..."` 属性内（内联样式） |
| **JavaScript** | 完全不支持，任何 JS 代码都会被过滤 |
| **字体** | 不支持 web 字体（`@font-face` / Google Fonts），只能使用系统字体 |
| **布局** | 不支持 flex、grid 布局，需用 `<table>` 实现多栏布局 |
| **宽度** | 内容宽度自适应手机屏幕（约 375px），图片宽度 100% |
| **圆角** | `border-radius` 部分支持（iOS 支持较好，安卓部分机型不支持），不可依赖 |
| **定位** | `position: fixed` 不支持，`position: absolute` 支持有限 |
| **图片** | 必须先上传到微信素材库获得 URL，或使用绝对 URL（含 http/https） |
| **背景图** | 部分支持，复杂背景图建议用 table 背景色或直接用 img 标签 |

### 场景核心气质

- **阅读舒适**：公众号文章第一使命是让人读完，字号行距要舒适
- **品牌识别**：通过金色装饰、衬线标题（用系统字体栈模拟）、色彩组合建立品牌感
- **简洁不花哨**：公众号不是网页，不做复杂布局和动效
- **系统兼容**：在 iOS 和安卓微信中都能正常显示

### 场景核心约束

- **所有样式内联**，无 class、无外部 CSS、无 JS
- **宽度适配手机**（约 375px 逻辑像素）
- **用 table 做布局**，不用 flex/grid
- **用系统字体**，不用 web 字体
- **图片用绝对 URL**（上传到微信素材库后替换）

---

## 2. 典型页面结构

公众号推文采用 **封面图 → 开头引导 → 正文多section → 结尾CTA/关注引导** 的四阶段结构：

```
┌─────────────────────────────┐
│  ① 封面图                    │ ← 在微信编辑器后台设置
│  (微信后台设置 900×383px)     │    不写在HTML正文中
├─────────────────────────────┤
│  ② 开头引导语                 │ ← 1-2段文字，引入主题
│  (可加品牌色引导块)            │    可含金色引用装饰
├─────────────────────────────┤
│  ③ 正文多 Section ×N         │ ← 正文主体
│  ├─ 小标题（皇家蓝）          │    每个section之间用分隔线
│  ├─ 正文段落                 │
│  ├─ 金色圆点列表/引用块       │    交替使用不同元素
│  ├─ 配图（宽度100%）         │
│  └─ ...                     │
├─────────────────────────────┤
│  ④ 结尾 CTA / 关注引导        │ ← 引导关注、阅读原文
│  (品牌色背景块/表格)          │    可含二维码占位说明
└─────────────────────────────┘
```

### 结构要点

1. **封面图**：不在 HTML 正文中，在微信后台编辑器设置（建议尺寸 900×383px，2.35:1 比例）
2. **开头引导**：文章开头 1-2 段引入语，可使用金色左边框引用样式
3. **正文 section**：每段有小标题，之间用金色分割线或圆点分割，穿插图片和引用
4. **结尾 CTA**：引导关注公众号、阅读原文、留言互动，可用品牌色背景块突出

---

## 3. 色彩使用指南

### 3.1 色彩使用总原则

公众号场景严格使用品牌三色，但因平台限制（内联样式、无 CSS 变量），所有色值必须直接写 HEX 值：

| 角色 | 色名 | HEX | 使用比例 |
|------|------|-----|----------|
| 主色 | 皇家蓝 | `#0A2463` | 55% |
| 辅助色 | 复古金 | `#F4D35E` | 30% |
| 点缀色 | 酒红 | `#D8315B` | 15% |
| 背景色 | 暖米白 | `#FDFBF6` | 页面底色（可选） |
| 正文色 | 墨黑/深灰 | `#333333` 或 `#0D1225` | 正文主文字 |

### 3.2 皇家蓝 `#0A2463`（55%）— 标题与链接

| 用途 | 内联样式写法 | 说明 |
|------|-------------|------|
| **小标题** | `<h2 style="color:#0A2463;...">` | section 标题，加粗 |
| **链接文字** | `<a style="color:#0A2463;...">` | 文内链接，可加金色下划线 |
| **引用块文字** | `<p style="color:#0A2463;...">` | 引用块内文字 |
| **序号/编号** | `<span style="color:#0A2463;...">` | 步骤编号 |

### 3.3 复古金 `#F4D35E`（30%）— 装饰与背景

> **重要提醒**：金色 `#F4D35E` 在白底上做文字时对比度严重不足，在公众号场景中**必须用作背景色块而非文字色**。

| 用途 | 内联样式写法 | 说明 |
|------|-------------|------|
| **装饰线/分隔线** | `<td style="border-top:2px solid #F4D35E;...">` 或 `<hr style="border-color:#F4D35E;...">` | section 之间的分隔 |
| **标签背景** | `<span style="background:#F4D35E;color:#0A2463;...">` | 金色底+皇家蓝字 |
| **引用块边框** | `<td style="border-left:4px solid #F4D35E;...">` | 引用块金色左边框 |
| **引用块背景** | `<td style="background:#FEFAED;...">` | 极浅金色背景（金色100色阶） |
| **金色圆点** | 用 `◆` 符号代替 CSS list-style | `<span style="color:#F4D35E;">◆</span>` |
| **表头背景** | `<th style="background:#F4D35E;color:#0A2463;...">` | 表格表头 |
| **金色文字** | **禁止在白底上用 `#F4D35E` 做文字** | 如需金色文字，用深金 `#B8951F` |

### 3.4 酒红 `#D8315B`（15%）— 强调与CTA

| 用途 | 内联样式写法 | 说明 |
|------|-------------|------|
| **重点强调文字** | `<strong style="color:#D8315B;">` | 正文中的核心关键词 |
| **CTA 按钮/区域** | `<td style="background:#D8315B;color:#fff;...">` | 结尾行动区背景 |
| **重点标签** | `<span style="background:#D8315B;color:#fff;...">` | "重点"/"必看"标签 |
| **警告提示** | `<span style="color:#D8315B;">` | 需要注意的内容 |

### 3.5 正文与中性色

| 元素 | 色值 | 内联样式 |
|------|------|----------|
| **正文主文字** | `#333333` 或 `#0D1225` | `style="color:#333333;"` |
| **辅助说明** | `#666666` 或 `#6B7288` | `style="color:#666666;"` |
| **分割线** | `#F4D35E`（金色）或 `#E8E8E8` | `style="border-top:1px solid #E8E8E8;"` |
| **引用块背景** | `#FEFAED`（极浅金） | `style="background:#FEFAED;"` |
| **页面底色** | 默认白底即可，暖米白用 `#FDFBF6` | 用 table 包裹设置 |

### 色彩使用铁律（公众号场景）

1. **金色在白底上绝不做正文文字**（对比度不足），必须用背景色块
2. **链接色用皇家蓝 `#0A2463`**，不使用微信默认蓝色
3. **酒红只做小面积强调**，不大面积铺色
4. **所有色值直接写 HEX**，不使用 CSS 变量、rgb()、hsl()（兼容性考虑）
5. **颜色数量克制**，一篇文章中颜色不超过 4 种（三色+正文灰）

---

## 4. 排版规范

### 4.1 字号规范

> 微信公众号字号单位用 **px**，不使用 rem、em、vw 等相对单位。

| 元素 | 字号 | 行高 | 字重 | 颜色 |
|------|------|------|------|------|
| **文章大标题** | 20-22px | 1.4 | bold | `#0A2463` |
| **小标题 (h2)** | 17-18px | 1.5 | bold | `#0A2463` |
| **子标题 (h3)** | 16px | 1.5 | bold | `#0A2463` |
| **正文** | **15-16px** | **1.75-2** | normal | `#333333` |
| **引用正文** | 15-16px | 1.75 | normal/italic | `#0A2463` |
| **辅助说明/图注** | 13-14px | 1.5 | normal | `#666666` |
| **标签/徽章** | 12-13px | 1.4 | bold | `#0A2463`（金色底） |
| **CTA按钮文字** | 16px | 1.4 | bold | `#FFFFFF`（酒红底） |

> **正文字号推荐 15px**（14px 偏小，16px 在某些机型上显得大）。标题 18px 左右最舒适。

### 4.2 间距规范

所有间距通过 `padding`、`margin`、`<br>` 或空行实现：

| 间距类型 | 推荐值 | 实现方式 |
|----------|--------|----------|
| **段间距** | 10-15px | `<p style="margin:0 0 15px;">` 或段间空行 |
| **标题上方间距** | 20-25px | `margin-top:25px` |
| **标题下方间距** | 10-15px | `margin-bottom:10px` |
| **图片上下间距** | 15-20px | 图片前后加空行或 `margin` |
| **引用块内边距** | 15px 20px | `padding:15px 20px` |
| **列表项间距** | 8-12px | `margin-bottom:10px` |
| **左右边距** | 15px | 用 table 包裹或 `padding:0 15px` |
| **行距（正文）** | **1.75-2** | `line-height:1.8` |

### 4.3 字体策略（系统字体栈）

> **不使用 web 字体**（Google Fonts 在微信内不可靠，且 `@font-face` 被过滤）。
> 使用系统字体栈，iOS 和安卓各自调用最佳中文字体。

```html
<!-- 标题字体栈（衬线风格） -->
<section style="font-family:'Noto Serif SC','Songti SC','STSong','SimSun','Times New Roman',serif;">

<!-- 正文字体栈（无衬线，微信默认优化） -->
<section style="font-family:-apple-system,BlinkMacSystemFont,'Helvetica Neue','PingFang SC','Microsoft YaHei',sans-serif;">
```

| 用途 | 字体栈 | 说明 |
|------|--------|------|
| **标题** | `'Noto Serif SC','Songti SC','STSong','SimSun',serif` | iOS 用 Songti SC（宋体），安卓用 Noto Serif SC 或系统宋体 |
| **正文** | `-apple-system,BlinkMacSystemFont,'Helvetica Neue','PingFang SC','Microsoft YaHei',sans-serif` | 微信默认优化的系统字体栈 |
| **斜体/引用** | 在正文字体栈基础上加 `font-style:italic` | 中文斜体在微信中显示为正常字体，不影响阅读 |

> **中文字体说明**：微信公众号内，iOS 设备会自动使用 PingFang SC，安卓使用系统默认中文字体。显式指定 Songti SC 可让标题在 iOS 上显示为宋体衬线风格。

### 4.4 段落排版细节

1. **不使用首行缩进**（text-indent）：公众号文章惯例是段间距分隔，不缩进
2. **段间距 > 行间距**：用 `margin-bottom:15px` 区分段落
3. **左对齐**：`text-align:left`，不使用两端对齐（微信对 justify 支持不佳）
4. **强调方式**：
   - 重点词：`<strong style="color:#0A2463;">`（皇家蓝加粗）或 `<strong style="color:#D8315B;">`（酒红加粗）
   - 关键词高亮：用金色背景模拟荧光笔 `<span style="background:#F4D35E;color:#0A2463;padding:0 3px;">`
5. **中英文混排**：中英文之间加空格
6. **不用 text-transform**：中文不需要大写转换

---

## 5. 推荐布局

公众号场景布局受平台限制，推荐以下几种经过验证的布局模式：

### 5.1 简单垂直流（默认布局）

```
┌───────────────────────┐
│ 引导语段落             │
│                       │
│ 【小标题】             │ ← 皇家蓝加粗
│ 正文段落...            │
│ 正文段落...            │
│                       │
│ 图片（宽度100%）       │
│                       │
│ 【小标题】             │
│ 正文段落...            │
│ ◆ 金色圆点列表项1      │
│ ◆ 金色圆点列表项2      │
│ ◆ 金色圆点列表项3      │
└───────────────────────┘
```

- 最基础的布局，兼容性最好
- 所有内容垂直排列，不用 table 做多栏
- 适用于大多数文章

### 5.2 两栏布局（用 table 实现）

```html
<table cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <td width="30%" valign="top">
      <!-- 左栏：图片或标签 -->
      <img src="..." width="100%" style="display:block;">
    </td>
    <td width="5%" valign="top"><!-- 间距 --></td>
    <td width="65%" valign="top">
      <!-- 右栏：文字 -->
      <p style="font-size:15px;line-height:1.8;color:#333;margin:0;">文字内容</p>
    </td>
  </tr>
</table>
```

- 用 `<table>` 而非 flex/grid
- 必须设置 `cellpadding="0" cellspacing="0" border="0"`
- 用 `width` 属性和 `valign="top"` 控制对齐
- 间距用空 `<td>` 实现

### 5.3 引用块布局（金色边框+背景）

```html
<table cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <td width="4" bgcolor="#F4D35E" style="width:4px;"></td>
    <td width="15" style="width:15px;"></td>
    <td bgcolor="#FEFAED" style="padding:15px 20px;background:#FEFAED;">
      <p style="font-size:15px;line-height:1.8;color:#0A2463;margin:0;font-style:italic;">
        引用/金句内容文字...
      </p>
    </td>
  </tr>
</table>
```

- 用 table 第一列做 4px 金色左边框
- 第二列做间距
- 第三列极浅金背景+内边距
- 文字用皇家蓝、可加斜体

### 5.4 背景色块 Section

```html
<table cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <td bgcolor="#0A2463" style="background:#0A2463;padding:25px 20px;border-radius:8px;">
      <p style="font-size:18px;color:#F4D35E;font-weight:bold;margin:0 0 10px;">区块标题</p>
      <p style="font-size:15px;line-height:1.8;color:#fff;margin:0;">区块内容文字...</p>
    </td>
  </tr>
</table>
```

- 皇家蓝背景 + 金色标题 + 白色正文
- 用于打破节奏，制造视觉焦点
- 不使用 border-radius（兼容考虑），直角也可
- 一篇文章中 1-2 个深色块即可

### 5.5 CTA 结尾区

```html
<table cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <td bgcolor="#D8315B" style="background:#D8315B;padding:30px 20px;text-align:center;">
      <p style="font-size:18px;color:#fff;font-weight:bold;margin:0 0 10px;">
        关注公众号，获取更多内容
      </p>
      <p style="font-size:14px;color:rgba(255,255,255,0.85);margin:0 0 20px;">
        每周分享深度思考与专业见解
      </p>
      <!-- 按钮用 table 模拟 -->
      <table cellpadding="0" cellspacing="0" border="0" align="center">
        <tr>
          <td bgcolor="#fff" style="background:#fff;padding:12px 30px;border-radius:6px;">
            <a href="#" style="font-size:16px;color:#D8315B;font-weight:bold;text-decoration:none;">
              点击关注
            </a>
          </td>
        </tr>
      </table>
    </td>
  </tr>
</table>
```

- 酒红背景，白色文字
- 按钮用嵌套 table 实现（圆角不可靠，直角也可接受）
- 居中对齐
- 简洁有力，不堆砌信息

---

## 6. 组件选用

### 6.1 必用组件

| 组件 | 实现方式 | 用途 |
|------|----------|------|
| **金色引用块** | table 模拟（左边框+浅金背景） | 金句、引言、重点段落 |
| **金色圆点列表** | 用 `◆` 符号代替 CSS list-style | 要点列举 |
| **金色分割线** | `<hr>` 或 table 空行加 border-top | section 之间 |
| **小标题样式** | `<h2>` 或 `<p>` + 内联 style | section 标题 |
| **结尾 CTA 块** | table 酒红背景 | 关注引导 |

### 6.2 金色圆点列表实现

```html
<p style="font-size:15px;line-height:1.8;color:#333;margin:0 0 10px;padding-left:20px;text-indent:-12px;">
  <span style="color:#F4D35E;font-size:12px;">◆</span>
  &nbsp;&nbsp;第一个要点的内容文字...
</p>
<p style="font-size:15px;line-height:1.8;color:#333;margin:0 0 10px;padding-left:20px;text-indent:-12px;">
  <span style="color:#F4D35E;font-size:12px;">◆</span>
  &nbsp;&nbsp;第二个要点的内容文字...
</p>
```

- 用 `◆`（菱形）符号作为金色圆点
- 通过 `padding-left` + `text-indent` 实现悬挂缩进
- 金色符号与文字之间用 `&nbsp;&nbsp;` 间距

### 6.3 金色分割线实现

```html
<!-- 方式一：hr 标签（简单） -->
<hr style="border:none;border-top:2px solid #F4D35E;width:60px;margin:25px 0;">

<!-- 方式二：table 模拟（更可控） -->
<table cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <td style="padding:20px 0;">
      <hr style="border:none;border-top:2px solid #F4D35E;width:50px;margin:0;">
    </td>
  </tr>
</table>
```

- 分割线长度 50-60px，不是全宽
- 金色 2px，居中或左对齐
- 上下各留 20px 间距

### 6.4 标签 Badge 实现

```html
<span style="display:inline-block;background:#F4D35E;color:#0A2463;font-size:12px;font-weight:bold;padding:3px 10px;border-radius:3px;margin-right:8px;">标签文字</span>
```

- 金色背景 + 皇家蓝文字
- 圆角不可靠，不依赖也可以
- 用于文章开头的分类标签

### 6.5 不推荐使用的元素/效果

| 元素/效果 | 原因 |
|-----------|------|
| **flex / grid 布局** | 微信不完全支持 |
| **border-radius** | iOS 支持好，安卓部分机型不支持，不可依赖 |
| **box-shadow** | 部分支持，但效果不一致 |
| **position: fixed/absolute** | fixed 不支持，absolute 支持有限 |
| **transform / transition / animation** | 不支持或被过滤 |
| **web 字体（@font-face / Google Fonts）** | 不支持 |
| **外部 CSS / class 选择器** | 被过滤 |
| **JavaScript** | 完全不支持 |
| **backdrop-filter** | 不支持 |
| **background-clip: text（渐变文字）** | 不支持 |
| **复杂 SVG** | 部分支持，建议用图片代替 |
| **emoji 作为装饰** | 不同平台渲染不一致，影响品牌感 |

---

## 7. 特殊注意事项

### 7.1 所有样式必须内联

这是公众号场景的第一铁律：

```html
<!-- ❌ 错误：使用 class 和外部 CSS -->
<style>
  .title { color: #0A2463; font-size: 18px; }
</style>
<p class="title">小标题</p>

<!-- ✅ 正确：所有样式内联 -->
<p style="color:#0A2463;font-size:18px;font-weight:bold;line-height:1.5;margin:25px 0 10px;">小标题</p>
```

- 可以在开发时用 class 写样式，**粘贴到微信编辑器前必须全部转为内联样式**
- 推荐工具：Premailer（自动将 CSS 转为内联样式）
- 微信编辑器会自动过滤 `<style>` 和 `<script>` 标签

### 7.2 用 table 代替 flex/grid

```html
<!-- ❌ 错误：使用 flex -->
<div style="display:flex;gap:15px;">
  <div style="width:30%;">左栏</div>
  <div style="width:70%;">右栏</div>
</div>

<!-- ✅ 正确：使用 table -->
<table cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <td width="30%" valign="top">左栏</td>
    <td width="15"></td>
    <td width="69%" valign="top">右栏</td>
  </tr>
</table>
```

### 7.3 图片使用规则

1. **图片必须先上传到微信公众号素材库**，获得微信的图片 URL（`mmbiz.qpic.cn` 域名）
2. 开发时可用占位图，但粘贴到编辑器后必须替换为微信素材库图片
3. **图片宽度设 100%**：`<img style="width:100%;display:block;" src="...">`
4. **图片加 `display:block`**：消除图片下方默认间距
5. **GIF 动图**：支持，但文件大小控制在 2MB 以内
6. **不使用背景图片**：用 `<img>` 标签代替

### 7.4 微信编辑器兼容性问题

1. **复制粘贴到微信编辑器后，务必在手机微信中预览**（公众号后台提供预览功能）
2. **iOS 和安卓都要测试**：渲染差异较大
3. **空行被吞**：微信编辑器会过滤多余空行，用 `<p style="margin:15px 0;"></p>` 或 `<br>` 控制间距
4. **margin 合并**：微信编辑器会重置部分 margin，建议用 padding 控制内间距
5. **section 标签**：部分版本会被替换为 div，建议用 `<div>` 或 `<p>` 更安全
6. **HTML 注释**：会被过滤，不要依赖

### 7.5 公众号开发工作流建议

```
1. 在本地 HTML 文件中开发（可用 class 写样式提高效率）
2. 使用工具（如 Premailer / inline-css）将 CSS 自动转为内联样式
3. 复制内联后的 HTML 源码
4. 打开微信公众号后台 → 图文消息 → 切换到 HTML 模式（或用第三方编辑器如 135编辑器/秀米）
5. 粘贴 HTML 代码
6. 上传图片到素材库，替换所有图片 URL
7. 在手机上预览效果（iOS + 安卓）
8. 调整细节后发布
```

### 7.6 深色模式适配（P2）

微信支持深色模式，公众号文章在深色模式下会自动反色。品牌色在深色模式下的注意事项：

- 皇家蓝 `#0A2463` 在深色模式下对比度仍然足够
- 金色 `#F4D35E` 在深色模式下表现良好（作为装饰色）
- 酒红 `#D8315B` 在深色模式下略暗，可在浅色模式下保证效果即可
- 背景色在深色模式下会被微信自动转换，不需要额外处理
- 如果要强制浅色模式，可在最外层加 `<body style="background:#fff;color:#333;">`（部分版本有效）

---

## 8. 场景专属 Checklist

在交付任何公众号排版内容之前，必须通过以下检查：

### P0 — 必须通过（缺一不可）

- [ ] **所有样式写在标签 style 属性内（内联样式）**，无 class、无外部 CSS
- [ ] **无 JavaScript 代码**，无 `<script>` 标签
- [ ] **使用 table 布局代替 flex/grid**（需要多栏时）
- [ ] **正文字号 15-16px**，行距 1.75-2，手机阅读舒适
- [ ] **图片使用绝对路径 URL**（最终发布前替换为微信素材库 URL）
- [ ] **三种品牌色严格为 `#0A2463` / `#F4D35E` / `#D8315B`**
- [ ] **链接颜色为皇家蓝 `#0A2463`**，不用微信默认蓝色
- [ ] **金色不在白底上用作正文文字**（用作背景色块/边框/符号）
- [ ] **使用系统字体栈**，不引用外部字体
- [ ] **图片宽度 100%**，加 `display:block`
- [ ] **已在手机微信中预览**（至少 iOS 测试通过）
- [ ] **不用不支持的 CSS 属性**（flex/grid/position:fixed/backdrop-filter/transform复杂动画等）

### P1 — 应该通过（尽量满足）

- [ ] **金色装饰元素**：引用块有金色左边框、列表有金色圆点、有金色分割线
- [ ] **引用块品牌化**：金色左边框+极浅金背景+皇家蓝斜体文字
- [ ] **小标题用皇家蓝加粗**，与正文有明确层级区分
- [ ] **段间距 10-15px**，段落之间不拥挤
- [ ] **文章有至少一个金色引用块**（金句/重点）
- [ ] **结尾有 CTA 引导**（关注/阅读原文/留言）
- [ ] **酒红色仅用于强调和 CTA**，不大面积使用
- [ ] **图片有说明文字**（图注用 13-14px 灰色）
- [ ] **标签/badge 使用金色背景+皇家蓝文字**

### P2 — 加分项（锦上添花）

- [ ] **适配深色模式**：在微信深色模式下色彩仍然协调
- [ ] **有品牌色块 section**（皇家蓝或酒红背景块打破节奏）
- [ ] **封面图与正文色调统一**（封面图在微信后台设置）
- [ ] **文末有二维码/公众号名片引导关注**
- [ ] **关键信息用金色荧光笔效果高亮**（金色背景+皇家蓝文字）
- [ ] **有作者/来源信息**（13-14px 灰色，文末或开头）

---

## 附录：公众号文章 HTML 骨架示例

```html
<!-- 粘贴到微信编辑器时，使用 <body> 内的内容 -->
<section style="font-family:-apple-system,BlinkMacSystemFont,'Helvetica Neue','PingFang SC','Microsoft YaHei',sans-serif;max-width:100%;padding:0 15px;color:#333;font-size:15px;line-height:1.8;">

  <!-- 开头引导语 -->
  <p style="font-size:15px;line-height:1.8;color:#333;margin:0 0 15px;">
    开头引导语，引入文章主题...
  </p>

  <!-- 金色引用块 -->
  <table cellpadding="0" cellspacing="0" border="0" width="100%" style="margin:20px 0;">
    <tr>
      <td width="4" bgcolor="#F4D35E" style="width:4px;"></td>
      <td width="15" style="width:15px;"></td>
      <td bgcolor="#FEFAED" style="padding:15px 20px;background:#FEFAED;">
        <p style="font-size:15px;line-height:1.8;color:#0A2463;margin:0;font-style:italic;">
          「金句/引用内容...」
        </p>
      </td>
    </tr>
  </table>

  <!-- 分隔线 -->
  <table cellpadding="0" cellspacing="0" border="0" width="100%">
    <tr><td style="padding:20px 0;"><hr style="border:none;border-top:2px solid #F4D35E;width:50px;margin:0;"></td></tr>
  </table>

  <!-- Section 1 -->
  <p style="font-size:18px;color:#0A2463;font-weight:bold;line-height:1.5;margin:25px 0 10px;font-family:'Noto Serif SC','Songti SC','STSong',serif;">
    第一部分小标题
  </p>

  <p style="font-size:15px;line-height:1.8;color:#333;margin:0 0 15px;">
    正文段落内容，<strong style="color:#0A2463;">重点内容用皇家蓝加粗</strong>，普通文字用深灰色...
  </p>

  <!-- 配图 -->
  <p style="margin:20px 0;">
    <img src="REPLACE_WITH_WECHAT_IMAGE_URL" style="width:100%;display:block;border-radius:4px;" alt="配图说明">
  </p>
  <p style="font-size:13px;color:#666;text-align:center;margin:-10px 0 15px;">图片说明文字</p>

  <!-- 金色圆点列表 -->
  <p style="font-size:15px;line-height:1.8;color:#333;margin:0 0 10px;padding-left:20px;text-indent:-12px;">
    <span style="color:#F4D35E;font-size:12px;">◆</span>&nbsp;&nbsp;第一个要点的内容文字...
  </p>
  <p style="font-size:15px;line-height:1.8;color:#333;margin:0 0 10px;padding-left:20px;text-indent:-12px;">
    <span style="color:#F4D35E;font-size:12px;">◆</span>&nbsp;&nbsp;第二个要点的内容文字...
  </p>
  <p style="font-size:15px;line-height:1.8;color:#333;margin:0 0 15px;padding-left:20px;text-indent:-12px;">
    <span style="color:#F4D35E;font-size:12px;">◆</span>&nbsp;&nbsp;第三个要点，包含<strong style="color:#D8315B;">酒红强调的重点</strong>...
  </p>

  <!-- 分隔线 -->
  <table cellpadding="0" cellspacing="0" border="0" width="100%">
    <tr><td style="padding:20px 0;"><hr style="border:none;border-top:2px solid #F4D35E;width:50px;margin:0;"></td></tr>
  </table>

  <!-- Section 2 -->
  <p style="font-size:18px;color:#0A2463;font-weight:bold;line-height:1.5;margin:25px 0 10px;font-family:'Noto Serif SC','Songti SC','STSong',serif;">
    第二部分小标题
  </p>

  <p style="font-size:15px;line-height:1.8;color:#333;margin:0 0 15px;">
    正文内容...
  </p>

  <!-- 结尾 CTA -->
  <table cellpadding="0" cellspacing="0" border="0" width="100%" style="margin-top:30px;">
    <tr>
      <td bgcolor="#D8315B" style="background:#D8315B;padding:30px 20px;text-align:center;">
        <p style="font-size:18px;color:#fff;font-weight:bold;margin:0 0 10px;font-family:'Noto Serif SC','Songti SC',serif;">
          关注公众号，获取更多深度内容
        </p>
        <p style="font-size:14px;color:rgba(255,255,255,0.85);margin:0 0 20px;">
          每周分享专业思考与实践经验
        </p>
        <table cellpadding="0" cellspacing="0" border="0" align="center">
          <tr>
            <td bgcolor="#fff" style="background:#fff;padding:12px 30px;">
              <a href="#" style="font-size:16px;color:#D8315B;font-weight:bold;text-decoration:none;">
                点击关注
              </a>
            </td>
          </tr>
        </table>
      </td>
    </tr>
  </table>

</section>
```

### 常用内联样式速查表

```html
<!-- 正文段落 -->
<p style="font-size:15px;line-height:1.8;color:#333;margin:0 0 15px;">文字</p>

<!-- 小标题 -->
<p style="font-size:18px;color:#0A2463;font-weight:bold;line-height:1.5;margin:25px 0 10px;">小标题</p>

<!-- 皇家蓝加粗 -->
<strong style="color:#0A2463;">重点文字</strong>

<!-- 酒红强调 -->
<strong style="color:#D8315B;">警告/必看</strong>

<!-- 金色荧光笔高亮 -->
<span style="background:#F4D35E;color:#0A2463;padding:0 3px;">关键词</span>

<!-- 金色标签 -->
<span style="display:inline-block;background:#F4D35E;color:#0A2463;font-size:12px;font-weight:bold;padding:3px 10px;">标签</span>

<!-- 图片 -->
<img src="URL" style="width:100%;display:block;" alt="">

<!-- 图注 -->
<p style="font-size:13px;color:#666;text-align:center;margin:-10px 0 15px;">说明文字</p>

<!-- 金色分割线 -->
<hr style="border:none;border-top:2px solid #F4D35E;width:50px;margin:25px 0;">

<!-- 辅助说明 -->
<p style="font-size:13px;color:#666;margin:10px 0;">说明文字</p>
```

---

## 场景定位

微信公众号排版是以手机阅读为核心的内容传播形态，用于品牌公众号推文、知识长文、产品/活动宣发、周报合集等通过微信订阅号/服务号推送的图文内容。适用于：公众号推文、知识付费长文、品牌故事、活动通知、行业观点、周报合集。不适用于：网页设计（用Portfolio/Landing）、PPT演示（用Deck）、小红书竖版卡片（用Cards）、邮件（用Email）。核心原则是"手机阅读舒适、微信编辑器兼容、品牌识别一致"——所有样式必须内联，用table做布局，不依赖外部CSS/JS/字体，复制粘贴到微信编辑器后不丢失样式，iOS和安卓都能正常显示。

## 推荐节奏（Section 序列）

公众号推文的"节奏"是从上到下的内容模块排列，受手机屏幕宽度限制（约375px逻辑像素）：

### 方案 A：知识长文型（最常用，1500-3000字）
1. 引导语（1-2段，可含金句引用块）— 引入主题，建立阅读预期
2. 金色短分割线
3. 第一部分小标题（皇家蓝衬线加粗）+正文段落+配图/列表
4. 金色短分割线
5. 第二部分小标题+正文+引用块/数据/列表
6. 金色短分割线
7. 第三部分小标题+正文+配图
8. 酒红CTA结尾块（关注引导/阅读原文）

### 方案 B：产品/活动宣发型（800-1500字，情绪递进）
1. 引导语+品牌色标签（金色badge）
2. 皇家蓝深色背景块（核心信息/痛点）— 视觉冲击
3. 金色分割线
4. 产品亮点1（金色圆点列表）
5. 产品亮点2（左图右文table布局）
6. 金句引用块（金色左边框+极浅金背景）
7. 酒红CTA块（立即报名/购买按钮）

### 方案 C：周报/合集型（1000-2000字，信息密度高）
1. 期号标题（皇家蓝大字）+一句话导语
2. 金色分割线
3. 模块一：推荐文章（3-5条金色圆点列表，每条标题皇家蓝加粗）
4. 模块二：行业动态（简短条目+链接）
5. 模块三：工具/资源推荐（配图+简短说明）
6. 结尾金句+关注引导

### 方案 D：极简短讯型（300-800字，快速阅读）
1. 一句话导语
2. 正文（2-3段，关键词用皇家蓝加粗或金色荧光笔高亮）
3. 金色圆点列表（3-5个要点）
4. 极简CTA（一行酒红文字链接，不用色块）

### 方案 E：品牌故事/深度文章型（3000-5000字，长文沉浸）
1. 开篇金句引用块（情绪建立）
2. 引子段落（故事化引入）
3. 金色分割线
4. 第一章小标题+正文（穿插配图、引用、列表）
5. 皇家蓝深色块（转折点/核心观点）
6. 金色分割线
7. 第二章小标题+正文
8. 金色圆点列表（要点总结）
9. 结尾段落+酒红CTA（关注+留言引导）

## 专属装饰手法（Signature Touches）

公众号场景装饰受平台限制，只能用内联样式和HTML字符实现，但仍有丰富的品牌签名手法：

- **#07 Decorative Rule 金色短分割线**：section之间用50-60px长、2px粗的金色横线（`<hr style="border:none;border-top:2px solid #F4D35E;width:50px;margin:25px 0;">`），不是全宽分割线，是公众号最稳定的装饰签名
- **#04 Pull Quote 金色左边框引用块**：用嵌套table实现4px金色左边框+极浅金背景`#FEFAED`+皇家蓝斜体文字，用于金句和重点段落
- **#20 Numbered Index 金色菱形列表符**：用`◆`金色菱形符号（`<span style="color:#F4D35E;font-size:12px;">◆</span>`）代替默认list-style，通过padding-left+text-indent实现悬挂缩进
- **#18 Badge & Stamp 金色标签badge**：文章开头的分类标签用金色背景`#F4D35E`+皇家蓝文字的inline-block小胶囊（padding:3px 10px, font-size:12px）
- **#05 Highlight 金色荧光笔高亮**：正文中关键词用金色背景标记（`<span style="background:#F4D35E;color:#0A2463;padding:0 3px;">关键词</span>`）
- **#14 Section Marker 衬线小标题**：小标题用衬线字体栈（Noto Serif SC/Songti SC）+皇家蓝加粗+17-18px，与正文形成对比
- **#15 Divider 皇家蓝深色块**：用table+bgcolor实现皇家蓝背景`#0A2463`+金色标题+白色正文的深色section，打破全白节奏，每篇文章1-2个
- **#16 Alert Box 酒红CTA块**：结尾用酒红背景`#D8315B`+白色文字+白色按钮（嵌套table模拟）的CTA区域
- **图注样式**：图片下方居中灰色小字说明（13px, #666, text-align:center）
- **酒红强调词**：正文中需要极强强调的词用`<strong style="color:#D8315B;">`，每段最多1-2个
- **皇家蓝加粗**：一般强调用皇家蓝加粗`<strong style="color:#0A2463;">`，是最常用的强调方式
- **金色序号**：步骤/编号可用金色数字（01/02/03），但用字符实现不用CSS counter

## 推荐布局组合

公众号场景布局受平台限制（不支持flex/grid），全部用table实现：

| 布局 | 名称 | 适用位置 | 说明 |
|------|------|----------|------|
| **简单垂直流** | 单栏文字流 | 正文主体（默认） | p标签垂直排列，最兼容最基础 |
| **金色引用块table** | 左边框引用 | 金句/重点段落 | 三列表格：4px金色边距列+间距列+内容列 |
| **两栏table** | 左图右文/图文并排 | 产品介绍/人物介绍 | table+两td，左30%+间距+右65%，valign:top |
| **皇家蓝深色块table** | 深色背景section | 核心观点/情绪转折 | 单td bgcolor:#0A2463，金标题+白文字，1-2次/篇 |
| **酒红CTA块table** | 结尾行动区 | 文末 | 单td bgcolor:#D8315B，居中白文字+嵌套table白色按钮 |
| **金色badge** | 标签/分类 | 文章开头、段落标签 | inline-block span，金色底皇家蓝字 |
| **三栏等宽table**（慎用） | 三列内容并排 | 合集/推荐列表 | 移动端体验差，仅在内容短小时使用 |
| **居中table** | 按钮/居中内容 | CTA按钮、居中引用 | align="center"的嵌套table |

## 色彩策略

公众号场景色彩策略核心：白底为主，皇家蓝标题和链接，金色装饰（线/边框/背景块），酒红仅CTA和极强强调。

**皇家蓝 #0A2463（55%，标题与链接）**
- 所有小标题（h2级别）文字颜色
- 文内链接文字颜色（不用微信默认蓝）
- 引用块内文字颜色
- 常规强调词加粗颜色（`<strong style="color:#0A2463;">`）
- 深色块（bgcolor:#0A2463）的背景色，上面放金色标题+白色正文
- 金色badge上的文字颜色
- 荧光笔高亮的文字颜色（金色背景上）

**复古金 #F4D35E（30%，装饰与背景）**
- section之间的金色短分割线（2px粗，50-60px长）
- 引用块的4px左边框
- 引用块的极浅金背景`#FEFAED`
- 金色菱形`◆`列表符号
- 金色badge标签背景色
- 荧光笔高亮的背景色
- 皇家蓝深色块上的标题文字颜色
- 表头背景色（如有表格）
- **白底上绝对不用金色做文字色**（对比度不足），金色只做背景色块、边框、线条、符号
- **如需金色文字效果，只能在深色背景上使用**

**酒红 #D8315B（15%，CTA与极强强调）**
- 结尾CTA块的背景色（整篇文章唯一的酒红大面积色块）
- CTA按钮的背景色（白色文字）
- 正文中极少数需要极强强调的词（`<strong style="color:#D8315B;">`），每篇文章不超过5处
- "重点"/"必看"等警告标签背景色
- **酒红在正文中克制到极致——只有结尾CTA块是酒红大面积，其他位置几乎不用**

**背景与中性色**：
- 页面背景：白色`#FFFFFF`（微信默认），不用暖米白（与微信UI不协调）
- 正文：深灰`#333333`（不是纯黑#000，更柔和）
- 辅助说明/图注：中灰`#666666`
- 引用块背景：极浅金`#FEFAED`
- 分割线：金色`#F4D35E`（section之间）或灰色`#E8E8E8`（条目之间）
- 所有色值必须直接写HEX，不用CSS变量/rgb/hsl

## 场景禁忌（Don'ts）

1. **使用class或外部CSS**：微信编辑器会过滤`<style>`中的class选择器和`<link>`外部CSS，所有样式必须内联在style属性中
2. **使用flex/grid布局**：微信不完全支持，必须用`<table>`实现多栏布局
3. **引用web字体（Google Fonts/@font-face）**：不支持，必须用系统字体栈
4. **白底上用金色#F4D35E做正文文字**：对比度严重不足（<3:1），在手机上看不清
5. **使用border-radius/box-shadow/backdrop-filter**：iOS支持好但安卓部分机型不支持，不可依赖
6. **使用JavaScript**：完全不支持，任何JS都会被过滤
7. **使用position:fixed/transform/animation**：不支持或被过滤，公众号是静态内容
8. **正文小于14px**：手机阅读吃力，底线14px，推荐15px
9. **段间距用空行`<br><br>`实现**：微信编辑器会吞空行，必须用`<p style="margin-bottom:15px;">`控制
10. **使用emoji做装饰**：不同平台渲染不一致，影响品牌感，必要时用HTML实体字符（◆●—等）
11. **全宽分割线**：section之间用50-60px金色短线，不用全宽横线（像135编辑器那种廉价感）
12. **复制到微信编辑器后不在手机上预览**：iOS和安卓渲染差异大，必须手机预览才能发布
13. **使用渐变文字background-clip:text**：不支持
14. **图片用相对路径**：必须上传到微信素材库获得mmbiz.qpic.cn的URL

## 场景专属Checklist

- [ ] 所有样式写在标签style属性内（内联样式），无class、无外部CSS、无`<style>`依赖
- [ ] 无JavaScript代码，无`<script>`标签
- [ ] 多栏布局用`<table>`实现（cellpadding=0 cellspacing=0 border=0），不用flex/grid
- [ ] 正文字号15-16px，行距1.75-2，段间距10-15px，手机阅读舒适
- [ ] 小标题17-18px皇家蓝加粗，衬线字体栈（Noto Serif SC/Songti SC/STSong/serif）
- [ ] 金色短分割线（50-60px长，2px粗，#F4D35E）分隔各section
- [ ] 至少1个金色左边框引用块（4px金边+#FEFAED背景+皇家蓝斜体文字）
- [ ] 列表用金色`◆`菱形符号（padding-left+text-indent悬挂缩进），不用默认disc
- [ ] 金色不在白底上做文字色（仅背景块/边框/线条/符号）
- [ ] 酒红色仅用于结尾CTA块和极少数强调词（每篇≤5处）
- [ ] 结尾有酒红CTA行动区（关注/阅读原文/留言引导）
- [ ] 链接颜色为皇家蓝`#0A2463`，不用微信默认蓝色
- [ ] 图片使用绝对URL（最终替换为微信素材库mmbiz URL），width:100%+display:block
- [ ] 图片有alt文本，配图下方有13px灰色居中图注
- [ ] 所有色值直接写HEX（#0A2463/#F4D35E/#D8315B/#333/#666），不用CSS变量
- [ ] 不使用不支持的CSS：border-radius依赖、box-shadow依赖、position:fixed、backdrop-filter、transform/animation、渐变文字
- [ ] 使用系统字体栈，不引用外部字体
- [ ] 已在手机微信中预览（至少iOS测试通过，安卓最好也测）
- [ ] 中英文之间有空格，不使用text-indent首行缩进
- [ ] 复制粘贴到微信编辑器后，在编辑器中检查样式未丢失

---

*Scene: WeChat Official Account (公众号排版) v1.0 · Feihong Design System*
*基于 DNA.md v2.0 · 最后更新：2026-07-08*
