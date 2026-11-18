# 02. User Roles & Permission Model

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Users & Roles  
> **Source Reference**: `Source File.docx` (§3, §4 F19)

---

## 1. Role Hierarchy & Definitions `[Proposed]` (Source: §4 F19)

The project source explicitly defines four operational user roles under Feature 19:
> *"19. Multi-user & Permissions — Different roles: Owner, Farm Manager, Worker, and Agronomist."*  
> — `Source File.docx` (§4 F19)

```
+---------------------------------------------------------------------------------+
|                               ROLE HIERARCHY                                    |
|                                                                                 |
|   [ Owner ] --------> Full administrative control over all farms & accounts     |
|       |                                                                         |
|   [ Farm Manager ] -> Farm & field setup, sensor config, mission management     |
|       |                                                                         |
|   +---+---------------------------------+                                       |
|   |                                     |                                       |
| [ Agronomist ]                    [ Worker ]                                    |
| Diagnosis review, validation &    Field scouting, photo capture & checklist     |
| expert agronomic adjustments      completion                                    |
+---------------------------------------------------------------------------------+
```

---

## 2. Functional Permission Matrix `[Proposed]` (Source: §3, §4 F19)

| Functional Module | System Action | Owner | Farm Manager | Agronomist | Worker | Source Reference |
| :--- | :--- | :---: | :---: | :---: | :---: | :--- |
| **Farm Management** | Create / Delete Farms & Fields | **Yes** | **Yes** | View Only | View Only | `§3 F10` |
| | Switch Active Farm | **Yes** | **Yes** | **Yes** | **Yes** | `§3 F10` |
| **Scouting Missions** | Create Mission & Task Checklist | **Yes** | **Yes** | **Yes** | No | `§3 F8` |
| | Execute & Complete Checklist | **Yes** | **Yes** | **Yes** | **Yes** | `§3 F8` |
| **Image & Location** | Capture / Submit Photos & GPS | **Yes** | **Yes** | **Yes** | **Yes** | `§3 F11` |
| | View Offline Sync Queue Status | **Yes** | **Yes** | **Yes** | **Yes** | `§3 F6` |
| **Diagnosis & AI** | View AI Detections & Bounding Boxes | **Yes** | **Yes** | **Yes** | **Yes** | `§3 F3, §3 F4` |
| | Confirm / Correct AI Diagnosis | **Yes** | No | **Yes** | No | `§4 F4` |
| | Consult AI Agricultural Agent | **Yes** | **Yes** | **Yes** | **Yes** | `§3 F12` |
| **Sensors & Telemetry** | View Live Sensor Readings | **Yes** | **Yes** | **Yes** | **Yes** | `§3 F3` |
| | Pair Nodes via QR Code | **Yes** | **Yes** | No | No | `§4 F17` |
| **Reporting & Analytics** | Export PDF Inspection Reports | **Yes** | **Yes** | **Yes** | No | `§3 F9` |
| | Access Longitudinal Analytics | **Yes** | **Yes** | **Yes** | View Only | `§3 F7` |
| **User Administration** | Manage Roles & Permissions | **Yes** | No | No | No | `§4 F19` |
