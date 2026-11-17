# Rollback & Disaster Recovery Strategy

> **Module**: Project Management & QA | **Status**: Approved Baseline

Automated deployment rollback triggers and blue-green failover.

## Rollback Triggers

Helm rollback triggered automatically if HTTP 5xx error rate exceeds 1% during canary rollout.
