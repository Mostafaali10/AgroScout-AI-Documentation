# Data Protection & Cryptography

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Encryption at rest, encryption in transit, key management, and data sanitation.

## Cryptographic Standards

- Data in Transit: TLS 1.3 with strict cipher suites.
- Data at Rest: AWS KMS / HashiCorp Vault managed AES-256 keys for database and S3 buckets.
- Mobile Storage: Encrypted SQLite databases using SQLCipher with biometric-derived encryption keys.
