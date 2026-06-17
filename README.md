# Neutrino API Demo

## Quick Start (Python)

\`\`\`bash
pip install openai
\`\`\`

\`\`\`python
from openai import OpenAI

client = OpenAI(
    base_url="https://api. 你的域名.com/v1",
    api_key="your-api-key"
)

response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[
        {"role": "user", "content": "Explain quantum computing in simple terms."}
    ]
)

print(response.choices[0].message.content)
\`\`\`

## Streaming (Python)

\`\`\`python
from openai import OpenAI

client = OpenAI(
    base_url="https://api. 你的域名.com/v1",
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
\`\`\`

## Node.js

\`\`\`bash
npm install openai
\`\`\`

\`\`\`javascript
import OpenAI from 'openai';

const client = new OpenAI({
  baseURL: 'https://api. 你的域名.com/v1',
  apiKey: 'your-api-key',
});

const response = await client.chat.completions.create({
  model: 'deepseek-chat',
  messages: [{ role: 'user', content: 'Hello!' }],
});

console.log(response.choices[0].message.content);
\`\`\`

---

[Get your API key →](https://www.neutrinoitapi.com/)
