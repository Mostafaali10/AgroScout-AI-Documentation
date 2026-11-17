# Database Architecture & Relational Design

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Relational schemas, geospatial indexing, and time-series hyper-tables.

## Database Schemas

- **PostgreSQL 15 + PostGIS**: `users`, `farms`, `parcels` (with `GEOMETRY(POLYGON, 4326)`), `scouting_events` (with `GEOMETRY(POINT, 4326)`), `diagnoses`.
- **TimescaleDB**: `iot_telemetry` table partitioned by `timestamp` into 7-day chunks with automated compression.
- **Redis 7.x**: Session cache, API rate limit counters, active mission tracking.
