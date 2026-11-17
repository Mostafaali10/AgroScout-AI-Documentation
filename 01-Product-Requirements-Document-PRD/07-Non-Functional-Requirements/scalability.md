# NFR-04: Scalability Requirements

> **Module**: AgroScout AI PRD | **Status**: Approved Baseline

Horizontal scaling targets for users, telemetry streams, and geospatial queries.

## Scalability Targets

- Horizontal scaling capable of handling 50,000 active farms and 250,000 connected IoT nodes.
- Read replicas for PostGIS database to handle high volume spatial query spikes during harvest seasons.
