# API Conventions & Guidelines

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Naming standards, query filters, pagination, and status codes.

## Conventions

- Resource names are plural nouns (`/farms`, `/parcels`, `/scouting-missions`).
- Standard pagination query parameters: `?page=1&limit=20`.
- ISO-8601 UTC timestamps across all models (`2026-11-17T20:00:00Z`).
