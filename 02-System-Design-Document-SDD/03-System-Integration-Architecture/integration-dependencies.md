# Integration Dependency Map

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Upstream and downstream dependency mapping across services.

## Dependency Graph

- `agroscout-mobile` depends on `agroscout-core-api`
- `agroscout-core-api` depends on `PostgreSQL`, `Redis`, and `agroscout-ai-inference`
- `agroscout-iot-ingest` depends on `EMQX Broker` and `TimescaleDB`
- `agroscout-rag-agent` depends on `Vector DB (ChromaDB)` and LLM Provider API
