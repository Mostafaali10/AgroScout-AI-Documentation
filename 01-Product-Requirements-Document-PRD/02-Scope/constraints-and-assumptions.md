# 02. Architectural Constraints, Hardware & Software Candidates

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Scope Definition  
> **Source Reference**: `Source File.docx` (§5)

---

## 1. Hardware & Component Candidates `[Confirmed / Proposed]` (Source: §5)

### A. Ground Nodes & Physical Sensors
The field telemetry layer is implemented via modular ground nodes with the following component statuses:

| Component | Engineering Purpose | Architectural Status in Source |
| :--- | :--- | :--- |
| **ESP32 Microcontroller** | Reads analog/digital sensor values and communicates ground-node data to backend `(Source: §5)`. | **Core Proposed Component** `[Confirmed]` |
| **DHT22** | Digital sensor measuring ambient air temperature and relative humidity `(Source: §5)`. | **Core Proposed Sensor** `[Confirmed]` |
| **Capacitive Soil Moisture Sensor** | Probe measuring volumetric soil moisture level resistantly to corrosion `(Source: §5)`. | **Core Proposed Sensor** `[Confirmed]` |
| **Battery Voltage Monitor** | Hardware circuit reporting ground-node battery voltage to detect power depletion `(Source: §5)`. | **Optional** `[Proposed]` |
| **Leaf Wetness Sensor** | Specialized resistive/capacitive grid detecting moisture film on foliage `(Source: §5)`. | **Optional** `[Proposed]` |
| **DS18B20 Waterproof Probe** | Submersible temperature probe for specialized deep-soil or liquid thermal sensing `(Source: §5)`. | **Optional** `[Proposed]` |

### B. Optical & Camera Options Under Consideration `[TBD]` (Source: §5)
Camera selection is explicitly **not finalized**. Three distinct options are under active architectural evaluation:

```
+--------------------------------------------------------------------------------------------------+
|                                CAMERA SELECTION TRADE-OFF MATRIX                                 |
+--------------------------+------------------------------------+----------------------------------+
| Option 1: ESP32-CAM      | Option 2: Smartphone Camera        | Option 3: RPi Zero 2 W + Cam v3  |
+--------------------------+------------------------------------+----------------------------------+
| * Low-cost testing tool. | * Superior native image quality.   | * Closest to drone camera.       |
| * Limited resolution.    | * Native on-board GPS receiver.    | * Autofocus & lower latency.     |
| * Requires close range.  | * Validates early field workflow.  | * Team estimate: ~8,000 EGP.     |
| * Needs external GPS.    | * Does not simulate drone camera.  | * Subject to budget & power.     |
+--------------------------+------------------------------------+----------------------------------+
```

1. **Option 1 — ESP32-CAM**: Low-cost module for initial verification of the end-to-end image pipeline (`camera → image/stream transfer → app/system → AI → bounding box`). Constrained by poor high-light exposure, low resolution, and transmission latency; requires a separate GPS module if coordinates must originate from the camera `(Source: §5)`.
2. **Option 2 — Mobile Phone Camera**: Utilizes the mobile device camera and native smartphone GPS. Delivers high resolution without additional hardware; effective for initial manual scouting, though it does not simulate aerial drone capture `(Source: §5)`.
3. **Option 3 — Raspberry Pi Zero 2 W + Camera Module 3**: Higher-grade edge computer providing autofocus, superior optics, and reduced streaming latency. Considered the closest simulation of an aerial drone payload. Initial team cost estimate: approximately **8,000 EGP** (requires budget and power verification before purchase) `(Source: §5)`.

---

## 2. Software Architecture & Technology Candidates `[Confirmed / TBD]` (Source: §5)

The software stack combines affirmed design patterns with open technology candidates:

| Domain | Architecture / Component | Decision Status | Source Reference |
| :--- | :--- | :--- | :--- |
| **Mobile Client** | **Flutter Framework** | **Confirmed** | `§5` |
| **Mobile Architecture** | **Clean Architecture** (Domain, Data, Presentation) | **Confirmed** | `§5` |
| **Mobile State Mgmt** | **BLoC / Cubit Pattern** | **Confirmed** | `§5` |
| **Inference Location** | **Backend-Based Processing** (Centralized AI) | **Confirmed** | `§2, §5` |
| **Embedded Firmware** | **C++ / Arduino Framework** for ESP32 nodes | **Confirmed Candidate** | `§5` |
| **AI Vision Model** | **YOLOv8** (Object localization / bounding boxes) | **Candidate Under Study** `[TBD]` | `§5` |
| **Backend Framework** | Application APIs, auth, storage, data coordination | **Not Finalized** `[TBD]` | `§5` |
| **IoT Protocol** | **HTTP vs MQTT** for ground-node sensor telemetry | **Candidate Under Study** `[TBD]` | `§5` |
| **Map Rendering** | **Google Maps vs Mapbox** (`google_maps_flutter` / `flutter_map`) | **Candidate Under Study** `[TBD]` | `§5` |
| **Local Storage** | **SQLite vs Hive** for offline mobile cache | **Candidate Under Study** `[TBD]` | `§5` |
| **Firebase Cloud** | Authentication / push / storage responsibilities | **Requires Confirmation** `[TBD]` | `§5` |
