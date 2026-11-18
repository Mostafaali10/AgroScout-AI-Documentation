# FR-10: Multiple Farms & Fields Specification

> **Status**: Draft – Derived from Source File  
> **Module**: Functional Requirements / Multiple Farms & Fields  
> **Source Reference**: `Source File.docx` (§3 F10)

---

## 1. Module Objective `[Confirmed]` (Source: §3 F10)

Provides multi-tenant hierarchical management allowing agricultural operators to register and oversee multiple independent farms and subdivide each farm into distinct registered fields.

---

## 2. Detailed Functional Requirements `[Confirmed]` (Source: §3 F10)

### FR-FRM-01: Multi-Farm Account Association `[Confirmed]` (Source: §3 F10)
- **Requirement Statement**: The system shall associate multiple distinct farms with a single authenticated user account.
- **Rationale**: Farmers and agribusinesses frequently manage non-contiguous land holdings across different geographic regions.
- **Verification**: Create multiple farms under a single account and verify complete independence of farm properties.

### FR-FRM-02: Hierarchical Field Partitioning `[Confirmed]` (Source: §3 F10)
- **Requirement Statement**: Under each registered farm, the system shall allow users to create and manage multiple individual fields (sub-parcels).
- **Rationale**: Enables granular organization matching crop rotations, irrigation zones, and soil types within a farm.
- **Verification**: Add multiple fields under Farm 1; verify that Field A and Field B belong strictly to Farm 1.

### FR-FRM-03: Relational Asset & Telemetry Isolation `[Confirmed]` (Source: §3 F10)
- **Requirement Statement**: The system shall maintain strict relational isolation, ensuring that deployed sensors, disease detections, scouting missions, and historical inspection records remain bound to their correct parent farm and specific field.
- **Rationale**: Prevents data contamination and ensures analytics and alerts reflect only the relevant physical plot.
- **Verification**: Query telemetry and findings for Farm A; assert zero leakage of data from Farm B.

### FR-FRM-04: Active Farm Context Switching `[Confirmed]` (Source: §3 F10)
- **Requirement Statement**: The mobile application shall provide an active farm selector allowing users to switch the active operational context instantly, refreshing dashboards, maps, and mission views to the selected farm.
- **Rationale**: Enables seamless operational review of distinct agricultural holdings without logging out.
- **Verification**: Switch active farm from selector; verify immediate reload of dashboard, telemetry, and map to the newly selected farm.
