# System Design Overview

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Comprehensive architectural blueprint of the AgroScout AI enterprise platform.

## Architectural Philosophy

AgroScout AI is engineered around four core tenets:
1. **Edge-to-Cloud Symmetry**: Compute tasks (AI inference, sync queues) operate deterministically both on disconnected mobile devices and cloud clusters.
2. **Geospatial Centricity**: Every observation, photo, sensor packet, and rover waypoint is anchored to precise WGS84 coordinates.
3. **Event-Driven Telemetry**: Sensor readings stream via MQTT into partitioned time-series storage.
4. **Pragmatic Microservices**: Clean separation of API Gateway, Geospatial Service, AI Inference Engine, and IoT Ingestion pipeline.

## Subsystems Overview

- **Mobile Client**: Flutter application with BLoC pattern and local Hive/Isar storage.
- **Backend Cluster**: FastAPI services, PostGIS spatial database, TimescaleDB telemetry store, MinIO S3 object storage.
- **AI Ecosystem**: PyTorch training pipeline, TensorRT/ONNX cloud serving, TFLite mobile models, LangChain RAG agent.
- **Embedded Hardware**: Dual-tier MCU/MPU nodes (ESP32-S3 sensor hub + Raspberry Pi CM4 scouting rover).
