# Multi-Agent-IT-Helpdesk-system - LangGraph


This repository contains an basic implementation of a Multi-Agent IT Helpdesk System that combines Advanced Retrieval-Augmented Generation (RAG) techniques with a Human-in-the-Loop (HITL) workflow. The system is designed to deliver accurate, context-aware responses for IT support while ensuring oversight and continuous improvement through human feedback.
The advanced RAG framework incorporates query optimization, retrieval, relevance assessment, and reranking to enhance query processing. The architecture consists of three primary agents, each designed to perform specific tasks to efficiently handle user queries.


The multi-agent architecture powering this IT Helpdesk system is designed for scalability, efficiency, and human oversight. Below is the visual representation:
![architecture](https://github.com/user-attachments/assets/4eee2dd0-ac46-45c9-8ebd-c4559e3095a0)



**Intake Agent:** This agent receives the user query and transforms it into an interpretable, optimized form. It ensures that the query is structured in a way that enables effective processing by subsequent agents.
**Coordinator Agent:** Acting as a router, the coordinator agent evaluates the query and directs it to either the Resolution Agent or the Escalation Agent based on the severity and impact of the request. It determines whether the query is resolvable by the user or requires escalation to a more advanced process.
**Resolution Agent:** This agent connects to a vector database through a retrieval tool, employing an agentic RAG mechanism to process the user request. It uses this mechanism to retrieve relevant context from the database. If pertinent context is retrieved, the Resolution Agent generates a response to resolve the query. If the necessary context is not found, the query is forwarded to the Escalation Agent.
**Escalation Agent:** Operating with a Human-in-the-Loop (HIL) mechanism, this agent gathers additional details from the user, such as troubleshooting steps or system information, to facilitate the escalation process. Once the user provides the required information, the Escalation Agent processes it and generates a structured escalation summary, adhering to a predefined schema that ensures all necessary details are included for effective escalation.



**Memory management:**
Memory management is implemented using in-memory checkpointers to persist system state and facilitate interaction continuity across sessions. Specifically, I leveraged MemorySaver in LangGraph, which functions as an in-memory checkpointer by capturing and storing the execution state at each node of the graph. This mechanism enables the system to resume workflows from intermediate steps, preserve conversational context, and support multi-turn interactions across different sessions without external storage dependencies.



## Generative AI Architecture on Azure for Enterprise Applications


![azure-architecture](https://github.com/user-attachments/assets/d259472b-3ce9-45f9-8ec7-4dfb5534defb)







