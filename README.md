# Intello-Agent
An autonomous Human-in-the-Loop (HITL) AI agent built with MERN, LangGraph, and MCP. Automates web research, email, scheduling, and Instagram publishing with secure human oversight.

# Autonomous Executive AI Agent

An advanced, stateful AI agent built on the MERN stack, LangGraph, and the Model Context Protocol (MCP). This agent acts as a digital executive assistant capable of orchestrating complex, multi-tool workflows while strictly adhering to a **Human-in-the-Loop (HITL)** security model.

The agent possesses the autonomy to read, analyze, and draft tasks across various platforms, but operates on a "Draft and Verify" mechanism—pausing execution to require explicit human authorization before triggering any outbound or state-changing API actions.

## 🚀 Core Capabilities

* **Web Intelligence:** Executes autonomous web searches to gather context, verify facts, and enrich drafted content.
* **Email Management:** Reads, summarizes, and contextualizes incoming emails, and drafts thread-aware outbound replies.
* **Calendar Orchestration:** Accesses Google Calendar to identify free/busy slots and stages new meetings or reminders.
* **Computer Vision:** Ingests and analyzes images to extract text, describe visual elements, and determine context.
* **Instagram Publishing:** Combines visual analysis and web intelligence to generate optimized Instagram captions, hashtags, and staged posts.

## 🛡️ Human-in-the-Loop (HITL) Architecture

To prevent unauthorized actions, the LangGraph state machine enforces a strict boundary between READ and WRITE operations:
1. **Analyze & Draft:** The agent freely uses read tools (Search, Read Email, Check Calendar, Analyze Image) to formulate a complete draft.
2. **Halt & Request:** The agent suspends the workflow and presents the drafted email, calendar event, or Instagram post to the human operator.
3. **Execute:** The final API execution (Send, Book, Publish) is only triggered upon explicit human approval. 

## 🛠️ Tech Stack

* **Frontend:** React.js
* **Backend:** Node.js, Express, MongoDB
* **Agent Orchestration:** LangChain, LangGraph (for stateful, cyclic agent routing)
* **Tool Integration:** Model Context Protocol (MCP)
