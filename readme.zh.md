<div align="center">
	<h1>英智Llama3.1服务</h1>
</div>

<div align="center">
    <a href="readme.zh.md">中文</a>
    <span>|</span>
    <a href="readme.md">English</a>
</div>

<br>

<div align="center">
    <p>查看<a href="https://github.com/jobsimi/awesome-cognihub-llm-free-apis">Github</a> <span>| </span> <a href="https://gitee.com/jobsimi/awesome-cognihub-llm-free-apis">Gitee</a>获取最新内容</p>
</div>

<br>

<br>

# 目录

- [目录](#目录)
- [快速使用](#快速使用)
- [在编程语言里使用](#在编程语言里使用)
  - [Shell](#shell)
  - [Python](#python)
  - [Node.js](#nodejs)
- [在第三方应用里使用](#在第三方应用里使用)
  - [在 NextChat 里使用](#在-nextchat-里使用)
- [Q\&A](#qa)
  - [404 Not Found](#404-not-found)
- [参考](#参考)

<br>

将您的“API_KEY”（购买包含本服务的套餐后才可拿到）添加到 HTTP 请求头“Authorization”中即可接入本服务来使用 API。

<div align="center">
    前往英智智汇API平台，并点击 立即购买： <a href="https://cognihub.baystoneai.com/cognihub/doc/service/66b97dd5fb19cc7397384f42">https://cognihub.baystoneai.com/cognihub/doc/service/66b97dd5fb19cc7397384f42</a>
</div>

<br>

# 快速使用

打开您的命令行，粘贴如下的内容，然后回车即可：

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

# 在编程语言里使用

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

# 在第三方应用里使用

## 在 NextChat 里使用

NextChat 在线版
https://app.nextchat.dev

1. 设置
2. 自定义接口
3. 模型服务商：OpenAI
4. 接口地址：{SERVICE_API_BASE_URL}
5. API Key：{YOUR_API_KEY}
6. 自定义模型名：llama3.1
7. 模型：选择自定义的模型
8. Enjoy

# Q&A

## 404 Not Found

请检查 API_BASE_URL 是否正确，如果使用 OpenAI 方式接入，请带上 API 的版本“v1”，即：

{SERVICE_API_BASE_URL}/v1

# 参考

- OpenAI API compatible: https://ollama.com/blog/openai-compatibility
- Ollama API 文档: https://github.com/ollama/ollama
