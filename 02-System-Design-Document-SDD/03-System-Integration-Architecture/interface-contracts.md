# Interface Contracts

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Formal contract definitions for inter-service communication.

## Standard Contract Envelope

All REST responses adhere to the standard envelope:
```json
{
  "success": true,
  "timestamp": "2026-11-17T20:00:00Z",
  "data": {},
  "error": null
}
```
