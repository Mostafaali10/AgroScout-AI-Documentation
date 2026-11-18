# FR-06: Offline Mode & Synchronization Specification

> **Status**: Draft – Derived from Source File  
> **Module**: Functional Requirements / Offline Synchronization  
> **Source Reference**: `Source File.docx` (§2, §3 F6, §5)

---

## 1. Module Objective `[Confirmed]` (Source: §3 F6)

Preserves uninterrupted scouting capabilities in remote rural environments lacking cellular network connectivity by persisting inspection data locally and managing a resilient, idempotent multi-stage synchronization pipeline upon reconnection.

---

## 2. Detailed Functional Requirements `[Confirmed]` (Source: §3 F6)

### FR-SYNC-01: Local Data & Image Persistence `[Confirmed]` (Source: §3 F6)
- **Requirement Statement**: When network connectivity is unavailable, the mobile application shall persist captured foliage images, inspection logs, and associated metadata (GPS coordinates, capture timestamps, farm/field IDs) safely in local device storage (SQLite or Hive candidate).
- **Rationale**: Prevents data loss during field scouting rounds in disconnected rural zones.
- **Verification**: Enable airplane mode on mobile device, execute photo captures and scouting notes, and verify that all records are written to local storage.

### FR-SYNC-02: Automated Connection Detection & Ingestion `[Confirmed]` (Source: §3 F6)
- **Requirement Statement**: The mobile application shall actively monitor network interface state and automatically initiate the upload of queued pending inspection records upon the restoration of internet connectivity.
- **Rationale**: Eliminates manual intervention, ensuring field data reaches the central backend as soon as connectivity resumes.
- **Verification**: Restore network connection after offline captures and verify that the sync queue transitions automatically to uploading.

### FR-SYNC-03: Five-Stage Synchronization Lifecycle `[Confirmed]` (Source: §3 F6)
- **Requirement Statement**: The synchronization engine shall manage and display each queued inspection item through five explicit lifecycle states:
  1. `Pending Upload`: Item is saved locally, awaiting network availability or active queue dispatch.
  2. `Uploading`: Image and metadata payload are currently transmitting over the network.
  3. `Processing`: Payload has been received by the Backend and is currently undergoing AI image analysis.
  4. `Completed`: AI analysis has finished, diagnostic findings are stored on the Backend, and results are mirrored on the client.
  5. `Failed`: Transmission or backend processing encountered an error requiring retry.
- **Rationale**: Clear status indicators eliminate ambiguity, allowing users to track the exact progress of each submitted inspection.
- **Verification**: State transition testing validating that every item transitions sequentially through these five discrete states.

### FR-SYNC-04: Idempotent Retries & Deduplication `[Confirmed]` (Source: §3 F6)
- **Requirement Statement**: The system shall support retry handling for failed transfers while enforcing strict deduplication rules to prevent duplicate inspection records when network interruptions cause repeated upload attempts.
- **Rationale**: Unstable mobile connections often lead to retries; deduplication guarantees database integrity and reporting accuracy.
- **Verification**: Simulate dropped network connections midway through transmission; verify successful retry and assert that only one unique record exists on the backend.

### FR-SYNC-05: Backend Inference Dependency Rule `[Confirmed]` (Source: §2, §3 F6, §5)
- **Requirement Statement**: The application shall explicitly reflect the architectural constraint: *A new backend disease result is not available for an offline image until that image is successfully uploaded to the Backend and processed*. The UI shall display a clear pending state rather than showing a placeholder or ungrounded local diagnosis.
- **Rationale**: Ensures farmers understand that definitive AI analysis occurs centrally on the Backend, preventing reliance on nonexistent offline local models.
- **Verification**: Inspect an offline item in the UI and confirm that the disease diagnosis field displays "Awaiting Backend Upload/Processing" until the item enters the `Completed` state.
