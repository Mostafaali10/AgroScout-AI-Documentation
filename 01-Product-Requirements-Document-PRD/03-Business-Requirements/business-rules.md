# Business Rules & Constraints

> **Module**: AgroScout AI PRD | **Status**: Approved Baseline

Operational boundaries and decision rules enforced throughout the platform.

## Core Business Rules

1. **BR-001 (Chemical Recommendation Caution)**: The AI advisor must never prescribe restricted chemical compounds without a clear safety disclaimer and dosage validation based on farm area.
2. **BR-002 (Offline Quota)**: Mobile clients can record unlimited offline scouting points; synchronization occurs automatically when network bandwidth > 200 kbps.
3. **BR-003 (Access Control)**: Field technicians may capture data and run missions but cannot delete farm boundaries or historical reports without Farm Manager approval.
