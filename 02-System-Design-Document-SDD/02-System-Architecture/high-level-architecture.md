# High-Level Architecture

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Simplified structural overview depicting interactions between the four engineering tracks.

## Track Integration

### 1. Mobile <-> Backend
Secure REST API and WebSockets for real-time mission updates; bi-directional sync engine for offline field logs.

### 2. Edge IoT <-> Backend
MQTT telemetry sent over 4G LTE-M / LoRaWAN to cloud broker (EMQX); automatic persistence into TimescaleDB.

### 3. AI <-> Backend / Mobile
Mobile runs quantized TFLite models on device (20MB footprint). Cloud runs high-precision YOLOv11/ConvNeXt models with ensemble validation for complex cases.

### 4. Embedded Rover <-> Mobile
Local Wi-Fi AP direct connection for manual rover teleoperation and mission waypoint provisioning.
