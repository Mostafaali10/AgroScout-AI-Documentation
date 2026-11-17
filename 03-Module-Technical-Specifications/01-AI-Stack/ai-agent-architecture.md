# Agricultural AI Agent Architecture

> **Module**: Technical Specifications | **Status**: Approved Baseline

LLM agent tool-use, RAG retrieval chain, and memory design.

## Architecture

LangChain/LangGraph agent equipped with custom tools: `query_sensor_history()`, `fetch_disease_info()`, `calculate_spray_dosage()`. Uses ChromaDB for vector retrieval.
