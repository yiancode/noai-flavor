# noai-flavor

去除 AI 味儿 —— 一个帮助 AI 生成更自然内容的开源指南库。

## 为什么需要这个项目？

### 文本内容的 AI 味儿

用 AI 辅助写作时，生成的内容常常带有明显的"AI味"：

- 开头总是"在当今社会..."
- 每段都用 emoji 装饰 ✅❌🎯
- 结构永远是"首先...其次...最后..."
- 结尾必有"总之"、"综上所述"

### 网站设计的 AI 味儿

用 AI 开发网站时，生成的界面也有明显的"AI味"：

- 配色死板：蓝紫渐变色用到吐（#6366F1、#8B5CF6）
- 布局死板：首屏放个大标题，下面三个卡片并排
- 字体死板：基本上就是 Inter、Roboto 等几种固定字体
- Emoji 泛滥：🚀⚡🔒 满屏幕都是表情图标
- 内容空洞：基本没有真实图片，文字风格也比较刻板

这些模式一眼就能被认出，让内容失去真实感。

**noai-flavor** 收集了这些反模式（文本 + 前端），并提供可直接使用的 Prompt，帮助你让 AI 生成更有人味的内容。

## 快速开始

### 方式 0：使用 Skills（推荐 ⭐）

最简单的使用方式是安装 noai-flavor skill，一键触发去除 AI 味儿。

#### Claude Code

```bash
# 1. 添加 noai-flavor skills 仓库
/plugin marketplace add yiancode/noai-flavor https://github.com/yiancode/noai-flavor

# 2. 安装 skill
/plugin install noai-flavor@yiancode/noai-flavor
```

使用：
```bash
/noai-flavor writing    # 文本内容去 AI 味儿
/noai-flavor web        # 网站开发去 AI 味儿
```

#### 其他 AI 工具

查看完整安装指南：[skills/README.md](skills/README.md)

---

### 文本内容去 AI 味儿

#### 方式一：直接使用 Prompt

复制 [`prompts/base/anti-ai-core.md`](prompts/base/anti-ai-core.md) 的内容，添加到你的 AI 对话的 System Prompt 中。

#### 方式二：按平台使用

- 公众号：[`prompts/platforms/wechat.md`](prompts/platforms/wechat.md)
- 知乎：[`prompts/platforms/zhihu.md`](prompts/platforms/zhihu.md)
- 小红书：[`prompts/platforms/xiaohongshu.md`](prompts/platforms/xiaohongshu.md)

### 网站开发去 AI 味儿

#### 方式一：使用 AGENTS.md 文件

将 [`prompts/frontend/anti-ai-web.md`](prompts/frontend/anti-ai-web.md) 的内容保存为 `AGENTS.md` 或 `.cursorrules`，放在项目根目录。

主流 AI 编程工具（Cursor、Claude Code、Windsurf 等）会自动读取这个文件。

#### 方式二：学习反模式

阅读 [`patterns/frontend/`](patterns/frontend/) 目录下的反模式文档，了解如何避免 AI 味儿：

- [蓝紫渐变配色](patterns/frontend/color-schemes.md)
- [Hero + 三卡片布局](patterns/frontend/layout-patterns.md)
- [过度依赖主流组件库](patterns/frontend/component-libraries.md)
- [空洞内容和占位符](patterns/frontend/empty-content.md)

#### 方式三：使用推荐资源

查看 [`resources/`](resources/) 目录下的资源推荐：

- [UI 组件库](resources/ui-libraries.md) - Aceternity UI、Magic UI 等特色组件库
- [图片资源](resources/image-resources.md) - Iconify、Pexels、unDraw 等
- [配色工具](resources/color-tools.md) - Coolors、Adobe Color 等
- [设计工具](resources/design-tools.md) - Google Stitch、Figma 等

### 集成到工具

- [Claude Code 集成](integration/claude-code.md)
- [ChatGPT 使用方式](integration/chatgpt.md)
- [Cursor 集成](integration/cursor.md)
- [API 调用示例](integration/api-usage.md)

## 项目结构

```
noai-flavor/
├── skills/            # AI Agent Skills（一键触发）
├── patterns/          # AI 反模式库（要避免的写法）
│   ├── frontend/      # 前端开发反模式
│   └── ...            # 文本内容反模式
├── prompts/           # 可直接使用的 Prompt
│   ├── base/          # 基础提示词
│   ├── frontend/      # 前端开发提示词
│   └── platforms/     # 平台特化提示词
├── resources/         # 推荐资源
│   ├── ui-libraries.md      # UI 组件库
│   ├── image-resources.md   # 图片资源
│   ├── color-tools.md       # 配色工具
│   └── design-tools.md      # 设计工具
├── examples/          # 对比示例（AI味 vs 自然）
├── integration/       # 工具集成指南
└── scripts/           # 辅助脚本
```

## 核心反模式

### 文本内容反模式

| 反模式 | 说明 | 文档 |
|--------|------|------|
| Emoji 滥用 | 用 ✅❌🎯 做列表标记 | [patterns/emoji-abuse.md](patterns/emoji-abuse.md) |
| 套话陈词 | "不是...而是..."、"众所周知" | [patterns/cliche-phrases.md](patterns/cliche-phrases.md) |
| 模板结构 | 死板的总分总、三段论 | [patterns/template-structures.md](patterns/template-structures.md) |
| 机械过渡 | "接下来"、"下面我们来看" | [patterns/transition-patterns.md](patterns/transition-patterns.md) |
| 列表强迫症 | 什么都要列成 1234 | [patterns/list-obsession.md](patterns/list-obsession.md) |

### 前端开发反模式

| 反模式 | 说明 | 文档 |
|--------|------|------|
| 蓝紫渐变配色 | #6366F1、#8B5CF6 用到吐 | [patterns/frontend/color-schemes.md](patterns/frontend/color-schemes.md) |
| Hero + 三卡片布局 | 千篇一律的布局模式 | [patterns/frontend/layout-patterns.md](patterns/frontend/layout-patterns.md) |
| 过度依赖主流组件库 | Shadcn/Material UI 默认样式 | [patterns/frontend/component-libraries.md](patterns/frontend/component-libraries.md) |
| 固定字体选择 | Inter、Roboto 用到吐 | [patterns/frontend/typography.md](patterns/frontend/typography.md) |
| 空洞内容和占位符 | Emoji 图标、灰色占位图、空洞文案 | [patterns/frontend/empty-content.md](patterns/frontend/empty-content.md) |

## 推荐资源

### UI 组件库

不要直接使用主流组件库的默认样式，试试这些有特色的组件库：

- **[Aceternity UI](https://ui.aceternity.com)** - 炫酷视觉效果（Sparkles、Aurora、Meteors）
- **[Magic UI](https://magicui.design)** - 动画组件、流光边框
- **[ikun-ui](https://ikun-ui.netlify.app)** - Svelte + UnoCSS（练习时长两年半🏀）
- **[Radix UI](https://www.radix-ui.com)** - 无样式原语，完全自定义
- **[Mantine](https://mantine.dev)** - 100+ 组件，功能丰富

完整列表：[resources/ui-libraries.md](resources/ui-libraries.md)

### 图片资源

不要用 Emoji 和灰色占位图，使用这些真实资源：

- **[Iconify](https://iconify.design)** - 20 万+ 免费矢量图标
- **[unDraw](https://undraw.co)** - 免费 SVG 插画，可自定义颜色
- **[Pexels](https://www.pexels.com)** - 高质量免费照片
- **[Picsum Photos](https://picsum.photos)** - 占位图（真实照片，不是灰色方块）

完整列表：[resources/image-resources.md](resources/image-resources.md)

### 配色工具

不要用蓝紫渐变，生成独特配色：

- **[Coolors](https://coolors.co)** - 快速生成配色方案
- **[Adobe Color](https://color.adobe.com)** - 专业配色工具

完整列表：[resources/color-tools.md](resources/color-tools.md)

### 设计工具

设计优先开发，不要一次梭哈：

- **[Google Stitch](https://stitch.google.com)** - AI 设计工具
- **[Figma](https://www.figma.com)** - 专业设计工具
- **[Screenshot to Code](https://screenshottocode.com)** - 截图转代码

完整列表：[resources/design-tools.md](resources/design-tools.md)

## 使用示例

### Skills 使用示例

#### 文本写作

```bash
/noai-flavor writing

写一篇关于时间管理的公众号文章，800 字左右
```

AI 会：
- 自动应用反 AI 规则
- 不用套话开头
- 不用三段论结构
- 不用 emoji 装饰
- 生成自然的文章内容

#### 网站开发

```bash
/noai-flavor web

开发一个个人技术博客首页
```

AI 会：
- 询问风格偏好（科技感/优雅/极简）
- 应用反 AI 规则（不用蓝紫色、不用 Hero + 三卡片）
- 使用推荐资源（Iconify 图标、Pexels 图片）
- 生成有个性的网站代码

完整示例：[examples/before-after/](examples/before-after/)

## 7 个去除网站 AI 味儿的方法

1. **让 AI 参考真实网站** - 提供具体参考对象
2. **设计优先开发** - 先做 Demo，再开发功能
3. **丰富网站图片** - 使用 Iconify、Pexels、unDraw 等资源
4. **提示词约束** - 反向提示、角色设定、语境注入
5. **Agent Skills** - 使用 noai-flavor skill（本项目提供）
6. **反 AI 味儿组件库** - 使用 Aceternity UI、Magic UI 等特色库
7. **自主配色** - 使用 Coolors、Adobe Color 生成独特配色

完整说明：[patterns/frontend/7-methods.md](patterns/frontend/7-methods.md)

## 贡献

欢迎提交新的反模式或改进建议！请查看 [CONTRIBUTING.md](CONTRIBUTING.md)。

## License

- 代码：MIT License
- 内容：CC BY 4.0
