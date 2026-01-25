# Claude Code 集成

## 方式一：添加到 CLAUDE.md

在 `~/.claude/CLAUDE.md` 或项目根目录的 `CLAUDE.md` 中添加：

```markdown
## 写作规范

写作内容时，参考 noai-flavor 项目的指南，避免 AI 写作反模式。

核心规则：
- 不用 emoji 做列表标记
- 不用"在当今社会"、"综上所述"等套话
- 不用"首先其次最后"三段论
- 句式要有变化，像聊天不像写报告
- 开头直接切入，结尾不必总结

详细指南：https://github.com/xxx/noai-flavor
```

## 方式二：Skill 调用

如果你设置了自定义 Skill，可以创建一个写作 Skill：

```markdown
# 自然写作 Skill

## 触发
/write 或 /natural

## 执行
写作时自动应用 noai-flavor 规则。
```

## 方式三：项目特定配置

在项目的 `CLAUDE.md` 中指定平台：

```markdown
## 项目说明

这是一个公众号内容项目。

写作时参考 noai-flavor/prompts/platforms/wechat.md 的规则。
```

## 验证是否生效

让 Claude Code 写一段内容，检查：

1. 是否有 emoji 列表？
2. 是否用了"综上所述"？
3. 结构是否太死板？

如果还有 AI 味，可以在对话中明确提醒。
