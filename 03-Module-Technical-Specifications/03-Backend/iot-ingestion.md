# IoT Ingestion Engine & MQTT Consumer

> **Module**: Technical Specifications | **Status**: Approved Baseline

EMQX broker integration, message deduplication, and bulk batch inserts.

## Ingestion Flow

Async MQTT consumer buffering sensor readings into Redis batches before bulk executing SQL `INSERT INTO iot_telemetry`.
