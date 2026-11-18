# 02. Recommended & Differentiating Features (24 Proposed Capabilities)

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Product Features  
> **Source Reference**: `Source File.docx` (§4)

---

## 1. Overview & Prioritization Strategy `[Proposed]` (Source: §4)

This catalog details the 24 proposed enhancements evaluated by the project team beyond the baseline scope. Features carrying formal team prioritization tags (`[Priority: High]` or `[Priority: Medium]`) represent prime candidates for subsequent release sprints, subject to final resource and timeline confirmation.

```
+----------------------------------------------------------------------------------------------------+
|                                 FEATURE PRIORITIZATION MATRIX                                      |
+--------------------------+------------------------------------+------------------------------------+
| Priority: HIGH           | Priority: MEDIUM                   | Optional / Differentiating         |
+--------------------------+------------------------------------+------------------------------------+
| * Disease Severity (F-01)| * Multiple Disease Detect (F-03)   | * Smart Alerts (F-09)              |
| * Risk Prediction (F-02) | * Expert Agronomist Review (F-04)  | * Sensor Health (F-10)             |
| * Disease Heatmap (F-05) | * Crop Lifecycle Tracking (F-07)   | * Irrigation Recs (F-12)           |
| * Smart Task Recs (F-06) | * Weather Integration (F-08)       | * Arabic & English Support (F-24)  |
|                          |                                    | * QR Pairing, Activity Log, RBAC   |
+--------------------------+------------------------------------+------------------------------------+
```

---

## 2. AI & Computer Vision Enhancements `[Proposed]` (Source: §4)

1. **Disease Severity Assessment `[Priority: High]` (Source: §4 F1)**:
   Classify infection severity into categorical brackets (**Low / Medium / High**) and compute an estimate of the percentage of affected leaf surface area.
2. **Disease Risk Prediction `[Priority: High]` (Source: §4 F2)**:
   Analyze environmental correlations (ambient temperature, air humidity, and soil moisture) to estimate the epidemiological likelihood of fungal/bacterial spread before visible foliar symptoms appear.
3. **Multiple Disease Detection `[Priority: Medium]` (Source: §4 F3)**:
   Detect and localize more than one disease or physiological deficiency within a single foliage image, rendering distinct bounding boxes for each diagnosed pathology.
4. **Expert Review Workflow `[Priority: Medium]` (Source: §4 F4)**:
   Enable professional agronomists to review computer vision diagnoses, permitting them to confirm or correct the identification while preserving original model predictions for auditability.

---

## 3. Farm Management & Decision Support `[Proposed]` (Source: §4)

5. **Disease Heatmap Visualization `[Priority: High]` (Source: §4 F5)**:
   Generate a geospatial density heatmap depicting high-concentration infection clusters across farm acreage, moving beyond isolated point pins.
6. **Smart Task Recommendations `[Priority: High]` (Source: §4 F6)**:
   Automatically suggest targeted field actions based on inspection outcomes (e.g., prompt a re-inspection mission for a suspected outbreak zone within 48 hours).
7. **Crop Lifecycle Tracking `[Priority: Medium]` (Source: §4 F7)**:
   Log crop variety, initial planting date, and active vegetative/phenological growth stages, correlating them directly with historical scouting records.
8. **Weather Service Integration `[Priority: Medium]` (Source: §4 F8)**:
   Incorporate local meteorological forecasts directly into dashboards and link weather trends to agricultural risk alerts (e.g., prolonged high humidity).

---

## 4. Monitoring & Telemetry Intelligence `[Proposed]` (Source: §4)

9. **Smart Environmental Alerts (Source: §4 F9)**:
   Dispatch automated alerts when infection probability spikes or when sensor readings exceed safe agronomic thresholds.
10. **Sensor Health & Uptime Monitoring (Source: §4 F10)**:
    Track device operational telemetry for every deployed ESP32 node, including battery voltage, last heartbeat timestamp, and transmission health.
11. **Historical Image Comparison (Source: §4 F11)**:
    Provide side-by-side temporal visual comparison of the identical plant or field coordinate over successive scouting cycles to evaluate disease progression.
12. **Irrigation Advisory Recommendations (Source: §4 F12)**:
    Suggest optimal irrigation schedules based on real-time soil moisture and crop water requirements, *explicitly operating without automated valve or pump control for the initial scope*.

---

## 5. Conversational AI Agent Capabilities `[Proposed]` (Source: §4)

13. **Agricultural Chat Assistant (Source: §4 F13)**:
    Direct conversational interface permitting the farmer to inquire freely about plant diseases, crop care, and recent inspection results.
14. **Image-Based Q&A (Source: §4 F14)**:
    Enable users to submit foliage photos directly within the conversational interface and ask contextual diagnostic questions tied to the vision model's output.
15. **Personalized Agronomic Guidance (Source: §4 F15)**:
    Tailor assistant recommendations to the active farm context, incorporating crop species, growth stage, and current field telemetry.
16. **Knowledge Attribution & Uncertainty Transparency (Source: §4 F16)**:
    Surface the underlying agronomic knowledge sources cited by the assistant alongside a clear confidence level, ensuring diagnoses are never framed as infallible.

---

## 6. Additional Differentiating Enhancements `[Proposed]` (Source: §4)

17. **QR Code Ground-Node Pairing (Source: §4 F17)**:
    Affix unique QR codes to physical ESP32 enclosures, allowing field workers to link a sensor node to a specific parcel by scanning it in the mobile app.
18. **Farm Activity Logbook (Source: §4 F18)**:
    Maintain a chronological audit log recording farm management events such as irrigation, fertilizer application, and manual chemical treatments.
19. **Multi-User RBAC Permissions (Source: §4 F19)**:
    Implement explicit role-based permissions separating `Owner`, `Farm Manager`, `Worker`, and `Agronomist`.
20. **Detection Confidence Tracking (Source: §4 F20)**:
    Store numerical confidence scores for all model predictions and track longitudinal performance against expert-confirmed diagnoses.
21. **Field Health Score Index (Source: §4 F21)**:
    Compute a consolidated numerical health index (0–100) per field synthesizing disease prevalence, mission outcomes, and sensor telemetry.
22. **Sensor Anomaly Detection (Source: §4 F22)**:
    Implement automated heuristic or statistical anomaly detection to identify faulty hardware or erratic sensor spikes.
23. **Before & After Treatment Evaluation (Source: §4 F23)**:
    Compare photographic crop condition before and after agronomic treatment interventions to evaluate spray efficacy.
24. **Multi-Language Support (Arabic & English) (Source: §4 F24)**:
    Provide comprehensive bilingual localization across Arabic and English to maximize mobile accessibility for regional farmers.
