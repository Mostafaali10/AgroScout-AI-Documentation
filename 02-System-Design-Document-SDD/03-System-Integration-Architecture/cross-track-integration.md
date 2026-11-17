# Cross-Track Integration Matrix

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Explicit integration points between Mobile, AI, Backend, and Embedded tracks.

## Track Matrix

1. **Flutter to Backend**: REST OpenAPI 3.0 specification with gzip payload compression.
2. **Backend to AI Service**: gRPC protocol with Protocol Buffers for sub-millisecond serialization overhead.
3. **Embedded Rover to Backend**: MQTT over TLS with JSON payloads adhering to the AgroScout Sensor Schema v1.
4. **Mobile to Embedded Hardware**: BLE (Bluetooth Low Energy) for pairing; local HTTP for direct rover video streaming.
