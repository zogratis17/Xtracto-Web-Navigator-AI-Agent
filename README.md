# Web-Navigator-AI-Agent

## Problem Statement Chosen : Web Navigator AI Agent

## Required Solution

Build an AI Agent that can take natural language instructions and autonomously drive the web on a local computer.The system should combine a locally running LLM (for understanding and planning) with a browser automation setup such as Chrome Headless or a browser inside a local VM. Users should be able to give simple commands (e.g., “search for laptops under 50k and list top 5”) and the agent should execute them by controlling the browser, extracting results, and returning structured outputs. Optional features include multi-step reasoning, error handling, task memory, and basic GUI for interaction.

## Reason to Choose the Statement:

The increasing complexity of web-based tasks and the need for automation in everyday browsing make an AI-powered web navigator highly relevant. By enabling users to interact with the web using natural language, this solution bridges the gap between human intent and digital execution, improving productivity and accessibility. The project leverages cutting-edge AI and browser automation technologies, aligning with current trends in local AI deployment and privacy. It also offers significant value for developers, businesses, and individuals seeking efficient, autonomous web interactions without relying on cloud-based solutions.

## 🚀 Solution Overview

### Proposed Approach
We propose building a **Web Navigator AI Agent** as a **browser extension** that connects directly to a **local LLM (Ollama)** through a lightweight backend running inside Docker.  
The extension acts as a bridge between the browser (DOM/page control) and the LLM, enabling natural language instructions to be executed as real browser actions.  
Context and internet knowledge will be enhanced using **web tooling** + **FAISS vector DB (RAG)**, while chat history and threads are persisted in a local database.

## 🔑 Key Features / Modules

1. **Instruction Parsing & Reasoning**  
   - Local LLM (Ollama with models like Llama 3, Qwen, etc.)  
   - Converts natural language → step-by-step browser actions  

2. **Extension Control Layer**  
   - Chrome/Firefox extension to directly control DOM elements (click, type, scrape, extract data)  
   - Toggle **ON/OFF switch** for activating/deactivating the agent  
   - Supports multiple threads (separate chat sessions per task)  

3. **Backend Orchestration (Dockerized)**  
   - FastAPI (Python) or Express.js (Node.js) backend containerized with Docker  
   - Acts as bridge between extension ↔ Ollama LLM ↔ FAISS DB  
   - Provides REST/WebSocket endpoints on a local port for communication  

4. **Search & RAG (Retrieval-Augmented Generation)**  
   - Use web scraping + APIs for live data retrieval  
   - FAISS as vector DB for context storage and similarity search  
   - Injects relevant knowledge back into the LLM’s reasoning loop  

5. **Memory & Context Management**  
   - Local DB (MongoDB / SQLite) for chat persistence and thread management  
   - Stores history, visited sites, and task-specific data  
   - Context recall across sessions (e.g., “continue from last search”)  

6. **User Experience (UX)**  
   - Browser extension popup UI for interacting with the LLM  
   - Switch between threads (conversations/tasks) seamlessly  
   - Results displayed in structured format (lists, tables, summaries)  
