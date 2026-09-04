# Agents to Research and Write an Article

<img alt="repo-badges" src="https://img.shields.io/github/stars/Saqib-Agentic-AI/agents-to-research-and-write-an-article?style=social" /> <img alt="python" src="https://img.shields.io/badge/python-3.8%2B-blue" /> <img alt="issues" src="https://img.shields.io/github/issues/Saqib-Agentic-AI/agents-to-research-and-write-an-article" />

<span style="color:#0b63ce; font-size:18px; font-weight:600">Multi-agent research and automated article authoring powered by CrewAI and Ollama.</span>

---

A modular Python-based multi-agent system that autonomously researches topics and drafts polished blog articles. Designed for researchers, content creators, and developers who want to automate content production while keeping full control over prompts, agent workflows, and outputs.

Why this repo?
- Turn complex research tasks into readable articles automatically.
- Combine specialized agents for search, summarization, fact-checking, and writing.
- Built with extensibility in mind — add agents, swap models, or tweak workflows.

Key features
- Agent orchestration using CrewAI-style workflows
- Local/remote model integrations via Ollama or pluggable model drivers
- Configurable research pipeline: topic discovery → retrieval → synthesis → drafting → QA
- Export formats: Markdown (ready for publishing), plain text, and optional HTML

Table of contents
1. [Demo / Quick Look](#demo--quick-look)  
2. [Getting Started](#getting-started)  
3. [How it works (overview)](#how-it-works-overview)  
4. [Configuration](#configuration)  
5. [Usage examples](#usage-examples)  
6. [Extending the system](#extending-the-system)  
7. [Contributing & Support](#contributing--support)  
8. [Credits](#credits)

Demo / Quick look
-----------------
(Replace the placeholder below with a GIF or screenshot for maximum impact)

![demo-placeholder](https://via.placeholder.com/900x250.png?text=Demo+-+Agents+research+and+write+an+article)

Getting started
---------------

Prerequisites
- Python 3.8+
- pip (or poetry)
- Ollama (optional, for local model hosting)
- API keys or connectors for any third-party data sources you plan to use

Install
1. Clone the repo:
   git clone https://github.com/Saqib-Agentic-AI/agents-to-research-and-write-an-article.git
2. Create and activate a virtual environment:
   python -m venv .venv
   source .venv/bin/activate  # macOS / Linux
   .venv\Scripts\activate     # Windows
3. Install dependencies:
   pip install -r requirements.txt

Configuration
-------------
- Copy config/example_config.yml to config/config.yml
- Edit model and agent settings (e.g., choose between Ollama or external LLM endpoints)
- Add API keys and credentials to a secure .env file or your environment

How it works (overview)
-----------------------
1. Topic selection agent: receives a high-level prompt (topic, audience, constraints).
2. Research agents: run targeted searches, retrieve sources, and extract facts.
3. Summarization & synthesis agents: condense findings into structured notes and outlines.
4. Drafting agent: writes a first-pass article draft based on synthesized notes.
5. QA and fact-check agents: verify claims and ensure citation links are included.
6. Exporter: outputs final article in Markdown and optional HTML for publishing.

Architecture (simple)
- orchestrator.py — agent flow controller
- agents/
  - search_agent.py
  - summarizer_agent.py
  - draft_agent.py
  - qa_agent.py
- connectors/
  - ollama_driver.py
  - web_search.py
- config/
  - config.yml
- outputs/
  - articles/

Usage examples
--------------
Run the pipeline with a topic:
python run_pipeline.py --topic "The future of multimodal AI in publishing" --audience "technical writers" --output outputs/articles/

Get an interactive prompt (dev):
python interactive_agent.py

Output
------
- Final Markdown saved to outputs/articles/{topic-slug}.md
- Optional logs and intermediate JSON for debugging and reproducibility

Best practices
--------------
- Start small: run short topics to tune prompts and agent order.
- Lock model versions when you need reproducible outputs (Ollama or pinned API models).
- Keep a log of source URLs and timestamps for auditability.

Extending the system
--------------------
- Add new agents: create a new class in agents/ and register it in orchestrator.py
- Plug in a model provider: implement the Driver interface in connectors/
- Add exporters: support additional output formats (Word, PDF, CMS APIs)

Contributing & support
----------------------
Contributions are welcome — whether that's bug fixes, new agents, or improved prompts. Please:
1. Fork the repo
2. Open a feature branch
3. Submit a PR with tests and clear description

For issues and feature requests, open an issue on GitHub.

Credits
-------
Created by the Agentic-AI experiments team. Uses CrewAI-style orchestration and Ollama-compatible model drivers.

License
-------
Please add a LICENSE file (e.g., MIT) to clearly state repository terms.

Contact
-------
For questions, ideas, or collaboration: reach out via GitHub Discussions or open an issue.
