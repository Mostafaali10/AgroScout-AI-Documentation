# FR-08: Scouting Missions Specification

> **Status**: Draft – Derived from Source File  
> **Module**: Functional Requirements / Scouting Missions  
> **Source Reference**: `Source File.docx` (§3 F8, §7)

---

## 1. Module Objective `[Confirmed]` (Source: §3 F8)

Organizes, schedules, assigns, and tracks structured field-inspection assignments across specific farms, parcels, or coordinate target locations.

---

## 2. Detailed Functional Requirements `[Confirmed]` (Source: §3 F8)

### FR-MSN-01: Mission Creation & Spatial Scoping `[Confirmed]` (Source: §3 F8)
- **Requirement Statement**: The system shall enable authorized users to create a scouting mission by selecting a target farm, a specific registered field, a predefined inspection sub-area, or targeted coordinate locations.
- **Rationale**: Standardizes inspection rounds and directs human scouts or camera operators to designated agricultural parcels.
- **Verification**: Create a mission selecting Farm X and Field Y; verify persistent association in mission catalog.

### FR-MSN-02: Task Checklist Definition & Presentation `[Confirmed]` (Source: §3 F8)
- **Requirement Statement**: Each scouting mission shall support the definition and display of an itemized checklist of required inspection tasks (e.g., specific trees to photograph, perimeter checks, or sensor verifications).
- **Rationale**: Ensures thorough, repeatable inspection protocols across different field workers.
- **Verification**: Add checklist items to a mission, open the mission on mobile, and verify checklist rendering and check-off interactivity.

### FR-MSN-03: Three-State Mission Lifecycle Tracking `[Confirmed]` (Source: §3 F8)
- **Requirement Statement**: The system shall track and display each mission's operational status through three defined lifecycle states:
  1. `Pending`: Mission created and assigned, awaiting field execution.
  2. `In Progress`: Scout has initiated field inspection and checklist items are actively being completed.
  3. `Completed`: All mandatory tasks or inspection sweeps are finished and submitted.
- **Rationale**: Provides farm managers with visibility into ongoing and completed field operations.
- **Verification**: State transition testing validating progression from `Pending` -> `In Progress` -> `Completed`.

### FR-MSN-04: Autopilot Flight-Path Boundary Invariant `[Confirmed]` (Source: §3 F8, §7)
- **Requirement Statement**: The mission management interface shall strictly adhere to the baseline scope boundary: *Direct drone flight-path control or autonomous navigation is not confirmed for the initial scope*. Missions coordinate human tasks and camera inspection areas, but do not transmit automated MAVLink / autopilot commands to drone hardware.
- **Rationale**: Prevents unverified robotics scope creep and maintains safety in initial platform releases.
- **Verification**: Inspect mission configuration UI and confirm absence of autonomous robotic flight control mechanisms.
