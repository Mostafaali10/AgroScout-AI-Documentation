# Data Exchange Models

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Core JSON data structures exchanged across subsystem boundaries.

## Key Exchange Models

- **TelemetryPacket**: `{ device_id, timestamp, battery_pct, sensors: { temp_c, humidity_pct, soil_moisture_pct, npk: { n, p, k } } }`
- **DiagnosisRequest**: `{ image_base64, parcel_id, gps: { lat, lon, alt }, crop_type }`
- **DiagnosisResponse**: `{ diagnosis_id, primary_disease, confidence, severity_index, treatment_recommendations }`
