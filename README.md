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


## 📊 Data Handling

This section explains how our AI Web Navigator Agent manages data — from input sources to preprocessing, storage, and pipelines.

---

### 🔹 Data Sources Used
The system interacts primarily with **real-time web data** and locally stored context.  
- **Browser Automation (Playwright):** Extracts HTML, text, links, and metadata from visited pages.  
- **LLM Responses (Ollama):** Converts natural-language queries into structured JSON “plans.”  
- **User Queries (Extension):** Plain-English prompts from the browser extension.  
- **Context Memory (FAISS):** Stores vectorized embeddings of past queries and results for retrieval.  
- **Local Database (SQLite):** Persists chat history, structured outputs, and session context.  

---

### 🔹 Preprocessing Methods
Before storage or execution, data undergoes lightweight preprocessing for consistency:
- **HTML Parsing & Cleaning:** Extracts relevant text, headings, and links (removes ads, scripts, boilerplate).  
- **Embeddings Generation:** Converts text snippets into dense vectors (using LLM embeddings) for semantic search in FAISS.  
- **Normalization:** Ensures JSON plan responses from the LLM follow a consistent schema (action, query, params).  
- **Error Handling:** Ambiguous or malformed LLM responses are sanitized and logged.  
- **Deduplication:** Avoids storing repeated snippets or queries in memory.  

---

### 🔹 Storage & Pipeline Setup
The pipeline ensures smooth movement of data between components:

1. **User Query (Extension → Backend):**  
   - Prompt sent to FastAPI server.  

2. **Planning (Backend → LLM):**  
   - Query converted to structured JSON plan by Ollama.  

3. **Execution (Backend → Browser via Playwright):**  
   - Plan executed (search, scrape, click, extract).  
   - Extracted data preprocessed (clean HTML → text, links, metadata).  

4. **Context Handling:**  
   - Key snippets vectorized → stored in **FAISS** for semantic recall.  
   - Session chat + results logged in **SQLite** for persistence.  

5. **Response Delivery (Backend → Extension):**  
   - Structured JSON results returned and displayed in UI.  

---

### 🔹 Current Storage Choices
- **SQLite:** Lightweight, reliable, and easy to persist user sessions locally.  
- **FAISS:** Optimized vector search for fast semantic retrieval.  
- **JSON (Inter-process):** Used for standardized communication between LLM, backend, and extension.  

---

### 💡 Future Improvements
- Replace SQLite with **MongoDB/Postgres** for scaling.  
- Use **LangChain memory abstractions** for advanced context management.  
- Add **encryption/local-first storage** for sensitive browsing data.  

