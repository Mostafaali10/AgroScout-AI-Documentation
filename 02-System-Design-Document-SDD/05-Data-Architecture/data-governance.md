# Data Governance & Lifecycle Policy

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Retention, compliance, privacy, and backup governance policies.

## Policies

- High-resolution scouting images retained in S3 Standard storage for 180 days, then transitioned to Infrequent Access.
- Telemetry raw samples compressed after 30 days and rolled up to hourly averages after 365 days.
- Farmers have full data export rights (GeoJSON, CSV) and GDPR-compliant account deletion.
