# Use Case Specification: UC-01 Field Scouting & Geotagged Photo Submission

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Use Case Specifications  
> **Source Reference**: `Source File.docx` (§2, §3 F8, §3 F11, §5)

---

## 1. Actors
- **Primary Actor**: Field Scout / Agricultural Worker
- **Supporting Systems**: Mobile Device Camera / Optical Sensor, Native Device GPS Subsystem, Central Backend

---

## 2. Preconditions
- The scout is authenticated in the AgroScout mobile application.
- Target farm and field are selected or registered in the app.
- Camera and Location permissions are enabled on the mobile device.

---

## 3. Main Success Scenario (Nominal Flow)
1. Scout navigates to the active field and opens the Scouting Mission or Camera Submission module `(Source: §3 F8, §3 F11)`.
2. Scout points camera at a suspected plant or foliage showing abnormal discoloration/lesions and triggers image capture `(Source: §3 F11)`.
3. The mobile application retrieves native GPS coordinates (latitude, longitude) and local capture timestamp `(Source: §3 F11)`.
4. The application associates the photo with metadata (farm ID, field ID, timestamp, GPS) `(Source: §2, §3 F11)`.
5. If cellular/Wi-Fi network is available, the mobile application transmits the inspection payload to the Central Backend `(Source: §2)`.
6. The Backend acknowledges reception, sets inspection status to `Processing`, and triggers the AI analysis pipeline `(Source: §2, §3 F6)`.
7. Scout marks the corresponding mission checklist task as completed `(Source: §3 F8)`.

---

## 4. Alternative & Exception Flows
- **4a. No Cellular Connectivity (Offline Environment)**:
  1. System detects lack of internet connection.
  2. Mobile application persists photo and coordinate metadata to local device storage `(Source: §3 F6)`.
  3. Item is assigned status `Pending Upload` and pending sync indicator increments on Dashboard `(Source: §3 F1, §3 F6)`.
  4. Use case completes locally; synchronization is deferred until connection is restored (see `UC-03`).
- **4b. Missing GPS Coordinates**:
  1. Device fails to acquire GPS fix (e.g. dense canopy or disabled hardware).
  2. System prompts scout to associate the photo with a registered farm field zone manually `(Source: §3 F2, §3 F11)`.
  3. Payload is packaged with zone identifier and submitted.
