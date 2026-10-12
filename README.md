# AI Finance Assistant

An AI-powered financial analyst that uses **Retrieval-Augmented Generation (RAG)** to answer questions about your spending in natural language. Built as a single-file HTML app — no server, no database, no tracking.

## Features

- **RAG-Powered Q&A** — Ask anything about your finances and get answers grounded in your actual transaction data
- **Smart Context Retrieval** — Automatically finds the most relevant transactions for each question
- **CSV/JSON Upload** — Load your own transaction data or use built-in Ghanaian sample data
- **Financial Dashboard** — Live stats: income, spending, net savings, transaction count
- **Quick Prompts** — One-click questions: top spending, cancel subscriptions, savings trend, health summary
- **Conversation Memory** — Maintains context across multiple questions in a session
- **Privacy-First** — All data stays in your browser. Only the relevant transactions are sent to the API, never your full dataset.

## How It Works

1. **Data Loading** — Upload a CSV/JSON file or load sample data (30 Ghanaian transactions across Sep-Oct 2026)
2. **RAG Pipeline** — When you ask a question, the system:
   - Scores all transactions by relevance to your query
   - Retrieves the top 10 most relevant transactions
   - Sends them to the LLM as context along with your question
3. **LLM Response** — Claude 3 Haiku (via OpenRouter) generates a grounded, conversational answer

## Tech Stack

- **Frontend**: Vanilla HTML/CSS/JS (single file, zero dependencies)
- **AI**: Anthropic Claude 3 Haiku via OpenRouter API
- **RAG**: Custom keyword-scoring retrieval system (no vector DB needed for this scale)
- **Storage**: Browser localStorage (API key only)

## Getting Started

### Quick Start

1. Open `ai-finance-assistant.html` in any modern browser
2. Click **"Load Sample Data"** to explore with demo data
3. Add your [OpenRouter API key](https://openrouter.ai/keys) (free tier works)
4. Ask questions like:
   - "Where did I spend the most this month?"
   - "What subscriptions can I cancel?"
   - "How much did I save vs last month?"
   - "Give me a financial health summary"

### Upload Your Own Data

**CSV Format:**
```csv
date,description,amount,category
2026-10-01,Salary,5000,Income
2026-10-02,Rent,-1200,Housing
2026-10-03,Groceries,-350,Food
```

**JSON Format:**
```json
[
  { "date": "2026-10-01", "description": "Salary", "amount": 5000, "category": "Income" },
  { "date": "2026-10-02", "description": "Rent", "amount": -1200, "category": "Housing" }
]
```

## AI Skills Demonstrated

This project demonstrates core AI engineering concepts:

- **Retrieval-Augmented Generation (RAG)** — Grounding LLM responses in real user data
- **Context Window Management** — Selecting the most relevant transactions to fit within token limits
- **Prompt Engineering** — System prompts that instruct the LLM to be a financial analyst
- **Conversation Memory** — Maintaining multi-turn context for follow-up questions
- **Data Parsing** — Handling multiple input formats (CSV, JSON) with validation
- **API Integration** — OpenRouter API with proper auth, error handling, and rate limiting

## API

Uses [OpenRouter](https://openrouter.ai) — a unified API for 200+ AI models. Free tier available.

**Model**: `anthropic/claude-3-haiku` (fast, cost-effective for this use case)

## License

MIT

## Author

[Jesseokai](https://github.com/Jesseokai)
