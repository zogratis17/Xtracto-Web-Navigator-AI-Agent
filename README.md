# Web-Navigator-AI-Agent

## Problem Statement Chosen : Web Navigator AI Agent

## Required Solution

Build an AI Agent that can take natural language instructions and autonomously drive the web on a local computer.The system should combine a locally running LLM (for understanding and planning) with a browser automation setup such as Chrome Headless or a browser inside a local VM. Users should be able to give simple commands (e.g., “search for laptops under 50k and list top 5”) and the agent should execute them by controlling the browser, extracting results, and returning structured outputs. Optional features include multi-step reasoning, error handling, task memory, and basic GUI for interaction.

## Reason to Choose the Statement:

The increasing complexity of web-based tasks and the need for automation in everyday browsing make an AI-powered web navigator highly relevant. By enabling users to interact with the web using natural language, this solution bridges the gap between human intent and digital execution, improving productivity and accessibility. The project leverages cutting-edge AI and browser automation technologies, aligning with current trends in local AI deployment and privacy. It also offers significant value for developers, businesses, and individuals seeking efficient, autonomous web interactions without relying on cloud-based solutions.

## 🚀 Solution Overview

### Proposed Approach
We propose building a **Browser–LLM Bridge Extension** that connects directly to a **local LLM (Ollama)** through a lightweight backend running inside Docker.  
The extension acts as a bridge between the browser (web page + DOM control) and the LLM, enabling natural language instructions to be executed as real browser actions.  
Context and internet knowledge will be enhanced using **web tooling** + **FAISS vector DB (RAG)**, while chat history and threads are persisted in a local database.

---

## 🔑 Key Features / Modules

1. **Instruction Parsing & Reasoning**  
   - Local LLM (Ollama with models like Llama 3, Qwen, etc.)  
   - Converts natural language → multi-step browser action plans  

2. **Extension Control Layer**  
   - Chrome/Firefox extension as the control point  
   - Uses APIs like `chrome.tabs`, `chrome.scripting`, `chrome.debugger` for browser control  
   - Page interaction: navigate, click, type, extract DOM data  
   - Toggle **ON/OFF switch** to enable/disable AI agent  
   - Supports multiple threads (chat sessions per task)  

3. **Backend Orchestration (Dockerized)**  
   - FastAPI (Python) or Express.js (Node.js) backend inside Docker  
   - Bridge between extension ↔ Ollama ↔ FAISS DB  
   - REST/WebSocket endpoints over a local port for communication  

4. **Search & RAG (Retrieval-Augmented Generation)**  
   - Web scraping + API calls to fetch live data  
   - **Hybrid RAG:** combine local LLM reasoning with real-time internet content  
   - FAISS vector DB for knowledge storage and semantic search  
   - Inject relevant retrieved knowledge into LLM’s responses  

5. **Memory & Context Management**  
   - Local DB (MongoDB / IndexedDB / SQLite) for chat persistence  
   - Stores history, visited sites, and session-specific data  
   - Thread-based memory for switching contexts  
   - Contextual AI: LLM gets real-time browser/page state to improve accuracy  

6. **User Experience (UX)**  
   - Extension popup UI for interacting with the LLM  
   - Easy thread switching between different conversations/tasks  
   - Results displayed as structured outputs (lists, tables, summaries)  
   - User-centric controls for privacy and chat data management  
