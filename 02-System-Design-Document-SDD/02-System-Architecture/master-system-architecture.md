# Master System Architecture

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

End-to-end multi-tier architectural specification.

## Tier Breakdown

1. **Presentation Tier**: Flutter Mobile App (Android/iOS) and Angular/React Web Admin Dashboard.
2. **Edge Computing Tier**: Rover-mounted Raspberry Pi CM4 executing live object detection and obstacle avoidance; ESP32 telemetry nodes.
3. **Gateway Tier**: Kong / NGINX API Gateway managing mTLS, rate limiting, and JWT authentication.
4. **Application Tier**: FastAPI asynchronous microservices communicating via Redis Pub/Sub and RabbitMQ.
5. **Persistence Tier**: PostgreSQL 15 + PostGIS (geospatial), TimescaleDB (time-series), Redis (caching), MinIO (raw leaf images).
