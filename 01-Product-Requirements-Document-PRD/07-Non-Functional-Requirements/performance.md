# NFR-01: Performance Requirements

> **Module**: AgroScout AI PRD | **Status**: Approved Baseline

Latency, throughput, and resource utilization benchmarks.

## Benchmarks

- On-Device Model Inference: <= 250ms on modern smartphone (Snapdragon 7 series or newer).
- Cloud API Latency: 95th percentile response time <= 200ms for REST endpoints.
- Cold App Launch: <= 1.8 seconds on mid-range Android/iOS devices.
- MQTT Telemetry Throughput: Sustained 5,000 messages/sec with < 50ms ingestion latency.
