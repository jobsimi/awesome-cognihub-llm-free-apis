<div align="center">
	<h1>AI2NV CogniHub LLM Free APIs</h1>
</div>

<div align="center">
    <a href="readme.zh.md">中文</a>
    <span>|</span>
    <a href="readme.md">English</a>
</div>

<br>

<div align="center">
    <p>Follow us in <a href="https://github.com/jobsimi/awesome-cognihub-llm-free-apis">Github</a> <span>| </span> <a href="https://gitee.com/jobsimi/awesome-cognihub-llm-free-apis">Gitee</a> to get the latest updates and discussions.</p>
</div>

<br>

# Contents

- [Contents](#contents)
- [QuickStart](#quickstart)
- [Supported Models](#supported-models)
- [In programming languages](#in-programming-languages)
  - [Shell](#shell)
  - [Python](#python)
  - [Node.js](#nodejs)
- [In Third Party Tools](#in-third-party-tools)
  - [In NextChat](#in-nextchat)
- [Q\&A](#qa)
  - [404 Not Found](#404-not-found)
- [Reference](#reference)

<br>

Add your “API_KEY” (You can get it after you purchase the package that includes this service) to the HTTP request header“Authorization” to access the service to use the API.

<div align="center">
    Go to AI2NV CogniHub and select service to purchase: <a href="https://cognihub.baystoneai.com/cognihub/pricing">https://cognihub.baystoneai.com/cognihub/pricing</a>
</div>

<br>

# QuickStart

Open your command line, paste the following and hit enter:

```sh
export API_BASE_URL="{SERVICE_API_BASE_URL}"
export API_KEY="{YOUR_API_KEY}"

curl -X POST $API_BASE_URL/v1/chat/completions -H "Content-Type: application/json" -H "Authorization: Bearer $API_KEY" -d '{
    "model": "llama3.1",
    "stream": true,
    "messages": [
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "英智人工智能智汇API是什么？"}
    ]
}'
```

# Supported Models

Purchase the package https://cognihub.baystoneai.com/cognihub/pricing that includes the API service to get the API_KEY, and then you can use the following models:

|     model      |                             API_BASE_URL                             |
| :------------: | :------------------------------------------------------------------: |
|    llama3.1    | https://api.baystoneai.com/cognihub/service/66b97dd5fb19cc7397384f42 |
| mistral-large  | https://api.baystoneai.com/cognihub/service/66bd78f0e12059ab04073ec2 |
| qwen2-instruct | https://api.baystoneai.com/cognihub/service/668b6ecdcd9460b2c6963a97 |

Need to support other models? Please go to the AI2NV CogniHub API platform to feedback: <a href="https://cognihub.baystoneai.com/cognihub/sale/contact">https://cognihub.baystoneai.com/cognihub/sale/contact</a>

# In programming languages

## Shell

```sh
export API_BASE_URL="{SERVICE_API_BASE_URL}"
export API_KEY="{YOUR_API_KEY}"

curl -X POST $API_BASE_URL/v1/chat/completions -H "Content-Type: application/json" -H "Authorization: Bearer $API_KEY" -d '{
    "model": "llama3.1",
    "stream": true,
    "messages": [
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "英智人工智能智汇API是什么？"}
    ]
}'
```

## Python

```python
from openai import OpenAI

API_BASE_URL = "{SERVICE_API_BASE_URL}"
API_KEY = "{YOUR_API_KEY}"


client = OpenAI(base_url=f"{API_BASE_URL}/v1", api_key=API_KEY)

response = client.chat.completions.create(
    model="llama3.1",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "英智人工智能智汇API是什么？"}
    ],
)

print(response.choices[0].message.content)
```

## Node.js

```js
import { OpenAI } from "openai";

const API_BASE_URL = "{SERVICE_API_BASE_URL}";
const API_KEY = "{YOUR_API_KEY}";

const client = new OpenAI({ baseURL: `${API_BASE_URL}/v1`, apiKey: API_KEY });

const response = await client.chat.completions.create({
  model: "llama3.1",
  messages: [
    { role: "system", content: "You are a helpful assistant." },
    { role: "user", content: "英智人工智能智汇API是什么？" },
  ],
});

console.log(response.choices[0].message.content);
```

# In Third Party Tools

## In NextChat

NextChat Online
https://app.nextchat.dev

1. Setting
2. Custom Endpoint
3. Model Provider：OpenAI
4. OpenAI Endpoint：{SERVICE_API_BASE_URL}
5. OpenAI API Key：{YOUR_API_KEY}
6. Custom Models：llama3.1
7. Model：select customed model
8. Enjoy

# Q&A

## 404 Not Found

Please check if the API_BASE_URL is correct. If you are using the OpenAI method to access, please add the API version "v1", that is:

{SERVICE_API_BASE_URL}/v1

# Reference

- OpenAI API compatible: https://ollama.com/blog/openai-compatibility
- Ollama API doc: https://github.com/ollama/ollama
