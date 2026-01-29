# noai-flavor Skills

本目录包含 noai-flavor 的 AI Agent Skills，可以在各种 AI 工具中使用。

## 什么是 Skills？

Skills 是预先编写好的专业能力包，可以让 AI 在特定场景下表现更专业。安装 skill 后，你可以通过简单的命令或关键词触发使用。

## 可用 Skills

### noai-flavor

去除 AI 味儿助手，支持：
- **文本内容**：去除套话、emoji 滥用、三段论等
- **网站开发**：去除蓝紫渐变、Hero + 三卡片布局等

**使用场景：**
- 写文章、写文案、写公众号
- 开发网站、设计界面、前端开发

---

## 安装方法

### 方法 1：Claude Code（推荐）

```bash
# 1. 添加 noai-flavor skills 仓库
/plugin marketplace add yiancode/noai-flavor https://github.com/yiancode/noai-flavor

# 2. 安装 noai-flavor skill
/plugin install noai-flavor@yiancode/noai-flavor
```

安装后，可以使用：
```
/noai-flavor writing    # 文本内容去 AI 味儿
/noai-flavor web        # 网站开发去 AI 味儿
```

---

### 方法 2：Cursor

1. 将 `skills/noai-flavor.md` 的内容复制
2. 打开 Cursor 设置 > AI Rules
3. 创建一个新的 Rule，名称为 "noai-flavor"
4. 粘贴内容并保存

使用时，在 Prompt 中添加：
```
@noai-flavor 帮我写一篇文章...
```

---

### 方法 3：API 集成

如果你使用 Claude API 或 OpenAI API：

```python
import anthropic

# 读取 skill 内容
with open('skills/noai-flavor.md', 'r') as f:
    skill_content = f.read()

# 创建客户端
client = anthropic.Anthropic(api_key="your-api-key")

# 调用 API
message = client.messages.create(
    model="claude-sonnet-4-5-20250929",
    max_tokens=4096,
    system=[
        {
            "type": "text",
            "text": skill_content
        }
    ],
    messages=[
        {
            "role": "user",
            "content": "写一篇关于时间管理的文章"
        }
    ]
)

print(message.content)
```

---

### 方法 4：直接使用（任何 AI 工具）

1. 打开 `skills/noai-flavor.md`
2. 复制"Skill 内容"部分
3. 粘贴到 AI 对话中作为上下文
4. 然后提出你的需求

---

## 使用示例

### 示例 1：文本写作

**输入：**
```
/noai-flavor writing

写一篇关于时间管理的公众号文章，800 字左右
```

**AI 会：**
1. 识别这是文本内容场景
2. 应用反 AI 规则（不用套话、不用 emoji、不用三段论）
3. 生成符合规则的文章内容

---

### 示例 2：网站开发

**输入：**
```
/noai-flavor web

开发一个个人技术博客首页
```

**AI 会：**
1. 识别这是网站开发场景
2. 询问风格偏好（科技感/优雅/极简）
3. 应用反 AI 规则（不用蓝紫色、不用 Hero + 三卡片）
4. 使用推荐资源（Iconify、Pexels、特色组件库）
5. 生成代码

---

### 示例 3：智能识别

**输入：**
```
帮我写一篇小红书笔记，介绍我的新产品
```

**AI 会：**
1. 自动识别这是文本内容场景
2. 主动询问："我发现这是写作任务，需要启用 noai-flavor 去除 AI 味儿吗？"
3. 确认后应用规则

---

## 高级用法

### 自定义配置

你可以在调用时提供额外的约束：

```
/noai-flavor web

开发 SaaS 产品落地页

额外要求：
- 风格：科技感、黑客帝国风格
- 配色：黑色 + 绿色（矩阵风格）
- 组件库：Aceternity UI
- 必须有代码雨效果
```

---

### 平台特化

对于特定平台，可以结合使用：

**公众号文章：**
```
/noai-flavor writing

使用公众号平台规则（prompts/platforms/wechat.md）
写一篇关于...的文章
```

**知乎回答：**
```
/noai-flavor writing

使用知乎平台规则（prompts/platforms/zhihu.md）
回答这个问题：...
```

---

### 对比模式

查看优化前后的对比：

```
/noai-flavor writing --compare

写一篇关于时间管理的文章
```

AI 会展示：
- ❌ 优化前（AI 味儿重）
- ✅ 优化后（去除 AI 味儿）

---

## 故障排除

### Q1: Skill 不生效？

**检查：**
1. 是否正确安装了 skill？
2. 调用命令是否正确？（`/noai-flavor` 或 `@noai-flavor`）
3. 尝试重启 AI 工具

### Q2: 生成的内容还是有 AI 味儿？

**解决：**
1. 明确告诉 AI："请严格遵守 noai-flavor 规则"
2. 提供更具体的约束条件
3. 生成后让 AI 自检："请检查是否符合 noai-flavor 规则"

### Q3: 如何更新 skill？

**Claude Code：**
```bash
/plugin update noai-flavor@yiancode/noai-flavor
```

**其他方式：**
重新复制最新的 `skills/noai-flavor.md` 内容

---

## 贡献

如果你有改进建议：

1. Fork 项目：https://github.com/yiancode/noai-flavor
2. 修改 `skills/noai-flavor.md`
3. 提交 Pull Request

---

## 相关资源

- **项目文档**：https://github.com/yiancode/noai-flavor
- **反模式库**：[patterns/](../patterns/)
- **提示词模板**：[prompts/](../prompts/)
- **推荐资源**：[resources/](../resources/)
- **案例对比**：[examples/before-after/](../examples/before-after/)

---

## 反馈

使用过程中遇到问题或有建议？

- 提交 Issue：https://github.com/yiancode/noai-flavor/issues
- 讨论区：https://github.com/yiancode/noai-flavor/discussions

---

## License

MIT License

内容部分：CC BY 4.0
