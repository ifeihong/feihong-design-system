# Feihong Design System · Scene: Email / EDM
# 飞鸿品牌设计系统 · 场景规范：邮件 / EDM 排版

> 本规范定义飞鸿品牌设计系统在「邮件 HTML / EDM / Newsletter」场景中的具体应用方式。
> 邮件场景是前端开发中兼容性要求最严苛的领域，所有规则以实际邮件客户端渲染效果为准。

---

## 1. 场景定义

### 适用内容形态

邮件/EDM 场景适用于以下内容形态：

| 类型 | 说明 | 典型长度 |
|------|------|----------|
| **Newsletter 订阅邮件** | 定期内容推送、行业洞察、周报/月报 | 500-2000字 |
| **产品/活动通知** | 产品更新、活动邀请、促销通知 | 300-1000字 |
| **欢迎邮件/Onboarding** | 新用户注册欢迎、引导流程 | 200-800字 |
| **商务邮件** | 提案、报价、合作邀约 | 200-1000字 |
| **事务性邮件** | 订单确认、密码重置、通知提醒 | 精简为主 |

### 核心平台约束（最高优先级）

> **铁律：邮件 HTML 使用 table 布局，不是 div。所有样式内联，无 JS，无外部 CSS。Outlook 是最大的兼容性挑战。**

| 约束项 | 具体限制 |
|--------|----------|
| **布局方式** | **必须使用 `<table>` 布局**，`<div>` 仅用于文本块内 |
| **CSS** | 所有样式内联在标签的 `style="..."` 属性中，`<style>` 标签仅用于媒体查询（部分客户端支持） |
| **JavaScript** | 完全不支持，所有邮件客户端都会过滤 JS |
| **外部 CSS** | 不支持 `<link>` 引入外部 CSS |
| **外部图片** | 支持，但必须使用**绝对 URL**（含 `http://` 或 `https://`），大部分客户端默认屏蔽图片 |
| **字体** | 不支持 web 字体（`@font-face`），只能使用系统字体 |
| **宽度** | 固定 **600px** 居中（部分推荐 580-620px），这是邮件行业标准 |
| **按钮** | 用 `<table>` 模拟按钮，**不使用 `<button>` 标签**（Outlook 渲染差异大） |
| **背景图** | Outlook 2007-2019 不支持 CSS `background-image`，需要 VML (Vector Markup Language) 处理 |
| **border-radius** | Outlook 不支持圆角，按钮/容器圆角需用图片或接受直角 |
| **margin/padding** | `<div>` 和 `<p>` 上的 margin/padding 在 Outlook 中不可靠，**用 `<td>` 的 padding 控制间距** |
| **CSS 定位** | `position: fixed/absolute/relative` 支持极差，不用 |
| **flex/grid** | 完全不支持 |

### 场景核心气质

- **专业可信**：邮件代表品牌形象，排版规整、清晰、无错乱
- **高效传达**：收件人快速扫读就能获取核心信息
- **跨客户端一致**：在 Gmail、Outlook、Apple Mail、QQ邮箱、网易邮箱等都能正常显示
- **品牌识别**：即使在图片被屏蔽的情况下，品牌色和排版仍然可识别

### 需要兼容的主要邮件客户端

| 客户端 | 渲染引擎 | 注意事项 |
|--------|----------|----------|
| **Outlook 2007-2019 (Windows)** | **Microsoft Word** | 最严苛的兼容目标，支持 VML，不支持多数 CSS |
| **Outlook.com (网页版)** | 类似浏览器 | 较好，但会改写 CSS |
| **Gmail (网页/App)** | 浏览器/移动端 | 较好，支持部分 `<style>` |
| **Apple Mail (macOS/iOS)** | WebKit | 最好的支持度，可使用部分 CSS3 |
| **QQ邮箱 / 网易邮箱** | 国内主流 | 会过滤部分标签，需测试 |
| **Foxmail / 企业微信邮箱** | 国内客户端 | 类似 Outlook 兼容性 |

---

## 2. 典型邮件结构

邮件采用 **Preheader → 头部 → Hero → 正文 → CTA → Footer** 的六段式结构，全部用 table 实现：

```
┌─────────────────────────────────────────┐
│  Preheader 预览文字（不在邮件中显示）       │ ← 收件箱预览行
│  "查看本月精彩内容 | 飞鸿 Newsletter"      │
├─────────────────────────────────────────┤
│  ① 头部 Header                           │
│  ┌─────────────────────────────────────┐│
│  │ [Logo]                    导航文字    ││ ← 600px 宽，品牌色或白底
│  └─────────────────────────────────────┘│
├─────────────────────────────────────────┤
│  ② Hero 区                              │
│  ┌─────────────────────────────────────┐│
│  │                                     ││
│  │  大标题（皇家蓝衬线风格）              ││ ← 600px 宽
│  │  副标题/导语                         ││    可有背景色或配图
│  │  [CTA 按钮]                          ││
│  │                                     ││
│  └─────────────────────────────────────┘│
├─────────────────────────────────────────┤
│  ③ 正文内容                              │
│  ┌─────────────────────────────────────┐│
│  │  Section 1 小标题                    ││
│  │  正文段落文字...                     ││
│  │  ◆ 要点列表                          ││
│  │  ┌─────────────────────────────┐    ││
│  │  │  图片（宽度100%）             │    ││
│  │  └─────────────────────────────┘    ││
│  │                                     ││
│  │  Section 2 小标题                    ││
│  │  正文段落...                         ││
│  └─────────────────────────────────────┘│
├─────────────────────────────────────────┤
│  ④ CTA 行动区                            │
│  ┌─────────────────────────────────────┐│
│  │                                     ││
│  │  行动引导文字                         ││
│  │  ┌─────────────────────────────┐    ││
│  │  │  CTA 按钮（酒红 table 模拟）  │    ││
│  │  └─────────────────────────────┘    ││
│  │                                     ││
│  └─────────────────────────────────────┘│
├─────────────────────────────────────────┤
│  ⑤ Footer 页脚                          │
│  ┌─────────────────────────────────────┐│
│  │ 飞鸿 Feihong · 品牌slogan            ││
│  │ 联系方式 | 退订链接 | 社交媒体        ││
│  │ 公司地址信息                          ││
│  └─────────────────────────────────────┘│
└─────────────────────────────────────────┘
```

### 结构要点

1. **Preheader 文本**：在 `<head>` 中隐藏设置，显示在收件箱预览行，影响打开率
2. **头部**：Logo + 简短导航（可选），高度 60-80px，白底或品牌色底
3. **Hero**：大标题+副标题+主 CTA，是邮件最重要的部分
4. **正文**：垂直堆叠的 section，每个 section 有小标题和内容
5. **CTA 区**：重复主 CTA 按钮（酒红色）
6. **Footer**：退订链接（商业邮件必须有）、联系方式、公司信息、地址

---

## 3. 色彩使用指南

### 3.1 色彩使用总原则

邮件场景使用品牌三色，但因图片默认被屏蔽，色彩必须在纯 HTML/CSS 中就能传达品牌感：

| 角色 | 色名 | HEX | 主要用途 |
|------|------|-----|----------|
| **主色** | 皇家蓝 | `#0A2463` | 标题、链接、头部背景、品牌识别 |
| **辅助色** | 复古金 | `#F4D35E` | 装饰线、按钮 hover（备选）、小点缀 |
| **点缀色** | 酒红 | `#D8315B` | **CTA 按钮**、重点强调 |
| **背景色** | 暖米白 | `#FDFBF6` | 邮件外层背景 |
| **内容背景** | 纯白 | `#FFFFFF` | 内容区背景（600px） |
| **正文色** | 墨黑/深灰 | `#333333` | 正文主文字 |
| **辅助文字** | 灰色 | `#666666` | Footer、辅助说明 |

### 3.2 皇家蓝 `#0A2463`（55%）— 品牌识别

| 用途 | 实现方式 |
|------|----------|
| **标题文字** | `<h1 style="color:#0A2463;">`（用 `<p>` + style 代替 h1 更安全） |
| **链接文字** | `<a style="color:#0A2463;">` |
| **头部/区块背景** | `<td bgcolor="#0A2463" style="background:#0A2463;">`（同时写 bgcolor 属性和 style） |
| **引用块左边框** | 用嵌套 table 实现（一列窄宽蓝色 td） |

> **重要**：邮件中设置背景色，必须同时写 HTML `bgcolor` 属性和 CSS `background` 属性，确保 Outlook 兼容：
> ```html
> <td bgcolor="#0A2463" style="background:#0A2463;">
> ```

### 3.3 复古金 `#F4D35E`（30%）— 装饰点缀

| 用途 | 实现方式 |
|------|----------|
| **装饰线/分隔线** | `<td style="border-top:2px solid #F4D35E;">` 或 1px 高金色 td |
| **金色背景块** | `<td bgcolor="#F4D35E" style="background:#F4D35E;">` |
| **小图标/装饰** | 用金色字符 `◆` 或小图片 |
| **金色文字（深色底上）** | `<span style="color:#F4D35E;">`（仅在皇家蓝/深色背景上） |

> **金色文字规则**：白底上绝不使用金色文字（对比度不足），金色仅在深色背景上作为文字使用。

### 3.4 酒红 `#D8315B`（15%）— CTA 与行动

| 用途 | 实现方式 |
|------|----------|
| **CTA 按钮背景** | `<td bgcolor="#D8315B" style="background:#D8315B;">`（按钮主色） |
| **强调文字** | `<strong style="color:#D8315B;">` |
| **重要标签** | `<span style="background:#D8315B;color:#fff;">` |

> **CTA 按钮必须用酒红色**，这是邮件中最重要的行动焦点。

### 3.5 背景色规范

| 区域 | 色值 | 写法 |
|------|------|------|
| **邮件最外层背景** | `#FDFBF6`（暖米白） | `<body bgcolor="#FDFBF6">` + 包裹 table 的 bgcolor |
| **内容区背景** | `#FFFFFF`（纯白） | 600px 主 table `bgcolor="#FFFFFF"` |
| **头部/深色区块** | `#0A2463`（皇家蓝） | `<td bgcolor="#0A2463">` |
| **CTA 区背景** | `#D8315B`（酒红）或 `#FFFFFF` | 依设计而定 |
| **Footer 背景** | `#F5F5F5`（浅灰）或 `#0A2463` | Footer 区分于正文 |

### 色彩使用铁律（邮件场景）

1. **所有颜色同时写 `bgcolor` 属性和 `style="background:..."`**（Outlook 兼容）
2. **CTA 按钮统一用酒红 `#D8315B`**，白底白字不做按钮
3. **金色在白底上不用作文字**，仅做装饰线/背景块
4. **背景色不超过 3 种**（暖米白/皇家蓝/酒红），保持简洁
5. **正文文字用 `#333333`**，不用纯黑 `#000000`

---

## 4. 排版规范

### 4.1 基础邮件结构骨架

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <title>邮件标题</title>
  <!-- Preheader 文本 -->
  <span style="display:none;font-size:1px;color:#FDFBF6;line-height:1px;max-height:0;max-width:0;opacity:0;overflow:hidden;">
    预览文字，显示在收件箱标题旁边 | 飞鸿 Newsletter
  </span>
  <!--[if mso]>
  <style type="text/css">
  table {border-collapse: collapse;}
  .outlook-bg { background-color: #0A2463 !important; }
  </style>
  <![endif]-->
  <style type="text/css">
    /* 仅用于媒体查询（响应式），Gmail/Apple Mail 支持 */
    @media only screen and (max-width: 600px) {
      .main-table { width: 100% !important; }
      .mobile-hide { display: none !important; }
    }
  </style>
</head>
<body bgcolor="#FDFBF6" style="margin:0;padding:0;background-color:#FDFBF6;font-family:-apple-system,BlinkMacSystemFont,'Helvetica Neue','PingFang SC','Microsoft YaHei',sans-serif;">

  <!-- 外层包裹 table，居中 -->
  <table cellpadding="0" cellspacing="0" border="0" width="100%" bgcolor="#FDFBF6">
    <tr>
      <td align="center" style="padding:20px 0;">

        <!-- 主内容 table，600px 宽 -->
        <table cellpadding="0" cellspacing="0" border="0" width="600" class="main-table" bgcolor="#FFFFFF" style="width:600px;max-width:600px;">
          <!-- 邮件内容在这里 -->
        </table>

      </td>
    </tr>
  </table>

</body>
</html>
```

### 4.2 字号规范

邮件字号全部使用 **px**，不使用 rem/em/%（Outlook 兼容）：

| 元素 | 字号 | 行高 | 字重 | 颜色 |
|------|------|------|------|------|
| **Preheader** | 1px（隐藏） | 1px | normal | 同背景色 |
| **Hero 大标题** | 28-32px | 1.3 | bold | `#0A2463` |
| **Section 标题** | 20-22px | 1.4 | bold | `#0A2463` |
| **副标题/导语** | 16-18px | 1.5 | normal | `#333333` |
| **正文** | **15-16px** | **1.6-1.8** | normal | `#333333` |
| **按钮文字** | 16px | 1 | bold | `#FFFFFF`（酒红底） |
| **辅助文字/Footer** | 12-13px | 1.5 | normal | `#666666` |
| **小字声明** | 11-12px | 1.4 | normal | `#999999` |

### 4.3 间距规范

> **重要**：邮件中所有间距用 `<td>` 的 `padding` 控制，不用 `<p>` 或 `<div>` 的 `margin`（Outlook 不可靠）。

| 间距类型 | 推荐值 | 实现方式 |
|----------|--------|----------|
| **内容区左右内边距** | 30-40px | 所有内容 td 统一 `padding:0 40px` |
| **段间距** | 15-20px | `<td style="padding-bottom:15px;">` 或空行 td |
| **标题上方间距** | 30px | `padding-top:30px` |
| **标题下方间距** | 10-15px | `padding-bottom:15px` |
| **按钮上下间距** | 20-30px | `padding:25px 0` |
| **区块间距** | 30-40px | 空 tr + td 设置高度 |
| **按钮内边距** | 14px 32px | 按钮 td 的 padding |
| **表格 cellspacing** | 0 | `<table cellspacing="0">` |
| **表格 cellpadding** | 0 | `<table cellpadding="0">`（手动在 td 上加 padding） |

### 4.4 字体策略（系统字体）

```html
<!-- 正文标准字体栈 -->
<td style="font-family:-apple-system,BlinkMacSystemFont,'Segoe UI','Helvetica Neue',Arial,'PingFang SC','Microsoft YaHei',sans-serif;font-size:15px;line-height:1.8;color:#333;">

<!-- 标题字体栈（衬线，用系统衬线） -->
<td style="font-family:Georgia,'Times New Roman','Noto Serif SC','Songti SC','STSong',serif;font-size:28px;font-weight:bold;color:#0A2463;line-height:1.3;">
```

| 用途 | 字体栈 |
|------|--------|
| **标题（衬线风格）** | `Georgia,'Times New Roman','Noto Serif SC','Songti SC','STSong',serif` |
| **正文（无衬线）** | `-apple-system,BlinkMacSystemFont,'Segoe UI','Helvetica Neue',Arial,'PingFang SC','Microsoft YaHei',sans-serif` |
| **等宽/代码** | `'Courier New',Courier,monospace` |

> **不用 web 字体**：Google Fonts 在部分邮件客户端中不加载，会 FOIT（不可见文字）。
> **衬线标题实现**：英文用 Georgia（系统自带衬线），中文系统自动用宋体/Songti SC，效果接近 Playfair Display 的经典衬线感。

---

## 5. 推荐布局

邮件场景布局相对固定，以下是经过验证的经典布局模式：

### 5.1 单栏布局（推荐，兼容性最好）

```
┌──────────────────────────────────────┐  ← 600px
│  Header: Logo + 品牌色条              │
├──────────────────────────────────────┤
│                                      │
│  Hero 大标题                          │
│  Hero 副标题                          │
│  [CTA 按钮]                          │
│                                      │
├──────────────────────────────────────┤
│  ── 金色分隔线 ──                     │
│                                      │
│  Section 标题                         │
│  正文段落文字...                      │
│  正文段落文字...                      │
│                                      │
│  图片（width="540"）                  │
│                                      │
│  Section 标题                         │
│  正文段落...                          │
│  ● 要点1                              │
│  ● 要点2                              │
│                                      │
├──────────────────────────────────────┤
│  CTA 区（酒红背景或白底）              │
│  ┌──────────────────────────────┐    │
│  │        CTA 按钮               │    │
│  └──────────────────────────────┘    │
├──────────────────────────────────────┤
│  Footer（浅灰背景）                   │
│  品牌信息 | 退订 | 联系方式            │
└──────────────────────────────────────┘
```

- **所有内容垂直堆叠**，不用多栏（最兼容）
- 内容区宽度 600px，内边距 30-40px
- 图片宽度 540px（600 - 40*2），不超过内容区宽度

### 5.2 两栏布局（用嵌套 table，谨慎使用）

```html
<!-- 两栏布局：用 table 实现 -->
<table cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <!-- 左栏 -->
    <td width="50%" valign="top" style="padding:0 10px 0 0;">
      <table cellpadding="0" cellspacing="0" border="0" width="100%">
        <tr><td>
          <img src="..." width="100%" style="display:block;width:100%;" alt="">
          <p style="font-size:14px;line-height:1.6;color:#333;margin:10px 0 0;">左栏内容</p>
        </td></tr>
      </table>
    </td>
    <!-- 右栏 -->
    <td width="50%" valign="top" style="padding:0 0 0 10px;">
      <table cellpadding="0" cellspacing="0" border="0" width="100%">
        <tr><td>
          <img src="..." width="100%" style="display:block;width:100%;" alt="">
          <p style="font-size:14px;line-height:1.6;color:#333;margin:10px 0 0;">右栏内容</p>
        </td></tr>
      </table>
    </td>
  </tr>
</table>
```

- 两栏仅在需要并排展示内容时使用
- 移动端需要用媒体查询将两栏变单栏（`display:block;width:100%`），但 Outlook 不支持媒体查询
- **Outlook 中两栏可能出问题**，重要邮件建议用单栏

### 5.3 引用块布局（用嵌套 table 实现左边框）

```html
<table cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <!-- 金色左边框 -->
    <td width="4" bgcolor="#F4D35E" style="width:4px;background:#F4D35E;"></td>
    <td width="20" style="width:20px;"></td>
    <!-- 引用内容 -->
    <td style="padding:15px 0;">
      <p style="font-family:Georgia,serif;font-size:17px;line-height:1.6;color:#0A2463;margin:0;font-style:italic;">
        引用/金句内容文字...
      </p>
    </td>
  </tr>
</table>
```

- 第一列 4px 宽，金色背景作为左边框
- 第二列 20px 宽做间距
- 第三列放置引用文字
- 不使用 `border-left`（Outlook 支持但嵌套 table 更可靠）

### 5.4 CTA 按钮布局（用 table 模拟）

```html
<!-- 按钮居中 -->
<table cellpadding="0" cellspacing="0" border="0" align="center">
  <tr>
    <td bgcolor="#D8315B" style="background:#D8315B;border-radius:6px;">
      <a href="https://..." target="_blank" style="display:inline-block;padding:14px 36px;font-family:-apple-system,BlinkMacSystemFont,sans-serif;font-size:16px;font-weight:bold;color:#FFFFFF;text-decoration:none;border-radius:6px;">
        <!--[if mso]><i style="mso-text-raise:14pt;">&nbsp;</i><![endif]-->
        立即查看
        <!--[if mso]><i style="mso-text-raise:14pt;">&nbsp;</i><![endif]-->
      </a>
    </td>
  </tr>
</table>
```

**按钮实现要点**：
- 用 `<table>` + `<td bgcolor>` 实现按钮背景，不用 `<button>` 或 `<div>`
- 同时写 `bgcolor` 属性和 `style="background:..."`
- `<a>` 标签设为 `display:inline-block`（或 block），加 padding
- 文字颜色白色 `#FFFFFF`
- **圆角不可靠**：Outlook 不支持 border-radius，接受直角或使用 VML 圆角（子弹头按钮 bulletproof button）
- 使用 `<!--[if mso]-->` 条件注释为 Outlook 添加垂直居中 hack

**子弹头按钮（Bulletproof Button，VML 实现 Outlook 圆角）**：

```html
<!-- 更可靠的按钮：VML + CSS 双重保险 -->
<div>
  <!--[if mso]>
  <v:roundrect xmlns:v="urn:schemas-microsoft-com:vml" xmlns:w="urn:schemas-microsoft-com:office:word" href="https://..." style="height:48px;v-text-anchor:middle;width:200px;" arcsize="13%" strokecolor="#D8315B" fillcolor="#D8315B">
    <w:anchorlock/>
    <center style="color:#ffffff;font-family:-apple-system,sans-serif;font-size:16px;font-weight:bold;">立即查看</center>
  </v:roundrect>
  <![endif]-->
  <!--[if !mso]><!-->
  <a href="https://..." target="_blank" style="background-color:#D8315B;border-radius:6px;color:#ffffff;display:inline-block;font-family:-apple-system,sans-serif;font-size:16px;font-weight:bold;line-height:48px;text-align:center;text-decoration:none;width:200px;-webkit-text-size-adjust:none;">立即查看</a>
  <!--<![endif]-->
</div>
```

---

## 6. 组件选用

### 6.1 必用组件

| 组件 | 实现方式 | 用途 |
|------|----------|------|
| **Table 按钮** | 嵌套 table + bgcolor 或 VML 子弹头按钮 | CTA 行动按钮 |
| **金色分隔线** | 1px 高金色 td 或 border-top | section 之间分隔 |
| **头部 Logo 区** | table 行，Logo 图片 + 品牌色 | 品牌识别 |
| **Footer 区** | 独立 table 行，浅灰/蓝色背景 | 法律信息、退订 |
| **Preheader 文本** | 隐藏 span | 收件箱预览 |

### 6.2 分割线实现

```html
<!-- 方式一：空 td 做分割线（最可靠） -->
<table cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <td style="padding:20px 0;">
      <table cellpadding="0" cellspacing="0" border="0" width="60" align="left">
        <tr><td height="2" bgcolor="#F4D35E" style="height:2px;background:#F4D35E;font-size:0;line-height:0;">&nbsp;</td></tr>
      </table>
    </td>
  </tr>
</table>

<!-- 方式二：border-top（更简单，Outlook 支持较好） -->
<table cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr><td style="border-top:2px solid #F4D35E;padding-top:20px;font-size:0;line-height:0;">&nbsp;</td></tr>
</table>
```

- 分割线长度 50-60px（不是全宽）
- 金色 2px，左对齐
- 上下各留 20px 间距

### 6.3 列表实现（不用 ul/ol）

邮件中不使用 `<ul>` / `<ol>`（Outlook 渲染不一致），用 table 模拟列表：

```html
<table cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <td width="20" valign="top" style="padding-top:2px;">
      <span style="color:#F4D35E;font-size:12px;">◆</span>
    </td>
    <td style="padding-bottom:12px;font-size:15px;line-height:1.8;color:#333;">
      第一个要点内容文字...
    </td>
  </tr>
  <tr>
    <td width="20" valign="top" style="padding-top:2px;">
      <span style="color:#F4D35E;font-size:12px;">◆</span>
    </td>
    <td style="padding-bottom:12px;font-size:15px;line-height:1.8;color:#333;">
      第二个要点内容文字...
    </td>
  </tr>
</table>
```

- 第一列 20px 宽，金色 `◆` 符号作为圆点
- 第二列文字内容，padding-bottom 控制项间距
- 不使用 CSS `list-style`

### 6.4 图片处理

```html
<img src="https://example.com/image.jpg" alt="图片描述" width="540" style="display:block;width:100%;max-width:540px;height:auto;border:0;outline:none;text-decoration:none;" border="0">
```

图片规则：
1. **必须使用绝对 URL**（`https://...`）
2. **必须设置 `width` 属性和 `style="width:100%"`**（响应式）
3. **必须设置 `alt` 文本**（图片被屏蔽时显示）
4. **加 `border="0"`**（消除链接图片的蓝色边框）
5. **加 `display:block`**（消除图片下方间隙）
6. **设置 `height:auto`**（保持比例）
7. **图片托管在可靠的 CDN/服务器**，URL 永久有效
8. **Logo 图片加品牌色背景的 alt 样式**（图片未加载时也可识别）：
   ```html
   <td bgcolor="#0A2463" style="background:#0A2463;padding:20px 40px;">
     <img src="logo.png" alt="Feihong 飞鸿" width="120" style="display:block;width:120px;border:0;" border="0">
   </td>
   ```

### 6.5 不使用/避免的元素

| 元素/效果 | 原因 |
|-----------|------|
| **`<div>` 做布局** | Outlook 中 div 渲染不可靠，用 table |
| **`<button>` 标签** | 各客户端渲染差异大，用 table 模拟 |
| **`margin` 在 p/div 上** | Outlook 中 margin 支持差，用 td padding |
| **`position` 定位** | 支持极差 |
| **flex / grid / float** | 完全不支持或支持差 |
| **`background-image` (CSS)** | Outlook 不支持，需要 VML |
| **border-radius** | Outlook 不支持，接受直角或用 VML |
| **box-shadow** | Outlook 不支持 |
| **JavaScript** | 完全不支持 |
| **`<iframe>` / `<video>` / `<audio>`** | 大部分客户端不支持 |
| **`<form>`** | 邮件中不使用表单 |
| **外部 CSS / `<link>`** | 不支持 |
| **web 字体 (@font-face)** | 大部分客户端不加载 |
| **CSS 动画 / transition** | 极少客户端支持 |
| **单px 间距用空白 gif** | 可用，但推荐用 padding/空td |

---

## 7. 特殊注意事项

### 7.1 Outlook 兼容性（VML 背景图）

如果需要在 Outlook 中显示背景图，必须使用 VML：

```html
<!--[if gte mso 9]>
<v:background xmlns:v="urn:schemas-microsoft-com:vml" fill="t">
  <v:fill type="tile" src="https://example.com/bg.jpg" color="#0A2463"/>
</v:background>
<![endif]-->
```

> **建议**：除非必要，避免使用背景图。用纯色背景 + 前景 `<img>` 标签代替更可靠。

### 7.2 纯文本版本

商业邮件应同时提供纯文本版本：
- 大部分邮件发送平台（Mailchimp、SendGrid、Mailgun 等）会自动生成
- 纯文本版本应包含与 HTML 版本相同的核心内容和链接
- 包含退订链接
- 纯文本版本有助于提高送达率（避免被判定为垃圾邮件）

### 7.3 商业邮件法律要求

1. **必须包含退订链接**（Unsubscribe link）：
   ```html
   <p style="font-size:12px;color:#999;line-height:1.5;">
     如果您不希望继续收到此类邮件，<a href="UNSUBSCRIBE_URL" style="color:#999;text-decoration:underline;">点击退订</a>。
   </p>
   ```
2. **必须包含发件人物理地址**（CAN-SPAM 法案要求）
3. **必须有明确的发件人信息**（公司名称/品牌名）
4. **主题行不能有误导性**
5. **退订链接必须有效**且在 10 个工作日内处理

### 7.4 避免触发垃圾邮件过滤器

避免以下 spam 触发词和做法：
- 避免全大写标题、过多感叹号
- 避免 spam 触发词："免费"、"中奖"、"限时优惠"、"点击这里"、"紧急"等（尤其是英文邮件中的 "Free!"、"Act now!"、"Limited time"）
- 图片与文字比例合理（不要全图邮件，至少 50% 文字）
- 不使用隐藏文字（与背景同色的文字）
- 不使用过多链接
- 发件人域名配置 SPF、DKIM、DMARC 记录
- 邮件列表使用 Double Opt-in（双重确认订阅）

### 7.5 邮件测试清单

发送前必须在以下环境测试：
- [ ] **Outlook 2016/2019 (Windows)** — 最严苛的测试
- [ ] **Gmail (Chrome)** — 网页版主流
- [ ] **Apple Mail (iPhone)** — 移动端主流
- [ ] **QQ邮箱 / 网易邮箱** — 国内主流
- [ ] **Outlook.com 网页版**
- [ ] **图片默认屏蔽状态**下是否仍可阅读（alt 文本、品牌色背景）
- [ ] **链接是否正确可点击**
- [ ] **退订链接是否有效**
- [ ] **移动端是否可正常显示**

可用测试工具：
- **Litmus**（付费，最全面）
- **Email on Acid**（付费）
- **Putsmail**（免费，发送测试邮件）
- **Mailtrap**（测试环境，不实际发送）

### 7.6 其他注意事项

1. **Doctype**：使用 `<!DOCTYPE html>` 或 XHTML 1.0 Strict
2. **meta viewport**：必须设置 `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
3. **X-UA-Compatible**：`<meta http-equiv="X-UA-Compatible" content="IE=edge">` 帮助旧版 IE/Outlook 渲染
4. **body reset**：`<body style="margin:0;padding:0;">` 消除默认边距
5. **表格 border/cellpadding/cellspacing 全部设为 0**，手动控制间距
6. **图片不要用 `style="width:100%"` 单独设置**，同时加 `width` 属性（Outlook 不识别 CSS width）
7. **长链接用短链服务**，避免 URL 过长撑破布局
8. **邮件大小控制在 100KB 以内**（代码部分），图片总大小控制在 500KB 以内

---

## 8. 场景专属 Checklist

在交付任何邮件 HTML 之前，必须通过以下检查：

### P0 — 必须通过（缺一不可）

- [ ] **使用 table 布局**，不是 div 布局
- [ ] **所有样式内联**在 style 属性中，无外部 CSS，无 class 依赖
- [ ] **无 JavaScript**，无 `<script>` 标签
- [ ] **邮件宽度固定 600px**，居中对齐
- [ ] **CTA 按钮用 table 模拟**（或 VML 子弹头按钮），不使用 `<button>` 标签
- [ ] **按钮可点击**：`<a>` 标签有正确的 href，padding 足够大（触摸友好）
- [ ] **图片使用绝对 URL**（含 https://）
- [ ] **所有背景色同时写 `bgcolor` 属性和 `style="background:..."`**
- [ ] **三种品牌色严格为 `#0A2463` / `#F4D35E` / `#D8315B`**
- [ ] **正文文字颜色 `#333333`**，字号 15-16px，行距 1.6-1.8
- [ ] **间距用 td 的 padding 控制**，不依赖 p/div 的 margin
- [ ] **cellpadding="0" cellspacing="0" border="0"** 在所有 table 上
- [ ] **图片有 alt 属性**，图片被屏蔽时仍可理解内容
- [ ] **Outlook 兼容基本样式**：无 flex/grid/position/border-radius 依赖
- [ ] **在至少一个主流客户端中测试通过**（Gmail 或 Apple Mail）

### P1 — 应该通过（尽量满足）

- [ ] **Preheader 预览文本**已设置，显示在收件箱标题旁
- [ ] **商业邮件包含退订链接**
- [ ] **Footer 包含发件人信息和物理地址**
- [ ] **金色装饰元素**：分隔线、列表圆点、引用边框
- [ ] **CTA 按钮用酒红 `#D8315B`**，是邮件中最醒目的元素
- [ ] **标题用衬线字体栈**（Georgia/Songti SC），正文用系统无衬线
- [ ] **图片有 `border="0"` 和 `display:block`**
- [ ] **有纯文本版本**
- [ ] **链接颜色为皇家蓝 `#0A2463`**，不用浏览器默认蓝色
- [ ] **段落间距舒适**，不拥挤不松散

### P2 — 加分项（锦上添花）

- [ ] **响应式**：移动端通过 `@media` 查询适配（Outlook 不支持，但 Gmail/Apple Mail 支持）
- [ ] **VML 子弹头按钮**：Outlook 中也有圆角按钮
- [ ] **VML 背景图**（如需要背景图）
- [ ] **暗色模式适配**：用 `@media (prefers-color-scheme: dark)` 适配
- [ ] **Logo 图片在品牌色背景上**（图片屏蔽时仍有品牌识别）
- [ ] **已在 Litmus/Email on Acid 中跨客户端测试**
- [ ] **邮件大小 < 100KB**（代码），加载快速
- [ ] **SPF/DKIM/DMARC 已配置**，送达率有保障

---

## 附录：邮件 HTML 完整骨架示例

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <title>飞鸿 Newsletter · 2026年7月</title>
  <!-- Preheader 预览文本 -->
  <span style="display:none;font-size:1px;color:#FDFBF6;line-height:1px;max-height:0;max-width:0;opacity:0;overflow:hidden;font-family:Arial,sans-serif;">
    本月精选：品牌设计系统更新 + 三个新场景规范发布 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  </span>
  <!--[if mso]>
  <noscript>
    <xml>
      <o:OfficeDocumentSettings>
        <o:PixelsPerInch>96</o:PixelsPerInch>
      </o:OfficeDocumentSettings>
    </xml>
  </noscript>
  <style type="text/css">
    table {border-collapse: collapse; mso-table-lspace: 0pt; mso-table-rspace: 0pt;}
    td, p, a {mso-line-height-rule: exactly;}
  </style>
  <![endif]-->
  <style type="text/css">
    @media only screen and (max-width: 620px) {
      .main-table { width: 100% !important; }
      .content-td { padding: 0 20px !important; }
      .mobile-center { text-align: center !important; }
    }
  </style>
</head>
<body bgcolor="#FDFBF6" style="margin:0;padding:0;background-color:#FDFBF6;font-family:-apple-system,BlinkMacSystemFont,'Segoe UI','Helvetica Neue',Arial,'PingFang SC','Microsoft YaHei',sans-serif;-webkit-text-size-adjust:100%;-ms-text-size-adjust:100%;">

  <!-- 外层包裹 -->
  <table cellpadding="0" cellspacing="0" border="0" width="100%" bgcolor="#FDFBF6" style="background-color:#FDFBF6;">
    <tr>
      <td align="center" style="padding:30px 0;">

        <!-- 主内容区 600px -->
        <table cellpadding="0" cellspacing="0" border="0" width="600" class="main-table" bgcolor="#FFFFFF" style="width:600px;max-width:600px;background-color:#FFFFFF;">

          <!-- Header -->
          <tr>
            <td bgcolor="#0A2463" align="left" style="background-color:#0A2463;padding:24px 40px;" class="content-td">
              <p style="margin:0;font-family:Georgia,'Noto Serif SC','Songti SC',serif;font-size:22px;font-weight:bold;color:#F4D35E;line-height:1.3;">Feihong 飞鸿</p>
            </td>
          </tr>

          <!-- Hero -->
          <tr>
            <td style="padding:40px 40px 30px;" class="content-td">
              <p style="margin:0 0 10px;font-family:Georgia,'Noto Serif SC','Songti SC',serif;font-size:30px;font-weight:bold;color:#0A2463;line-height:1.3;">
                本月精选
              </p>
              <p style="margin:0 0 25px;font-size:16px;line-height:1.7;color:#666;">
                品牌设计系统新增三个场景规范，覆盖小红书、公众号、邮件全渠道。
              </p>
              <!-- CTA 按钮 -->
              <table cellpadding="0" cellspacing="0" border="0" align="left">
                <tr>
                  <td bgcolor="#D8315B" style="background-color:#D8315B;border-radius:6px;">
                    <a href="https://example.com" target="_blank" style="display:inline-block;padding:14px 36px;font-family:-apple-system,sans-serif;font-size:16px;font-weight:bold;color:#FFFFFF;text-decoration:none;border-radius:6px;">
                      立即阅读
                    </a>
                  </td>
                </tr>
              </table>
            </td>
          </tr>

          <!-- 金色分隔线 -->
          <tr>
            <td style="padding:0 40px;" class="content-td">
              <table cellpadding="0" cellspacing="0" border="0" width="60" align="left">
                <tr><td height="2" bgcolor="#F4D35E" style="height:2px;background-color:#F4D35E;font-size:0;line-height:0;">&nbsp;</td></tr>
              </table>
            </td>
          </tr>

          <!-- Section 1 -->
          <tr>
            <td style="padding:30px 40px 10px;" class="content-td">
              <p style="margin:0 0 12px;font-family:Georgia,'Noto Serif SC',serif;font-size:20px;font-weight:bold;color:#0A2463;line-height:1.4;">
                新场景规范发布
              </p>
              <p style="margin:0 0 15px;font-size:15px;line-height:1.8;color:#333;">
                本月我们发布了三个全新的场景规范文件，覆盖社交媒体和邮件渠道的品牌一致性需求。
              </p>
              <!-- 金色圆点列表 -->
              <table cellpadding="0" cellspacing="0" border="0" width="100%">
                <tr>
                  <td width="20" valign="top" style="padding-top:3px;">
                    <span style="color:#F4D35E;font-size:12px;">◆</span>
                  </td>
                  <td style="padding-bottom:10px;font-size:15px;line-height:1.8;color:#333;">
                    <strong style="color:#0A2463;">小红书图文卡片规范</strong>：3:4 竖版，html2canvas 导出
                  </td>
                </tr>
                <tr>
                  <td width="20" valign="top" style="padding-top:3px;">
                    <span style="color:#F4D35E;font-size:12px;">◆</span>
                  </td>
                  <td style="padding-bottom:10px;font-size:15px;line-height:1.8;color:#333;">
                    <strong style="color:#0A2463;">公众号排版规范</strong>：内联样式，table 布局
                  </td>
                </tr>
                <tr>
                  <td width="20" valign="top" style="padding-top:3px;">
                    <span style="color:#F4D35E;font-size:12px;">◆</span>
                  </td>
                  <td style="padding-bottom:10px;font-size:15px;line-height:1.8;color:#333;">
                    <strong style="color:#0A2463;">邮件 EDM 规范</strong>：table 布局，Outlook 兼容
                  </td>
                </tr>
              </table>
            </td>
          </tr>

          <!-- 引用块 -->
          <tr>
            <td style="padding:20px 40px;" class="content-td">
              <table cellpadding="0" cellspacing="0" border="0" width="100%">
                <tr>
                  <td width="4" bgcolor="#F4D35E" style="width:4px;background-color:#F4D35E;"></td>
                  <td width="20" style="width:20px;"></td>
                  <td style="padding:15px 0;">
                    <p style="margin:0;font-family:Georgia,'Noto Serif SC',serif;font-size:17px;line-height:1.6;color:#0A2463;font-style:italic;">
                      真正的品牌一致性，是在每一个触点上都传递相同的品质感。
                    </p>
                  </td>
                </tr>
              </table>
            </td>
          </tr>

          <!-- CTA 区 -->
          <tr>
            <td style="padding:20px 40px 40px;" class="content-td" align="center">
              <p style="margin:0 0 20px;font-size:16px;line-height:1.6;color:#333;">
                想要了解更多品牌设计细节？
              </p>
              <table cellpadding="0" cellspacing="0" border="0" align="center">
                <tr>
                  <td bgcolor="#D8315B" style="background-color:#D8315B;border-radius:6px;">
                    <a href="https://example.com" target="_blank" style="display:inline-block;padding:14px 36px;font-family:-apple-system,sans-serif;font-size:16px;font-weight:bold;color:#FFFFFF;text-decoration:none;border-radius:6px;">
                      查看完整设计系统
                    </a>
                  </td>
                </tr>
              </table>
            </td>
          </tr>

          <!-- Footer -->
          <tr>
            <td bgcolor="#F5F5F5" style="background-color:#F5F5F5;padding:30px 40px;" class="content-td">
              <p style="margin:0 0 10px;font-size:13px;line-height:1.6;color:#666;text-align:center;">
                <strong style="color:#0A2463;">Feihong 飞鸿</strong> · 远见卓识
              </p>
              <p style="margin:0 0 10px;font-size:12px;line-height:1.6;color:#999;text-align:center;">
                邮箱：hello@example.com &nbsp;|&nbsp; 网站：example.com
              </p>
              <p style="margin:0;font-size:11px;line-height:1.5;color:#999;text-align:center;">
                您收到此邮件是因为您订阅了飞鸿 Newsletter。<br>
                如果不希望继续收到，<a href="UNSUBSCRIBE_URL" style="color:#999;text-decoration:underline;">点击退订</a>。<br>
                公司地址：XX市XX区XX路XX号
              </p>
            </td>
          </tr>

        </table>
        <!-- /主内容区 -->

      </td>
    </tr>
  </table>

</body>
</html>
```

---

## 场景定位

邮件/EDM/Newsletter是以邮件为载体的品牌内容传播和商业通讯形态，用于Newsletter订阅推送、产品/活动通知、欢迎邮件、商务邮件、事务性邮件（订单确认/密码重置）等需要在各种邮件客户端中可靠渲染的HTML内容。适用于：Newsletter周报/月报、产品更新通知、活动邀请、促销通知、欢迎序列邮件、商务提案邮件、事务性邮件。不适用于：网页设计（用Portfolio/Landing）、公众号文章（用WeChat）、即时通讯（邮件是异步通讯）。核心原则是"Outlook兼容第一、600px固定宽度、table布局、内联样式"——在Gmail/Outlook/Apple Mail/QQ邮箱/网易邮箱等所有主流客户端中都能正常显示，图片被屏蔽时品牌色和排版仍然可识别，CTA按钮清晰可点击。

## 推荐节奏（Section 序列）

邮件场景的"节奏"是固定600px宽度内从上到下的模块排列：

### 方案 A：Newsletter内容型（最常用，500-2000字）
1. Preheader预览文字（隐藏，收件箱预览行）
2. Header头部（皇家蓝背景+Logo/品牌名金色文字）
3. Hero区（大标题皇家蓝衬线+副标题+主CTA按钮酒红）
4. 金色短分割线
5. Section 1（小标题皇家蓝+正文段落+金色圆点列表）
6. 金色短分割线
7. Section 2（小标题+正文+配图或引用块）
8. CTA重复区（居中文字+酒红按钮）
9. Footer（浅灰背景+品牌信息+退订链接+地址）

### 方案 B：产品/活动通知型（300-800字，行动导向）
1. Preheader（行动导向文案，如"限时8折|立即查看"）
2. Header（白底+Logo左对齐，简洁）
3. Hero区（配图+大标题+副标题+酒红CTA按钮）
4. 核心信息（金色圆点列表3-5条关键信息）
5. 附加说明（灰色小字，条款/细则）
6. CTA按钮重复
7. Footer（标准）

### 方案 C：欢迎/Onboarding型（200-600字，温暖引导）
1. Preheader（欢迎语+核心价值）
2. Header（皇家蓝背景+Logo）
3. 欢迎Hero（大标题"欢迎加入"+亲切的欢迎语+酒红"开始使用"按钮）
4. 三步引导（金色数字01/02/03+简短说明，可用table三栏或垂直排列）
5. 帮助资源链接（皇家蓝链接列表）
6. Footer（标准）

### 方案 D：商务/提案型（200-1000字，专业正式）
1. Preheader（提案/报价主题）
2. Header（极简白底+品牌名）
3. 称呼（"尊敬的XX先生/女士，"）
4. 正文段落（正式商务语气，皇家蓝小标题分节）
5. 核心提案/报价信息（可用table表格呈现数据）
6. 金色分割线
7. 行动请求（明确的下一步+联系方式）
8. 落款（个人/公司名+签名）
9. Footer（极简）

### 方案 E：事务性邮件型（极精简，订单确认/密码重置）
1. Preheader（事务信息，如"您的订单#12345已确认"）
2. Header（白底+Logo极简）
3. 核心信息（大标题确认状态+1-2句说明+关键信息表格）
4. 订单/操作详情（table表格，数据行）
5. 帮助链接（如有问题联系客服）
6. Footer（标准法律信息）

## 专属装饰手法（Signature Touches）

邮件场景装饰比公众号更加克制（Outlook兼容性限制），但品牌签名依然清晰：

- **#07 Decorative Rule 金色短分割线**：用1px高金色td或border-top实现50-60px长金色短线，分隔section，是邮件最稳定的装饰签名（Outlook可靠）
- **#14 Section Marker 衬线标题**：标题用Georgia+Times New Roman+Noto Serif SC衬线字体栈+皇家蓝色，模拟Playfair Display的经典感
- **#18 Badge & Stamp 金色标签**：用bgcolor金色td+皇家蓝字实现badge标签，用于"NEW"/"更新"等标记
- **#20 Numbered Index 金色菱形列表符**：用`◆`金色字符在table两列布局中实现列表（左列20px放金色◆，右列放文字），不用ul/ol
- **#04 Pull Quote 金色左边框引用块**：用嵌套table实现4px金色左边框+内容区，引用金句（注意：不依赖border-left，用一列窄td做边框）
- **#16 Alert Box 酒红CTA按钮**：用嵌套table+bgcolor:#D8315B实现酒红按钮，是邮件中最重要的行动元素（子弹头按钮VML方案兼容Outlook圆角）
- **#15 Divider 皇家蓝Header区**：Header行用bgcolor:#0A2463皇家蓝背景+金色品牌名文字，建立第一印象的品牌识别
- **Preheader隐藏文本**：在head中用display:none的span设置预览文字，显示在收件箱标题旁，影响打开率
- **金色Logo句号**：品牌名"Feihong 飞鸿"后的金色句号，延续品牌签名（用`<span style="color:#F4D35E;">。</span>`）
- **浅色Footer区**：Footer用bgcolor:#F5F5F5浅灰背景（注意：冷灰#F5F5F5在邮件中可接受，因为Footer是功能区），区分正文
- **alt文本品牌化**：Logo图片alt文本设置品牌名，图片被屏蔽时仍可识别；配图alt描述图片内容
- **VML子弹头按钮**（高级）：用VML条件注释为Outlook提供圆角按钮，其他客户端用CSS border-radius

## 推荐布局组合

邮件场景布局全部用table实现，选择非常克制：

| 布局 | 名称 | 适用位置 | 说明 |
|------|------|----------|------|
| **单栏垂直流** | 600px单栏 | 正文主体（默认必选） | 所有内容垂直堆叠在600px主table中，最兼容 |
| **Header品牌条** | 皇家蓝/白底头部 | 邮件顶部（必选） | 一行table，Logo+品牌名，高度60-80px |
| **Hero区** | 标题+副标题+CTA | Header之后（必选） | 大标题28-32px+副标题+主按钮 |
| **金色引用块table** | 左边框金句 | 正文中穿插 | 三列嵌套table：4px金边+间距+内容 |
| **两栏table**（慎用） | 图文并排/双列 | 产品展示/三步引导 | 50%+50%两td，移动端变单栏需媒体查询（Outlook不支持） |
| **酒红CTA块** | 行动区 | Hero区、邮件结尾（必选） | 居中嵌套table，bgcolor:#D8315B+白色文字按钮 |
| **数据table** | 表格数据 | 订单详情/报价/对比 | 标准table行，金色表头bgcolor+皇家蓝字 |
| **Footer区** | 页脚 | 邮件底部（必选） | 浅灰/蓝色bgcolor，退订链接+地址+联系方式 |

## 色彩策略

邮件场景色彩策略核心：外层暖米白，内容区纯白，皇家蓝品牌识别+Header，金色装饰线/点缀，酒红CTA按钮。图片被屏蔽时色彩仍传达品牌。

**皇家蓝 #0A2463（55%，品牌识别）**
- Header头部背景色（bgcolor="#0A2463"同时写style background）
- 所有标题文字颜色（Hero大标题、section小标题）
- 链接文字颜色（不用浏览器默认蓝）
- 金色badge上的文字颜色
- 数据表格表头背景色（金色底上皇家蓝字，或皇家蓝底上金字）
- 深色背景块（如需强调section）
- **所有背景色必须同时写HTML bgcolor属性和CSS background属性**

**复古金 #F4D35E（30%，装饰点缀）**
- section之间的金色短分割线
- 引用块的4px左边框（用窄td bgcolor实现）
- 金色菱形`◆`列表符号
- Header皇家蓝背景上的品牌名/Logo文字颜色
- badge标签背景色
- 数据表格表头背景色（可选）
- 金色Logo句号
- **白底上绝对不用金色文字**（对比度不足）
- **金色仅在深色背景（皇家蓝）上作为文字色**
- **金色面积小而精致，用于线、点、边框、小块背景**

**酒红 #D8315B（15%，CTA按钮）**
- CTA按钮背景色（邮件中最重要的行动元素，必须是酒红）
- 按钮文字白色#FFFFFF
- 极少数需要极强强调的文字（`<strong style="color:#D8315B;">`）
- **酒红=行动/CTA，绝不用于普通文字或大面积背景（除CTA区块外）**
- **CTA按钮是邮件中唯一的酒红大面积色块**

**背景与中性色**：
- 邮件最外层背景：暖米白`#FDFBF6`（body bgcolor+外层table bgcolor）
- 内容区背景：纯白`#FFFFFF`（600px主table bgcolor）
- Header背景：皇家蓝`#0A2463`
- CTA区背景：白色`#FFFFFF`或酒红`#D8315B`（依设计）
- Footer背景：浅灰`#F5F5F5`（功能区，冷灰可接受）或皇家蓝
- 正文：深灰`#333333`（非纯黑#000）
- 辅助文字：中灰`#666666`
- Footer小字：`#999999`
- **所有颜色同时写bgcolor属性和style="background:..."双保险**

## 场景禁忌（Don'ts）

1. **使用div做布局**：Outlook（Word渲染引擎）中div不可靠，所有布局必须用`<table>`
2. **使用`<button>`标签**：各客户端渲染差异巨大，CTA按钮必须用嵌套table+`<a>`模拟
3. **依赖margin在p/div上控制间距**：Outlook中margin支持差，所有间距用`<td>`的padding控制
4. **使用flex/grid/float/position**：完全不支持或支持极差
5. **使用border-radius/box-shadow依赖圆角阴影**：Outlook不支持，必须接受直角或用VML实现
6. **使用web字体（@font-face/Google Fonts）**：大部分客户端不加载，会FOIT，必须用系统字体
7. **使用CSS background-image**：Outlook 2007-2019不支持，需要VML；建议用纯色背景+前景img标签
8. **邮件宽度超过600px**：行业标准600px，超过在很多客户端和预览窗格中显示异常
9. **CTA按钮不用酒红色**：酒红=行动，这是品牌识别的核心，按钮必须是酒红底白字
10. **图片只写src不写alt**：大部分客户端默认屏蔽图片，alt文本是图片被屏蔽时的唯一信息
11. **背景色只写style不写bgcolor属性**：Outlook只认bgcolor属性，必须双写
12. **使用JavaScript**：所有邮件客户端都会过滤JS
13. **邮件代码超过100KB**：Gmail会截断超过102KB的邮件，代码要精简
14. **忘记退订链接**：商业邮件法律要求必须有退订链接（CAN-SPAM法案）
15. **全图邮件（Image-only）**：图片被屏蔽时用户什么都看不到，且容易触发垃圾邮件过滤，至少50%文字

## 场景专属Checklist

- [ ] 所有布局用`<table>`实现（cellpadding=0 cellspacing=0 border=0），不用div/flex/grid
- [ ] 所有样式内联在style属性中，无外部CSS依赖（`<style>`仅用于媒体查询）
- [ ] 无JavaScript代码，无`<script>`标签
- [ ] 主内容区宽度固定600px居中（width="600"+style width:600px;max-width:600px）
- [ ] CTA按钮用嵌套table模拟（或VML子弹头按钮），不用`<button>`标签
- [ ] CTA按钮为酒红色`#D8315B`底+白色文字，padding足够触摸友好（14px 32px+）
- [ ] 所有背景色同时写`bgcolor`属性和`style="background:..."`（Outlook兼容）
- [ ] 三种品牌色严格为`#0A2463`/`#F4D35E`/`#D8315B`
- [ ] 外层背景暖米白`#FDFBF6`，内容区纯白`#FFFFFF`
- [ ] 间距全部用td的padding控制，不依赖p/div的margin
- [ ] Preheader预览文本已设置（display:none隐藏span，显示在收件箱标题旁）
- [ ] 图片使用绝对URL（https://），有alt属性，有border="0"和display:block
- [ ] 列表用金色`◆`符号+table两列布局实现，不用ul/ol
- [ ] section之间有金色短分割线（50-60px，2px）
- [ ] 标题用衬线字体栈（Georgia/'Times New Roman'/'Noto Serif SC'/serif）
- [ ] 正文15-16px，行距1.6-1.8，颜色#333333
- [ ] 金色不在白底上做文字色（仅装饰线/边框/符号/深色底上文字）
- [ ] Header有品牌识别（Logo/品牌名+皇家蓝或白底）
- [ ] Footer包含退订链接、发件人信息、物理地址（商业邮件法律要求）
- [ ] 已在至少Outlook 2016+/Gmail/Apple Mail/QQ邮箱中测试通过
- [ ] 图片默认屏蔽状态下仍可理解核心内容（alt文本+品牌色背景）
- [ ] 邮件HTML代码<100KB，不被Gmail截断
- [ ] 链接有正确href和target="_blank"
- [ ] 有纯文本版本（提升送达率）
- [ ] SPF/DKIM/DMARC已配置（送达率保障）

---

*Scene: Email / EDM (邮件排版) v1.0 · Feihong Design System*
*基于 brand-dna.md v2.0 · 最后更新：2026-07-08*
