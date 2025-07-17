# 🤖 AI Agent with MCP Server

This project demonstrates how to build intelligent AI agents using a custom **MCP Server**. These agents go beyond basic chatbots by interacting with real-world tools such as APIs, performing actions like posting tweets, calculating values, or fetching external data — all in real time.

By connecting a Large Language Model (LLM) such as **Gemini** or **OpenAI GPT** to the MCP server, the agent can call tools, access the internet, and maintain contextual conversations using real-time capabilities.

---

## ✨ Features

- 🧠 AI agent capable of calling tools using natural language.
- 🌐 Internet + API access via tools defined on an MCP server.
- 🧰 Modular tools using Zod validation schemas.
- 🔁 Real-time interaction using Server-Sent Events (SSE).
- 📤 Automate posting on platforms like Twitter using an AI agent.
- 🛠️ Easily extendable tool system for new functionalities.

---

## 🧱 Tech Stack

- **Node.js + TypeScript** – Backend server and tools
- **Express.js** – MCP Server
- **Zod** – Schema validation for tool parameters
- **SSE (Server-Sent Events)** – Real-time communication
- **Gemini / OpenAI GPT** – LLMs powering the agent
- **Twitter API** – For posting tweets automatically

---


---

## ⚙️ Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/ai-agent-mcp.git
cd ai-agent-mcp
```
### 2. Install dependencies
Install server dependencies:
```bash
cd server
npm install
```
Install Client dependencies:
```bash
cd ../client
npm install
```
### 3. Setup environment variables
Create a .env file in both server/ and client/ directories with the following content:

```bash
# For Twitter API
TWITTER_API_KEY=your_api_key
TWITTER_API_SECRET=your_api_secret
TWITTER_ACCESS_TOKEN=your_access_token
TWITTER_ACCESS_SECRET=your_access_token_secret

# For Gemini/OpenAI
GEMINI_API_KEY=your_gemini_api_key
OPENAI_API_KEY=your_openai_api_key

# Port
PORT=3010

```
### 4. Run the MCP server

```bash
cd server
npx tsx mcpServer.ts
```

## 🛠️ Available Tools

You can define custom tools inside the `server/tools/` folder. Each tool includes:

- A function to perform a task (e.g., posting a tweet)
- A Zod schema to validate inputs

### ✨ Examples

- `postTweet`: Posts a tweet using the Twitter API.
- `addNumbers`: Adds two numbers passed as input.

### 🔧 Creating Your Own Tools

To create a custom tool:

1. **Define the function logic** inside a new file in `server/tools/`
2. **Add a Zod schema** to validate the input parameters
3. **Register the tool** in `tools/index.ts` so it can be invoked by the MCP agent



