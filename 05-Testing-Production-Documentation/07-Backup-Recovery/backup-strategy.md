# Backup Strategy & Retention Schedule

> **Module**: Project Management & QA | **Status**: Approved Baseline

Automated PostgreSQL snapshot backups and MinIO bucket replication.

## Backup Frequency

Continuous WAL archiving with Point-In-Time-Recovery (PITR); full daily database snapshots retained for 90 days.
