# Contributing to **Web Navigator AI Agent**

Thank you for your interest in learning about our **Web Navigator AI Agent**!  
This document outlines how our team collaborated to design and build the project, with clear roles, workflows, and responsibilities.  

---

## 👥 Team Roles & Contributions  

| Member | Role | Contributions / Responsibilities |
|--------|------|----------------------------------|
| **Hari Prasath N T** | Project Lead / Architect | - Defined project vision, milestones, and roadmap.<br>- Designed modular architecture linking LLM, backend, and frontend.<br>- Oversaw integration and workflow alignment.<br>- Guided Git workflow and best practices.<br>- Conducted code reviews and final validation. |
| **Vijesh** | LLM Specialist | - Configured and optimized **Ollama** (and alternative local LLMs).<br>- Designed prompt strategies for multi-step reasoning.<br>- Implemented error handling for ambiguous tasks.<br>- Ensured accurate structured outputs.<br>- Documented LLM usage and configuration tips. |
| **Madhu Shankara G S** | Backend Developer | - Built FastAPI backend for LLM ↔ Browser ↔ Extension communication.<br>- Integrated Playwright for automation and scraping.<br>- Developed pipelines for structured data extraction.<br>- Added error handling, retries, and backend logging.<br>- Wrote tests for backend stability and scalability. |
| **Sudharsan** | Frontend Developer | - Built extension UI with toggles, session management, and chat view.<br>- Connected frontend to backend APIs.<br>- Designed clean UX for result visualization.<br>- Implemented responsive and minimal design.<br>- Handled state management for switching sessions/threads. |
| **Vellayudham** | Research & Systems Engineer | - Researched tooling for **Docker virtualization**, vector DBs (FAISS), and local DB storage.<br>- Configured deployment setups for offline-first operation.<br>- Built local storage integration for chat history.<br>- Explored innovation points for future scaling (multi-agent, cloud/offline sync). |


## ⚡ How We Worked  

### Planning & Vision  
- Conducted brainstorming sessions to define problem statement & scope.  
- Designed modular architecture separating **LLM**, **backend orchestration**, and **browser extension**.  
- Broke down tasks with ownership and timelines.  

### Collaboration & Workflow  
- Used **GitHub projects** + feature branches for parallel development.  
- Weekly sync-ups to align progress and resolve blockers.  
- Shared diagrams, architecture drafts, and mockups in GitHub Discussions.  
- Followed **PR-based workflow** with code reviews for every feature.  

### Development  
- **Backend:** APIs, automation, RAG integration, error handling.  
- **Frontend/Extension:** UI toggles, chat threads, DB integration.  
- **LLM Integration:** Prompt strategies, structured outputs, reasoning optimizations.  
- **Systems Setup:** Dockerized services, local DB + FAISS memory integration.  

### Testing & Review  
- Unit tests for backend API reliability.  
- Manual + automated tests for browser actions.  
- UI testing for extension interactivity and responsiveness.  
- Peer code reviews before merges to main branch.  

### Documentation & Presentation  
- Maintained **README.md** for workflow, setup, and demo usage.  
- Created **CONTRIBUTING.md** (this file) to explain team workflow.  
- Added diagrams, sequence flows, and RAG pipeline documentation.  
- Prepared demo materials for hackathon showcase.  

---

## 💡 What Made Our Workflow Unique  

1. **Offline-first LLM + Web Automation** → Works even with minimal connectivity.  
2. **Lightweight Extension Bridge** → Direct toggle control + local DB storage.  
3. **Iterative RAG Integration** → FAISS-powered context retrieval for smarter browsing.  
4. **Dockerized Environment** → Quick replication across dev machines.  
5. **Innovation-First Research Role** → A dedicated member (Vellayudham) focused on exploring cutting-edge ideas while others built the core.  

---

## ✅ Summary  

Our team followed a **modular, collaborative, and innovation-driven approach** to deliver a functional **Web Navigator AI Agent**.  
By clearly dividing responsibilities, maintaining strong communication, and prioritizing reliability, we built a system that bridges **LLMs, browser automation, and user interfaces** in a unique way.  

This approach not only ensured project success but also laid the groundwork for future extensions like **multi-agent orchestration, cloud sync, and advanced RAG pipelines**.  

---

⚡ **Next Steps for Contributors**: If you’d like to contribute, check out our [README.md](./README.md), open an issue with your proposal, and join us in pushing the boundaries of autonomous web navigation.  
