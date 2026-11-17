# System Component Catalog

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Detailed catalog of services, daemons, and software packages.

## Component Inventory

| Component Name | Tech Stack | Role |
| :--- | :--- | :--- |
| `agroscout-mobile` | Flutter 3.x / Dart | Field scouting, offline storage, camera capture |
| `agroscout-api-gateway` | NGINX / Kong | Ingress routing, SSL termination, JWT auth |
| `agroscout-core-api` | Python 3.11 / FastAPI | Farm management, users, reports, CRUD |
| `agroscout-iot-ingest` | Go / Python / EMQX | MQTT message consumption, telemetry validation |
| `agroscout-ai-inference` | Triton Inference Server / PyTorch | High-throughput cloud disease diagnosis |
| `agroscout-rag-agent` | LangChain / ChromaDB / LLM | Agronomic recommendation conversational engine |
