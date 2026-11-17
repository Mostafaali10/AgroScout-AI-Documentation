# System Troubleshooting Guide

> **Module**: Project Management & QA | **Status**: Approved Baseline

Root cause analysis flows for common issues across mobile, sensors, and cloud.

## Common Scenarios

1. Mobile sync stuck: Verify local SQLite transaction lock.
2. Rover camera timeout: Inspect CSI ribbon cable seating.
3. Telemetry packet drop: Check EMQX client keepalive interval.
