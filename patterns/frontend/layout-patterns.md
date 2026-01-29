# 反模式：Hero + 三卡片布局

## 特征描述

AI 生成的网站布局千篇一律：
- 首屏大标题（Hero Section）+ 副标题 + CTA 按钮
- 下方三个卡片并排，介绍功能特性
- 完美居中对齐
- 等宽等高的卡片
- 线性对称的布局

## 为什么会这样？

这是最"安全"的布局模式：
- Landing Page 模板中出现频率最高
- 结构清晰，不容易出错
- Tailwind、Bootstrap 等框架的默认示例都是这样

AI 认为：**"专业网站 ≈ Hero + 三卡片"**

## 反面示例

```html
<!-- AI 典型输出 -->
<section class="hero text-center py-20">
  <h1 class="text-5xl font-bold">革命性的产品标题</h1>
  <p class="text-xl text-gray-600">一句话介绍我们的产品</p>
  <button class="mt-8 px-8 py-4">立即开始</button>
</section>

<section class="features grid grid-cols-3 gap-8">
  <div class="card text-center p-8">
    <div class="icon">🚀</div>
    <h3>快速</h3>
    <p>比其他产品快 10 倍</p>
  </div>
  <div class="card text-center p-8">
    <div class="icon">🔒</div>
    <h3>安全</h3>
    <p>企业级安全保障</p>
  </div>
  <div class="card text-center p-8">
    <div class="icon">⚡</div>
    <h3>高效</h3>
    <p>提升团队生产力</p>
  </div>
</section>
```

## 改进写法

### 方案 1：反向提示

```
布局禁止清单：
❌ Hero + 三卡片布局
❌ 完美居中对齐
❌ 等宽多栏（必须不对称）
❌ 线性对称布局
```

### 方案 2：不对称布局

```html
<!-- 不对称、更有呼吸感的布局 -->
<section class="hero text-left py-32 px-16">
  <div class="max-w-2xl">
    <h1 class="text-6xl font-bold leading-tight">
      革命性的产品标题
    </h1>
    <p class="text-lg text-gray-700 mt-6">
      一句话介绍我们的产品
    </p>
  </div>
</section>

<section class="features py-20">
  <!-- 交错布局 -->
  <div class="flex items-center mb-16">
    <div class="w-1/2">
      <h3 class="text-3xl font-bold">快速</h3>
      <p class="mt-4">比其他产品快 10 倍</p>
    </div>
    <div class="w-1/2">
      <img src="..." alt="feature illustration" />
    </div>
  </div>

  <div class="flex items-center flex-row-reverse">
    <div class="w-1/2">
      <h3 class="text-3xl font-bold">安全</h3>
      <p class="mt-4">企业级安全保障</p>
    </div>
    <div class="w-1/2">
      <img src="..." alt="feature illustration" />
    </div>
  </div>
</section>
```

### 方案 3：参考优秀设计

```
请参考以下网站的布局风格：
- Stripe (stripe.com) - 不对称、大留白
- Linear (linear.app) - 极简、深色模式
- Vercel (vercel.com) - 现代、流动感

避免使用 Hero + 三卡片的传统布局。
```

## 规则（供 AI 参考）

```
【布局规则】
1. 禁止 Hero + 三卡片的传统布局
2. 禁止完美居中对齐（标题可以左对齐）
3. 禁止等宽等高的卡片网格
4. 必须使用不对称布局
5. 优先使用：
   - 交错式布局（图文左右交替）
   - 大胆的留白和间距
   - 不规则的网格系统
   - Z 字形视觉流
   - 卡片大小和位置错落有致
```

## 推荐布局参考

优秀的布局设计网站：
- [Awwwards](https://www.awwwards.com/) - 获奖网站设计
- [Dribbble](https://dribbble.com/) - 设计师作品展示
- [Land-book](https://land-book.com/) - Landing Page 灵感

## 案例对比

### ❌ AI 味儿重

- 完美居中
- 三卡片并排
- 对称布局
- 等宽等高

### ✅ 去除 AI 味儿

- 左对齐文案
- 图文交错
- 不对称布局
- 大小错落
- 大胆留白
