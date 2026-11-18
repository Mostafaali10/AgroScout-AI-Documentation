# FR-03: Live Monitoring Specification

> **Status**: Draft – Derived from Source File  
> **Module**: Functional Requirements / Live Monitoring  
> **Source Reference**: `Source File.docx` (§3 F3, §5, §7)

---

## 1. Module Objective `[Confirmed]` (Source: §3 F3)

Provides a live or near-live operational feed of ground-node environmental telemetry, device operational health, incoming optical imagery/video, and centralized backend disease diagnoses.

---

## 2. Detailed Functional Requirements `[Confirmed]` (Source: §3 F3)

### FR-MON-01: Microclimate & Soil Telemetry Ingestion `[Confirmed]` (Source: §3 F3)
- **Requirement Statement**: The system shall present current or recently received telemetry readings for ambient temperature, air humidity, and soil moisture from connected ground nodes.
- **Rationale**: Continuous microclimate visibility allows operators to detect sudden environmental shifts that encourage disease incubation.
- **Verification**: Ingest sample telemetry payloads and verify immediate UI metric update on the Live Monitoring screen.

### FR-MON-02: Device Hardware Status Tracking `[Confirmed]` (Source: §3 F3)
- **Requirement Statement**: The monitoring interface shall display the operational status of supported field devices, including connectivity state and battery status where supported by hardware.
- **Rationale**: Enables field staff to identify disconnected or battery-depleted ground nodes promptly.
- **Verification**: Toggle simulated node connectivity and verify status indicator updates between online and offline.

### FR-MON-03: Optical Image & Video Feed Ingestion `[Confirmed / TBD]` (Source: §3 F3, §7)
- **Requirement Statement**: The system shall display incoming camera images or streaming video feeds in accordance with the finalized camera integration workflow (ESP32-CAM, mobile camera, or Raspberry Pi Zero 2 W).
- **Rationale**: Visual verification of field conditions enables rapid visual inspection without walking to remote plots.
- **Verification**: Transmit test image/stream payloads and verify visual rendering in the live feed container.

### FR-MON-04: Backend Diagnostic Result Presentation `[Confirmed]` (Source: §3 F3)
- **Requirement Statement**: The interface shall present backend-generated disease analysis results associated with incoming imagery, providing access to full detection details and bounding boxes where supported.
- **Rationale**: Delivers automated disease analysis directly into the live monitoring workflow.
- **Verification**: Dispatch an image payload, await backend inference completion, and verify diagnosis details appear in the feed.

### FR-MON-05: Adaptive Telemetry Cadence `[Confirmed / TBD]` (Source: §3 F3, §7)
- **Requirement Statement**: The update frequency of the monitoring interface (real-time, near-real-time, or periodic batching) shall adapt dynamically to the finalized communication architecture and power budget (HTTP vs MQTT).
- **Rationale**: Accommodates varying field connectivity constraints and device battery conservation strategies.
- **Verification**: Test telemetry reception under periodic polling and event-driven MQTT configurations.
