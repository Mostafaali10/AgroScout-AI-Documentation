# Requirements Traceability Matrix (RTM)

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Engineering Traceability  
> **Source Reference**: `Source File.docx` (§1, §2, §3, §4, §5, §7)

---

## 1. Traceability Architecture

This matrix provides bi-directional end-to-end traceability linking:
`Source File Bullet (§3)` <--> `Feature ID` <--> `Functional Requirement (FR)` <--> `User Story (US)` <--> `Acceptance Criterion (AC)`

This guarantees that:
1. Every statement in `Source File.docx` is accounted for in the engineering specifications.
2. Zero unauthorized or ungrounded external requirements have been introduced.
3. Every functional requirement has an explicit Agile user story and an empirical verification gate.

---

## 2. Master Traceability Matrix

| Source Ref | Feature ID | Feature Name | Functional Req (FR) | Agile User Story (US) | Acceptance Criterion (AC) | Target Module |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **§3 F1.1** | `FEAT-01` | Dashboard | `FR-DASH-01, 02, 03` | `US-01.1` | `AC-01.1` | Flutter / Dashboard |
| **§3 F1.2** | `FEAT-01` | Dashboard | `FR-DASH-04` | `US-01.2` | `AC-01.2` | Flutter / Navigation |
| **§3 F1.3** | `FEAT-01` | Dashboard | `FR-DASH-05` | `US-01.3` | `AC-01.3` | Flutter / Sync Engine |
| **§3 F1.4** | `FEAT-01` | Dashboard | `FR-DASH-06` | `US-01.4` | `AC-01.4` | Backend / Weather API |
| **§3 F2.1** | `FEAT-02` | Farm Map | `FR-MAP-01` | `US-02.1` | `AC-02.1` | Flutter / Mapbox/Google |
| **§3 F2.2** | `FEAT-02` | Farm Map | `FR-MAP-02` | `US-02.2` | `AC-02.2` | Flutter / Mapbox/Google |
| **§3 F2.3** | `FEAT-02` | Farm Map | `FR-MAP-03` | `US-02.3` | `AC-02.3` | Flutter / UI Modal |
| **§3 F2.4** | `FEAT-02` | Farm Map | `FR-MAP-04` | `US-02.4` | `AC-02.4` | Flutter / Gestures |
| **§3 F3.1** | `FEAT-03` | Live Monitoring | `FR-MON-01, 02` | `US-03.1` | `AC-03.1` | Flutter & Embedded ESP32|
| **§3 F3.2** | `FEAT-03` | Live Monitoring | `FR-MON-03` | `US-03.2` | `AC-03.2` | Flutter & Edge Camera |
| **§3 F3.3** | `FEAT-03` | Live Monitoring | `FR-MON-04` | `US-03.3` | `AC-03.3` | Backend / AI Engine |
| **§3 F3.4** | `FEAT-03` | Live Monitoring | `FR-MON-05` | `US-03.4` | `AC-03.4` | Ingestion / HTTP-MQTT |
| **§3 F4.1** | `FEAT-04` | History & Details | `FR-HIST-01` | `US-04.1` | `AC-04.1` | Central DB & Mobile Cache|
| **§3 F4.2** | `FEAT-04` | History & Details | `FR-HIST-02` | `US-04.2` | `AC-04.2` | Flutter / Filtering Logic|
| **§3 F4.3** | `FEAT-04` | History & Details | `FR-HIST-03` | `US-04.3` | `AC-04.3` | Flutter / Map Routing |
| **§3 F5.1** | `FEAT-05` | Settings & Profile| `FR-SETT-01` | `US-05.1` | `AC-05.1` | Backend Auth & User DB |
| **§3 F5.2** | `FEAT-05` | Settings & Profile| `FR-SETT-02` | `US-05.2` | `AC-05.2` | Flutter / Preferences |
| **§3 F5.3** | `FEAT-05` | Settings & Profile| `FR-SETT-03, 04` | `US-05.3` | `AC-05.3` | Flutter / Auth Session |
| **§3 F6.1** | `FEAT-06` | Offline Mode | `FR-SYNC-01` | `US-06.1` | `AC-06.1` | Flutter / SQLite-Hive |
| **§3 F6.2** | `FEAT-06` | Offline Mode | `FR-SYNC-02` | `US-06.2` | `AC-06.2` | Flutter / Connectivity |
| **§3 F6.3** | `FEAT-06` | Offline Mode | `FR-SYNC-03` | `US-06.3` | `AC-06.3` | Sync State Machine |
| **§3 F6.4** | `FEAT-06` | Offline Mode | `FR-SYNC-04` | `US-06.4` | `AC-06.4` | Backend Deduplication |
| **§3 F6.5** | `FEAT-06` | Offline Mode | `FR-SYNC-05` | `US-06.5` | `AC-06.5` | Architectural Invariant |
| **§3 F7.1** | `FEAT-07` | Farm Analytics | `FR-ANL-01` | `US-07.1` | `AC-07.1` | Backend Analytics / Charts|
| **§3 F7.2** | `FEAT-07` | Farm Analytics | `FR-ANL-02` | `US-07.2` | `AC-07.2` | Backend Pathogen Stats |
| **§3 F7.3** | `FEAT-07` | Farm Analytics | `FR-ANL-03, 04` | `US-07.3` | `AC-07.3` | Flutter / Chart Widgets |
| **§3 F8.1** | `FEAT-08` | Scouting Missions | `FR-MSN-01` | `US-08.1` | `AC-08.1` | Flutter / Mission Planner |
| **§3 F8.2** | `FEAT-08` | Scouting Missions | `FR-MSN-02` | `US-08.2` | `AC-08.2` | Flutter / Checklist UI |
| **§3 F8.3** | `FEAT-08` | Scouting Missions | `FR-MSN-03` | `US-08.3` | `AC-08.3` | Mission State Machine |
| **§3 F8.4** | `FEAT-08` | Scouting Missions | `FR-MSN-04` | `US-08.4` | `AC-08.4` | Scope Guardrail (No Autopilot)|
| **§3 F9.1** | `FEAT-09` | Export Reports | `FR-REP-01, 02` | `US-09.1` | `AC-09.1` | PDF Generation Engine |
| **§3 F9.2** | `FEAT-09` | Export Reports | `FR-REP-03` | `US-09.2` | `AC-09.2` | Sensor Telemetry Ingestion|
| **§3 F9.3** | `FEAT-09` | Export Reports | `FR-REP-04, 05` | `US-09.3` | `AC-09.3` | Native OS Share Sheet |
| **§3 F10.1**| `FEAT-10` | Multi-Farm & Field| `FR-FRM-01, 02` | `US-10.1` | `AC-10.1` | Multi-Tenant Data Schema |
| **§3 F10.2**| `FEAT-10` | Multi-Farm & Field| `FR-FRM-03` | `US-10.2` | `AC-10.2` | Relational DB Isolation |
| **§3 F10.3**| `FEAT-10` | Multi-Farm & Field| `FR-FRM-04` | `US-10.3` | `AC-10.3` | Flutter Context Switcher|
| **§3 F11.1**| `FEAT-11` | Camera Submission | `FR-CAM-01` | `US-11.1` | `AC-11.1` | Mobile / Edge Camera |
| **§3 F11.2**| `FEAT-11` | Camera Submission | `FR-CAM-02` | `US-11.2` | `AC-11.2` | Mobile GPS Subsystem |
| **§3 F11.3**| `FEAT-11` | Camera Submission | `FR-CAM-03` | `US-11.3` | `AC-11.3` | Ingestion API Transport |
| **§3 F12.1**| `FEAT-12` | AI Advisor Agent | `FR-AGT-01` | `US-12.1` | `AC-12.1` | AI Conversational Service|
| **§3 F12.2**| `FEAT-12` | AI Advisor Agent | `FR-AGT-02` | `US-12.2` | `AC-12.2` | Multi-Modal Vision Link |
| **§3 F12.3**| `FEAT-12` | AI Advisor Agent | `FR-AGT-03` | `US-12.3` | `AC-12.3` | Agronomic Knowledge Base |
| **§3 F12.4**| `FEAT-12` | AI Advisor Agent | `FR-AGT-04` | `US-12.4` | `AC-12.4` | Multi-Turn Dialogue Memory|
| **§3 F12.5**| `FEAT-12` | AI Advisor Agent | `FR-AGT-05` | `US-12.5` | `AC-12.5` | Mandatory Safety Disclaimer|

---

## 3. Cross-Cutting Capabilities & Non-Functional Traceability

| Source Section | Architecture / Quality Domain | Artifact Identifier | Document Reference |
| :--- | :--- | :--- | :--- |
| **§1, §2, §5** | Cross-Cutting: Plant Disease Vision Pipeline | `CAP-AI-01` to `CAP-AI-05` | `05-Functional-Requirements/disease-detection.md` |
| **§1, §2, §5** | Cross-Cutting: Ground Node Telemetry Pipeline | `CAP-IOT-01` to `CAP-IOT-05` | `05-Functional-Requirements/sensor-data.md` |
| **§5 Software** | Mobile Architecture (Clean Architecture / BLoC) | `NFR-ARCH-01`, `NFR-ARCH-02` | `06-Non-Functional-Requirements/non-functional-requirements.md` |
| **§5 Software** | Embedded Firmware (C++ / Arduino on ESP32) | `NFR-ARCH-03` | `06-Non-Functional-Requirements/non-functional-requirements.md` |
| **§3 F6** | Reliability & Idempotent Offline Synchronization | `NFR-REL-01` to `NFR-REL-03` | `06-Non-Functional-Requirements/non-functional-requirements.md` |
| **§3 F12, §4 F16**| Safety Guardrail & Diagnostic Uncertainty | `NFR-SAFE-01`, `NFR-SAFE-02` | `06-Non-Functional-Requirements/non-functional-requirements.md` |
| **§4 F24** | Bilingual Localization (Arabic & English) | `NFR-USE-01` | `06-Non-Functional-Requirements/non-functional-requirements.md` |
| **§5 Components**| Hardware Performance & Optical Trade-Offs | `NFR-PERF-01`, `NFR-PERF-02` | `06-Non-Functional-Requirements/non-functional-requirements.md` |
| **§7 Items** | Architectural Open Questions Register | `OQ-01` to `OQ-08` | `02-Scope/open-questions.md` |
| **§4 Rec Features**| Prioritized Enhancements & Differentiating Features | `FEAT-REC-01` to `FEAT-REC-24` | `04-Features/recommended-features.md` |
