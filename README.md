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