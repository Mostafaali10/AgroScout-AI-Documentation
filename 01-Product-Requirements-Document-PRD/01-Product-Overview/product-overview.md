# 01. Product Overview — AgroScout AI

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Product Overview  
> **Source Reference**: `Source File.docx` (§1, §6)

---

## 1. Executive Summary `[Confirmed]` (Source: §1)

**AgroScout AI** is a smart agriculture monitoring and AI-assisted crop inspection platform. The platform combines:
- A cross-platform **Flutter mobile application** for field operations and dashboard management.
- Scalable **Backend services** for data coordination, business logic, and API provisioning.
- **AI-based plant-disease analysis** to detect and localize foliar crop abnormalities.
- **Drone or camera imagery** to survey larger agricultural areas efficiently.
- **IoT ground nodes** to acquire localized environmental and soil parameters.

The primary objective of AgroScout AI is to assist farmers and agricultural operators in monitoring their fields, identifying potential crop problems at earliest stages, and making better-informed operational decisions `(Source: §1)`.

---

## 2. Core Technology Pillars `[Confirmed]` (Source: §1)

The platform is architected around four foundational technology concepts:

```
+---------------------------------------------------------------------------------+
|                                 AGROSCOUT AI                                    |
+------------------------+-------------------------------+------------------------+
| 1. AI & Computer Vision| 2. Drone Technology           | 3. IoT Sensors         |
|    Image analysis to   |    Aerial image capture for   |    Ground-node micro-  |
|    identify visual     |    rapid large-area field     |    climate and soil    |
|    pathogen patterns.  |    surveying.                 |    telemetry.          |
+------------------------+-------------------------------+------------------------+
|                                4. Geospatial Mapping                            |
|    Associating findings and sensor telemetry with GPS coordinates & field zones.|
+---------------------------------------------------------------------------------+
```

1. **AI & Computer Vision**: Analyzes plant imagery to detect and identify visual patterns associated with possible foliar diseases `(Source: §1)`.
2. **Drone Technology**: Captures aerial imagery across agricultural acreage to survey large fields significantly faster than manual walk-through scouting `(Source: §1)`.
3. **IoT Sensors**: Collects continuous environmental and soil readings, specifically ambient air temperature, relative air humidity, and soil moisture `(Source: §1)`.
4. **Geospatial Mapping**: Associates image findings and sensor telemetry with precise GPS coordinates or registered field zones, visualizing them interactively within the mobile application `(Source: §1)`.

---

## 3. Engineering Team Structure `[Confirmed]` (Source: §6)

The project engineering team comprises six members distributed across four core technical domains:

| Domain | Allocation | Primary Engineering Focus in Scope |
| :--- | :--- | :--- |
| **Artificial Intelligence (AI)** | 2 Members | Plant-disease image analysis model exploration, candidate evaluation (e.g., YOLOv8), bounding box output `(Source: §5, §6)`. |
| **Mobile Development (Flutter)** | 2 Members | Flutter client architecture (Clean Architecture, BLoC/Cubit), offline sync engine, interactive map, dashboards `(Source: §5, §6)`. |
| **Backend Engineering** | 1 Member | Application APIs, authentication, data persistence, AI image pipeline coordination, IoT telemetry ingestion `(Source: §5, §6)`. |
| **Embedded Systems (IoT)** | 1 Member | ESP32 firmware development (C++ / Arduino), sensor interfacing (DHT22, capacitive soil probe), device telemetry transmission `(Source: §5, §6)`. |
