# NFR-02: Security & Privacy Requirements

> **Module**: AgroScout AI PRD | **Status**: Approved Baseline

Encryption, authentication security, and vulnerability compliance.

## Security Standards

- TLS 1.3 encryption for all data in transit; AES-256-GCM for data at rest.
- JWT tokens with SHA-256 signature and short expiration.
- Strict OWASP Top 10 API Security compliance.
- Field devices use mutual TLS (mTLS) with pre-provisioned X.509 device certificates.
