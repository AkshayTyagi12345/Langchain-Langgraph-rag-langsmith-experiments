LangChain Advanced Chains, RAG & LangSmith Examples
==================================================

This repository contains hands-on, progressive examples demonstrating
core and advanced concepts in LangChain, LangSmith, RAG (Retrieval-
Augmented Generation), Agents, and LangGraph.

The goal of this repo is to serve as a learning and reference project
for building observable, debuggable, and production-style LLM pipelines.


Tech Stack
----------
- Python 3.9+
- LangChain
- LangSmith (Tracing & Observability)
- LangGraph
- OpenAI (Chat + Embeddings)
- FAISS (Vector Store)
- PDF-based RAG
- ReAct Agents
- DuckDuckGo Search Tool


Project Structure
-----------------
.
## 📁 Project Structure

- simple_llm_call.py
- sequential_chain.py
- rag_v1.py
- rag_v2.py
- rag_v3.py
- rag_v4.py
- agent_react_weather.py
- rag_5_langgraph.py
- islr.pdf
- .env
- README.md



File Explanations
-----------------

1) simple_llm_call.py
--------------------
Concepts:
- PromptTemplate
- ChatOpenAI
- OutputParser
- LCEL (pipe operator)

Description:
A minimal example showing a single-step LLM call using LangChain
Expression Language.

Use case:
Understand the absolute basics of LangChain chaining.


2) sequential_chain.py
----------------------
Concepts:
- Sequential chain pattern
- Prompt -> LLM -> Parser

Description:
Demonstrates a simple sequential execution flow using LangChain
components. Serves as a base for multi-step pipelines.


3) rag_v1.py (Basic PDF RAG)
----------------------------
Concepts:
- PDF loading
- Text chunking
- Embeddings
- FAISS vector store
- Retriever + LLM

Description:
A basic Retrieval-Augmented Generation pipeline that answers questions
strictly from a PDF document.

Key idea:
No tracing, no caching – pure RAG fundamentals.


4) rag_v2.py (RAG with LangSmith Tracing)
----------------------------------------
Concepts:
- LangSmith @traceable
- Traced setup steps
- RunnableParallel

Description:
Introduces LangSmith observability by tracing:
- PDF loading
- Document splitting
- Vector store creation
- Query execution

Each step becomes visible in the LangSmith UI.


5) rag_3.py (Hierarchical Tracing)
---------------------------------
Concepts:
- Parent/child traces
- Root runs
- Logical grouping of pipeline steps

Description:
Shows how to group multiple steps under a single traced run,
representing a real-world production tracing pattern.


6) rag_4.py (Cached RAG with Index Reuse)
----------------------------------------
Concepts:
- Vector index caching
- PDF fingerprinting (hash, size, mtime)
- Conditional rebuilds
- Disk-persisted FAISS indexes

Description:
Production-grade RAG pipeline that avoids recomputing embeddings
and supports cached FAISS index reuse.

Why this matters:
- Saves cost
- Faster startup
- Scalable design


7) agent_react_weather.py (ReAct Agent)
--------------------------------------
Concepts:
- ReAct agent pattern
- LangChain tools
- DuckDuckGo search
- External API calls (Weather)

Description:
Demonstrates an agent that reasons and acts by deciding when to:
- Search the web
- Call a weather API
- Combine tool outputs

Classic agentic workflow example.


8) rag_5_langgraph.py (LangGraph Parallel Evaluation)
----------------------------------------------------
Concepts:
- LangGraph StateGraph
- Parallel node execution
- Structured outputs
- Aggregation logic
- LangSmith tracing

Description:
Advanced example using LangGraph to evaluate an essay on multiple
dimensions (language, analysis, clarity) in parallel and aggregate
scores and feedback.

Senior-level, interview-ready example.


LangSmith Setup
---------------
Create a .env file with:

OPENAI_API_KEY=your_openai_key
LANGCHAIN_TRACING_V2=true
LANGCHAIN_API_KEY=your_langsmith_key
LANGCHAIN_PROJECT=langchain_rag_demo

Open LangSmith dashboard:
https://smith.langchain.com


How to Run
----------
Install dependencies:

pip install -U langchain langchain-openai langchain-community faiss-cpu \
pypdf langsmith langgraph python-dotenv

Run any file, for example:

python rag_4.py


Who This Repo Is For
-------------------
- LLM / GenAI Engineers
- LangChain learners
- MLOps & observability practitioners
- Interview preparation (Senior AI/ML roles)
- Anyone building real-world RAG systems


Key Takeaways
-------------
- LCEL chaining patterns
- RAG from basics to production-ready
- LangSmith observability best practices
- Agentic workflows
- LangGraph parallelism
- Cost-efficient vector caching


Future Improvements 
-------------------
- Streaming responses
- LangSmith evaluation datasets
- Replace FAISS with Pinecone / Weaviate
- Deploy as FastAPI service

Worked by - Akshay Tyagi 
Thank you very  much for  have a look.
