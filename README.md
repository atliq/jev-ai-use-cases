# Jev in Practice

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/atliq/jev-ai-use-cases/blob/main/jev_decision_guide.ipynb)

Practical examples of using [Jev](https://typesafe.ai/blog/introducing-system-one-models-and-jev) (TypeSafe AI's decision model) in real applications, built with LangChain.

**An LLM writes. Jev decides.** You give Jev your options and it picks one, tells you how sure it is, and never answers outside your list.

## What's inside

| Example | What Jev decides |
|---|---|
| Support ticket triage | Which team, how urgent, whether the customer wants a refund |
| Model routing | Small, premium, or private model for each request |
| Reply guardrails | Whether an AI-written reply is safe to send |
| Tool selection | Which tool an agent should use, and blocking risky tool calls |
| Finance inbox | Document type, urgency, and "bank details changed" fraud |

- `jev_decision_guide.ipynb`: the notebook, with outputs from a real run

## Setup

1. Install the dependencies:
   ```bash
   pip install "langchain-typesafe[experimental]" langchain-groq python-dotenv pandas
   ```
2. Create a `.env` file with your keys (Jev runs through OpenRouter, the LLMs through Groq):
   ```
   OPENROUTER_API_KEY=your_openrouter_key
   GROQ_API_KEY=your_groq_key
   ```
3. Open `jev_decision_guide.ipynb` and run it top to bottom.

**Running in Colab?** There's no `.env` file there. Add both keys under *Secrets* (the key icon in the left sidebar), then run this before the setup cell:
```python
import os
from google.colab import userdata
os.environ["OPENROUTER_API_KEY"] = userdata.get("OPENROUTER_API_KEY")
os.environ["GROQ_API_KEY"] = userdata.get("GROQ_API_KEY")
```

> Note: `langchain-typesafe` is in early alpha and its middleware is experimental, so the API may change.
