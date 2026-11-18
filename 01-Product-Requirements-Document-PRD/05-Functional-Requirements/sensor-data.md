# Cross-Cutting Capability: IoT Sensor Telemetry Pipeline

> **Status**: Draft – Derived from Source File  
> **Module**: Functional Requirements / Core Capabilities (IoT Telemetry)  
> **Source Reference**: `Source File.docx` (§1, §2, §3 F3, §5, §7)

---

## 1. Capability Overview `[Confirmed]` (Source: §1, §2)

The IoT sensor telemetry capability governs the collection, transmission, persistence, and presentation of environmental microclimate and soil moisture data acquired from on-field ground nodes. It serves as a shared infrastructure layer powering the Dashboard `(§3 F1)`, Live Monitoring `(§3 F3)`, History Logs `(§3 F4)`, PDF Export Reports `(§3 F9)`, and multi-modal risk analysis `(§2, §4 F2)`.

---

## 2. Telemetry Architecture & Hardware Hierarchy `[Confirmed / Proposed]` (Source: §5)

```
+-----------------------------------------------------------------------------------+
|                            ESP32 GROUND NODE ARCHITECTURE                         |
+-----------------------------------------------------------------------------------+
| [ ESP32 Microcontroller ] (Core Proposed Component / Firmware: C++ Arduino)      |
|                                                                                   |
|  ├── [ DHT22 Sensor ] ------------------> Ambient Temperature & Relative Humidity |
|  │                                        (Core Proposed Sensor)                  |
|  ├── [ Capacitive Soil Moisture Probe ] -> Volumetric Soil Moisture Level         |
|  │                                        (Core Proposed Sensor)                  |
|  ├── [ Battery Voltage Monitor ] -------> Power Depletion Telemetry (Optional)    |
|  ├── [ Leaf Wetness Sensor ] -----------> Leaf Surface Moisture Film (Optional)   |
|  └── [ DS18B20 Waterproof Probe ] ------> Deep Soil / Liquid Temperature (Optional)|
+-----------------------------------------------------------------------------------+
                                   │
                                   ▼ [ Communication Candidate: HTTP or MQTT ]
+-----------------------------------------------------------------------------------+
|                              CENTRAL BACKEND SERVICES                             |
| Ingestion API -> Telemetry Normalization -> Database Storage -> Multi-Screen Push  |
+-----------------------------------------------------------------------------------+
```

---

## 3. Detailed Capability Requirements `[Confirmed / TBD]` (Source: §1, §3 F3, §5, §7)

### CAP-IOT-01: Core Environmental Telemetry Ingestion `[Confirmed]` (Source: §1, §5)
- **Requirement Statement**: The telemetry pipeline shall continuously or periodically ingest readings from the core ground-node sensors:
  1. *Ambient Air Temperature* (via DHT22).
  2. *Relative Air Humidity* (via DHT22).
  3. *Volumetric Soil Moisture* (via Capacitive Soil Moisture Sensor).
- **Rationale**: Temperature, air humidity, and soil moisture constitute the primary physical variables governing foliar fungal and bacterial spore germination.
- **Verification**: Transmit simulated ESP32 payload containing temperature, humidity, and moisture values; verify proper storage and retrieval via backend API.

### CAP-IOT-02: Optional Sensor Ingestion Support `[Proposed]` (Source: §5)
- **Requirement Statement**: The ingestion pipeline and database schema shall support optional telemetry attributes when equipped on specific ground nodes:
  - *Battery Voltage*: Telemetry reporting battery charge to indicate low-power warning states.
  - *Leaf Wetness*: Specialized sensor data recording liquid water film duration on foliage.
  - *Submersible Soil Temperature*: High-precision waterproof probe temperature readings (via DS18B20).
- **Rationale**: Extends telemetry fidelity for advanced microclimate monitoring without breaking base nodes.
- **Verification**: Ingest payload with optional battery voltage, leaf wetness, and DS18B20 fields; confirm successful database ingestion.

### CAP-IOT-03: Embedded Firmware Implementation `[Confirmed Candidate]` (Source: §5)
- **Requirement Statement**: The firmware for the ESP32 ground-node microcontrollers shall be implemented in C++ utilizing the Arduino framework, interfacing with digital and analog GPIO sensor pins.
- **Rationale**: C++ / Arduino on ESP32 offers mature sensor driver libraries, low power sleep modes, and rapid prototyping.
- **Verification**: Firmware compilation and physical serial monitoring verifying clean sensor readouts.

### CAP-IOT-04: Multi-Screen Telemetry Distribution `[Confirmed]` (Source: §3)
- **Requirement Statement**: Ingested sensor telemetry shall be indexed by farm and field, feeding:
  - **Dashboard**: Showing latest microclimate parameters `(Source: §3 F1)`.
  - **Live Monitoring**: Displaying real-time sensor metrics and device statuses `(Source: §3 F3)`.
  - **History & Details**: Linking environmental conditions to historical disease detections `(Source: §3 F4)`.
  - **Export Reports**: Incorporating concurrent sensor telemetry in PDF exhibits `(Source: §3 F9)`.
- **Rationale**: Ensures farmers and agronomists have environmental context alongside visual disease evidence.
- **Verification**: Verify that telemetry ingested from Node A updates Dashboard, Live Monitoring, and History views for the parent field.

### CAP-IOT-05: Protocol Selection & Transmission Cadence `[TBD]` (Source: §3 F3, §5, §7)
- **Requirement Statement**: The transmission protocol connecting ground nodes to the Backend (HTTP REST vs MQTT publish/subscribe) and the reporting frequency (real-time streaming, near-real-time intervals, or periodic battery-efficient wakeups) remain architectural open decisions subject to power budget and hardware testing.
- **Rationale**: Preserves architectural flexibility to match network constraints and power availability in remote fields.
- **Verification**: Benchmark HTTP vs MQTT battery consumption and latency on physical ESP32 test nodes.
