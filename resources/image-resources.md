# 图片资源推荐

去除 AI 味儿的关键之一是**使用真实图片资源，而不是占位符**。

## 问题

AI 生成的网站常见问题：
- 使用灰色占位图（via.placeholder.com）
- 用 Emoji 作为图标（🚀⚡🔒）
- 没有真实内容，空洞

## 解决方案

主动告诉 AI 去哪里找图片资源。

## 图标库

### Iconify

**特点**：
- 20 万+ 免费矢量图标
- 包含 Material Design、FontAwesome、Heroicons 等所有主流图标集
- 支持自定义颜色和大小
- 可以直接用 Web Component 或导出 SVG

**使用方式**：

```html
<!-- 方式 1：Web Component -->
<script src="https://code.iconify.design/iconify-icon/1.0.7/iconify-icon.min.js"></script>

<iconify-icon icon="mdi:rocket-launch-outline"></iconify-icon>
<iconify-icon icon="material-symbols:security"></iconify-icon>
```

```tsx
// 方式 2：React 组件
import { Icon } from '@iconify/react'

<Icon icon="mdi:rocket-launch-outline" />
```

**搜索图标**：https://iconify.design

**提示词示例**：
```
使用 Iconify 图标库，不要使用 Emoji。
图标搜索：https://iconify.design
```

---

## 插画库

### unDraw

**特点**：
- 完全免费的 SVG 插画
- 可以自定义主色调
- 风格统一、现代
- 商业使用无需署名

**使用方式**：

1. 访问 https://undraw.co
2. 搜索关键词（如 "coding"、"team"）
3. 自定义颜色
4. 下载 SVG 或直接用 URL

**提示词示例**：
```
使用 unDraw 插画库添加插画：
https://undraw.co

根据网站内容搜索相关插画，自定义颜色为主题色。
```

### Illustrations.co

**特点**：
- 免费插画集合
- 多种风格（扁平、手绘、3D）

**官网**：https://illustrations.co

---

## 真实照片库

### Pexels

**特点**：
- 高质量免费图片和视频
- 商业使用无需署名
- 提供 API，可以搜索图片
- 每周更新

**使用方式**：

```html
<!-- 直接使用图片 URL -->
<img src="https://images.pexels.com/photos/3184291/pexels-photo-3184291.jpeg"
     alt="person working on laptop" />
```

**API 使用**：
```javascript
// Pexels API（需要免费注册获取 API Key）
fetch('https://api.pexels.com/v1/search?query=coding', {
  headers: {
    Authorization: 'YOUR_API_KEY'
  }
})
```

**官网**：https://www.pexels.com

**提示词示例**：
```
使用 Pexels 搜索真实照片：
https://www.pexels.com

搜索与网站内容相关的高质量照片。
```

---

### Unsplash

**特点**：
- 高质量摄影作品
- 艺术性更强
- 提供 API

**官网**：https://unsplash.com

---

## 占位图

### Picsum Photos

**特点**：
- 占位图用**真实照片**，而不是灰色方块
- 可以指定尺寸
- 每次刷新显示不同图片

**使用方式**：

```html
<!-- 基础用法：指定宽高 -->
<img src="https://picsum.photos/600/400" alt="placeholder" />

<!-- 指定具体图片 ID -->
<img src="https://picsum.photos/id/237/600/400" alt="dog" />

<!-- 灰度图片 -->
<img src="https://picsum.photos/600/400?grayscale" alt="grayscale" />

<!-- 模糊图片 -->
<img src="https://picsum.photos/600/400?blur=2" alt="blurred" />
```

**官网**：https://picsum.photos

**提示词示例**：
```
占位图使用 Picsum Photos（真实照片）：
https://picsum.photos

不要使用 via.placeholder.com 或灰色方块。
```

---

## 综合提示词模板

将以下内容加入你的 Prompt：

```markdown
## 图片系统

网站必须使用真实图片资源，不要使用占位符。

### 1. 图标
使用 Iconify (https://iconify.design)
- 20 万+ 免费矢量图标
- 不要使用 Emoji（🚀⚡🔒）

示例代码：
<iconify-icon icon="mdi:rocket-launch-outline"></iconify-icon>

### 2. 插画
使用 unDraw (https://undraw.co)
- 免费 SVG 插画
- 可自定义颜色
- 搜索与网站内容相关的插画

### 3. 真实照片
使用 Pexels (https://www.pexels.com)
- 高质量免费图片
- 搜索与网站内容相关的照片

示例代码：
<img src="https://images.pexels.com/photos/..." alt="..." />

### 4. 占位图
使用 Picsum Photos (https://picsum.photos)
- 真实照片，不是灰色方块

示例代码：
<img src="https://picsum.photos/600/400" alt="..." />

### 禁止项
❌ 不要使用 Emoji 作为功能图标
❌ 不要使用 via.placeholder.com
❌ 不要使用 Lorem Ipsum 占位文本
```

## 使用流程

### 1. 开发阶段
使用 Picsum Photos 作为占位图：
```html
<img src="https://picsum.photos/600/400" alt="feature illustration" />
```

### 2. 完善阶段
用 Pexels 搜索相关真实照片替换：
```html
<img src="https://images.pexels.com/photos/3184291/..."
     alt="person working on laptop" />
```

### 3. 图标使用
始终使用 Iconify，不要用 Emoji：
```html
<!-- ❌ 不要这样 -->
<span>🚀</span>

<!-- ✅ 要这样 -->
<iconify-icon icon="mdi:rocket-launch-outline"></iconify-icon>
```

## 授权说明

| 资源 | 授权 | 商业使用 | 署名 |
|------|------|----------|------|
| Iconify | MIT | ✅ | ❌ |
| unDraw | 开源 | ✅ | ❌ |
| Pexels | 免费 | ✅ | ❌（建议） |
| Unsplash | 免费 | ✅ | ❌（建议） |
| Picsum Photos | 免费 | ✅ | ❌ |

所有推荐资源都可以商业使用，无需署名。

## 案例对比

### ❌ AI 味儿重

```html
<div class="feature">
  <span>🚀</span>
  <h3>快速</h3>
  <p>比其他产品快 10 倍</p>
  <img src="https://via.placeholder.com/600x400" alt="placeholder" />
</div>
```

问题：
- 用 Emoji 当图标
- 灰色占位图

### ✅ 去除 AI 味儿

```html
<div class="feature">
  <iconify-icon icon="mdi:rocket-launch-outline"
                style="font-size: 48px; color: #FF6B35;">
  </iconify-icon>

  <h3>快速</h3>
  <p>比其他产品快 10 倍</p>

  <img src="https://images.pexels.com/photos/3184291/..."
       alt="person working on laptop" />
</div>
```

改进：
- 矢量图标代替 Emoji
- 真实照片代替占位图
