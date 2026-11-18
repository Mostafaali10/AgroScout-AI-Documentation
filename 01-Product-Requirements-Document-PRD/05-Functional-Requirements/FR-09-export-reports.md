# FR-09: Export Reports Specification

> **Status**: Draft – Derived from Source File  
> **Module**: Functional Requirements / Export Reports  
> **Source Reference**: `Source File.docx` (§3 F9)

---

## 1. Module Objective `[Confirmed]` (Source: §3 F9)

Compiles inspection findings, diagnostic imagery, geolocation coordinates, and environmental telemetry into standardized, shareable PDF agronomic reports for archiving, compliance, and consulting.

---

## 2. Detailed Functional Requirements `[Confirmed]` (Source: §3 F9)

### FR-REP-01: PDF Document Generation `[Confirmed]` (Source: §3 F9)
- **Requirement Statement**: The system shall generate formatted, printable PDF inspection reports on demand.
- **Rationale**: Farmers and agronomists require portable, offline-accessible documentation for agronomic consultations, chemical purchasing, or regulatory compliance.
- **Verification**: Trigger PDF export and verify document generation without rendering errors.

### FR-REP-02: Mandatory Report Content Ingestion `[Confirmed]` (Source: §3 F9)
- **Requirement Statement**: Each exported inspection report shall include high-resolution detection images, identified plant disease labels, exact capture dates/timestamps, and geographic GPS coordinates.
- **Rationale**: Comprehensive photographic and geospatial evidence is required to substantiate diagnosis and track outbreak progression.
- **Verification**: Inspect generated PDF structure and confirm presence of foliage images, pathogen labels, timestamps, and coordinates.

### FR-REP-03: Environmental Telemetry Inclusion `[Confirmed]` (Source: §3 F9)
- **Requirement Statement**: Where ground-node sensors are linked to the inspected area, the report shall embed relevant concurrent environmental readings (ambient air temperature, air humidity, and soil moisture).
- **Rationale**: Provides environmental context explaining fungal incubation and soil moisture deficits.
- **Verification**: Export report for an area with active sensors and verify the presence of the sensor telemetry section.

### FR-REP-04: Farm & Parcel Scope Selection `[Confirmed]` (Source: §3 F9)
- **Requirement Statement**: The reporting module shall permit users to configure report boundaries, generating reports for an entire selected farm or scoped specifically to an individual registered field.
- **Rationale**: Prevents clutter when reporting on specific problematic parcels.
- **Verification**: Select a specific field filter and verify that only findings and sensors for that field appear in the generated document.

### FR-REP-05: Local Storage & Native Sharing `[Confirmed]` (Source: §3 F9)
- **Requirement Statement**: The mobile application shall allow users to save the generated PDF file directly to local device storage and dispatch it via native mobile operating system share sheets (e.g., messaging apps, email, cloud drives).
- **Rationale**: Ensures rapid distribution to field consultants and agronomic advisors.
- **Verification**: Verify invocation of the native OS share sheet upon PDF generation completion.
