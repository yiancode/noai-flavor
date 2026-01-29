# 反模式：空洞内容和占位符

## 特征描述

AI 生成的网站常见问题：
- 没有真实图片，全是 placeholder
- 文案空洞："提升生产力"、"卓越的用户体验"
- Lorem Ipsum 占位文本
- Emoji 作为图标：🚀⚡🔒
- 被动语态和长句

## 为什么会这样？

AI 不知道你的实际内容，只能：
- 生成通用文案
- 使用占位图
- 用 Emoji 填充空白

结果就是：**看起来很专业，但没有灵魂**。

## 反面示例

### 空洞文案

```html
<h1>提升您的生产力</h1>
<p>通过我们卓越的解决方案，您将体验到前所未有的效率提升。</p>

<div class="feature">
  <span>🚀</span>
  <h3>快速高效</h3>
  <p>比同类产品快 10 倍</p>
</div>
```

问题：
- "提升生产力" - 说了等于没说
- "卓越的解决方案" - 套话
- 🚀 - 用 Emoji 当图标
- "比同类产品快 10 倍" - 没有具体数据

### 占位图

```html
<img src="https://via.placeholder.com/600x400" alt="placeholder" />
```

## 改进写法

### 方案 1：具体化文案

```
文案必须做到：
- 具体化："每天节省 2 小时重复劳动"（不要说"提升生产力"）
- 口语化："用起来就像呼吸一样自然"（不要说"卓越的用户体验"）
- 带情绪："再也不用在 10 个群里找文件了"（不要说"高效协作"）
- 可以挑衅："别再假装你会看完那些 PPT 了"
```

示例：

```html
<h1>每天节省 2 小时重复劳动</h1>
<p>用起来就像呼吸一样自然。再也不用在 10 个群里找文件了。</p>

<div class="feature">
  <!-- 用真实图标，不用 Emoji -->
  <svg>...</svg>
  <h3>5 秒完成报表</h3>
  <p>以前要手动复制粘贴半小时</p>
</div>
```

### 方案 2：主动获取图片资源

告诉 AI 去哪里找图片：

```
必须使用真实图片资源：
1. 插画：使用 unDraw (https://undraw.co)
2. 图标：使用 Iconify (https://iconify.design)
3. 真实照片：使用 Pexels (https://www.pexels.com)
4. 占位图：使用 Picsum Photos (https://picsum.photos)
```

示例：

```html
<!-- 使用 Iconify 图标 -->
<iconify-icon icon="mdi:rocket-launch"></iconify-icon>

<!-- 使用 Pexels 真实照片 -->
<img src="https://images.pexels.com/photos/..." alt="..." />

<!-- 使用 Picsum 占位图（真实照片，不是灰色方块） -->
<img src="https://picsum.photos/600/400" alt="..." />

<!-- 使用 unDraw 插画 -->
<img src="https://undraw.co/illustrations/..." alt="..." />
```

### 方案 3：拒绝被动语态

```
文案禁止清单：
❌ 被动语态："您将体验到..."
❌ 长句子：超过 15 个字的句子
❌ 空洞词汇："卓越"、"革命性"、"颠覆性"
❌ Emoji 作为功能图标
❌ Lorem Ipsum 占位文本
```

## 规则（供 AI 参考）

```
【内容规则】

文案要求：
1. 具体化：用数字、场景、对比
   ✅ "每天节省 2 小时重复劳动"
   ❌ "提升生产力"

2. 口语化：像朋友聊天
   ✅ "用起来就像呼吸一样自然"
   ❌ "卓越的用户体验"

3. 带情绪：可以幽默、自嘲、挑衅
   ✅ "再也不用在 10 个群里找文件了"
   ❌ "高效协作"

4. 短句：每句话不超过 15 个字

图片要求：
1. 图标：使用 Iconify (https://iconify.design)
2. 插画：使用 unDraw (https://undraw.co)
3. 照片：使用 Pexels (https://www.pexels.com)
4. 占位图：使用 Picsum Photos (https://picsum.photos)
5. 禁止：
   - Emoji 作为功能图标
   - via.placeholder.com 灰色占位图
   - Lorem Ipsum 占位文本
```

## 推荐图片资源

| 资源 | 类型 | 链接 |
|------|------|------|
| unDraw | 免费 SVG 插画，可自定义颜色 | https://undraw.co |
| Iconify | 20 万+ 免费矢量图标 | https://iconify.design |
| Pexels | 免费高质量图库（有 API） | https://www.pexels.com |
| Picsum Photos | 占位图（真实照片，不是灰色） | https://picsum.photos |
| Unsplash | 高质量免费图片 | https://unsplash.com |
| Illustrations | 免费插画库 | https://illustrations.co |

## 案例对比

### ❌ AI 味儿重

```html
<section>
  <h2>提升您的生产力 🚀</h2>
  <p>通过我们卓越的解决方案，您将体验到前所未有的效率提升。我们的产品采用了最先进的技术架构。</p>
  <img src="https://via.placeholder.com/600x400" alt="placeholder" />
</section>
```

问题：
- 空洞文案
- Emoji 装饰
- 长句、被动语态
- 灰色占位图

### ✅ 去除 AI 味儿

```html
<section>
  <h2>每天节省 2 小时</h2>
  <p>以前复制粘贴半小时的报表，现在 5 秒搞定。</p>
  <p>不用再在 10 个群里找文件了。</p>

  <!-- 使用真实图片 -->
  <img src="https://images.pexels.com/photos/3184291/..."
       alt="person working on laptop" />

  <!-- 使用 Iconify 图标，不用 Emoji -->
  <iconify-icon icon="mdi:rocket-launch-outline"></iconify-icon>
</section>
```

改进：
- 具体数字（2 小时、5 秒）
- 具体场景（复制粘贴报表、找文件）
- 短句、主动语态
- 真实图片
- 矢量图标代替 Emoji
