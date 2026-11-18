# 01. Product Scope — Baseline, In-Scope & Out-of-Scope

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Scope Definition  
> **Source Reference**: `Source File.docx` (§2, §3, §4, §7)

---

## 1. Baseline In-Scope Capabilities `[Confirmed]` (Source: §3)

The confirmed baseline for the AgroScout AI platform comprises twelve functional modules:

| Feature ID | Feature Name | Core Functional Responsibility | Source Reference |
| :--- | :--- | :--- | :--- |
| **F-01** | **Dashboard** | Overview of selected farm, recent activity, recent disease detections, alerts, latest sensor readings, shortcuts, pending sync status, and optional weather info. | `§3 F1` |
| **F-02** | **Farm Map** | Geospatial rendering of registered farms, fields, sensors, and GPS-linked disease detection pins with clickable details (image, label, timestamp, confidence). | `§3 F2` |
| **F-03** | **Live Monitoring** | Current or recent sensor telemetry (temp, air humidity, soil moisture, device status), camera imagery/feed, and backend disease analysis. | `§3 F3` |
| **F-04** | **History & Details** | Historical inspection log with disease name, image, timestamp, GPS, confidence, sensor context, multi-factor filtering, and map navigation. | `§3 F4` |
| **F-05** | **Settings & Profile** | Profile management, application and alert preferences, connectivity and sync status diagnostics, and secure logout. | `§3 F5` |
| **F-06** | **Offline Mode & Synchronization** | Local persistence of inspection data and images without internet; automated multi-stage synchronization (`Pending Upload` -> `Uploading` -> `Processing` -> `Completed` / `Failed`); idempotent deduplication. | `§3 F6` |
| **F-07** | **Farm Analytics** | Temporal trends comparing detection counts by day and week, most frequent diseases, recurring problem zones, and visual charts. | `§3 F7` |
| **F-08** | **Scouting Missions** | Creation and execution of field scouting assignments linked to specific farms/fields; checklist task tracking across `Pending`, `In Progress`, and `Completed` states. | `§3 F8` |
| **F-09** | **Export Reports** | Generation of shareable PDF agronomic inspection reports containing disease imagery, diagnostic details, GPS coordinates, timestamps, and sensor telemetry. | `§3 F9` |
| **F-10** | **Multiple Farms & Fields** | Hierarchical multi-tenant organization allowing users to manage multiple farms, partition each farm into distinct fields, and isolate telemetry/history per farm. | `§3 F10` |
| **F-11** | **Camera Image + Location Submission** | Pipeline capturing plant imagery, associating native GPS and capture timestamp, and transmitting payload to the Backend. | `§3 F11` |
| **F-12** | **AI Agricultural Agent** | Conversational agronomic assistant answering disease queries, interpreting symptoms, explaining causes, suggesting prevention/treatment, and communicating uncertainty. | `§3 F12` |

---

## 2. Explicitly Out-of-Scope (Initial Release) `[Confirmed]` (Source: §2, §3, §4, §7)

To prevent scope creep and align development with team capacity, the following features are explicitly categorized as **Out-of-Scope** for the initial baseline:

1. **Direct Autonomous Drone Navigation / Waypoint Control**:
   - *"Direct drone flight-path control or autonomous navigation is not confirmed for the initial scope."* `(Source: §3 F8, §7)`. The platform consumes imagery and metadata captured via drone, but does not execute real-time flight autopilot.
2. **On-Device Local AI Inference**:
   - Mobile and edge devices do not execute local quantized neural network inference for offline image diagnosis `(Source: §2, §5)`. Full diagnostic results require backend connectivity and upload.
3. **Automated Actuator / Irrigation Control**:
   - The platform provides agronomic recommendations only (e.g., irrigation timing advice based on soil moisture); it does **not** command automated irrigation valves, pumps, or actuators `(Source: §4 F12)`.
4. **Guaranteed / Definite Agronomic Certifications**:
   - The platform AI assistant acts solely as an advisory guidance tool. It is strictly constrained from providing legally guaranteed or absolute diagnostic certifications `(Source: §3 F12)`.
