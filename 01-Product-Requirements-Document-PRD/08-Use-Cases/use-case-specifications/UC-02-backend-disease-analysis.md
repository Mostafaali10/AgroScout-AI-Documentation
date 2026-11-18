# Use Case Specification: UC-02 Backend AI Disease Analysis & Spatial Mapping

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Use Case Specifications  
> **Source Reference**: `Source File.docx` (§2, §3 F2, §3 F3, §3 F4, §5)

---

## 1. Actors
- **Primary System**: Central Backend Services
- **Secondary Systems**: AI Vision Engine (YOLOv8 candidate), Flutter Mobile Application, Relational/Object Database

---

## 2. Preconditions
- A foliage image and associated spatial/temporal metadata have been successfully ingested by the Backend `(Source: §2)`.
- The AI vision service is operational and reachable by the Backend.

---

## 3. Main Success Scenario (Nominal Flow)
1. Central Backend receives image payload, GPS coordinates, timestamp, and farm/field identifiers `(Source: §2, §3 F11)`.
2. Backend assigns a unique record identifier, persists the image binary to storage, and writes an initial inspection entry in the database `(Source: §2)`.
3. Backend dispatches an inference request to the AI Vision Engine `(Source: §2)`.
4. AI Vision Engine analyzes visual patterns, identifies the foliar pathogen class, computes a confidence score, and determines bounding box coordinates for localized leaf lesions `(Source: §1, §5)`.
5. AI Vision Engine returns diagnostic payload to the Backend `(Source: §2)`.
6. Backend queries recent telemetry from ground nodes (temperature, air humidity, soil moisture) associated with the target field to provide environmental context `(Source: §2, §3 F4)`.
7. Backend updates inspection record with pathogen name, confidence score, bounding boxes, and associated sensor readings, transitioning status to `Completed` `(Source: §3 F4, §3 F6)`.
8. Flutter mobile application receives updated data and renders:
   - A high-priority alert on the **Dashboard** `(Source: §3 F1)`.
   - An interactive pin at the exact GPS coordinates on the **Farm Map** `(Source: §3 F2)`.
   - A diagnostic entry in the **Live Monitoring** feed `(Source: §3 F3)`.
   - An archived entry in the searchable **History & Details** catalog `(Source: §3 F4)`.

---

## 4. Alternative & Exception Flows
- **4a. AI Vision Model Fails or Times Out**:
  1. AI inference engine returns an error or exceeds response timeout threshold.
  2. Backend flags the inspection record status as `Failed` with diagnostic error code `(Source: §3 F6)`.
  3. Mobile client displays failure state in sync queue and offers manual or scheduled retry.
- **4b. Multi-Modal Interpretation Triggered `[Proposed]`**:
  1. If agreed sensor-fusion rules are active, the backend correlates high air humidity (>90%) with fungal pathogen detection `(Source: §2, §4 F2)`.
  2. Backend attaches an elevated risk advisory flag to the record for agronomist review `(Source: §4 F4)`.
