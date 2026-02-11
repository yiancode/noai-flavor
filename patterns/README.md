# AI 写作反模式索引

这个目录收集了 AI 写作中常见的"AI味"特征。每个文件包含：

- 特征描述
- 反面示例
- 改进写法
- 供 AI 参考的规则

## 反模式列表

### 内容层面

| 文件 | 反模式 | 严重程度 | 说明 |
|------|--------|----------|------|
| [cliche-phrases.md](cliche-phrases.md) | 套话陈词 | 高 | "在当今社会"、"不是...而是..." |
| [template-structures.md](template-structures.md) | 模板化结构 | 高 | 总分总、三段论、挑战与展望模板 |
| [significance-inflation.md](significance-inflation.md) | 夸大意义 | 高 | "标志着关键时刻"、"深远影响" |
| [promotional-language.md](promotional-language.md) | 宣传式语言 | 高 | "坐落于"、"充满活力的"、"令人叹为观止" |
| [vague-attribution.md](vague-attribution.md) | 模糊归因 | 高 | "专家认为"、"研究表明"却没有具体来源 |
| [superficial-analysis.md](superficial-analysis.md) | 肤浅分析 | 中 | "反映了"、"象征着"、"彰显了"假装有深度 |
| [generic-conclusions.md](generic-conclusions.md) | 通用积极结论 | 中 | "未来可期"、"前景光明" |

### 语言和词汇层面

| 文件 | 反模式 | 严重程度 | 说明 |
|------|--------|----------|------|
| [ai-vocabulary.md](ai-vocabulary.md) | AI 高频词汇 | 高 | "此外"、"深入探讨"、"至关重要"、"格局" |
| [grammar-tricks.md](grammar-tricks.md) | 语法小花招 | 中 | 系动词回避、否定排比、同义词循环、虚假范围 |
| [over-hedging.md](over-hedging.md) | 过度限定 | 中 | "可以潜在地可能被认为" |

### 格式和风格层面

| 文件 | 反模式 | 严重程度 | 说明 |
|------|--------|----------|------|
| [emoji-abuse.md](emoji-abuse.md) | Emoji 滥用 | 高 | 用 ✅❌🎯 做列表标记 |
| [list-obsession.md](list-obsession.md) | 列表强迫症 | 中 | 什么都要列成 1234，内联标题列表 |
| [formatting-overuse.md](formatting-overuse.md) | 格式滥用 | 中 | 破折号过度、粗体过度 |
| [transition-patterns.md](transition-patterns.md) | 机械过渡句 | 中 | "接下来"、"下面我们来看"、填充短语 |

### 交互痕迹层面

| 文件 | 反模式 | 严重程度 | 说明 |
|------|--------|----------|------|
| [chatbot-artifacts.md](chatbot-artifacts.md) | 聊天机器人痕迹 | 高 | "希望对您有帮助"、知识截止声明 |
| [sycophantic-tone.md](sycophantic-tone.md) | 谄媚语气 | 中 | "好问题！"、"您说得完全正确！" |

## 如何使用

1. **了解特征**：阅读每个反模式的描述，识别这些特征
2. **构建 Prompt**：将"规则"部分的内容加入你的 System Prompt
3. **对照检查**：写完后对照检查是否踩坑
4. **评分验证**：使用 [质量评分体系](../resources/quality-scoring.md) 量化检查效果

## 贡献新反模式

发现新的 AI 写作特征？参考现有文件格式，提交 PR。
