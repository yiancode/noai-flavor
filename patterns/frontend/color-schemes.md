# 反模式：蓝紫渐变配色

## 特征描述

AI 生成的网站最明显的特征就是**蓝紫色渐变**用到吐。

典型表现：
- 主色调：`#6366F1`（靛蓝）、`#8B5CF6`（紫色）
- 背景：蓝紫渐变（indigo-500 → purple-600）
- 按钮：紫色到粉色的渐变
- 完全依赖 Tailwind CSS 默认色板

## 为什么会这样？

AI 的训练数据中，很多现代网站采用 Tailwind 样式库，而这个库的默认主色调就是蓝紫色。AI 在学习数亿行代码时，这些颜色出现的频率是最高的。

于是 AI 就认为：**"现代化网站 ≈ 蓝紫色渐变"**

## 反面示例

```css
/* AI 典型输出 */
.hero {
  background: linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%);
}

.button {
  background: linear-gradient(to right, #8B5CF6, #EC4899);
}
```

## 改进写法

### 方案 1：反向提示

在 Prompt 中明确禁止：

```
设计禁止清单：
❌ 紫色/靛蓝色渐变（#6366F1、#8B5CF6）
❌ 纯平背景色（必须有噪点或渐变）
❌ Tailwind 默认色板
```

### 方案 2：指定配色方案

使用配色工具生成独特配色：

```
配色要求：
- 主色调：深灰色 (#1A1A1A) + 暖橙色 (#FF6B35)
- 背景：深色模式，带噪点纹理
- 强调色：琥珀色 (#FFA500)
```

### 方案 3：参考真实网站

```
请访问 [网站URL]，提取它的配色方案，然后生成类似风格的网站。
```

## 规则（供 AI 参考）

```
【配色规则】
1. 禁止使用 #6366F1（indigo）、#8B5CF6（purple）作为主色调
2. 禁止使用蓝紫色渐变背景
3. 必须使用自定义配色方案，不依赖 Tailwind 默认色板
4. 背景色必须有纹理、噪点或微妙渐变，不能是纯平色
5. 优先使用：
   - 深灰 + 暖色系（橙、琥珀、红）
   - 深色模式 + 冷蓝色点缀
   - 黑白灰 + 单一强调色
   - 自然色系（大地色、森林绿）
```

## 推荐配色工具

- [Coolors](https://coolors.co) - 主流配色生成器
- [Adobe Color](https://color.adobe.com) - Adobe 官方专业配色工具
- [Tailwind CSS Custom Colors](https://tailwindcss.com/docs/customizing-colors) - 自定义色板

## 案例对比

### ❌ AI 味儿重

```html
<div class="bg-gradient-to-r from-indigo-500 to-purple-600">
  <h1 class="text-white">欢迎使用我们的产品</h1>
  <button class="bg-gradient-to-r from-purple-500 to-pink-500">
    开始使用
  </button>
</div>
```

### ✅ 去除 AI 味儿

```html
<div class="bg-gray-900 relative">
  <!-- 噪点纹理 -->
  <div class="absolute inset-0 opacity-30"
       style="background-image: url('data:image/svg+xml,...')"></div>

  <h1 class="text-gray-100">欢迎使用我们的产品</h1>
  <button class="bg-orange-600 hover:bg-orange-700">
    开始使用
  </button>
</div>
```
