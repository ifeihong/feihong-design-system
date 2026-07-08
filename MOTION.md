# Feihong Design System — Motion Language
# 飞鸿品牌设计系统 · 动效规范

> ⚠️ **本文件是 Feihong Design System 的「动效宪法」** — 所有组件、页面、场景中的动画行为均以此为唯一准绳。
> 修改本文件意味着改变整个品牌的时间语言，请以对待品牌基因的审慎态度对待每一个数值。
>
> *Motion is not decoration. It is the choreography of attention.*
> *动效不是装饰，是注意力的编舞。*

---

## 📑 目录 / Table of Contents

1. [设计哲学 / Design Philosophy](#-设计哲学--design-philosophy)
2. [Feihong Easing — 统一缓动曲线](#-feihong-easing--统一缓动曲线)
3. [Duration Scale — 时长层级](#-duration-scale--时长层级)
4. [Three Motion Principles — 动效三原则](#-three-motion-principles--动效三原则)
5. [Easing Variants — 缓动变体](#-easing-variants--缓动变体)
6. [Stagger Delay — 交错延迟](#-stagger-delay--交错延迟)
7. [Reduced Motion Policy — 降级策略](#-reduced-motion-policy--降级策略)
8. [Forbidden Patterns — 禁止项](#-forbidden-patterns--禁止项)
9. [CSS Custom Properties — CSS 变量定义](#-css-custom-properties--css-变量定义)
10. [Implementation Checklist — 交付自检](#-implementation-checklist--交付自检)

---

## 🎭 设计哲学 / Design Philosophy

在 Feihong 的世界里，动效从来不是炫技的工具，而是 **空间的延伸、层级的叙事、呼吸的节奏**。

我们追求的动效语言是：**像高级定制时装的裙摆——在行走间自然垂落，有重量感，有空气感，但从不刻意摆动。**

| 特质 Quality | 含义 Meaning |
|-------------|-------------|
| **Weighted 有重量** | 元素不是飘入，而是沉稳地落位；有加速度，有惯性，但不弹 |
| **Deliberate 从容** | 不急于消失，不抢着出现；给用户足够时间感知变化 |
| **Refined 精致** | 曲线精确到小数点后两位，时长精确到 10ms 级别 |
| **Invisible 隐形** | 好的动效用户不会注意到它的存在，只会觉得"顺畅" |

> *"Good motion is felt, not seen."*
> *"好的动效是被感知的，不是被注意到的。"*

---

## 🎻 Feihong Easing — 统一缓动曲线

### The Signature Curve / 签名曲线

```
cubic-bezier(0.16, 1, 0.3, 1)
```

这是 Feihong Design System 唯一的 **标准出场缓动**（`--ease-out`），所有元素入场、悬停反馈、展开收起均默认使用此曲线。

### Why This Curve? / 为什么是这条曲线？

| 特征 Characteristic | 技术解析 Technical | 气质感受 Feeling |
|---------------------|-------------------|-----------------|
| **快速启动 (fast start)** | x1=0.16 意味着动画在极短时间内获得初速度，避免"慢吞吞"的迟钝感 | 响应迅速、不拖沓，给人"一切尽在掌控"的笃定感 |
| **温和减速 (gentle deceleration)** | y1=1 表示控制点达到最大输出值，元素以接近线性的高速冲入，然后优雅地减速归位 | 像天鹅降落——水面上的从容之下是看不见的加速 |
| **自然收束 (natural settle)** | x2=0.3, y2=1 确保终点没有过冲(overshoot)，没有回弹(bounce) | 沉稳落位，不弹跳、不浮夸，符合品牌"智者/统治者"原型的克制气质 |

这条曲线在业界被称为 **"Expo Out"** 家族的一员，被 Linear、Vercel、Apple 等追求极致品质感的产品广泛采用。它的气质是：**专业、笃定、从容、不讨好**——与 Feihong 品牌基因完美契合。

### 视觉对比 / Visual Comparison

| 缓动函数 | 感觉 | Feihong 使用？ |
|---------|------|---------------|
| `cubic-bezier(0.16, 1, 0.3, 1)` | 快速启动、优雅落位、无过冲 | ✅ **标准出场** |
| `ease` (0.25, 0.1, 0.25, 1) | 中庸、无个性、像浏览器默认 | ❌ 不使用 |
| `linear` | 机械、僵硬、无生命感 | ❌ 仅用于 opacity 极微动效 |
| `cubic-bezier(0.34, 1.56, 0.64, 1)` | 有过冲、弹、活泼 | ❌ 禁止——轻浮 |
| `cubic-bezier(0.68, -0.55, 0.27, 1.55)` | 大幅回弹、玩具感 | ❌ 严禁——幼稚 |

---

## ⏱️ Duration Scale — 时长层级

时长不是凭感觉选的，而是根据 **元素的尺寸、移动距离和语义权重** 精确匹配。

| Token | 时长 Duration | 场景 Scenario | 典型用例 Examples | 缓动 Easing |
|-------|--------------|--------------|-------------------|-------------|
| `--duration-micro` | **150–200ms** | Micro-interactions / 微交互 | 按钮悬停、开关切换、图标状态变化、输入框focus、标签选中 | `--ease-out` |
| `--duration-sm` | **250–350ms** | Small transitions / 小组件过渡 | Toast 出现、Tooltip 显示、下拉菜单展开、标签页切换 | `--ease-out` |
| `--duration-md` | **400–600ms** | Component entrance / 组件入场 | 卡片浮现、模态框弹出、面板滑入、内容块 Scroll Reveal | `--ease-out` |
| `--duration-lg` | **800–1200ms** | Page transitions / 页面级过渡 | 页面切换、Hero区域入场、大面积布局变化、首屏加载序列 | `--ease-out` + stagger |
| `--duration-ambient` | **3–6s** | Ambient animations / 环境呼吸 | 背景微妙光晕漂移、装饰元素极缓位移、状态指示灯pulse | `--ease-in-out` (loop) |

### 时长原则 / Duration Principles

1. **越大的元素动越慢** — 按钮(小)150ms，卡片(中)400ms，页面(大)800ms+
2. **入场快、离场更快** — 元素离开视野的时间约为入场的 60-70%，不阻挡用户的下一个动作
3. **移动距离越长，时长越长** — 横跨屏幕的导航抽屉需要 400ms，同位置的opacity变化只需 150ms
4. **永远不用 < 100ms** — 低于100ms的动画用户感知为"闪烁"而非"过渡"
5. **永远不用 > 1500ms** — 超过1.5s的动画会被感知为"卡顿"或"拖沓"（环境动画除外）

---

## 🏛️ Three Motion Principles — 动效三原则

所有动效决策必须同时满足以下三条原则，缺一不可。

### 1. Purposeful / 有目的

> *Every animation answers a question.*
> *每一个动画都在回答一个问题。*

| 合理解目的 Valid Purpose | 说明 Description |
|------------------------|-----------------|
| **空间关系 Spatial** | 告诉用户元素从哪来、到哪去，建立心智模型（如：抽屉从侧边滑出说明它"属于"侧边） |
| **层级焦点 Hierarchical** | 引导注意力到最重要的变化上（如：新消息卡片从上方滑入，用户自然看向它） |
| **反馈确认 Feedback** | 告诉用户"你的操作已被感知"（如：按钮按下时的缩放、表单提交后的成功状态） |
| **状态过渡 State** | 在两个状态之间架桥，避免突变带来的认知断裂（如：手风琴展开、暗色模式切换） |
| **情绪基调 Mood** | 极克制地传递品牌气质（如：首屏Hero的从容入场建立"沉稳"的第一印象） |

**❌ 没有目的的动画 = 视觉噪音。** 如果一个动画不能归入以上任何一类，删掉它。

### 2. Elegant / 优雅

> *Motion should feel like a silk scarf falling, not a rubber band snapping.*
> *动效应像丝巾垂落，而非橡皮筋弹回。*

- **缓入缓出**：所有位移和缩放动画必须使用非缓动(non-linear)曲线，绝不用 `linear`
- **自然物理感**：遵循"快入慢出"（ease-out）的自然规律——现实中物体都是先加速后减速落地
- **不弹跳、不过冲**：禁止 bounce、elastic、spring 过冲效果。Feihong 的世界里没有橡皮筋
- **流畅不突兀**：动画起点和终点在视觉上连续，没有"跳帧"感
- **材质感**：阴影和透明度随动画自然变化（如：浮起的卡片阴影同步加深，而不是突然变）

### 3. Restrained / 克制

> *Restraint is the ultimate luxury.*
> *克制是终极的奢华。*

- **一屏 ≤ 3 个同时动画**：同一视口内同时进行的动画不超过 3 个，避免视觉混乱
- **动效覆盖率 < 30%**：不是每个元素都需要动。静态的留白本身就是一种节奏
- **Scroll Reveal 只做一次**：元素滚入视口时触发一次 reveal，不反复触发
- **不抢内容风头**：动效永远服务于内容阅读，不能为了炫技而干扰信息获取
- **装饰性动画极弱**：纯装饰动效（呼吸光、漂浮粒子）透明度 ≤ 0.1，速度极慢(3s+)，且一屏最多1个

---

## 🎼 Easing Variants — 缓动变体

Feihong 定义 **三个缓动变量**，覆盖所有动画场景。没有第四种。

| Token | CSS Value | 语义 Semantic | 使用场景 Usage | 曲线特征 Character |
|-------|-----------|--------------|----------------|-------------------|
| `--ease-out` | `cubic-bezier(0.16, 1, 0.3, 1)` | **标准出场** / Standard exit | 元素入场、悬停反馈、展开、出现、reveal | 快入慢出，沉稳落位 |
| `--ease-in` | `cubic-bezier(0.7, 0, 0.84, 0)` | **元素离场** / Element exit | 元素离开视野、收起、关闭、消失 | 慢入快出，加速离去 |
| `--ease-in-out` | `cubic-bezier(0.65, 0, 0.35, 1)` | **状态切换** / State toggle | 双向切换（开关、暗色模式、折叠/展开双向）、循环呼吸 | 对称缓动，首尾温和 |

### 选用决策树 / Selection Decision Tree

```
元素是第一次出现吗？
  ├─ 是 → --ease-out（欢迎入场，优雅到位）
  └─ 否 → 元素是在两个状态间切换吗？
            ├─ 是（双向）→ --ease-in-out（对称过渡）
            └─ 否（消失）→ --ease-in（加速离场，不拖泥带水）
```

### 特殊场景 / Special Cases

| 场景 | 推荐缓动 | 备注 |
|------|---------|------|
| 仅 opacity 变化（无位移/缩放） | `--ease-out` 或 `linear` | opacity对缓动不敏感，极短时长下linear也可接受 |
| 颜色过渡（color/background） | `--ease-in-out` | 颜色是对称变化，不需要方向性 |
| transform: scale 按压反馈 | `--ease-out` (按下) + `--ease-out` (释放) | 按压和释放都用ease-out，时长150ms |
| 路径动画/描边动画 | `--ease-in-out` | 沿路径运动对称缓动最自然 |

---

## 🪜 Stagger Delay — 交错延迟

当多个同类元素需要依次入场时（如卡片组、列表项、导航项），使用 **交错延迟** 创造秩序感和仪式感。

### 规则 / Rules

| 参数 Parameter | 值 Value | 说明 Description |
|---------------|---------|-----------------|
| **基础延迟 Base delay** | `0ms` | 第一个元素无延迟，立即开始 |
| **交错增量 Stagger step** | **50–100ms** (`--stagger-step`) | 每个后续元素增加的延迟 |
| **最大总延迟 Max total** | `≤ 600ms` | 无论多少元素，最后一个元素的延迟不超过600ms（否则用户会觉得"慢"） |
| **动画时长 Duration** | 各元素自身的入场时长（micro/md/lg） | 交错元素并行播放，不是等前一个播完 |

### 计算公式 / Formula

```
delay(n) = min(n * --stagger-step, 600ms)
```

### 示例 / Example

```css
/* 卡片组入场：每张卡片延迟递增80ms */
.card {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 500ms var(--ease-out),
              transform 500ms var(--ease-out);
}

.card.visible {
  opacity: 1;
  transform: translateY(0);
}

.card:nth-child(1) { transition-delay: 0ms; }
.card:nth-child(2) { transition-delay: 80ms; }
.card:nth-child(3) { transition-delay: 160ms; }
.card:nth-child(4) { transition-delay: 240ms; }
.card:nth-child(5) { transition-delay: 320ms; }
/* nth-child(n): delay = min((n-1) * 80ms, 600ms) */
```

### 交错原则 / Stagger Principles

1. **只用于入场，不用于离场** — 元素离场时同时消失，干净利落
2. **同类元素才交错** — 不同类型的元素（标题+卡片+按钮）不需要机械交错，按层级自然编排
3. **延迟从"视觉焦点"开始向外扩散** — 不一定从上到下，从最重要的元素开始
4. **移动端慎用** — 小屏幕上stagger可以缩短到30-50ms，减少等待感

---

## ♿ Reduced Motion Policy — 降级策略

> *Accessibility is not optional. It is foundational.*
> *可访问性不是可选项，是基础。*

所有动画 **必须** 尊重用户的 `prefers-reduced-motion` 系统设置。这不是"加分项"，是硬性门槛。

### 策略 / Policy

| 用户设置 | 行为 Behavior |
|---------|--------------|
| `no-preference`（默认） | 正常播放所有动画 |
| `reduce`（用户开启减少动画） | **大幅降级** — 见下方规则 |

### 降级规则 / Reduction Rules

当检测到 `prefers-reduced-motion: reduce` 时：

1. **移除所有非必要动画**：Scroll Reveal、stagger入场、装饰性动效、hover缩放 → 全部取消，元素直接显示
2. **保留功能性过渡**：保留 ≤ 200ms 的opacity/color状态反馈（如按钮hover、表单focus），让用户仍能感知交互
3. **禁用自动播放动画**：所有自动触发的动画（包括ambient呼吸动画）停止
4. **保留loading状态**：loading spinner/pulse 可以保留（因为它们传达"正在加载"的关键信息），但应简化为静态指示器或更慢的pulse
5. **无动画模式下，用即时状态切换替代过渡**：`transition: none` 或 `transition-duration: 0ms`

### CSS 实现 / CSS Implementation

```css
/* 默认：完整动效 */
.some-element {
  transition: opacity 500ms var(--ease-out),
              transform 500ms var(--ease-out);
}

/* 降级模式 */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

> ⚠️ **注意**：上面的全局降级代码必须出现在所有 Feihong 模板的 CSS 中。这是P0门槛。

---

## 🚫 Forbidden Patterns — 禁止项

以下动效模式在 Feihong Design System 中 **严格禁止**，无例外。

| ❌ 禁止项 Forbidden | 原因 Why It's Banned | ✅ 替代方案 Use Instead |
|--------------------|---------------------|----------------------|
| **Bounce / Elastic / Spring 弹跳动画** | 轻浮、玩具感、像聊天软件的表情包动效，破坏沉稳专业的品牌气质 | `--ease-out` 优雅落位 |
| **过冲 Overshoot** (控制点y > 1) | 夸张、不稳重、有"讨好"感 | 精确止于终点值的 `cubic-bezier(0.16, 1, 0.3, 1)` |
| **无限循环动画** (除loading和极subtle pulse外) | 持续争夺注意力，干扰阅读，造成焦虑 | 动画仅在交互/入场时触发，单次播放；ambient动画opacity ≤ 0.1, duration ≥ 3s |
| **AI 光效动画**（发光、glow、shimmer、光斑扫过、iridescent） | 典型AI生成痕迹，廉价科技感，2024-2025的过时潮流 | 真实阴影、微妙径向渐变、金色静态装饰 |
| **Shimmer 骨架屏扫光** | 过度使用、像AI模板、分散注意力 | 使用纯色或微妙pulse的骨架屏，opacity 0.3-0.5 |
| **Parallax 大视差滚动** | 容易引起晕动症、性能差、喧宾夺主 | 极弱的视差（位移比 ≤ 1:1.1）或不用 |
| **Flip / 3D Rotation 翻转** | 花哨、像PPT特效、不专业 | opacity + 位移 的平面过渡 |
| **Glitch / 故障效果** | 刻意制造"损坏"感，与品牌"智者/统治者"原型相悖 | 干净的状态切换 |
| **Typewriter 打字机效果** | 拉长等待时间、影响阅读、过时 | 直接显示文本，可用fade-in替代 |
| **Count-up 数字滚动**（首页大数字） | 炫技、无实际信息量、干扰 | 数字直接显示，不需要滚动 |
| **渐变动画 (gradient animation)** | GPU消耗大、闪烁、不优雅 | 静态渐变，不做动画 |
| **Box-shadow 动画**（从无到有的阴影动画） | 性能差（触发重绘）、不流畅 | 用opacity预渲染阴影，或用transform+伪元素替代 |
| **使用 `all` 作为 transition 属性** | 不可控、性能差、容易意外动画其他属性 | 明确列出需要过渡的属性：`transition: opacity, transform` |

### 性能铁律 / Performance Rules

- **只动画 `transform` 和 `opacity`**：这两个属性由GPU合成层处理，不触发重排(relow)和重绘(repaint)
- **避免动画**：`width`, `height`, `top`, `left`, `margin`, `padding`, `box-shadow`, `background-position`
- **使用 `will-change` 但不滥用**：仅在确实需要优化的元素上使用，且动画结束后移除
- **使用 `requestAnimationFrame`**：JS动画必须使用rAF，不用setTimeout/setInterval
- **60fps 目标**：所有动画在中端设备上保持60fps，移动端不低于30fps

---

## 🎛️ CSS Custom Properties — CSS 变量定义

以下变量必须在全局 `:root` 中定义，与 `DNA.md` 中的色彩、字体、间距变量保持同层级。

```css
:root {
  /* ============================================
     FEIHONG MOTION TOKENS
     飞鸿动效系统变量 · v1.0
     ============================================ */

  /* --- Easing Curves 缓动曲线 --- */
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);     /* 标准出场 · Standard entrance / reveal */
  --ease-in: cubic-bezier(0.7, 0, 0.84, 0);      /* 元素离场 · Element exit / dismiss */
  --ease-in-out: cubic-bezier(0.65, 0, 0.35, 1); /* 状态切换 · State toggle / ambient */

  /* --- Duration Scale 时长层级 --- */
  --duration-micro: 150ms;   /* 微交互 · Micro-interactions: hover, focus, press */
  --duration-micro-max: 200ms;
  --duration-sm: 300ms;      /* 小组件 · Small transitions: toast, tooltip, menu */
  --duration-sm-min: 250ms;
  --duration-sm-max: 350ms;
  --duration-md: 500ms;      /* 组件入场 · Component entrance: card, modal, panel */
  --duration-md-min: 400ms;
  --duration-md-max: 600ms;
  --duration-lg: 1000ms;     /* 页面过渡 · Page transitions: hero, layout shift */
  --duration-lg-min: 800ms;
  --duration-lg-max: 1200ms;
  --duration-ambient: 4s;    /* 环境呼吸 · Ambient breathing (range: 3-6s) */

  /* --- Stagger 交错延迟 --- */
  --stagger-step: 80ms;      /* 交错增量 · Delay between sibling elements */
  --stagger-step-min: 50ms;
  --stagger-step-max: 100ms;
  --stagger-max-delay: 600ms;/* 最大总延迟 · Cap for last element */

  /* --- Motion Properties 常用动效属性 --- */
  --transition-base: opacity var(--duration-md) var(--ease-out),
                     transform var(--duration-md) var(--ease-out);
  --transition-fast: opacity var(--duration-micro) var(--ease-out),
                     transform var(--duration-micro) var(--ease-out);
  --transition-color: color var(--duration-sm) var(--ease-in-out),
                      background-color var(--duration-sm) var(--ease-in-out),
                      border-color var(--duration-sm) var(--ease-in-out);

  /* --- Transform Presets 变换预设 --- */
  --reveal-offset-y: 24px;    /* Scroll reveal 垂直入场距离 */
  --reveal-offset-x: 32px;    /* 水平滑入距离 */
  --press-scale: 0.97;        /* 按钮按下缩放 */
  --hover-lift: -2px;         /* 悬停上浮距离 */
  --hover-scale: 1.02;        /* 悬停放大比例 */

  /* --- Ambient Opacity 环境动效透明度上限 --- */
  --ambient-opacity-max: 0.1; /* 纯装饰动效最大透明度 */
}
```

### 动效工具类 / Utility Classes (可选)

```css
/* 基础入场动效 */
.feihong-reveal {
  opacity: 0;
  transform: translateY(var(--reveal-offset-y));
  transition: var(--transition-base);
  will-change: opacity, transform;
}
.feihong-reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}

/* 按钮悬停/按压 */
.feihong-interactive {
  transition: transform var(--duration-micro) var(--ease-out),
              box-shadow var(--duration-micro) var(--ease-out);
}
.feihong-interactive:hover {
  transform: translateY(var(--hover-lift)) scale(var(--hover-scale));
}
.feihong-interactive:active {
  transform: scale(var(--press-scale));
}

/* Reduced Motion 全局降级（必须包含） */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }

  .feihong-reveal {
    opacity: 1;
    transform: none;
  }
}
```

---

## ✅ Implementation Checklist — 交付自检

> 任何包含动效的 Feihong 设计交付前，必须通过以下检查。

### 🔴 P0 — 必须通过

- [ ] 所有动画使用 `cubic-bezier(0.16, 1, 0.3, 1)` 作为标准出场缓动，未使用 `linear`/`ease`/`bounce`/`elastic`
- [ ] 时长符合 Duration Scale：微交互 ≤ 200ms，组件入场 400-600ms，页面过渡 800-1200ms
- [ ] 已实现 `prefers-reduced-motion: reduce` 降级，非必要动画在降级模式下全部移除
- [ ] 同一视口内同时动画 ≤ 3 个
- [ ] 没有出现"禁止项"清单中的任何动效模式（bounce、无限循环、AI光效、shimmer等）
- [ ] 动画仅作用于 `transform` 和 `opacity`，未动画 `width`/`height`/`top`/`left`/`box-shadow`
- [ ] 没有使用 `transition: all`
- [ ] 每个动画都有明确目的（空间关系/层级焦点/反馈确认/状态过渡/情绪基调），不是为动而动

### 🟡 P1 — 应该通过

- [ ] 多元素入场使用 stagger 交错延迟（50-100ms 步长），且最后一个元素延迟 ≤ 600ms
- [ ] 离场动画使用 `--ease-in`，状态切换使用 `--ease-in-out`
- [ ] 入场比离场慢（离场时长约为入场的60-70%）
- [ ] 按钮/可交互元素有明确的 hover/active/press 状态反馈（150ms级别微动）
- [ ] Scroll Reveal 只触发一次，不反复触发
- [ ] 环境呼吸动效（如有）透明度 ≤ 0.1，时长 ≥ 3s，一屏最多1个

### 🟢 P2 — 加分项

- [ ] 使用 CSS 变量（`--ease-out`、`--duration-md` 等）而非硬编码数值
- [ ] 首屏加载有精心编排的入场序列（orchestrated entrance），而不是所有元素同时动
- [ ] 移动端 stagger 步长缩短至 30-50ms，减少等待
- [ ] 阴影和transform同步动画，制造真实的"浮起"物理感
- [ ] 使用 `will-change` 优化性能但不滥用

---

## 📐 Quick Reference — 速查卡

```
┌─────────────────────────────────────────────────────┐
│   FEIHONG MOTION · QUICK REFERENCE                  │
│   飞鸿动效 · 速查卡                                  │
├─────────────────────────────────────────────────────┤
│                                                     │
│   SIGNATURE EASE                                    │
│   ┌─────────────────────────────────────────────┐   │
│   │  cubic-bezier(0.16, 1, 0.3, 1)              │   │
│   │  Fast start · Gentle settle · No overshoot  │   │
│   └─────────────────────────────────────────────┘   │
│                                                     │
│   DURATION          │  USE FOR                      │
│   ──────────────────┼────────────────────────────   │
│   150–200ms         │  Button, hover, toggle        │
│   250–350ms         │  Toast, tooltip, menu         │
│   400–600ms         │  Card, modal, scroll-reveal   │
│   800–1200ms        │  Page, hero, layout           │
│   3–6s              │  Ambient pulse (opacity≤0.1)  │
│                                                     │
│   THREE EASINGS                                     │
│   --ease-out    →  Entrance / Reveal                │
│   --ease-in     →  Exit / Dismiss                   │
│   --ease-in-out →  Toggle / Ambient                 │
│                                                     │
│   THREE RULES                                       │
│   1. Purposeful  →  Every motion has a reason       │
│   2. Elegant     →  Silk scarf, not rubber band     │
│   3. Restrained  →  ≤3 concurrent motions per view  │
│                                                     │
│   NEVER: bounce · elastic · infinite loop · AI glow │
│   ALWAYS: respect prefers-reduced-motion            │
│                                                     │
└─────────────────────────────────────────────────────┘
```

---

*本文件是 Feihong Design System 的动效基石。所有组件、模板、场景中的动画行为均在此规范之下。*
*版本：v1.0 · 最后更新：2026-07-09*
*与 `DNA.md`、`components/`、`QUALITY.md` 共同构成 FEIHONG Design System 的核心规范体系。*
