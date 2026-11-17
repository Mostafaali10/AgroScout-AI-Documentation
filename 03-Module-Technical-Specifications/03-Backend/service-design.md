# Microservices & Domain Design

> **Module**: Technical Specifications | **Status**: Approved Baseline

Service separation between Core API, Ingestion Daemon, and AI Dispatcher.

## Service Responsibilities

- Core API: User management, farm polygons, report generation.
- IoT Ingestion: High-throughput MQTT packet consumer.
- AI Dispatcher: Asynchronous image triage and inference queue.
