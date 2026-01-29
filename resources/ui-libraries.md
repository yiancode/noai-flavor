# UI 组件库推荐

去除 AI 味儿的关键之一是**不要直接使用主流组件库的默认样式**。

## 问题

AI 为了保险，默认会选最主流的组件库：
- Shadcn UI
- Material UI
- Ant Design
- DaisyUI

这些库虽然专业，但**直接用默认样式，一眼就能认出来**。

## 解决方案

### 方案 1：使用小众但有特色的组件库

| 组件库 | 特点 | 适用场景 | 链接 |
|--------|------|----------|------|
| **Aceternity UI** | 150+ 炫酷视觉组件<br>Sparkles、Aurora、Meteors | 科技产品、创意网站 | https://ui.aceternity.com |
| **Magic UI** | 动画组件、微交互<br>流光边框、文字渐变 | 现代产品、设计工具 | https://magicui.design |
| **Brutalist UI** | 粗野主义风格<br>粗边框、硬阴影 | 个性网站、艺术项目 | - |
| **Glass UI** | 玻璃拟态效果<br>半透明、模糊背景 | 现代应用、仪表盘 | - |
| **ikun-ui** | Svelte + UnoCSS<br>轻量、现代 | 练习时长两年半的项目 | https://ikun-ui.netlify.app |
| **Radix UI** | 无样式原语组件<br>完全自定义 | 需要完全定制的项目 | https://www.radix-ui.com |
| **Mantine** | 100+ 组件<br>功能丰富 | 中后台、管理系统 | https://mantine.dev |
| **DaisyUI** | 30+ 主题<br>cyberpunk、retro | 多主题网站 | https://daisyui.com |

### 方案 2：深度定制主流组件库

如果必须使用 Shadcn/Material UI，必须深度定制：

```tsx
// ❌ 不要直接用默认样式
import { Button } from "@/components/ui/button"

<Button>点击我</Button>

// ✅ 深度定制样式
<Button className="bg-orange-600 hover:bg-orange-700
                  px-8 py-4 rounded-none border-2 border-black
                  shadow-[4px_4px_0px_0px_rgba(0,0,0,1)]">
  点击我
</Button>
```

## 详细介绍

### Aceternity UI

**最适合场景**：科技产品、SaaS 落地页、创意网站

**特色组件**：
- `<Sparkles>` - 闪光粒子效果
- `<AuroraBackground>` - 极光背景
- `<Meteors>` - 流星效果
- `<BackgroundBeams>` - 光束背景
- `<TypewriterEffect>` - 打字机效果

**示例**：
```tsx
import { AuroraBackground } from "@/components/ui/aurora-background"
import { Sparkles } from "@/components/ui/sparkles"

export default function Page() {
  return (
    <AuroraBackground>
      <h1>
        <Sparkles>革命性的产品</Sparkles>
      </h1>
    </AuroraBackground>
  )
}
```

**官网**：https://ui.aceternity.com

---

### Magic UI

**最适合场景**：现代产品、设计工具、营销网站

**特色功能**：
- 150+ 动画组件
- 流光边框效果
- 文字渐变动画
- 微交互组件

**示例**：
```tsx
import { ShimmerButton } from "@magicui/shimmer-button"

<ShimmerButton>流光按钮</ShimmerButton>
```

**官网**：https://magicui.design

---

### ikun-ui

**最适合场景**：练习时长两年半的项目🏀

**特点**：
- 基于 Svelte.js + UnoCSS
- 轻量、快速
- 现代化设计

**官网**：https://ikun-ui.netlify.app

---

### Radix UI

**最适合场景**：需要完全自定义样式的项目

**特点**：
- 无样式原语组件
- 只提供功能，不提供样式
- 完全控制视觉表现

**示例**：
```tsx
import * as Dialog from '@radix-ui/react-dialog'

<Dialog.Root>
  <Dialog.Trigger className="your-custom-button">
    打开对话框
  </Dialog.Trigger>

  <Dialog.Portal>
    <Dialog.Overlay className="your-custom-overlay" />
    <Dialog.Content className="your-custom-content">
      {/* 完全自定义的样式 */}
    </Dialog.Content>
  </Dialog.Portal>
</Dialog.Root>
```

**官网**：https://www.radix-ui.com

---

### Mantine

**最适合场景**：中后台系统、管理面板、复杂应用

**特点**：
- 100+ 开箱即用的组件
- 功能丰富、文档完善
- 深色模式支持

**官网**：https://mantine.dev

---

### DaisyUI

**最适合场景**：需要多主题切换的网站

**特点**：
- 30+ 内置主题
- cyberpunk、retro、cupcake 等个性主题
- 基于 Tailwind CSS

**示例**：
```html
<!-- 使用 cyberpunk 主题 -->
<html data-theme="cyberpunk">
  <button class="btn btn-primary">点击我</button>
</html>

<!-- 使用 retro 主题 -->
<html data-theme="retro">
  <button class="btn btn-primary">点击我</button>
</html>
```

**官网**：https://daisyui.com

## 如何选择

根据项目需求选择合适的组件库：

| 需求 | 推荐组件库 |
|------|-----------|
| 追求炫酷视觉效果 | Aceternity UI、Magic UI |
| 追求个性风格 | DaisyUI、Brutalist UI、Glass UI |
| 需要完全自定义 | Radix UI、Headless UI |
| 快速开发 + 特色 | Mantine、ikun-ui |
| 中后台系统 | Mantine、Ant Design（深度定制） |

## 使用提示词

告诉 AI 使用特定组件库：

```
必须使用 Aceternity UI 设计网站
你需要阅读官方文档来了解最新的使用方法：
https://ui.aceternity.com/components

不要使用 Shadcn UI 或 Material UI 的默认样式。
```

或者：

```
必须使用 Radix UI 作为无样式原语，然后完全自定义样式。
不要使用任何默认样式的组件库。
```

## 配合 Context7 插件

对于这些小众组件库，AI 可能不太熟悉用法。建议：

1. 安装 Context7 插件（实时查询文档）
2. 或者直接把官方文档 URL 发给 AI

这样 AI 就能正确使用这些组件库了。
