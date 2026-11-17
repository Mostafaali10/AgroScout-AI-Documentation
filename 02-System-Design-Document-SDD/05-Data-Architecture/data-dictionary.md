# Data Dictionary

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Field-level definitions, constraints, data types, and descriptions for all core entities.

## Core Entities Table

| Table | Column | Type | Constraints | Description |
| :--- | :--- | :--- | :--- | :--- |
| `parcels` | `id` | UUID | PK | Unique parcel identifier |
| `parcels` | `boundary` | GEOMETRY(Polygon, 4326) | NOT NULL | Spatial polygon coordinates |
| `scouting_events` | `crop_health_status` | VARCHAR(32) | ENUM | Healthy, Warning, Diseased |
| `iot_telemetry` | `soil_moisture` | NUMERIC(5,2) | 0.00 - 100.00 | Volumetric water content % |
