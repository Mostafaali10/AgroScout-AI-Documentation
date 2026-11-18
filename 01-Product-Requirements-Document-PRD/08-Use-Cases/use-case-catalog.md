# Use Case Catalog

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Use Cases  
> **Source Reference**: `Source File.docx` (§2, §3)

---

## 1. System Use Case Inventory `[Confirmed]` (Source: §2, §3)

The catalog indexes end-to-end operational use cases derived from the high-level system flow (§2) and the twelve core product features (§3).

| Use Case ID | Use Case Name | Primary Actor | Secondary Actors | Functional Scope |
| :--- | :--- | :--- | :--- | :--- |
| **UC-01** | Field Scouting & Geotagged Photo Submission | Field Scout / Worker | Mobile App, GPS Subsystem | `FEAT-08, FEAT-11` |
| **UC-02** | Backend AI Disease Analysis & Map Pinning | Central Backend | AI Vision Engine, Mobile App | `FEAT-02, FEAT-03, FEAT-04` |
| **UC-03** | Offline Inspection Storage & Eventual Sync | Mobile App (System) | Field Scout, Central Backend | `FEAT-06` |
| **UC-04** | AI Agricultural Agent Advisory Consultation | Farmer / Agronomist | AI Agricultural Agent, Backend | `FEAT-12` |
| **UC-05** | Exporting Shareable PDF Agronomic Report | Farm Manager | Reporting Engine, Mobile OS Share | `FEAT-09` |

---

## 2. Cross-Reference Index

Detailed step-by-step nominal flows, preconditions, and exception handling for core use cases are specified in the `use-case-specifications/` directory:
- [UC-01: Field Scouting & Geotagged Photo Submission](use-case-specifications/UC-01-field-scouting-and-image-submission.md)
- [UC-02: Backend AI Disease Analysis & Spatial Mapping](use-case-specifications/UC-02-backend-disease-analysis.md)
- [UC-03: Offline Inspection Storage & Eventual Sync](use-case-specifications/UC-03-offline-data-synchronization.md)
- [UC-04: AI Agricultural Agent Advisory Consultation](use-case-specifications/UC-04-ai-agent-consultation.md)
