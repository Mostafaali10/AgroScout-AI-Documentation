# Communication Protocols

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Detailed protocol stack specifications across physical, network, and application layers.

## Protocol Specifications

- **Mobile Sync**: HTTPS (TLS 1.3), HTTP/2 multiplexing.
- **IoT Telemetry**: MQTT 5.0 with QoS 1, TLS 8883.
- **Field Long-Range**: LoRaWAN 1.0.3 (EU868 / US915 / AS923 regional ISM bands).
- **Rover Live Video**: WebRTC (UDP) with fallback to HLS over HTTPS.
