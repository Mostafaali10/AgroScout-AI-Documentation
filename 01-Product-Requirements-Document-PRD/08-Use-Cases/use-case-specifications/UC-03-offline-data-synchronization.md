# Use Case Specification: UC-03 Offline Inspection Storage & Eventual Sync

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Use Case Specifications  
> **Source Reference**: `Source File.docx` (§2, §3 F6, §5)

---

## 1. Actors
- **Primary System**: Mobile Application Synchronization Engine (Flutter / BLoC)
- **Secondary Systems**: Local Database (SQLite or Hive candidate), Central Backend Services

---

## 2. Preconditions
- The field scout captured one or more foliage photos and scouting records while mobile device was offline.
- Items are persisted in local encrypted storage with status `Pending Upload` `(Source: §3 F6)`.
- Internet connectivity (cellular data or Wi-Fi) has been restored.

---

## 3. Main Success Scenario (Nominal Flow)
1. Mobile application detects active network connectivity via operating system network listeners `(Source: §3 F6)`.
2. The synchronization background engine queries local database for records tagged with status `Pending Upload` `(Source: §3 F6)`.
3. The engine selects a queued item and transitions its visible UI state from `Pending Upload` to `Uploading` `(Source: §3 F6)`.
4. The client dispatches a multipart HTTP request transmitting the foliage photo binary, capture timestamp, and GPS coordinates `(Source: §2, §3 F11)`.
5. The Central Backend validates payload integrity and checks the unique client-generated UUID / payload hash to enforce idempotency and avoid duplicate records `(Source: §3 F6)`.
6. Central Backend returns an HTTP acknowledgment; mobile synchronization engine transitions item status to `Processing` `(Source: §3 F6)`.
7. Central Backend executes AI model inference asynchronously `(Source: §2)`.
8. Once AI vision inference finishes, Backend publishes the result to the mobile client (or client polls status) `(Source: §2)`.
9. Mobile sync engine marks the local item status as `Completed`, stores the returned disease label, confidence score, and bounding boxes, and decrements the pending sync counter on the Dashboard `(Source: §3 F1, §3 F6)`.
10. The finding appears as a new marker on the Farm Map and an entry in History & Details `(Source: §3 F2, §3 F4)`.

---

## 4. Alternative & Exception Flows
- **4a. Network Disconnection During Transmission (Partial Upload)**:
  1. Connection drops while uploading photo bytes.
  2. Mobile sync engine catches socket exception and flags record status as `Failed` with retry counter increment `(Source: §3 F6)`.
  3. Sync engine schedules automatic retry when connection stabilizes without duplicating records on backend `(Source: §3 F6)`.
- **4b. Repeated Upload Handling (Deduplication Enforcement)**:
  1. Mobile client retries an upload that previously succeeded on backend but failed on client acknowledgment.
  2. Backend identifies identical client record UUID.
  3. Backend ignores redundant insert, returns existing processing status and record ID, preventing database duplication `(Source: §3 F6)`.
