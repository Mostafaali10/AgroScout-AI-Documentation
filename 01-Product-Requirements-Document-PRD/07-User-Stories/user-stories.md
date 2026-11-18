# User Stories Catalog

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Agile Artifacts  
> **Source Reference**: `Source File.docx` (§3, §4 F19)

---

## 1. User Story Mapping Overview

All user stories are derived directly from the twelve core features and explicit functional bullet points defined in Section 3 of `Source File.docx`, structured using standard Agile format:
`As a [Role], I want to [Capability], So that [Agronomic / Operational Benefit].`

---

## 2. Epics & User Stories

### Epic 1: Dashboard & Operational Overview (`FEAT-01`)
- **US-01.1 (Farm Summary & Alerts)**: As a Farmer, I want to see my farm information, recent disease detections, alerts, and latest sensor readings on the dashboard, so that I have an immediate snapshot of field conditions `(Source: §3 F1)`.
- **US-01.2 (Navigation Shortcuts)**: As a Field Worker, I want quick shortcuts to the map, monitoring, missions, history, analytics, and reports, so that I can navigate to active work with one tap `(Source: §3 F1)`.
- **US-01.3 (Pending Sync Counter)**: As a Field Scout, I want to see an indicator showing how many records are pending synchronization, so that I know whether my offline field records have reached the server `(Source: §3 F1)`.
- **US-01.4 (Weather Context)**: As a Farmer, I want to view weather information on the dashboard when a data feed is connected, so that I can anticipate weather-induced crop risks `(Source: §3 F1)`.

---

### Epic 2: Geospatial Farm Map (`FEAT-02`)
- **US-02.1 (Boundary Visualization)**: As a Farm Manager, I want to view all mapped farms and registered fields on an interactive map, so that I can visualize spatial boundaries clearly `(Source: §3 F2)`.
- **US-02.2 (Geotagged Disease Pins)**: As an Agronomist, I want disease detections to appear as markers on the map when valid GPS or zones are available, so that I know exactly where infections are occurring `(Source: §3 F2)`.
- **US-02.3 (Marker Detail Inspection)**: As a Farmer, I want to tap a map marker to view the foliage photo, disease label, timestamp, and confidence score, so that I can inspect the visual evidence behind the alert `(Source: §3 F2)`.
- **US-02.4 (Spatial Navigation)**: As a Field Scout, I want to pan and navigate between farms, fields, and affected areas, so that I can plan my inspection walking route `(Source: §3 F2)`.

---

### Epic 3: Live Monitoring & Sensors (`FEAT-03`)
- **US-03.1 (Telemetry Dashboard)**: As a Farmer, I want to view current temperature, air humidity, and soil moisture readings along with device operational status, so that I can detect adverse environmental spikes `(Source: §3 F3)`.
- **US-03.2 (Visual Feed Viewing)**: As a Farm Manager, I want to view incoming camera imagery or video feeds from the field, so that I can visually verify crop canopy conditions remotely `(Source: §3 F3)`.
- **US-03.3 (Live Diagnosis Display)**: As an Agronomist, I want to see backend-generated disease results and open full detection details from the monitoring view, so that I can review incoming diagnoses immediately `(Source: §3 F3)`.
- **US-03.4 (Adaptive Update Cadence)**: As an Embedded Engineer, I want the client telemetry interface to handle real-time, near-real-time, or periodic updates according to communication design, so that device power is preserved `(Source: §3 F3)`.

---

### Epic 4: History & Agronomic Auditing (`FEAT-04`)
- **US-04.1 (Historical Log Review)**: As an Agronomist, I want to review past inspection records showing disease name, photo, date/time, GPS coordinates, confidence score, and concurrent sensor readings, so that I have a complete diagnostic audit trail `(Source: §3 F4)`.
- **US-04.2 (Multi-Filter Auditing)**: As a Farm Manager, I want to filter historical records by farm, field, date range, and disease type, so that I can evaluate specific seasonal pathogen outbreaks `(Source: §3 F4)`.
- **US-04.3 (Map Re-Localization)**: As a Field Scout, I want to open any historical finding's location on the farm map, so that I can walk back to the exact physical spot for re-inspection `(Source: §3 F4)`.

---

### Epic 5: Settings & Preferences (`FEAT-05`)
- **US-05.1 (Profile Administration)**: As a User, I want to view and update my profile information and account settings, so that my contact details remain accurate `(Source: §3 F5)`.
- **US-05.2 (Preference Configuration)**: As a Farmer, I want to manage my application and alert notification preferences, so that I receive alerts relevant to my schedule `(Source: §3 F5)`.
- **US-05.3 (Sync Diagnostic & Logout)**: As a Field Worker, I want to check my connectivity/sync status and be able to log out securely, so that I know my device is operating safely `(Source: §3 F5)`.

---

### Epic 6: Offline Mode & Synchronization (`FEAT-06`)
- **US-06.1 (Local Offline Caching)**: As a Field Scout, I want to capture photos and inspection records without internet connectivity, so that I can continue scouting in remote rural fields without interruption `(Source: §3 F6)`.
- **US-06.2 (Automated Upload on Reconnection)**: As a Field Scout, I want the application to automatically upload pending records when internet returns, so that I do not need to manually trigger sync `(Source: §3 F6)`.
- **US-06.3 (Five-State Sync Tracking)**: As a User, I want to see clear item statuses (`Pending Upload`, `Uploading`, `Processing`, `Completed`, `Failed`), so that I know the exact state of my submissions `(Source: §3 F6)`.
- **US-06.4 (Deduplication on Retry)**: As a Backend Engineer, I want the system to handle retries cleanly without creating duplicate records, so that data integrity is maintained `(Source: §3 F6)`.
- **US-06.5 (Inference Dependency Awareness)**: As a Farmer, I want the app to inform me that backend diagnosis requires upload and processing, so that I understand why an offline image has no immediate AI result `(Source: §3 F6)`.

---

### Epic 7: Farm Analytics (`FEAT-07`)
- **US-07.1 (Daily & Weekly Trend Comparison)**: As a Farmer, I want to compare disease detection counts by day and week, so that I can evaluate whether infections are spreading or receding `(Source: §3 F7)`.
- **US-07.2 (Frequent Pathogen Identification)**: As an Agronomist, I want to see the most frequently detected diseases and recurring problem areas, so that I can recommend preventative measures `(Source: §3 F7)`.
- **US-07.3 (Visual Chart Summaries)**: As a Farm Manager, I want to view analytical trends via visual charts and spatial map summaries filtered by farm or field, so that I can present findings to stakeholders `(Source: §3 F7)`.

---

### Epic 8: Scouting Missions (`FEAT-08`)
- **US-08.1 (Mission Area Scoping)**: As a Farm Manager, I want to select a target farm, field, inspection area, or coordinate location when creating a mission, so that scouts know where to go `(Source: §3 F8)`.
- **US-08.2 (Checklist Assignment)**: As a Field Scout, I want to view a clear checklist of required inspection tasks for my assigned mission, so that I do not miss any critical field steps `(Source: §3 F8)`.
- **US-08.3 (Three-State Lifecycle Tracking)**: As a Farm Manager, I want to track mission statuses across `Pending`, `In Progress`, and `Completed`, so that I know the progress of daily field scouting `(Source: §3 F8)`.
- **US-08.4 (Initial Autopilot Boundary)**: As a Product Owner, I want mission definitions to focus on human inspection routes without autonomous drone flight control, keeping initial delivery focused and safe `(Source: §3 F8, §7)`.

---

### Epic 9: Export Reports (`FEAT-09`)
- **US-09.1 (Comprehensive PDF Export)**: As an Agronomist, I want to export shareable PDF reports containing foliage photos, disease names, timestamps, and GPS coordinates, so that I can document field diagnoses formally `(Source: §3 F9)`.
- **US-09.2 (Telemetry Exhibit Inclusion)**: As a Farmer, I want the PDF report to include relevant sensor readings when available, so that agricultural advisors understand the environmental context `(Source: §3 F9)`.
- **US-09.3 (Save & Share Integration)**: As a Farm Manager, I want to save reports to my phone or share them via messaging and email for a selected farm or field, so that my team receives fast updates `(Source: §3 F9)`.

---

### Epic 10: Multiple Farms & Fields (`FEAT-10`)
- **US-10.1 (Multi-Farm & Field Hierarchy)**: As an Owner, I want to associate multiple farms with my account and create fields under each farm, so that I can manage my entire agricultural enterprise in one platform `(Source: §3 F10)`.
- **US-10.2 (Strict Relational Association)**: As a Farm Manager, I want sensors, detections, missions, and history to remain bound to their correct farm and field, so that data never gets mixed up `(Source: §3 F10)`.
- **US-10.3 (Instant Active Farm Switching)**: As a Farmer, I want to switch my active farm easily and review each farm independently, so that I can manage separate locations with zero confusion `(Source: §3 F10)`.

---

### Epic 11: Camera Image & Location Submission (`FEAT-11`)
- **US-11.1 (Crop Problem Photo Capture)**: As a Field Scout, I want to capture or import an image of a plant exhibiting disease symptoms, so that the system can analyze it `(Source: §3 F11)`.
- **US-11.2 (Pipeline Dispatch)**: As a Mobile Developer, I want captured photos to be transmitted through the agreed camera/app/backend pipeline, so that central processing can take place `(Source: §3 F11)`.
- **US-11.3 (GPS & Time Metadata Tagging)**: As an Agronomist, I want images to have GPS coordinates and capture timestamps attached, so that findings can be plotted on the Farm Map `(Source: §3 F11)`.

---

### Epic 12: AI Agricultural Agent (`FEAT-12`)
- **US-12.1 (Conversational Disease Inquiry)**: As a Farmer, I want to ask questions about plant diseases and suspected crop problems in natural language, so that I can understand what is affecting my crops `(Source: §3 F12)`.
- **US-12.2 (Photo Interpretation Guidance)**: As a Field Scout, I want the AI assistant to help interpret submitted foliage photos where supported, so that I understand visual disease symptoms `(Source: §3 F12)`.
- **US-12.3 (Actionable Prevention & Treatment)**: As a Farmer, I want the assistant to explain symptoms, causes, and effects and suggest practical treatment and prevention steps, so that I can take corrective action `(Source: §3 F12)`.
- **US-12.4 (Contextual Follow-Up Q&A)**: As an Agronomist, I want to ask follow-up questions using past detections as context, so that I can have an ongoing dialogue about problem areas `(Source: §3 F12)`.
- **US-12.5 (Explicit Uncertainty Communication)**: As a Farmer, I want the AI assistant to communicate uncertainty clearly and frame its output as guidance rather than guaranteed diagnosis, so that I make informed, cautious chemical choices `(Source: §3 F12)`.
