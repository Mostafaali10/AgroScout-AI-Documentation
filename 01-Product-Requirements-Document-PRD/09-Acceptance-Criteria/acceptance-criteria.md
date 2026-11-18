# System Acceptance Criteria (AC)

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Quality Assurance Gates  
> **Source Reference**: `Source File.docx` (§3)

---

## 1. Quality Acceptance Framework

Every acceptance criterion corresponds directly to the functional bullets established in Section 3 of `Source File.docx`. Features must achieve verified **Pass** status across all criteria prior to release baseline approval.

---

## 2. Acceptance Verification Matrix

| AC ID | Target Feature | Acceptance Verification Criterion | Verification Method | Pass / Fail Condition |
| :--- | :--- | :--- | :--- | :--- |
| **AC-01.1** | Dashboard | System renders active farm name, latest disease detections, priority alerts, and recent sensor telemetry (temperature, humidity, moisture). | UI & Integration Test | **Pass**: All four data categories populate correctly from backend without null crashes. |
| **AC-01.2** | Dashboard | Tapping any of the six navigation shortcuts navigates to Map, Monitoring, Missions, History, Analytics, or Reports. | Functional UI Test | **Pass**: 100% of shortcut routes transition to the intended destination screen. |
| **AC-01.3** | Dashboard | When offline records exist locally, a visible pending sync badge displays the exact un-uploaded record count. | Offline Functional Test | **Pass**: Badge matches local database queue count and disappears when sync reaches 0. |
| **AC-01.4** | Dashboard | Weather forecast panel renders ambient conditions when connected to a valid weather data source. | Integration Test | **Pass**: Weather panel displays temperature/forecast without layout overflow. |
| **AC-02.1** | Farm Map | Interactive map renders registered farm boundaries and distinct sub-field polygons accurately. | Geospatial Verification | **Pass**: Polygons match registered GPS boundary coordinates on map canvas. |
| **AC-02.2** | Farm Map | Recorded disease detections with valid GPS plot as distinct visual markers on the map canvas. | Geospatial Verification | **Pass**: Markers render within correct field polygon boundaries. |
| **AC-02.3** | Farm Map | Tapping a disease marker opens a detail view displaying foliage photo, disease label, timestamp, and confidence score. | UI Verification | **Pass**: Modal displays photo, pathogen name, timestamp, and confidence percentage. |
| **AC-02.4** | Farm Map | Map canvas responds to zoom, pan, and bounds-fitting across multiple farms and affected parcels. | Gestural Verification | **Pass**: 60fps pan/zoom interaction without rendering artifacts or crashes. |
| **AC-03.1** | Live Monitoring | Live monitoring displays incoming temperature, humidity, soil moisture readings, and device online/offline status. | Telemetry Ingestion Test | **Pass**: Ingested sensor metrics update UI within agreed transmission cadence. |
| **AC-03.2** | Live Monitoring | Live monitoring container displays incoming optical imagery or video stream from field cameras. | Stream/Image Pipeline Test| **Pass**: Visual feed displays valid images/frames without buffer stalling. |
| **AC-03.3** | Live Monitoring | Backend-generated disease analysis results appear in monitoring view and open full diagnostic details. | End-to-End Pipeline Test | **Pass**: Inference output surfaces in monitoring feed with clickable detail access. |
| **AC-03.4** | Live Monitoring | Telemetry update frequency supports real-time streaming, near-real-time, or periodic batches per communication design. | Cadence Ingestion Test | **Pass**: Client receives and renders metrics under both continuous and batch modes. |
| **AC-04.1** | History & Details | Historical log displays disease name, photo, date/time, GPS coordinates, confidence score, and concurrent sensors. | Database Query Test | **Pass**: Complete historical record renders all required evidence fields. |
| **AC-04.2** | History & Details | Applying filters by farm, field, date range, and disease classification isolates matching records. | Data Filter Test | **Pass**: Query results contain only records satisfying 100% of selected filter parameters. |
| **AC-04.3** | History & Details | Selecting "Open on Map" from a historical finding centers the Farm Map on the finding's GPS coordinates. | Cross-Module Navigation | **Pass**: Map re-centers on coordinate pin with detail modal open. |
| **AC-05.1** | Settings & Profile | User can view and edit profile details, persisting updates across mobile and backend. | Account Management Test | **Pass**: Updated profile attributes persist across app restarts and database queries. |
| **AC-05.2** | Settings & Profile | User can toggle alert thresholds and notification preferences. | Preference Toggle Test | **Pass**: Push/local notifications trigger only when matching user preferences. |
| **AC-05.3** | Settings & Profile | Interface displays active connectivity status, sync queue health, and enables secure logout. | Session Security Test | **Pass**: Logout clears cached authentication tokens and returns to login gate. |
| **AC-06.1** | Offline Mode | App persists captured photos, sensor logs, and coordinate metadata to local storage when offline. | Airplane Mode Storage Test| **Pass**: 100% of offline captures survive app kill and device reboot in local storage. |
| **AC-06.2** | Offline Mode | Restoring network connection initiates automatic background upload of queued records to Backend. | Network State Listener | **Pass**: Upload sequence triggers within 5 seconds of network restoration. |
| **AC-06.3** | Offline Mode | Queued items transition sequentially through `Pending Upload`, `Uploading`, `Processing`, `Completed`, `Failed`. | State Machine Test | **Pass**: Every sync item logs each of the five states without illegal state skips. |
| **AC-06.4** | Offline Mode | Repeated upload attempts triggered by dropped connections do not create duplicate records on backend. | Idempotency Test | **Pass**: 5 repeated uploads of identical payload result in exactly 1 backend record. |
| **AC-06.5** | Offline Mode | UI explicitly indicates that new backend disease results require successful upload and processing. | UI Content Verification | **Pass**: Offline items show "Awaiting Upload / Processing" rather than fake results. |
| **AC-07.1** | Farm Analytics | Analytics dashboard compares pathogen detection counts by day and week. | Metric Aggregation Test | **Pass**: Daily and weekly aggregated totals match raw inspection database records. |
| **AC-07.2** | Farm Analytics | Analytics engine computes and displays most frequently detected diseases and persistent problem areas. | Ranking Algorithm Test | **Pass**: Diseases are ranked correctly by frequency; recurring problem zones highlighted. |
| **AC-07.3** | Farm Analytics | Visual trend charts and map summaries update when filtered by specific farm or individual field. | Analytics UI Test | **Pass**: Charts dynamically recalculate values matching selected spatial filter. |
| **AC-08.1** | Scouting Missions | User can create a scouting mission by selecting farm, field, inspection area, or coordinate target. | Mission Creation Test | **Pass**: Mission entity is created with correct spatial boundary association. |
| **AC-08.2** | Scouting Missions | Mission view presents assigned inspection checklist with interactive check-off controls. | Checklist UI Test | **Pass**: Check-off actions persist and reflect completion progress percentage. |
| **AC-08.3** | Scouting Missions | Mission transitions through `Pending`, `In Progress`, and `Completed` lifecycle states. | Mission Lifecycle Test | **Pass**: Mission status updates correctly upon initial start and final task completion. |
| **AC-08.4** | Scouting Missions | Mission workflow adheres to scope boundary: no autonomous drone waypoint flight commands emitted. | Architectural Guardrail | **Pass**: Zero MAVLink/autopilot execution calls verified in mission code. |
| **AC-09.1** | Export Reports | System compiles foliage photos, disease labels, capture timestamps, and GPS coordinates into a formatted PDF. | PDF Parsing Test | **Pass**: Generated PDF contains all inspection findings without corrupted text/images. |
| **AC-09.2** | Export Reports | Exported PDF includes concurrent temperature, humidity, and soil moisture telemetry where available. | Report Generation Test | **Pass**: Sensor telemetry table appears in PDF for parcels with linked ground nodes. |
| **AC-09.3** | Export Reports | User can save PDF to device storage and share via native mobile OS share sheets. | Native Integration Test | **Pass**: OS share sheet launches with valid binary PDF attachment. |
| **AC-10.1** | Multi-Farm & Field | User can create and manage multiple farms and add multiple registered fields under each farm. | Hierarchical Data Test | **Pass**: User account binds cleanly to N farms, each containing M independent fields. |
| **AC-10.2** | Multi-Farm & Field | Sensors, detections, missions, and history remain isolated within their registered farm and field. | Multi-Tenant Data Test | **Pass**: Zero cross-farm data leakage observed in queries or UI displays. |
| **AC-10.3** | Multi-Farm & Field | Switching active farm selector reloads dashboard, map, and telemetry to selected farm immediately. | UI State Context Test | **Pass**: All views refresh to target farm context within 500ms of selector change. |
| **AC-11.1** | Camera Submission | System captures foliage photo via mobile camera, field camera, or imports external drone image. | Image Capture Test | **Pass**: Photo buffer is loaded into memory without resolution degradation. |
| **AC-11.2** | Camera Submission | Image is packaged with native GPS coordinates and capture timestamp. | Metadata Extraction | **Pass**: Coordinates and ISO timestamp are verified in payload header. |
| **AC-11.3** | Camera Submission | Payload transmits through agreed communication pathway to Central Backend. | Network Transport Test | **Pass**: Backend confirms reception with HTTP 200/202 status code. |
| **AC-12.1** | AI Agent | Agent accepts natural language questions regarding crop diseases and returns agronomic explanations. | Conversational Q&A Test | **Pass**: Agent produces relevant, coherent answers to plant pathology inquiries. |
| **AC-12.2** | AI Agent | Agent assists in interpreting visual foliage patterns when image analysis capability is supported. | Multi-Modal Dialogue Test| **Pass**: Agent response references visual traits and detected disease labels. |
| **AC-12.3** | AI Agent | Agent structures guidance to include symptoms, underlying causes, potential effects, and treatments. | Response Structure Test | **Pass**: Output contains discrete sections for symptoms, causes, and treatments. |
| **AC-12.4** | AI Agent | Agent maintains multi-turn context and incorporates active farm detection history when relevant. | Context Retention Test | **Pass**: Follow-up queries correctly reference entities mentioned in previous turn. |
| **AC-12.5** | AI Agent | 100% of agent diagnostic outputs include the mandatory advisory disclaimer communicating uncertainty. | Safety Guardrail Test | **Pass**: Automated string assertion confirms disclaimer is present in every response. |
