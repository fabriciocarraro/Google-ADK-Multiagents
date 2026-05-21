# Multi-Agent Systems with Google ADK: A Hands-On Introduction

A self-contained Colab notebook that teaches the fundamentals of Google's Agent Development Kit (ADK) by building two real multi-agent systems from scratch.
Everything runs on the free Google AI Studio tier — no Google Cloud, no billing, no extra setup.

## Author

* [Fabrício Carraro](https://www.linkedin.com/in/fabriciocarraro)

## What you'll build

**1. A briefing generator** — researches any topic on the web, then summarizes it from multiple angles in parallel.

```
SequentialAgent
  ├── researcher (google_search)
  ├── ParallelAgent
  │     ├── summarizer
  │     └── key_points
  └── final_editor
```

**2. An internal company assistant** — routes employee questions to the right specialist (private policy docs via a simple RAG system, or the public web via google_search) depending on what's being asked.

```
LlmAgent (router)
  ├── web_researcher       (google_search)
  └── internal_researcher  (RAG over policy docs)
```

## Concepts covered

- `LlmAgent` — the core building block
- Custom Python tools and built-in tools (`google_search`)
- `SequentialAgent` for pipelines
- `ParallelAgent` for fan-out
- `AgentTool` for routing one LLM agent through another
- RAG with `gemini-embedding-001` and in-memory cosine similarity
- Session state, the `Runner`, and async event streaming

## Running the notebook

### Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<your-username>/<your-repo>/blob/main/adk_multiagent_intro.ipynb)

Once open in Colab:

1. Click the 🔑 (key) icon on the left sidebar
2. Add a new secret named `GOOGLE_API_KEY` with your API key as the value
3. Enable "Notebook access" for that secret
4. Run cells top to bottom

## Notebook structure

| Section | Topic |
|---|---|
| 1 | Setup and API key |
| 2 | Helper function to run agents with verbose tracing |
| 3 | First agent — with a custom Python tool |
| 4 | Adding web search with the built-in `google_search` tool |
| 5 | Chaining agents with `SequentialAgent` |
| 6 | Speeding things up with `ParallelAgent` |
| 7 | Full briefing pipeline |
| 8 | RAG + routing — building the internal assistant |
| 9 | Exercises to extend the system |
## License

[choose one — MIT and Apache-2.0 are both common for teaching material]
