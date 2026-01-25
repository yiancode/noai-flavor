# API 调用示例

## Python

```python
import requests

# 获取核心 prompt
def get_anti_ai_prompt():
    url = "https://raw.githubusercontent.com/xxx/noai-flavor/main/prompts/base/anti-ai-core.md"
    response = requests.get(url)
    # 提取代码块中的 prompt 内容
    content = response.text
    # 简单处理：取 ``` 之间的内容
    start = content.find("```\n") + 4
    end = content.find("\n```", start)
    return content[start:end]

# 使用示例
from openai import OpenAI

client = OpenAI()

system_prompt = get_anti_ai_prompt()

response = client.chat.completions.create(
    model="gpt-4",
    messages=[
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": "写一篇关于时间管理的短文"}
    ]
)

print(response.choices[0].message.content)
```

## JavaScript/TypeScript

```typescript
async function getAntiAiPrompt(): Promise<string> {
  const url = 'https://raw.githubusercontent.com/xxx/noai-flavor/main/prompts/base/anti-ai-core.md';
  const response = await fetch(url);
  const content = await response.text();

  // 提取 prompt 内容
  const match = content.match(/```\n([\s\S]*?)\n```/);
  return match ? match[1] : '';
}

// 使用示例
import Anthropic from '@anthropic-ai/sdk';

const client = new Anthropic();

const systemPrompt = await getAntiAiPrompt();

const message = await client.messages.create({
  model: 'claude-sonnet-4-20250514',
  max_tokens: 1024,
  system: systemPrompt,
  messages: [
    { role: 'user', content: '写一篇关于时间管理的短文' }
  ]
});

console.log(message.content[0].text);
```

## 本地缓存

频繁调用时建议缓存 prompt：

```python
import os
import requests
from datetime import datetime, timedelta

CACHE_FILE = '/tmp/noai-prompt-cache.txt'
CACHE_EXPIRY = timedelta(hours=24)

def get_anti_ai_prompt_cached():
    # 检查缓存
    if os.path.exists(CACHE_FILE):
        mtime = datetime.fromtimestamp(os.path.getmtime(CACHE_FILE))
        if datetime.now() - mtime < CACHE_EXPIRY:
            with open(CACHE_FILE, 'r') as f:
                return f.read()

    # 重新获取
    prompt = get_anti_ai_prompt()
    with open(CACHE_FILE, 'w') as f:
        f.write(prompt)
    return prompt
```

## 平台特定 Prompt

```python
PLATFORM_URLS = {
    'wechat': 'prompts/platforms/wechat.md',
    'zhihu': 'prompts/platforms/zhihu.md',
    'xiaohongshu': 'prompts/platforms/xiaohongshu.md',
}

def get_platform_prompt(platform: str) -> str:
    base_url = 'https://raw.githubusercontent.com/xxx/noai-flavor/main/'
    url = base_url + PLATFORM_URLS.get(platform, 'prompts/base/anti-ai-core.md')
    response = requests.get(url)
    return response.text
```
