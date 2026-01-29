# 7 个去除网站 AI 味儿的方法

本文档总结了去除网站 AI 味儿的 7 个核心方法，来源于实战经验总结。

---

## 方法 1：让 AI 参考真实网站

### 核心思路

不要让 AI 凭空想象，而是给它具体的参考对象。

### 4 种具体做法

#### 1.1 让 AI 直接访问网页

适用工具：Cursor、Claude Code（配合 Firecrawl MCP）

```
请访问 ai.codefather.cn，提取它的配色方案、字体选择和布局结构，
然后生成类似风格的网站。
```

AI 会自己去看那个网站，然后学着做。

#### 1.2 提供网页截图

适用工具：支持图片理解的 AI（Claude、GPT-4V）

```
请分析这张网站截图，提取：
1. 配色方案
2. 布局结构
3. 字体选择
4. 视觉风格

然后生成类似风格的网站。
```

搭配文字描述，让 AI 还原网站更准确。

#### 1.3 截图转代码工具

适用工具：Screenshot to Code (https://screenshottocode.com)

**流程：**
1. 截图喜欢的网站
2. 上传到 Screenshot to Code，转成代码
3. 把代码交给 AI，让它参考着做

抄代码比抄样式准确得多。

#### 1.4 套用现成模板

推荐资源：
- **HTML5 UP** (https://html5up.net) - 免费响应式网站
- **Start Bootstrap** (https://startbootstrap.com) - Bootstrap 模板
- **Colorlib** (https://colorlib.com) - 精美免费模板
- **WordPress 官方主题库** - 1 万+ 免费主题

**流程：**
1. 下载喜欢的模板
2. 把代码交给 AI
3. 让 AI 修改内容和功能

---

## 方法 2：设计优先开发

### 核心思路

不要上来就让 AI 梭哈整个项目，而是：
1. 先让 AI 做个前端 Demo（纯静态页面）
2. 对设计满意后，再让 AI 基于 Demo 开发完整项目

### 传统做法的问题

```
❌ 用户："帮我做一个包含用户系统、后台管理的完整 SaaS 平台"
AI：哗啦哗啦生成几十个文件
结果：页面风格不对，需要返工，浪费 Tokens
```

### 推荐做法

```
✅ 用户："先帮我设计 SaaS 平台的首页，纯静态页面"
AI：生成首页 HTML/CSS
用户：查看效果，调整配色
AI：重新生成
用户：满意了，"好的，现在基于这个设计开发完整项目"
AI：按照已定义的风格开发
```

### 推荐工具

**1. Google Stitch** (https://stitch.google.com)
- 输入描述，生成专业界面原型
- 支持手绘草图识别
- 人工修改主题风格
- 导出代码或设计文件

**2. Figma + Figma MCP**
- 在 Figma 中精细设计
- 安装 Figma MCP 扩展
- AI 直接读取设计文件生成代码

**3. Onlook** (https://onlook.dev)
- 可视化编辑网页代码
- 所见即所得
- 设计和开发无缝衔接

---

## 方法 3：丰富网站图片

### 核心思路

AI 生成的网站没有图片，我们主动告诉 AI 去哪里找图片。

### 4 类图片资源

#### 3.1 插画库

**unDraw** (https://undraw.co)
- 免费 SVG 插画
- 可自定义颜色
- 风格统一、现代

```
使用 unDraw 插画库：https://undraw.co
搜索与网站内容相关的插画
```

#### 3.2 图标库

**Iconify** (https://iconify.design)
- 20 万+ 免费矢量图标
- 包含所有主流图标集
- 不用 Emoji

```html
<!-- 使用 Iconify 图标 -->
<iconify-icon icon="mdi:rocket-launch-outline"></iconify-icon>

<!-- 不要用 Emoji -->
<span>🚀</span>
```

#### 3.3 真实照片

**Pexels** (https://www.pexels.com)
- 高质量免费图片
- 有 API 可搜索
- 商业使用无需署名

```
使用 Pexels 搜索真实照片：https://www.pexels.com
搜索与网站内容相关的高质量照片
```

#### 3.4 占位图

**Picsum Photos** (https://picsum.photos)
- 占位图用真实照片，不是灰色方块
- 可指定尺寸

```html
<!-- ✅ 使用 Picsum -->
<img src="https://picsum.photos/600/400" />

<!-- ❌ 不要用灰色占位图 -->
<img src="https://via.placeholder.com/600x400" />
```

### 综合提示词

```
网站必须使用真实图片资源：
1. 图标：Iconify (https://iconify.design)
2. 插画：unDraw (https://undraw.co)
3. 照片：Pexels (https://www.pexels.com)
4. 占位图：Picsum Photos (https://picsum.photos)

不要使用 Emoji 作为图标。
```

---

## 方法 4：提示词约束

### 核心思路

用强有力的约束条件，逼着 AI 偏离它的舒适区。

### 5 个提示词技巧

#### 4.1 反向提示（说明不要什么）

```
设计禁止清单：
❌ 紫色/靛蓝色渐变（#6366F1、#8B5CF6）
❌ 纯平背景色（必须有噪点或渐变）
❌ Hero + 三卡片布局
❌ 完美居中对齐
❌ Emoji 作为功能图标
❌ "提升生产力"等空洞词汇
```

#### 4.2 角色设定

```
你是一位资深独立设计师，专注于"反主流"的网页美学。
你鄙视千篇一律的 SaaS 模板，认为软件界面应该有触感和灵魂。

你的创意边界：
- "现代但不要紫色" → 试试深灰+橙色
- "极简但要有温度" → 用大留白+手绘插画
- "科技感但不要冰冷" → 用深色+暖色点缀
```

#### 4.3 拒绝空洞文案

```
网站的文字内容必须做到：
- 具体化："每天节省 2 小时重复劳动"（不要说"提升生产力"）
- 口语化："用起来就像呼吸一样自然"（不要说"卓越的用户体验"）
- 带情绪："再也不用在 10 个群里找文件了"（不要说"高效协作"）
- 可以挑衅："别再假装你会看完那些 PPT 了"
```

#### 4.4 语境注入

先给 AI 喂情绪，再提设计要求。

```
先阅读这段话感受氛围：
《黑客与画家》 - 编程语言是用来思考的

现在根据这种冷静、理性的情绪设计博客首页：
- 配色：深灰+冷蓝
- 布局：理性、有序
- 感觉：沉思的、专注的
```

AI 会把视觉参数和文本的情感特征对齐。

#### 4.5 复用提示词（AGENTS.md）

将所有规则保存为 `AGENTS.md` 或 `.cursorrules` 文件，放在项目根目录。

主流 AI 编程工具会自动读取。

**示例：**
```markdown
# 项目前端设计规则

## ❌ 绝对禁止项
- 紫色/靛蓝色渐变
- Hero + 三卡片布局
- Emoji 作为图标
- ...

## ✅ 必须遵守项
- 深灰+橙色配色
- 不对称布局
- 使用 Iconify 图标
- ...
```

完整模板：[`prompts/frontend/anti-ai-web.md`](../prompts/frontend/anti-ai-web.md)

---

## 方法 5：Agent Skills

### 核心思路

使用别人封装好的专业技能包，让 AI 学会去除 AI 味儿。

### 推荐 Skills

#### 5.1 Frontend-design（Anthropic 官方）

**安装方式（Claude Code）：**
```bash
# 1. 添加官方技能市场
/plugin marketplace add anthropics/skills

# 2. 安装技能包
/plugin install example-skills@anthropic-agent-skills
```

**使用方式：**
```
帮我开发个人作品集网站
```

AI 会主动问：我发现你安装了前端设计技能，需要用它吗？

确认后，AI 会生成独特风格的精美页面。

#### 5.2 UI UX Pro Max

最强大的去 AI 味儿技能。

**安装方式：**
```bash
# 1. 安装命令行工具
npm install -g uipro-cli

# 2. 进入项目目录，初始化（以 Cursor 为例）
uipro init --ai cursor
```

**工作原理：**
1. AI 根据你的需求识别产品类型和页面类型
2. 调用搜索脚本，在 data 目录里多维度搜索
3. 找到适合的配色、字体、布局风格
4. 综合生成完整设计方案
5. 按照方案生成代码

**优点：**
- AI 不需要把所有规则都背下来
- 用到哪个查哪个
- 生成的界面既专业又有设计感

---

## 方法 6：反 AI 味儿组件库

### 核心思路

不要让 AI 用主流组件库的默认样式，明确指定小众但有特色的组件库。

### 为什么主流库有 AI 味儿？

AI 为了保险，默认选最主流的：
- Shadcn UI
- Material UI
- Ant Design

这些库虽然专业，但**直接用默认样式，一眼就能认出来**。

### 推荐的小众库

#### 6.1 Aceternity UI

**特点：**150+ 炫酷视觉组件
**适合：**科技产品、SaaS 落地页

```
必须使用 Aceternity UI 设计网站
你需要阅读官方文档：https://ui.aceternity.com/components
```

**特色组件：**
- Sparkles - 闪光粒子
- Aurora Background - 极光背景
- Meteors - 流星效果

#### 6.2 Magic UI

**特点：**150+ 动画组件
**适合：**现代产品、设计工具

```
必须使用 Magic UI 设计网站
官方文档：https://magicui.design
```

#### 6.3 ikun-ui

**特点：**Svelte + UnoCSS，轻量快速
**适合：**练习时长两年半的项目🏀

```
必须使用 ikun-ui 设计网站
官方文档：https://ikun-ui.netlify.app
```

#### 6.4 Radix UI

**特点：**无样式原语，完全自定义
**适合：**需要完全控制样式的项目

```
必须使用 Radix UI 作为无样式原语，然后完全自定义样式。
不要使用任何默认样式的组件库。
```

### 配合 Context7 插件

对于小众组件库，AI 可能不熟悉用法：
1. 安装 Context7 插件（实时查询文档）
2. 或者直接把官方文档 URL 发给 AI

完整列表：[`resources/ui-libraries.md`](../resources/ui-libraries.md)

---

## 方法 7：自主配色

### 核心思路

用配色工具生成独特配色，告诉 AI 具体色值。

### 为什么要自主配色？

AI 默认会用：
- Tailwind CSS 默认色板
- 蓝紫色渐变（#6366F1、#8B5CF6）

这是最"安全"的选择，但也最容易产生 AI 味儿。

### 推荐配色工具

#### 7.1 Coolors

**特点：**快速生成配色方案

**使用流程：**
1. 访问 https://coolors.co
2. 按空格键生成随机配色
3. 点击颜色可以锁定
4. 满意后导出色值

#### 7.2 Adobe Color

**特点：**专业配色工具

**使用流程：**
1. 访问 https://color.adobe.com
2. 选择配色规则（互补色、类比色等）
3. 或从图片提取配色

### 使用方式

生成配色后，告诉 AI 具体色值：

```
配色要求：
- 主色：#FF6B35（暖橙色）
- 辅助色：#FFA500（琥珀色）
- 背景：#1A1A1A（深灰）
- 文字：#E5E5E5（浅灰）

禁止使用 #6366F1、#8B5CF6 等蓝紫色。
```

### 推荐配色方案

```css
/* 科技感：深灰 + 橙色 */
--color-bg: #1A1A1A;
--color-primary: #FF6B35;

/* 优雅感：黑白灰 + 金色 */
--color-bg: #FAFAFA;
--color-primary: #D4AF37;

/* 自然感：大地色 */
--color-bg: #F5F5DC;
--color-primary: #8B4513;
```

完整指南：[`resources/color-tools.md`](../resources/color-tools.md)

---

## 综合应用：完整提示词模板

将以上 7 个方法综合应用：

```markdown
开发 [项目类型] 的 [页面类型]

请严格遵守 AGENTS.md 中的设计规则。

## 方法 1：参考网站
请参考以下网站的设计风格：
- [网站 URL]
提取配色、布局、字体选择。

## 方法 2：设计优先
先生成纯静态页面，我确认设计后再继续开发功能。

## 方法 3：图片资源
- 图标：Iconify (https://iconify.design)
- 插画：unDraw (https://undraw.co)
- 照片：Pexels (https://www.pexels.com)
不要使用 Emoji 作为图标。

## 方法 4：约束条件
设计禁止清单：
❌ 蓝紫色渐变（#6366F1、#8B5CF6）
❌ Hero + 三卡片布局
❌ Emoji 图标
❌ 空洞文案

文案要求：
✅ 具体化："每天节省 2 小时"
✅ 口语化："用起来像呼吸一样自然"
✅ 带情绪："不用再找文件了"

## 方法 5：Agent Skills
（如果安装了 UI UX Pro Max，会自动启用）

## 方法 6：组件库
必须使用 Aceternity UI (https://ui.aceternity.com)
不要使用 Shadcn UI / Material UI 的默认样式。

## 方法 7：配色方案
- 主色：#FF6B35
- 辅助色：#FFA500
- 背景：#1A1A1A
- 文字：#E5E5E5
```

---

## 实战案例

完整案例对比：[`examples/before-after/frontend/case-studies.md`](../examples/before-after/frontend/case-studies.md)

包含：
- 个人技术博客
- SaaS 产品落地页
- 健身 APP 落地页

每个案例都展示了：
- 优化前的提示词和效果
- 优化后的提示词和效果
- 关键改进点分析

---

## 总结

**核心原则：**
1. 不要让 AI 凭空想象 → 给它参考对象
2. 不要一次做完所有事 → 先设计，后开发
3. 不要用占位符 → 主动提供图片资源
4. 不要说"要什么" → 更要说"不要什么"
5. 不要重复写提示词 → 封装为 Skills 或 AGENTS.md
6. 不要用主流默认样式 → 指定特色组件库
7. 不要让 AI 选颜色 → 自己生成配色方案

**一句话总结：**
从"请求者"变成"指挥官"，用明确的约束条件逼着 AI 偏离舒适区。
