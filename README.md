# Web-Navigator-AI-Agent

## Problem Statement Chosen : Web Navigator AI Agent

## Required Solution

Build an AI Agent that can take natural language instructions and autonomously drive the web on a local computer.

The system should combine a locally running LLM (for understanding and planning) with a browser automation setup such as Chrome Headless or a browser inside a local VM. Users should be able to give simple commands (e.g., “search for laptops under 50k and list top 5”) and the agent should execute them by controlling the browser, extracting results, and returning structured outputs.

Optional features include multi-step reasoning, error handling, task memory, and basic GUI for interaction.

## Core Features

- **Instruction Parsing**  
  Understand user input via locally running LLM.

- **Browser Control**  
  Automate browsing with Chrome Headless / VM-based browser.

- **Task Execution**  
  Perform simple tasks (search, click, extract text, fill forms).

- **Output**  
  Return clean, structured results to the user.

- **Local Setup**  
  Fully functional without cloud dependency.

## Additional Features

- Multi-step reasoning & task chaining
- Task memory (remember previous instructions)
- Error handling & retries
- GUI for easy interaction
- Save/export task results (CSV/JSON)
- Voice input for commands

## Suggested Tech Stacks

- **LLM:** Ollama / GPT4All / Local LLaMA
- **Orchestration:** Python or Node.js + LangChain
- **Browser Automation:** Playwright / Puppeteer / Selenium
- **Interface:** CLI or simple web app (React/Flask)

---

## Company

**OneCompiler**

### Company Industry

Online Coding and Development Platform

### About Company

We at OneCompiler help over 12.8 million developers worldwide to write, run and share code online. Our goal is to make coding more accessible for everyone around the world.

### Company Website

[https://onecompiler.com/e](https://onecompiler.com/e)
