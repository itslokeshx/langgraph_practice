# LangGraph Practice

Hands-on exploration of building AI agent workflows with [LangGraph](https://langchain-ai.github.io/langgraph/) — from a trivial node graph to a full-featured chatbot with tool calling, persistent memory, time travel, and a Gradio UI.

## Features Demonstrated

- **StateGraph basics** — defining states, nodes, and edges
- **LLM-powered chatbot** — using Groq for fast inference
- **Tool calling** — web search (Serper API) and push notifications (Pushover)
- **Autonomous tool routing** — `ToolNode` + `tools_condition`
- **Conversation memory** — in-memory (`MemorySaver`) and persistent SQLite (`SqliteSaver`) checkpointing
- **Time travel** — replaying and branching from past checkpoints
- **Gradio chat interface** — interactive web UI for the agent

## Contents

| File | Purpose |
|---|---|
| `LangGraph_Lab.ipynb` | Main Jupyter notebook with all code and experiments |
| `req.txt` | Python dependencies |
| `.env` | API keys (Groq, Serper, Pushover) |
| `memory.db` | SQLite checkpoint store (auto-created) |

## Requirements

- Python 3.12+
- API keys for: [Groq](https://console.groq.com), [Serper](https://serper.dev), [Pushover](https://pushover.net)

## Setup

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r req.txt
```

Create a `.env` file:

```
GROQ_API_KEY=your_key
SERPER_API_KEY=your_key
PUSHOVER_USER=your_user_key
PUSHOVER_TOKEN=your_app_token
```

## Usage

Launch Jupyter and run the notebook cells sequentially:

```bash
jupyter notebook LangGraph_Lab.ipynb
```

Or run the Gradio chat UI from the last cell to interact with the agent in your browser.

## Notebook Overview

1. **Silly Graph** — minimal LangGraph with a single node
2. **Chatbot** — LLM invocation via `ChatGroq`
3. **Tool-using Agent** — web search + push notifications
4. **With Memory** — conversation history via `MemorySaver`
5. **Persistent Memory** — SQLite-backed checkpoints
6. **Checkpoint Inspection** — browsing saved states
7. **Time Travel** — branching from past checkpoints
8. **Gradio UI** — web chat interface
