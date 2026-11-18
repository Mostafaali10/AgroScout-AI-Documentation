# FR-02: Farm Map Specification

> **Status**: Draft – Derived from Source File  
> **Module**: Functional Requirements / Geospatial Farm Map  
> **Source Reference**: `Source File.docx` (§3 F2)

---

## 1. Module Objective `[Confirmed]` (Source: §3 F2)

Delivers interactive geospatial visualization of agricultural properties, registered parcel boundaries, deployed sensor nodes, and geotagged plant-disease detections.

---

## 2. Detailed Functional Requirements `[Confirmed]` (Source: §3 F2)

### FR-MAP-01: Farm & Field Boundary Rendering `[Confirmed]` (Source: §3 F2)
- **Requirement Statement**: The system shall render mapped farms and all associated registered fields on an interactive geospatial canvas.
- **Rationale**: Farmers require clear geographic boundaries to organize field assets and localize problems.
- **Verification**: Map layer verification confirming farm polygons and field perimeters render accurately.

### FR-MAP-02: Geotagged Disease Detection Markers `[Confirmed]` (Source: §3 F2)
- **Requirement Statement**: The map shall plot distinct visual markers for recorded disease detections wherever valid GPS coordinates or mapped field zones are available.
- **Rationale**: Pinpointing exact infection locations enables precision targeted treatment instead of blanket spraying.
- **Verification**: Verify that inspection records with valid coordinate metadata plot at the correct geographic location.

### FR-MAP-03: Finding Detail Modal `[Confirmed]` (Source: §3 F2)
- **Requirement Statement**: Upon selecting a disease marker, the system shall display a finding details view showing the foliage photo, diagnosed disease label, capture timestamp, and AI confidence score when supplied.
- **Rationale**: Enables field operators to verify visual evidence and diagnostic certainty before taking action.
- **Verification**: Click marker interaction test verifying that the modal displays all required metadata fields.

### FR-MAP-04: Multi-Level Geospatial Navigation `[Confirmed]` (Source: §3 F2)
- **Requirement Statement**: The map interface shall support intuitive navigation, panning, and zooming between distinct farms, individual fields, and identified problem areas.
- **Rationale**: Facilitates rapid switching between high-level macro view and micro-plot investigation.
- **Verification**: Gesture and UI control testing validating fluid bounding box transitions across farm zones.
