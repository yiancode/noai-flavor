# 配色工具推荐

去除 AI 味儿的关键之一是**使用自定义配色方案，不依赖 Tailwind 默认色板**。

## 问题

AI 生成的网站配色单调：
- 蓝紫色渐变用到吐（#6366F1、#8B5CF6）
- 完全依赖 Tailwind CSS 默认色板
- 没有个性

## 解决方案

### 方案 1：快速生成配色方案

使用配色工具生成独特配色，然后告诉 AI 使用。

### 方案 2：明确禁止蓝紫色

在 Prompt 中明确禁止使用蓝紫色。

---

## 配色工具

### Coolors

**特点**：
- 最流行的配色生成器
- 按空格键随机生成配色
- 可以锁定某个颜色，生成其他配色
- 导出多种格式（HEX、RGB、CSS）

**使用流程**：

1. 访问 https://coolors.co
2. 按空格键生成随机配色
3. 点击颜色可以锁定（再按空格只改变其他颜色）
4. 满意后导出色值

**示例**：
```
生成的配色方案：
- 主色：#FF6B35（暖橙色）
- 辅助色：#F7931E（琥珀色）
- 背景：#1A1A1A（深灰）
- 文字：#E5E5E5（浅灰）
- 强调：#FFA500（橙色）
```

**官网**：https://coolors.co

---

### Adobe Color

**特点**：
- Adobe 官方专业配色工具
- 支持多种配色规则（互补色、类比色、三角色等）
- 可以从图片提取配色
- 探索社区配色方案

**使用流程**：

1. 访问 https://color.adobe.com
2. 选择配色规则（如"互补色"）
3. 调整主色，工具自动生成其他颜色
4. 或者上传图片，从图片提取配色

**官网**：https://color.adobe.com

---

### Tailwind CSS Custom Colors

**特点**：
- 可以自定义 Tailwind 色板
- 保持 Tailwind 工作流，但用自己的颜色

**使用方式**：

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        // 自定义品牌色，替换默认的 indigo
        'brand': {
          50: '#fff7ed',
          100: '#ffedd5',
          200: '#fed7aa',
          300: '#fdba74',
          400: '#fb923c',
          500: '#FF6B35', // 主色
          600: '#ea580c',
          700: '#c2410c',
          800: '#9a3412',
          900: '#7c2d12',
        },
      },
    },
  },
}
```

**文档**：https://tailwindcss.com/docs/customizing-colors

---

### Realtime Colors

**特点**：
- 实时预览配色方案
- 可以看到配色在实际网站中的效果
- 支持深色/浅色模式切换

**官网**：https://www.realtimecolors.com

---

### Palettte

**特点**：
- 从 Unsplash 图片生成配色
- 适合从参考图片提取配色

**官网**：https://palettte.app

---

## 推荐配色方案

### 科技感配色

```css
/* 深灰 + 橙色 */
--color-bg: #1A1A1A;
--color-primary: #FF6B35;
--color-secondary: #FFA500;
--color-text: #E5E5E5;
--color-muted: #6B7280;
```

```css
/* 深色 + 冷蓝 */
--color-bg: #0A0A0A;
--color-primary: #60A5FA;
--color-secondary: #3B82F6;
--color-text: #F5F5F5;
--color-muted: #9CA3AF;
```

### 优雅配色

```css
/* 黑白灰 + 金色 */
--color-bg: #FAFAFA;
--color-primary: #D4AF37;
--color-secondary: #1F2937;
--color-text: #111827;
--color-muted: #6B7280;
```

### 自然配色

```css
/* 大地色 */
--color-bg: #F5F5DC;
--color-primary: #8B4513;
--color-secondary: #A0522D;
--color-text: #2C1810;
--color-muted: #8B7355;
```

---

## 使用提示词

### 方法 1：指定具体配色

```
配色要求：
- 主色调：#FF6B35（暖橙色）
- 辅助色：#FFA500（琥珀色）
- 背景：#1A1A1A（深灰）
- 文字：#E5E5E5（浅灰）

禁止使用 #6366F1、#8B5CF6 等蓝紫色。
```

### 方法 2：描述配色风格

```
配色要求：
- 风格：科技感、现代
- 方向：深色模式，暖色系强调
- 禁止：蓝紫色渐变、Tailwind 默认色板
```

### 方法 3：参考网站配色

```
请参考以下网站的配色方案：
- Stripe (stripe.com)
- Linear (linear.app)
- Vercel (vercel.com)

不要使用蓝紫色渐变。
```

---

## 配色规则

### 禁止项

```
❌ 紫色/靛蓝色渐变（#6366F1、#8B5CF6、#A78BFA）
❌ Tailwind 默认 indigo/purple/violet 色板
❌ 高饱和度霓虹色
❌ 纯平背景色（必须有纹理或渐变）
```

### 推荐项

```
✅ 深灰 + 暖色系（橙、琥珀、红）
✅ 深色模式 + 冷蓝色点缀
✅ 黑白灰 + 单一强调色
✅ 自然色系（大地色、森林绿）
✅ 背景有微妙纹理或噪点
```

---

## 配色使用流程

### 1. 生成配色方案

使用 Coolors 或 Adobe Color 生成配色方案。

### 2. 定义 CSS 变量

```css
:root {
  /* 主色调 */
  --color-primary: #FF6B35;
  --color-secondary: #FFA500;

  /* 背景色 */
  --color-bg-primary: #1A1A1A;
  --color-bg-secondary: #252525;

  /* 文字色 */
  --color-text-primary: #E5E5E5;
  --color-text-secondary: #9CA3AF;

  /* 状态色 */
  --color-success: #10B981;
  --color-warning: #F59E0B;
  --color-error: #EF4444;
}
```

### 3. 告诉 AI 使用

```
使用以下配色方案：
- 主色：#FF6B35
- 辅助色：#FFA500
- 背景：#1A1A1A
- 文字：#E5E5E5

所有组件必须使用这些颜色，不要使用 Tailwind 默认色板。
```

---

## 配色对比

### ❌ AI 味儿重

```css
/* Tailwind 默认蓝紫色 */
.hero {
  background: linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%);
}

.button {
  background: #8B5CF6;
}
```

一眼就能看出是默认配色。

### ✅ 去除 AI 味儿

```css
/* 自定义深灰 + 橙色 */
.hero {
  background: #1A1A1A;
  /* 添加微妙纹理 */
  background-image: url('data:image/svg+xml,...');
}

.button {
  background: #FF6B35;
  transition: background 0.3s;
}

.button:hover {
  background: #FFA500;
}
```

完全不同的视觉效果。

---

## 配色灵感来源

### 参考优秀网站

- **Stripe** (stripe.com) - 深色 + 蓝色
- **Linear** (linear.app) - 极简黑白 + 紫色（但不是俗气的紫）
- **Vercel** (vercel.com) - 黑白 + 红色
- **GitHub** - 深色 + 绿色/蓝色

### 配色网站

- **Awwwards** (awwwards.com) - 获奖网站配色
- **Dribbble** (dribbble.com) - 设计师作品配色
- **Behance** (behance.net) - 专业设计配色

---

## 总结

**核心原则**：
1. 不要用蓝紫色渐变
2. 不要依赖 Tailwind 默认色板
3. 使用配色工具生成独特配色
4. 背景要有纹理，不要纯平色
5. 告诉 AI 具体的色值，不要让它自己选
