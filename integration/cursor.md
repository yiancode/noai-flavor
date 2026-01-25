# Cursor 集成

## 方式一：项目 Rules

在项目根目录创建 `.cursorrules` 文件：

```
# 写作规则

生成文案、文档、注释时，遵守以下规则：

## 禁止
- emoji 做列表标记
- "在当今"、"综上所述"等套话
- "首先其次最后"三段论
- 过度使用感叹号

## 要求
- 句式有变化
- 开头直接切入
- 像说话，不像写报告
- 可以不完美，不必面面俱到
```

## 方式二：全局 Rules

在 Cursor 设置中添加全局规则，适用于所有项目。

Settings → General → Rules for AI

## 适用场景

Cursor 集成主要用于：

- 代码注释（避免过度解释）
- README 和文档
- Commit message
- PR description

## 代码注释示例

❌ AI 味注释：
```python
# 这个函数用于计算用户的年龄
# 首先，它会获取用户的出生日期
# 然后，计算当前日期与出生日期的差值
# 最后，返回年龄值
def calculate_age(birth_date):
    ...
```

✅ 自然注释：
```python
# 根据生日算年龄
def calculate_age(birth_date):
    ...
```
