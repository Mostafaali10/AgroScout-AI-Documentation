# 03. Architectural Open Questions & Unfinalized Items

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Scope Definition  
> **Source Reference**: `Source File.docx` (§2, §5, §7)

---

## 1. Executive Summary `[TBD]` (Source: §7)

This document catalogs all architectural, hardware, and integration decisions explicitly identified in `Source File.docx` as **Not Yet Finalized**. These items serve as an open decision log for engineering alignment between AI, Flutter, Backend, and Embedded domain leads.

---

## 2. Open Decision Register `[TBD]` (Source: §7)

```
+------------------------------------------------------------------------------------------------------+
|                                 ARCHITECTURAL OPEN DECISION REGISTER                                 |
+----+-----------------------------+------------------------------------+------------------------------+
| ID | Decision Topic              | Scope & Alternatives Under Study   | Impacted Engineering Domains |
+----+-----------------------------+------------------------------------+------------------------------+
| OQ-1| Camera Hardware & Stream    | ESP32-CAM vs RPi Zero 2 W vs Mobile| Embedded, Mobile, AI         |
|    |                             | Still images vs Live Video stream. |                              |
+----+-----------------------------+------------------------------------+------------------------------+
| OQ-2| Drone Ingestion & GPS       | Drone -> App vs Drone -> Backend;  | Embedded, Backend, Mobile    |
|    |                             | Origin & precision of GPS metadata.|                              |
+----+-----------------------------+------------------------------------+------------------------------+
| OQ-3| Multi-Modal Sensor Fusion   | Algorithm/rules combining humidity | AI, Backend, Agronomy        |
|    |                             | and soil moisture with AI vision.  |                              |
+----+-----------------------------+------------------------------------+------------------------------+
| OQ-4| AI Model & Crop Taxonomy    | Final model (YOLOv8 candidate),    | AI, Agronomy                 |
|    |                             | supported crop species & pathogens.|                              |
+----+-----------------------------+------------------------------------+------------------------------+
| OQ-5| Backend Architecture Stack  | Framework, relational/NoSQL DB,    | Backend, Cloud DevOps        |
|    |                             | object storage, and API contracts. |                              |
+----+-----------------------------+------------------------------------+------------------------------+
| OQ-6| Field Protocol & Cadence    | HTTP REST vs MQTT publish/subscribe| Embedded, Backend            |
|    |                             | Telemetry frequency (real-time/min)|                              |
+----+-----------------------------+------------------------------------+------------------------------+
| OQ-7| Client Mapping & Local DB   | Mapbox vs Google Maps;             | Mobile (Flutter)             |
|    |                             | SQLite vs Hive; Firebase boundary. |                              |
+----+-----------------------------+------------------------------------+------------------------------+
| OQ-8| Autonomous Drone Scope      | Out of initial scope; future       | Embedded, Product            |
|    |                             | autopilot flight path boundary.    |                              |
+----+-----------------------------+------------------------------------+------------------------------+
```

### Detailed Breakdown:

1. **OQ-01: Optical Hardware & Transmission Workflow `(Source: §5, §7)`**
   - *Description*: Final camera hardware selection remains open. Furthermore, it must be determined whether field scouting relies on high-resolution still snapshots, live video streams, or a hybrid mode.
   - *Candidate Solutions*: ESP32-CAM, Mobile Phone Camera, or Raspberry Pi Zero 2 W + Camera Module 3.

2. **OQ-02: Aerial Drone Imagery Ingestion & Geolocation Source `(Source: §2, §7)`**
   - *Description*: The physical and network pathway through which drone imagery reaches the central Backend or Flutter client is unconfirmed. The exact source, accuracy, and format of coordinate metadata (EXIF GPS vs telemetry log) must be agreed upon.

3. **OQ-03: Environmental Telemetry & Image Sensor Fusion `(Source: §2, §7)`**
   - *Description*: Whether and how ground-node sensor readings (temperature, ambient humidity, soil moisture) are algorithmically fused with computer vision predictions to enhance diagnosis or risk scoring.

4. **OQ-04: AI Model Selection, Target Taxonomy & Datasets `(Source: §5, §7)`**
   - *Description*: Selection of the final deep learning architecture (YOLOv8 is an active example candidate). Definition of supported crop classes, pathogen taxonomy, training/validation datasets, accuracy targets, and GPU inference hosting.

5. **OQ-05: Backend Stack, Persistence & API Contracts `(Source: §5, §7)`**
   - *Description*: Selection of the backend programming framework, primary database, binary object storage for foliage photos, cloud hosting infrastructure, and interface contracts.

6. **OQ-06: Telemetry Ingestion Protocol & Cadence `(Source: §3 F3, §5, §7)`**
   - *Description*: Evaluation of HTTP REST vs MQTT for ESP32 ground-node transmissions. Determination of telemetry transmission intervals (continuous real-time, near-real-time, or scheduled batch updates).

7. **OQ-07: Mobile Maps, Local Persistence & Firebase Delegation `(Source: §5, §7)`**
   - *Description*: Finalizing the mapping library (`flutter_map` with Mapbox/OSM tiles vs `google_maps_flutter`). Selecting the offline mobile database engine (SQLite vs Hive). Clarifying Firebase's operational scope.

8. **OQ-08: Autonomous Drone Navigation Boundaries `(Source: §3 F8, §7)`**
   - *Description*: Confirming that automated mission waypoint dispatch and autonomous flight-path execution remain excluded from initial development, establishing when or if flight control enters the product roadmap.
