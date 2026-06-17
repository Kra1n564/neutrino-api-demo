# Neutrino API Demo

Example code for Neutrino API — a $5 OpenAI-compatible API with 5 million tokens. Same format, half the cost.

## Quick Start (Python)

```bash
pip install openai
```

```python
from openai import OpenAI

client = OpenAI(
    base_url="https://api.neutrinoitapi.com/v1",
    api_key="your-api-key"
)

response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[
        {"role": "user", "content": "Explain quantum computing in simple terms."}
    ]
)

print(response.choices[0].message.content)
```

## Streaming (Python)

```python
from openai import OpenAI

client = OpenAI(
    base_url="https://api.neutrinoitapi.com/v1",
    api_key="your-api-key"
)

stream = client.chat.completions.create(
    model="deepseek-chat",
    messages=[{"role": "user", "content": "Write a haiku about programming."}],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="")
```

## Node.js

```bash
npm install openai
```

```javascript
import OpenAI from 'openai';

const client = new OpenAI({
  baseURL: 'https://api.neutrinoitapi.com/v1',
  apiKey: 'your-api-key',
});

const response = await client.chat.completions.create({
  model: 'deepseek-chat',
  messages: [{ role: 'user', content: 'Hello!' }],
});

console.log(response.choices[0].message.content);
```

## Pricing

$5 for 5 million tokens. One-time. No subscription.

[Get your API key →](https://neutrinoitapi.com)
````

拉到页面底部，点 **"Commit new file"**。

---

## 第三步：创建两个示例文件（5分钟）

仍在仓库页面，点 **"Add file"** → **"Create new file"**。

### 文件一：`example_nonstream.py`

文件名填 `example_nonstream.py`，内容：

```python
"""
Neutrino API - Non-streaming example
$5 for 5 million tokens | https://neutrinoitapi.com
"""
from openai import OpenAI

client = OpenAI(
    base_url="https://api.neutrinoitapi.com/v1",
    api_key="your-api-key"
)

response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[
        {"role": "user", "content": "Explain quantum computing in simple terms."}
    ]
)

print(response.choices[0].message.content)
```

点 **"Commit new file"**。

### 文件二：`example_stream.py`

再点 **"Add file"** → **"Create new file"**，文件名填 `example_stream.py`，内容：

```python
"""
Neutrino API - Streaming example
$5 for 5 million tokens | https://neutrinoitapi.com
"""
from openai import OpenAI

client = OpenAI(
    base_url="https://api.neutrinoitapi.com/v1",
    api_key="your-api-key"
)

stream = client.chat.completions.create(
    model="deepseek-chat",
    messages=[{"role": "user", "content": "Write a haiku about programming."}],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="")
```


开发者点进去看到的是 README，里面有完整的 Python 和 Node.js 示例，复制粘贴改个 Key 就能跑。
