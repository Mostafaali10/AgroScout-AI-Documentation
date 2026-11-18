# 01. Users & Project Stakeholders

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Users & Roles  
> **Source Reference**: `Source File.docx` (§1, §3, §4 F19, §6)

---

## 1. System Stakeholder Landscape `[Confirmed]` (Source: §1, §6)

The AgroScout AI platform serves distinct agricultural personas and internal development stakeholders:

```
+-----------------------------------------------------------------------------------+
|                        AGROSCOUT AI STAKEHOLDER ECOSYSTEM                         |
+------------------------------------+----------------------------------------------+
| Agricultural Field Operators       | Engineering & Implementation Team            |
| * Smallholder & Commercial Farmers | * AI Engineers (2 Members)                   |
| * Farm Managers & Supervisors      | * Flutter Mobile Developers (2 Members)      |
| * Field Workers / Mobile Scouts    | * Backend Engineer (1 Member)                |
| * Agronomists & Pathology Reviewers| * Embedded Systems Engineer (1 Member)       |
+------------------------------------+----------------------------------------------+
```

---

## 2. Core User Personas & Responsibilities `[Confirmed / Proposed]` (Source: §1, §3, §4 F19)

### A. The Farmer (Farm Owner) `[Confirmed]` (Source: §1, §3 F1-F12)
- **Context**: Owns or leases one or more agricultural properties. Needs an overview of crop health without having to walk every meter of farmland every day.
- **Key Responsibilities & Needs**:
  - Review high-level farm health, weather conditions, and critical alerts on the Dashboard `(Source: §3 F1)`.
  - Switch between registered farms and fields to assess status independently `(Source: §3 F10)`.
  - Receive actionable early warnings of disease presence to avoid blanket pesticide costs `(Source: §1)`.
  - Consult the AI Agricultural Advisor for treatment guidelines `(Source: §3 F12)`.

### B. Farm Manager / Supervisor `[Proposed]` (Source: §4 F19)
- **Context**: Oversees daily farm operations, field work distribution, and resource allocation.
- **Key Responsibilities & Needs**:
  - Configure farms, register parcels/fields, and view ground-node sensor health `(Source: §3 F10, §4 F10)`.
  - Create and schedule Scouting Missions with specific task checklists `(Source: §3 F8)`.
  - Review disease analytics, problem heatmaps, and export formal PDF reports `(Source: §3 F7, §3 F9, §4 F5)`.

### C. Field Scout / Agricultural Worker `[Proposed]` (Source: §4 F19)
- **Context**: Operates directly on-field, frequently working in remote areas with intermittent or zero cellular connectivity.
- **Key Responsibilities & Needs**:
  - Execute assigned scouting missions and tick off task checklists `(Source: §3 F8)`.
  - Capture crop imagery with mobile or field cameras, automatically geotagging locations via GPS `(Source: §3 F11)`.
  - Rely on resilient offline caching to store captured photos and telemetry safely until network restoration `(Source: §3 F6)`.

### D. Agronomist / Plant Pathology Expert `[Proposed]` (Source: §4 F4, §4 F19)
- **Context**: Certified agricultural specialist or external consultant responsible for crop pathology validation.
- **Key Responsibilities & Needs**:
  - Review AI-generated disease diagnoses, examining captured photos, bounding boxes, and confidence levels `(Source: §4 F4)`.
  - Confirm or correct AI diagnoses while preserving the original model prediction audit trail `(Source: §4 F4)`.
  - Correlate visual foliar symptoms with microclimate sensor telemetry (temperature, humidity, soil moisture) `(Source: §2, §4 F2)`.

---

## 3. Engineering Team Stakeholders `[Confirmed]` (Source: §6)

- **AI Engineering Team (2 Members)**: Responsible for model evaluation, pathogen classification accuracy, bounding-box localization, and agricultural agent RAG/prompt interfaces `(Source: §5, §6)`.
- **Flutter Engineering Team (2 Members)**: Responsible for cross-platform UI, Clean Architecture adherence, BLoC state management, local database persistence, and offline queue synchronization `(Source: §5, §6)`.
- **Backend Engineer (1 Member)**: Responsible for ingestion APIs, database schema design, image storage pipelines, authentication, and coordinating AI model execution `(Source: §5, §6)`.
- **Embedded Systems Engineer (1 Member)**: Responsible for ESP32 firmware (C++/Arduino), sensor calibration, power management, and telemetry dispatch `(Source: §5, §6)`.
