# 反模式：固定字体选择

## 特征描述

AI 生成的网站字体选择非常固定：
- 英文字体：Inter、Roboto、Open Sans
- 中文字体：思源黑体、苹方
- 基本上就是 Google Fonts 和系统字体的常见组合

## 为什么会这样？

- 这些字体出现频率高，最"安全"
- 兼容性好，不容易出问题
- AI 认为：**"现代网站 ≈ Inter/Roboto"**

## 反面示例

```css
/* AI 典型输出 */
body {
  font-family: 'Inter', 'Roboto', sans-serif;
}

h1, h2, h3 {
  font-family: 'Inter', sans-serif;
  font-weight: 700;
}
```

## 改进写法

### 方案 1：使用个性字体

```css
/* 使用更有特色的字体 */
body {
  font-family: 'JetBrains Mono', 'Fira Code', monospace; /* 代码风格 */
}

/* 或者 */
body {
  font-family: 'Outfit', 'Space Grotesk', sans-serif; /* 几何风格 */
}

/* 或者 */
body {
  font-family: 'Playfair Display', 'Merriweather', serif; /* 衬线风格 */
}
```

### 方案 2：字体组合

```css
/* 标题和正文使用不同字体 */
body {
  font-family: 'Inter', sans-serif;
}

h1, h2, h3 {
  font-family: 'Space Grotesk', sans-serif; /* 几何感更强 */
  font-weight: 700;
}

code {
  font-family: 'Fira Code', 'JetBrains Mono', monospace;
}
```

### 方案 3：可变字体

```css
/* 使用可变字体，更细腻的字重控制 */
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');

body {
  font-family: 'Inter', sans-serif;
  font-variation-settings: 'wght' 450; /* 自定义字重 */
}

h1 {
  font-variation-settings: 'wght' 750;
}
```

## 规则（供 AI 参考）

```
【字体规则】
1. 避免使用最常见的组合：
   ❌ Inter + Roboto
   ❌ Open Sans + Lato

2. 根据网站风格选择字体：
   - 技术/代码类：JetBrains Mono, Fira Code, Source Code Pro
   - 现代/几何：Space Grotesk, Outfit, Satoshi
   - 优雅/衬线：Playfair Display, Merriweather, Lora
   - 人文/手写：Caveat, Patrick Hand, Indie Flower

3. 中文字体选择：
   - 现代：阿里巴巴普惠体、鸿蒙字体
   - 个性：站酷系列字体
   - 优雅：霞鹜文楷、思源宋体

4. 字体组合原则：
   - 标题字体 ≠ 正文字体
   - 最多使用 2-3 种字体
   - 注意字体授权
```

## 推荐字体资源

### 英文字体

| 字体 | 风格 | 适用场景 |
|------|------|----------|
| Space Grotesk | 几何、现代 | 科技产品 |
| Outfit | 圆润、友好 | 设计工具 |
| JetBrains Mono | 等宽、代码 | 开发者工具 |
| Playfair Display | 优雅、衬线 | 内容平台 |
| Satoshi | 现代、可读性强 | 通用场景 |

### 中文字体

| 字体 | 风格 | 下载 |
|------|------|------|
| 阿里巴巴普惠体 | 现代、清晰 | 免费商用 |
| 鸿蒙字体 | 圆润、舒适 | 免费商用 |
| 霞鹜文楷 | 优雅、手写感 | 开源 |
| 站酷系列 | 个性、艺术 | 免费商用 |

### 字体获取

- [Google Fonts](https://fonts.google.com) - 免费英文字体
- [Font Share](https://www.fontshare.com) - 精选免费字体
- [100font.com](https://www.100font.com) - 免费商用中文字体

## 案例对比

### ❌ AI 味儿重

```css
body {
  font-family: 'Inter', 'Roboto', sans-serif;
}
```

一眼就能看出是默认选择。

### ✅ 去除 AI 味儿

```css
/* 科技感 */
body {
  font-family: 'JetBrains Mono', monospace;
}

/* 或者现代感 */
body {
  font-family: 'Space Grotesk', sans-serif;
}

h1 {
  font-family: 'Outfit', sans-serif;
  font-weight: 800;
}
```

完全不同的视觉感受。
