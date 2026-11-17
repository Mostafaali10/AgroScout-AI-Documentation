# Authentication & Authorization Architecture

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Detailed architecture of identity management, token rotation, and RBAC enforcement.

## Mechanisms

- OAuth 2.0 with JWT access tokens and long-lived refresh tokens.
- Granular permission checks at service router level: `Depends(require_permission('farm:create'))`.
- Edge rover device authentication using mTLS with hardware-backed private keys.
