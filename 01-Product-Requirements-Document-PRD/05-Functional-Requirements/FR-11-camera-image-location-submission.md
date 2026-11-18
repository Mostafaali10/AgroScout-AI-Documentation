# FR-11: Camera Image + Location Submission Specification

> **Status**: Draft – Derived from Source File  
> **Module**: Functional Requirements / Image & Geolocation Submission  
> **Source Reference**: `Source File.docx` (§2, §3 F11, §5)

---

## 1. Module Objective `[Confirmed]` (Source: §3 F11)

Captures or receives optical plant imagery, packages it with capture timestamps and spatial coordinate metadata, and transmits the resulting diagnostic payload through the agreed system pipeline to the Central Backend.

---

## 2. Detailed Functional Requirements `[Confirmed]` (Source: §3 F11)

### FR-CAM-01: Optical Image Acquisition `[Confirmed]` (Source: §3 F11)
- **Requirement Statement**: The system shall capture or receive high-resolution imagery of a suspected crop or diseased foliar area from mobile device cameras, connected field cameras, or external drone imports.
- **Rationale**: Visual leaf patterns are the primary raw data input required for computer vision disease detection.
- **Verification**: Capture image via mobile camera interface and import sample external drone photo; verify proper byte array buffering.

### FR-CAM-02: Geolocation & Timestamp Metadata Packaging `[Confirmed]` (Source: §3 F11)
- **Requirement Statement**: The system shall automatically associate each captured image with native GPS coordinates (latitude/longitude) and capture timestamp metadata whenever available.
- **Rationale**: Spatial and temporal metadata are essential for plotting findings on the Farm Map and evaluating outbreak progression over time.
- **Verification**: Capture photo with GPS enabled; inspect payload and verify presence of ISO-8601 timestamp and geographic coordinates.

### FR-CAM-03: Multi-Path Pipeline Dispatch `[Confirmed / TBD]` (Source: §2, §3 F11, §5)
- **Requirement Statement**: The client shall package and transmit the photographic payload and metadata through the agreed transmission pathway (direct mobile-to-backend HTTPS/REST, or edge-camera intermediate bridge) to the Central Backend for processing.
- **Rationale**: Facilitates modular integration across various capture devices (mobile phone, ESP32-CAM, or Raspberry Pi Zero 2 W).
- **Verification**: Execute submission and confirm payload reception, integrity validation, and persistence on the backend.
