# Firmware Architecture (FreeRTOS & Embedded Linux)

> **Module**: Technical Specifications | **Status**: Approved Baseline

Dual-core task allocation, watchdogs, and state machine transitions.

## Firmware Design

ESP-IDF FreeRTOS tasks: Task_SensorRead (10Hz), Task_PowerManage (1Hz), Task_LoRaTelemetry (Event-driven).
