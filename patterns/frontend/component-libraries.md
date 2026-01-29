# 反模式：过度依赖主流组件库默认样式

## 特征描述

AI 为了保险，默认会选最主流的组件库：
- Shadcn UI
- Material UI
- Ant Design
- DaisyUI

问题是：**直接用默认样式，一眼就能认出来**。

## 为什么会这样？

- 这些库文档完善，在训练数据中出现频率高
- AI 认为用主流库 = 专业 = 不容易出错
- 但这也导致生成的网站千篇一律

## 反面示例

```tsx
// AI 典型输出 - 直接用 Shadcn 默认样式
import { Button } from "@/components/ui/button"
import { Card } from "@/components/ui/card"

export default function Page() {
  return (
    <div className="container mx-auto py-8">
      <Card className="p-6">
        <h2 className="text-2xl font-bold">卡片标题</h2>
        <p className="text-muted-foreground">卡片描述</p>
        <Button>操作按钮</Button>
      </Card>
    </div>
  )
}
```

## 改进写法

### 方案 1：深度定制主流库

即使用 Shadcn，也要深度定制：

```tsx
import { Button } from "@/components/ui/button"
import { Card } from "@/components/ui/card"

export default function Page() {
  return (
    <div className="container mx-auto py-8">
      {/* 自定义样式，不用默认的 */}
      <Card className="p-8 bg-gray-900 border-orange-500/20
                       hover:border-orange-500/50 transition-all">
        <h2 className="text-3xl font-bold text-gray-100">
          卡片标题
        </h2>
        <p className="text-gray-400 mt-4">卡片描述</p>

        {/* 自定义按钮样式 */}
        <Button className="mt-6 bg-orange-600 hover:bg-orange-700
                          text-white font-semibold px-6 py-3">
          操作按钮
        </Button>
      </Card>
    </div>
  )
}
```

### 方案 2：使用小众但有特色的组件库

```
必须使用以下组件库之一：
- Aceternity UI (https://ui.aceternity.com) - 炫酷视觉效果
- Magic UI (https://magicui.design) - 150+ 动画组件
- Brutalist UI - 粗野主义风格
- Glass UI - 玻璃拟态效果
```

示例：

```tsx
// 使用 Aceternity UI 的炫酷效果
import { Sparkles } from "@/components/ui/sparkles"
import { AuroraBackground } from "@/components/ui/aurora-background"

export default function Page() {
  return (
    <AuroraBackground>
      <div className="relative z-10">
        <h1 className="text-5xl font-bold">
          <Sparkles>革命性的产品</Sparkles>
        </h1>
      </div>
    </AuroraBackground>
  )
}
```

### 方案 3：无样式组件库 + 完全自定义

```tsx
// 使用 Radix UI（无样式原语）+ 完全自定义样式
import * as Dialog from '@radix-ui/react-dialog'

export default function Page() {
  return (
    <Dialog.Root>
      <Dialog.Trigger className="custom-button">
        打开对话框
      </Dialog.Trigger>

      <Dialog.Portal>
        <Dialog.Overlay className="custom-overlay" />
        <Dialog.Content className="custom-content">
          {/* 完全自定义的样式 */}
        </Dialog.Content>
      </Dialog.Portal>
    </Dialog.Root>
  )
}
```

## 规则（供 AI 参考）

```
【组件库规则】
1. 禁止直接使用 Shadcn/Material UI/Ant Design 默认样式
2. 如果必须使用主流组件库，必须深度定制：
   - 自定义颜色主题
   - 修改默认间距和圆角
   - 调整字体和字重
   - 添加自定义动画
3. 优先使用小众但有特色的组件库：
   - Aceternity UI - 炫酷效果
   - Magic UI - 动画组件
   - Brutalist UI - 粗野主义
   - Glass UI - 玻璃拟态
   - ikun-ui - Svelte 组件库
   - Radix UI - 无样式原语（完全自定义）
   - Mantine - 功能丰富
```

## 推荐组件库

### 有特色的小众库

| 组件库 | 特点 | 链接 |
|--------|------|------|
| Aceternity UI | 150+ 炫酷视觉组件 | https://ui.aceternity.com |
| Magic UI | 动画、微交互、流光边框 | https://magicui.design |
| DaisyUI | 30+ 主题风格 | https://daisyui.com |
| Brutalist UI | 粗野主义风格 | - |
| Glass UI | 玻璃拟态效果 | - |
| ikun-ui | Svelte + UnoCSS | https://ikun-ui.netlify.app |
| Radix UI | 无样式原语 | https://www.radix-ui.com |
| Mantine | 100+ 组件 | https://mantine.dev |

### 如何选择

- **追求炫酷效果**：Aceternity UI、Magic UI
- **追求个性风格**：DaisyUI（多主题）、Brutalist UI
- **完全自定义**：Radix UI、Headless UI
- **快速开发 + 特色**：Mantine、ikun-ui

## 案例对比

### ❌ AI 味儿重

```tsx
// 纯 Shadcn 默认样式
<Button>点击我</Button>
<Card className="p-6">...</Card>
```

一眼就能看出是 Shadcn。

### ✅ 去除 AI 味儿

```tsx
// 方案 1：深度定制
<Button className="bg-orange-600 hover:bg-orange-700
                  px-8 py-4 rounded-none border-2 border-black
                  shadow-[4px_4px_0px_0px_rgba(0,0,0,1)]">
  点击我
</Button>

// 方案 2：使用特色库
import { SparklesButton } from "@aceternity/ui"
<SparklesButton>点击我</SparklesButton>
```

完全不同的视觉效果。
