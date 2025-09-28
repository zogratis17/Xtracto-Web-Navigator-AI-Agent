# Xtracto - Web Navigator AI Agent

## a) Problem Statement Reference

🔹 **Problem Statement Chosen:**
Build an AI Agent that can take natural language instructions and autonomously drive the web on a local computer.

🔹 **Reason to Choose the Problem Statement:**
- The intersection of local LLMs and browser automation enables secure, cloud-independent AI tools.
- Rising demand for AI personal assistants that respect user privacy and work offline.
- Offers a practical, extensible framework for automating day-to-day web tasks, especially useful for researchers, professionals, and data analysts.
- Combines multiple domains: LLMs, automation, scraping, structured output generation, and human-AI interaction.

## b) Solution Overview

🔹 **Proposed Approach:**
Develop a fully local AI agent that can understand user instructions via a Local LLM, control a browser to execute tasks (e.g., search, scrape, click), and return clean, structured outputs in JSON/CSV formats.

🔹 **Key Features / Modules:**
- User Interface (CLI / Web App / Extension)
- Instruction Parser (LLM like Ollama / GPT4All)
- Orchestration Engine (Python/Node.js)
- Browser Automation (Playwright / Selenium)
- HTML Parser & Extractor
- Structured Output Formatter
- Storage Layer (VectorDB + Local DB)
- Task Memory & Reasoning Module
- Voice Input Handler (Optional)

## c) System Architecture

🔹 **Architecture Diagram:**
![architecture](assets/Architecture.png)

🔹 **Data Flow Explanation:**
1. User Input via CLI or Web App.
2. LLM interprets natural language and returns an action plan.
3. Orchestrator processes the plan and invokes browser automation.
4. Browser navigates, searches, clicks, or scrapes as instructed.
5. Parser extracts relevant data.
6. Output Layer structures and validates the result.
7. Result is returned to user and stored locally.
8. (Optional) VectorDB recalls previous tasks and context.

## d) Technology Stack

🔹 **Backend:**
- Python with FastAPI or Node.js
- LangChain / Custom Orchestrator

🔹 **Frontend:**
- CLI (Typer)
- Web App (React + Flask / Next.js + Express)

🔹 **Databases:**
- Structured: SQLite / PostgreSQL
- Unstructured: JSON/CSV Files
- Vector Storage: Chroma / Qdrant / Weaviate

🔹 **ML/AI Frameworks:**
- Ollama (LLaMA2 / Mistral)
- GPT4All
- LangChain (Optional)

## e) Algorithms & Models

🔹 **Algorithm(s) Chosen:**
- Natural Language Parsing via Local LLM
- Rule-based Planning & Action Mapping
- DOM Tree Traversal for web scraping
- Schema-based Validation for outputs

🔹 **Reason for Choice:**
- Local LLMs offer data privacy and offline capability.
- Rule-based orchestration allows transparency and control.
- HTML DOM traversal is robust across websites.
- Guardrails + Pydantic enable strict output formats.

🔹 **Model Training & Testing Approach:**
- Pretrained LLMs (LLaMA/Mistral) via Ollama, fine-tuned on instruction datasets.
- Few-shot prompting for zero-shot task parsing.
- Manual evaluation and synthetic benchmarks for instruction handling accuracy.

🔹 **APIs / Libraries:**
- Playwright / Selenium / Puppeteer
- BeautifulSoup / lxml / Playwright API
- Guardrails / Pydantic for validation
- OpenAI Whisper or Vosk (Voice Input)
- Pandas for CSV/JSON transformation

## f) Data Handling

🔹 **Data Sources Used:**
- Real-time public web data from browser sessions
- Sample datasets for validation: electronics, shopping, etc.

🔹 **Preprocessing Methods:**
- HTML cleaning
- Tag filtering (price, title, rating, etc.)
- Semantic chunking (for embeddings/memory)

🔹 **Storage / Pipeline Setup:**
Structured results saved as:
- CSV via Pandas
- JSON via Pydantic schemas
- Task history stored in SQLite or Postgres
- Task embeddings stored in VectorDB

## g) Implementation Plan

🔹 **Initial Setup & Environment:**
- Setup Python/Node environment
- Install Ollama + Playwright
- Initialize LLM models (e.g., Mistral via Ollama)

🔹 **Core Module Development:**
- LLM interface and instruction parsing
- Browser automation script
- DOM extraction module
- Output structuring

🔹 **Integration & Testing:**
- Chain modules through Orchestrator
- Add logging, error handling, retries
- Unit tests for each module

🔹 **Final Deployment-ready Build:**
- Create executable (via PyInstaller / pkg)
- Docker setup for portability
- GUI or CLI toggle in settings
- Export options (CSV, JSON)

## h) Performance & Validation

🔹 **Evaluation Metrics:**
- Accuracy of extracted data
- Instruction Parsing Success Rate
- Task Completion Time
- Output Validity (schema checks)

🔹 **Testing Strategy:**
- Unit & Integration Tests
- Simulated instruction sets (100+ test prompts)
- Stress test with long task chains
- Edge case handling (popups, captchas)

## i) Deployment & Scalability

🔹 **Deployment Plan:**
- Local executable (for CLI/GUI)
- Cross-platform packaging (Windows/Mac/Linux)
- Docker container for isolated runs

🔹 **Scalability Considerations:**
- Modular design: plug in new LLMs or automation engines
- Future support for:
  - Parallel browser sessions
  - Task queue & scheduler
  - Multi-user support (if web-based)

## ✅ Conclusion

This project delivers a fully local, privacy-focused AI agent capable of performing web tasks through natural language. It brings together the power of LLMs, browser automation, and structured data processing into one compact system, offering flexibility and extensibility for a wide range of personal and professional use cases.