# 01. Feature Catalog — 12 Core Baseline Features

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Product Features  
> **Source Reference**: `Source File.docx` (§3)

---

## 1. Core Feature Inventory `[Confirmed]` (Source: §3)

The following twelve features constitute the baseline functional inventory of the AgroScout AI platform.

---

### FEAT-01: Dashboard `[Confirmed]` (Source: §3 F1)
- **Objective**: Provides a centralized operational overview of the currently active farm and recent field activities.
- **Key Capabilities**:
  - Displays primary farm information and summary status.
  - Highlights recent plant disease detections and prioritized alerts.
  - Presents latest telemetry readings from ground-node sensors (temperature, humidity, soil moisture).
  - Supplies one-tap navigation shortcuts to Farm Map, Live Monitoring, Scouting Missions, History, Farm Analytics, and Export Reports.
  - Displays pending offline synchronization counters when un-uploaded records exist locally.
  - Displays integrated weather information when a suitable external data feed is connected `(Source: §3 F1)`.

---

### FEAT-02: Farm Map `[Confirmed]` (Source: §3 F2)
- **Objective**: Geospatial visualization of farms, registered parcels/fields, IoT sensor nodes, and location-linked diagnostic findings.
- **Key Capabilities**:
  - Renders boundaries and labels for mapped farms and registered sub-fields.
  - Plots interactive markers for disease detections when valid GPS coordinates or mapped field zones exist.
  - Enables users to tap a marker to inspect details: foliage photo, disease label, timestamp, and confidence score.
  - Supports intuitive geospatial navigation and zooming across multiple farms, fields, and high-infection zones `(Source: §3 F2)`.

---

### FEAT-03: Live Monitoring `[Confirmed]` (Source: §3 F3)
- **Objective**: Presents incoming or recently received environmental sensor telemetry and camera visuals.
- **Key Capabilities**:
  - Displays near-real-time or periodic readings of ambient air temperature, relative humidity, and soil moisture.
  - Reports hardware operational status of connected ground nodes.
  - Displays incoming optical images or streaming video according to the finalized camera workflow.
  - Surfaces backend-generated disease analysis results and allows opening full detection records.
  - Update cadence (continuous, near-real-time, or periodic) adapts to the finalized communication architecture `(Source: §3 F3)`.

---

### FEAT-04: History & Details `[Confirmed]` (Source: §3 F4)
- **Objective**: Comprehensive historical repository of past field inspections, sensor logs, and visual diagnostic records.
- **Key Capabilities**:
  - Catalogs past inspections displaying disease name, leaf photo, date/time, GPS coordinates, AI confidence score, and associated sensor readings where available.
  - Provides multi-parameter filtering by farm, registered field, date interval, and diagnosed pathogen type.
  - Allows users to select any historical record and view its precise origin on the interactive Farm Map `(Source: §3 F4)`.

---

### FEAT-05: Settings & Profile `[Confirmed]` (Source: §3 F5)
- **Objective**: User identity management, application configuration, and system diagnostic monitoring.
- **Key Capabilities**:
  - View and update user profile details and account security settings.
  - Configure application visual preferences and alert notification thresholds.
  - Monitor local network connectivity and synchronization engine health.
  - Execute secure account logout `(Source: §3 F5)`.

---

### FEAT-06: Offline Mode & Synchronization `[Confirmed]` (Source: §3 F6)
- **Objective**: Ensures unbroken field usability during intermittent or absent cellular network coverage.
- **Key Capabilities**:
  - Persists captured foliage photos, sensor telemetry, and inspection metadata safely in local device storage.
  - Automatically identifies restored network connectivity and uploads queued records to the Backend.
  - Displays explicit item statuses: `Pending Upload`, `Uploading`, `Processing`, `Completed`, and `Failed`.
  - Implements robust retry handling and idempotent deduplication to prevent duplicate records upon upload retries.
  - Enforces the system rule: *new backend disease results are not available for an offline image until that image is successfully uploaded and processed* `(Source: §3 F6)`.

---

### FEAT-07: Farm Analytics `[Confirmed]` (Source: §3 F7)
- **Objective**: Aggregates longitudinal inspection and pathogen detection trends to guide farm management.
- **Key Capabilities**:
  - Compares disease detection frequencies across daily and weekly intervals.
  - Identifies recurring pathogen outbreaks and geographically persistent problem areas.
  - Presents trends via intuitive analytical charts and map-based aggregation views.
  - Supports comparative filtering by specific farm or individual field `(Source: §3 F7)`.

---

### FEAT-08: Scouting Missions `[Confirmed]` (Source: §3 F8)
- **Objective**: Organizes, schedules, and tracks manual or drone-assisted crop inspection tasks.
- **Key Capabilities**:
  - Enables selection of target farm, parcel, inspection zone, or coordinate waypoint.
  - Creates structured mission tasks with predefined inspection checklists.
  - Tracks mission lifecycle statuses: `Pending`, `In Progress`, and `Completed`.
  - Notes explicitly: *Direct drone flight-path control or autonomous navigation is not confirmed for the initial scope* `(Source: §3 F8)`.

---

### FEAT-09: Export Reports `[Confirmed]` (Source: §3 F9)
- **Objective**: Generates shareable, printable PDF agronomic inspection reports for field records and agricultural consulting.
- **Key Capabilities**:
  - Compiles foliar detection photos, disease identifications, capture timestamps, and GPS coordinates.
  - Incorporates concurrent sensor telemetry (temperature, humidity, moisture) when available.
  - Exports formatted PDF files for a selected farm, specific field, or scouting mission.
  - Facilitates instant saving to device storage or sharing via mobile share sheets `(Source: §3 F9)`.

---

### FEAT-10: Multiple Farms & Fields `[Confirmed]` (Source: §3 F10)
- **Objective**: Provides hierarchical multi-farm organization for enterprise growers or multi-plot smallholders.
- **Key Capabilities**:
  - Links multiple independent farms to a single user account.
  - Enables creation and boundary registration of multiple fields under each farm.
  - Maintains strict domain separation, binding sensors, detections, scouting missions, and history to the correct farm and field.
  - Enables instant switching of the active farm context across the mobile application `(Source: §3 F10)`.

---

### FEAT-11: Camera Image + Location Submission `[Confirmed]` (Source: §3 F11)
- **Objective**: Captures crop imagery and packages it with necessary geographic and temporal metadata for backend analysis.
- **Key Capabilities**:
  - Captures or receives a photo of a suspected diseased crop from mobile camera, field camera, or drone import.
  - Packages the photo with available native GPS coordinates and capture timestamp.
  - Dispatches the payload through the agreed mobile/camera/backend communication pipeline for spatial mapping and inference `(Source: §3 F11)`.

---

### FEAT-12: AI Agricultural Agent `[Confirmed]` (Source: §3 F12)
- **Objective**: Conversational advisory assistant delivering specialized plant pathology knowledge and treatment recommendations.
- **Key Capabilities**:
  - Accepts natural language inquiries regarding foliar crop diseases and suspected field issues.
  - Assists in interpreting submitted crop imagery where supported by the underlying vision model.
  - Explains observed symptoms, underlying biological causes, and anticipated crop effects.
  - Recommends actionable prevention guidelines and targeted treatment options.
  - Supports multi-turn follow-up dialogues, optionally leveraging historical farm detections as conversational context.
  - Communicates uncertainty responsibly: *AI output is strictly advisory guidance, not a guaranteed agronomic diagnosis* `(Source: §3 F12)`.
