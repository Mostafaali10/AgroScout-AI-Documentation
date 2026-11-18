# FR-01: Dashboard Specification

> **Status**: Draft – Derived from Source File  
> **Module**: Functional Requirements / Dashboard  
> **Source Reference**: `Source File.docx` (§3 F1)

---

## 1. Module Objective `[Confirmed]` (Source: §3 F1)

Provides an executive and operational overview of the active farm, highlighting urgent agronomic events, recent disease detections, ground sensor telemetry, and offline synchronization status.

---

## 2. Detailed Functional Requirements `[Confirmed]` (Source: §3 F1)

### FR-DASH-01: Farm Context & Activity Overview `[Confirmed]` (Source: §3 F1)
- **Requirement Statement**: The dashboard shall display the profile of the selected active farm, including its name and recent field activity summary.
- **Rationale**: Farmers need instant visibility into current farm operations without navigating deep into sub-menus.
- **Verification**: Functional UI verification and farm switcher testing.

### FR-DASH-02: Recent Disease Detections & Alerts `[Confirmed]` (Source: §3 F1)
- **Requirement Statement**: The dashboard shall present a prioritized summary of recent plant-disease detections and high-priority alerts for the selected farm.
- **Rationale**: Rapid awareness of foliar infections enables timely containment before pathogen propagation.
- **Verification**: Integration testing confirming newly processed backend detections appear in the dashboard alert queue.

### FR-DASH-03: Latest Sensor Telemetry Panel `[Confirmed]` (Source: §3 F1)
- **Requirement Statement**: The dashboard shall display the most recently ingested telemetry readings from ground nodes, including ambient temperature, relative humidity, and soil moisture.
- **Rationale**: Immediate awareness of microclimate conditions helps assess plant stress and disease susceptibility.
- **Verification**: Verify that the latest sensor telemetry matches database records for connected ESP32 nodes.

### FR-DASH-04: Module Navigation Shortcuts `[Confirmed]` (Source: §3 F1)
- **Requirement Statement**: The dashboard shall provide one-tap shortcuts to the Farm Map, Live Monitoring, Scouting Missions, History, Farm Analytics, and Export Reports.
- **Rationale**: Ensures rapid navigation for field workers performing urgent multi-step workflows.
- **Verification**: UI navigation testing validating route transitions.

### FR-DASH-05: Pending Synchronization Indicator `[Confirmed]` (Source: §3 F1)
- **Requirement Statement**: The dashboard shall display a visible pending synchronization status indicator and item count whenever offline inspection records or images are stored locally awaiting upload.
- **Rationale**: Prevents accidental data loss and informs field workers that local findings are pending backend upload.
- **Verification**: Test offline photo capture and confirm badge visibility and count on the dashboard.

### FR-DASH-06: Integrated Weather Forecast `[Proposed / Contingent]` (Source: §3 F1)
- **Requirement Statement**: The dashboard may display weather forecasts and ambient conditions when a suitable external meteorological data source is integrated into the platform.
- **Rationale**: Provides environmental context for pest risks and field work planning.
- **Verification**: Verify weather widget rendering when the weather API integration is active.
