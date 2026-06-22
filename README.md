## Who is this for?

You want to use DeepSeek models, which are much cheaper than OpenAI. But:
- You don't have a Chinese phone number to register on DeepSeek's platform
- You don't use Alipay or WeChat to pay
- You want to pay in USD with a credit card
- You just want an OpenAI-compatible endpoint that works

→ This demo shows how to use Neutrino API as a drop-in replacement.
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

## Real example: cut your API bill in half

**Before (OpenAI GPT-4o mini):**
- $0.15 per 1M input tokens
- $0.60 per 1M output tokens
- Must prepay to get started

**After (Neutrino API with DeepSeek):**
- $5 flat = 5 million tokens total
- Same /v1/chat/completions endpoint
- Your existing OpenAI code changes 3 lines
## Pricing

$5 for 5 million tokens. One-time. No subscription.

[Get your API key →](https://neutrinoitapi.com)
