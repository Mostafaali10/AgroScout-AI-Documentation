# FR-01: Authentication & Authorization

> **Module**: AgroScout AI PRD | **Status**: Approved Baseline

Functional requirements for user sign-up, sign-in, session management, and RBAC.

## Requirements

1. System shall support email/password and SMS OTP authentication.
2. System shall issue rotating JWT access tokens (15-min lifespan) and secure HTTP-only refresh tokens (30-day lifespan).
3. Mobile app shall support biometric login (Fingerprint / Face ID) for local credential unlocking.
