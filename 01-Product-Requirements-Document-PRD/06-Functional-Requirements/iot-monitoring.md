# FR-08: IoT Sensor Telemetry Monitoring

> **Module**: AgroScout AI PRD | **Status**: Approved Baseline

Requirements for sensor data ingestion, threshold validation, and historical charts.

## Requirements

1. System shall ingest MQTT payloads containing ambient temperature, relative humidity, soil moisture (multi-depth), and NPK values.
2. Telemetry ingestion pipeline shall buffer readings during database failover without data loss.
3. Mobile app shall plot 24-hour, 7-day, and 30-day interactive time-series graphs.
