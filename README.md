# noai-flavor

去除 AI 味儿 —— 一个帮助 AI 写作更自然的开源指南库。

## 为什么需要这个项目？

用 AI 辅助写作时，生成的内容常常带有明显的"AI味"：

- 开头总是"在当今社会..."
- 每段都用 emoji 装饰 ✅❌🎯
- 结构永远是"首先...其次...最后..."
- 结尾必有"总之"、"综上所述"

这些模式一眼就能被认出，让内容失去真实感。

**noai-flavor** 收集了这些反模式，并提供可直接使用的 Prompt，帮助你让 AI 写出更有人味的内容。

## 快速开始

### 方式一：直接使用 Prompt

复制 [`prompts/base/anti-ai-core.md`](prompts/base/anti-ai-core.md) 的内容，添加到你的 AI 对话的 System Prompt 中。

### 方式二：按平台使用

- 公众号：[`prompts/platforms/wechat.md`](prompts/platforms/wechat.md)
- 知乎：[`prompts/platforms/zhihu.md`](prompts/platforms/zhihu.md)
- 小红书：[`prompts/platforms/xiaohongshu.md`](prompts/platforms/xiaohongshu.md)

### 方式三：集成到工具

- [Claude Code 集成](integration/claude-code.md)
- [ChatGPT 使用方式](integration/chatgpt.md)
- [Cursor 集成](integration/cursor.md)
- [API 调用示例](integration/api-usage.md)

## 项目结构

```
noai-flavor/
├── patterns/          # AI 反模式库（要避免的写法）
├── guidelines/        # 自然写作指南
├── prompts/           # 可直接使用的 Prompt
├── examples/          # 对比示例（AI味 vs 自然）
├── integration/       # 工具集成指南
└── scripts/           # 辅助脚本
```

## 核心反模式

| 反模式 | 说明 | 文档 |
|--------|------|------|
| Emoji 滥用 | 用 ✅❌🎯 做列表标记 | [patterns/emoji-abuse.md](patterns/emoji-abuse.md) |
| 套话陈词 | "不是...而是..."、"众所周知" | [patterns/cliche-phrases.md](patterns/cliche-phrases.md) |
| 模板结构 | 死板的总分总、三段论 | [patterns/template-structures.md](patterns/template-structures.md) |
| 机械过渡 | "接下来"、"下面我们来看" | [patterns/transition-patterns.md](patterns/transition-patterns.md) |
| 列表强迫症 | 什么都要列成 1234 | [patterns/list-obsession.md](patterns/list-obsession.md) |

## 贡献

欢迎提交新的反模式或改进建议！请查看 [CONTRIBUTING.md](CONTRIBUTING.md)。

## License

- 代码：MIT License
- 内容：CC BY 4.0
