# 🔎 Multi-Step Research Agent

An agentic research system built with **LangGraph, LangChain, Groq, and Tavily** that can break down complex research questions, perform multi-step web research, evaluate whether the gathered information is sufficient, identify knowledge gaps, conduct additional research when necessary, and synthesize the findings into a final report.

---

## 🚀 Features

- 🧩 **Query Decomposition**
  - Breaks a complex research question into smaller, focused sub-questions.

- 🌐 **Web Research**
  - Uses Tavily to search the web for relevant information.

- 📚 **Evidence Collection**
  - Extracts factual claims and supporting evidence from search results.

- 🔍 **Research Evaluation**
  - Evaluates whether the collected research is sufficient to answer the original question.

- 🔄 **Iterative Research**
  - Identifies research gaps and performs additional searches when the initial research is insufficient.

- 🧠 **LLM-Powered Reasoning**
  - Uses Groq-hosted LLMs through LangChain.

- 📝 **Final Synthesis**
  - Combines the collected findings into a structured final research report.

- 🕸️ **LangGraph Workflow**
  - Uses a stateful graph to coordinate the different stages of the research process.

- 🖥️ **Streamlit Interface**
  - Provides an interactive UI for submitting research questions and viewing results.

---

## 🏗️ Architecture

```text
                    User Query
                        │
                        ▼
               ┌─────────────────┐
               │   Decompose     │
               │     Query       │
               └────────┬────────┘
                        │
                        ▼
               ┌─────────────────┐
               │     Research    │
               │                 │
               │  Tavily Search  │
               └────────┬────────┘
                        │
                        ▼
               ┌─────────────────┐
               │    Evaluate     │
               │    Research     │
               └────────┬────────┘
                        │
                 ┌──────┴──────┐
                 │             │
             Sufficient      Insufficient
                 │             │
                 │             ▼
                 │       ┌─────────────┐
                 │       │  Identify   │
                 │       │    Gaps     │
                 │       └──────┬──────┘
                 │              │
                 │              ▼
                 │        Additional
                 │         Research
                 │              │
                 │              └───────┐
                 │                      │
                 └──────────────────────┘
                        │
                        ▼
               ┌─────────────────┐
               │    Synthesis    │
               │                 │
               │  Final Report   │
               └────────┬────────┘
                        │
                        ▼
                 Research Result