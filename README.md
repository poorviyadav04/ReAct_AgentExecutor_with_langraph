# ReAct Agent Executor with LangGraph

## Overview

This project implements a **ReAct-style AI agent** using **LangGraph** and **LangChain**.
The agent can reason about a query, decide when to use tools, execute them, and continue reasoning until it reaches a final answer.

## Tech Stack

* Python
* LangGraph
* LangChain
* Tavily Search API
* Claude / OpenAI compatible LLM
* python-dotenv

## Project Structure

```
project/
│
├── main.py     # Builds and runs the LangGraph workflow
├── nodes.py    # Agent reasoning node and tool node
├── react.py    # LLM setup and tool definitions
├── .env        # API keys
```

## Agent Workflow

The agent follows the **ReAct (Reason + Act)** pattern:

User Query
→ LLM Reasoning
→ Tool Call (if needed)
→ Tool Execution
→ Final Answer

## Tools Used

* **Tavily Search** – retrieves real-time web information
* **Triple Function** – simple demo tool that multiplies a number by three

## Setup

### Install dependencies

```
pip install langgraph langchain langchain-anthropic langchain-tavily python-dotenv
```

### Configure environment variables

Create a `.env` file:

```
ANTHROPIC_API_KEY=your_api_key
TAVILY_API_KEY=your_api_key
```

## Run the Project

```
python main.py
```

Example prompt:

```
What is the temperature in Delhi? List it and then triple it.
```

## License

MIT
