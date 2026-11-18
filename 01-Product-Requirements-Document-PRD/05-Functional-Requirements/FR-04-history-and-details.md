# FR-04: History & Details Specification

> **Status**: Draft – Derived from Source File  
> **Module**: Functional Requirements / History & Details  
> **Source Reference**: `Source File.docx` (§3 F4)

---

## 1. Module Objective `[Confirmed]` (Source: §3 F4)

Stores, indexes, and presents an immutable audit history of all prior crop inspections, plant pathogen detections, captured imagery, and environmental sensor readings.

---

## 2. Detailed Functional Requirements `[Confirmed]` (Source: §3 F4)

### FR-HIST-01: Comprehensive Record Ingestion & Storage `[Confirmed]` (Source: §3 F4)
- **Requirement Statement**: The system shall persistently store and display historical inspection records, each containing the identified disease name, foliage photo, timestamp, GPS coordinates, AI confidence score, and concurrent sensor readings when available.
- **Rationale**: Long-term agronomic analysis requires a historical audit trail of crop health and environmental conditions over time.
- **Verification**: Query database for past inspections and verify all core metadata fields render correctly in the history UI.

### FR-HIST-02: Multi-Factor Filtering & Search `[Confirmed]` (Source: §3 F4)
- **Requirement Statement**: The interface shall allow users to filter historical inspection records by active farm, registered field/parcel, date interval, and specific plant disease classification where supported.
- **Rationale**: Enables farmers and agronomists to isolate specific disease outbreaks across historical seasons and distinct fields.
- **Verification**: Apply individual and combined filter parameters (e.g., Farm A + Field 2 + Date Range) and verify that the results list matches criteria.

### FR-HIST-03: Geospatial Map Linkage `[Confirmed]` (Source: §3 F4)
- **Requirement Statement**: The system shall allow users to select any historical inspection finding and navigate directly to its corresponding geotagged location on the interactive Farm Map.
- **Rationale**: Re-inspecting problem locations requires fast spatial localization of where the historical symptom was recorded.
- **Verification**: Tap "Open on Map" from a historical record and verify the Farm Map centers on the specific GPS coordinates with the finding pin highlighted.
