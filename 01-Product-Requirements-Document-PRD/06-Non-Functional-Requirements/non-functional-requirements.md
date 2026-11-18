# Non-Functional Requirements (NFR) — Quality Attributes & Constraints

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Non-Functional Requirements  
> **Source Reference**: `Source File.docx` (§2, §3, §4, §5)

---

## 1. Quality Attributes & Architectural Governance

In strict accordance with the baseline project source file, non-functional requirements are grounded in verified technical constraints, avoiding unverified performance or security metrics. Quality attributes focus on software maintainability, offline reliability, uncertainty transparency, localization, and hardware trade-offs.

---

## 2. Detailed Non-Functional Requirements

### A. Maintainability & Software Architecture `[Confirmed]` (Source: §5)

- **NFR-ARCH-01: Flutter Clean Architecture Separation `(Source: §5)`**:
  The mobile application codebase shall be structured following **Clean Architecture** principles, enforcing strict separation of concerns between Domain (Entities, Use Cases), Data (Repositories, Data Sources, Models), and Presentation (UI Widgets, ViewModels/Cubits) layers.
  - *Rationale*: Protects business logic from UI changes and third-party library churn; enables modular unit testing.
  - *Verification*: Architectural static analysis and layer dependency code review.

- **NFR-ARCH-02: BLoC / Cubit State Management Pattern `(Source: §5)`**:
  All reactive application state, asynchronous event handling, and data streams within the Flutter application shall be managed using the **BLoC (Business Logic Component) / Cubit** framework.
  - *Rationale*: Provides predictable state transitions, simplifies asynchronous stream management, and ensures high testability.
  - *Verification*: Code review confirming no business logic resides inside Flutter stateful widget trees.

- **NFR-ARCH-03: Firmware Standardization (C++ / Arduino) `(Source: §5)`**:
  Firmware for all physical ground nodes shall be written in C++ targeting the Arduino framework on ESP32 microcontrollers.
  - *Rationale*: Maximizes code reuse, provides access to mature open-source sensor libraries, and simplifies maintenance for the embedded engineer.
  - *Verification*: Continuous compilation check of firmware source using platform toolchains.

---

### B. Reliability & Offline Data Resilience `[Confirmed]` (Source: §3 F6)

- **NFR-REL-01: Offline-First Data Preservation `(Source: §3 F6)`**:
  The mobile application shall ensure zero data loss during field scouting by persistently writing all captured photos, sensor logs, and coordinate metadata to local storage (SQLite or Hive candidate) before attempting network transmission.
  - *Rationale*: Agricultural fields frequently suffer total cellular dropouts; local persistence guarantees field work is preserved.
  - *Verification*: Execute inspection capture with Wi-Fi/cellular disabled, simulate device reboot, and verify local record recovery.

- **NFR-REL-02: Idempotent Synchronization & Deduplication `(Source: §3 F6)`**:
  The synchronization engine shall ensure idempotent network uploads. Repeated uploads triggered by network timeouts, dropped connections, or retries must never create duplicate inspection records or distorted analytics on the backend.
  - *Rationale*: Mobile retries on spotty 3G/EDGE networks often cause duplicate POST requests.
  - *Verification*: Submit the identical offline inspection payload 5 times in a test suite; assert the backend database stores exactly 1 record.

- **NFR-REL-03: Transparent Lifecycle State Indication `(Source: §3 F6)`**:
  Every queued inspection record shall clearly reflect its exact status among: `Pending Upload`, `Uploading`, `Processing`, `Completed`, and `Failed`.
  - *Rationale*: Eliminates user uncertainty regarding whether an image has been processed or is still sitting in the local queue.
  - *Verification*: Inspect UI status badges as an item progresses across the synchronization lifecycle.

---

### C. Safety, Uncertainty & Trust Transparency `[Confirmed]` (Source: §3 F12, §4 F16)

- **NFR-SAFE-01: Explicit Diagnostic Uncertainty Disclosure `(Source: §3 F12)`**:
  All AI-generated disease identifications, conversational agent recommendations, and treatment suggestions shall prominently display an explicit uncertainty disclosure stating that AI output is advisory guidance and not a guaranteed agronomic diagnosis.
  - *Rationale*: Mitigates crop damage liability, protects farmers from misdiagnosis, and reinforces human expert verification.
  - *Verification*: Automated UI test asserting disclaimer visibility on diagnostic detail views and chat screens.

- **NFR-SAFE-02: Agronomic Knowledge Attribution `(Source: §4 F16)`**:
  Where supported, conversational assistant recommendations shall surface underlying agricultural knowledge references alongside a numerical or categorical confidence score.
  - *Rationale*: Builds farmer trust and enables verification against recognized agricultural extension standards.
  - *Verification*: Inspect agent responses and verify presence of source citations and confidence metrics.

---

### D. Usability, Accessibility & Localization `[Proposed]` (Source: §4 F24)

- **NFR-USE-01: Bilingual Localization (Arabic & English) `(Source: §4 F24)`**:
  The mobile application interface, menus, labels, alerts, and report templates shall provide complete bidirectional localization supporting both Arabic (RTL) and English (LTR).
  - *Rationale*: Broadens accessibility for regional farmers, field workers, and international agricultural consultants.
  - *Verification*: Toggle language switch between Arabic and English; verify 100% string translation coverage and correct RTL/LTR layout mirroring.

---

### E. Hardware Constraints & Optical Performance Trade-offs `[Confirmed / TBD]` (Source: §5)

- **NFR-PERF-01: Optical Device Operating Limits `(Source: §5)`**:
  The image capture subsystem shall operate within the verified physical limits of the selected camera candidate:
  - *ESP32-CAM*: Constrained by low resolution, close-range focal requirement, and vulnerability to high-light saturation.
  - *Mobile Phone*: Delivers high-resolution capture with integrated GPS, but requires human walking.
  - *Raspberry Pi Zero 2 W + Camera Module 3*: Provides autofocus and lower latency closer to an aerial drone camera, subject to budget (~8,000 EGP early estimate) and power requirements.
  - *Rationale*: Prevents unrealistic algorithmic expectations on low-cost optical hardware.
  - *Verification*: Image quality benchmarking under direct midday sunlight and close-canopy shade.

- **NFR-PERF-02: Multi-Cadence Telemetry Ingestion `(Source: §3 F3, §5, §7)`**:
  The ground-node telemetry ingestion pipeline shall accommodate both periodic batching (e.g., deep sleep waking every N minutes to conserve battery) and continuous real-time transmission depending on protocol selection (HTTP vs MQTT).
  - *Rationale*: Balances field node battery lifespan against monitoring latency.
  - *Verification*: Measure battery discharge rates under 1-minute, 5-minute, and 15-minute transmission cycles.
