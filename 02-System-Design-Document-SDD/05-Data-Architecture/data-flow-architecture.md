# Data Flow Architecture

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

End-to-end data pipelines from sensor and camera capture to analytics.

## Data Pipeline Stages

1. **Ingress**: MQTT packets collected by EMQX; camera images uploaded to MinIO.
2. **Processing**: Celery workers run async AI inference and geospatial boundary checks.
3. **Storage**: Sensor telemetry written to hyper-tables in TimescaleDB; structured metadata to PostGIS.
4. **Analytics**: Aggregation jobs compute weekly crop health trends and disease risk indices.
