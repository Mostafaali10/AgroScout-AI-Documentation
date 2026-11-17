# Production Deployment Manual

> **Module**: Project Management & QA | **Status**: Approved Baseline

Step-by-step instructions for deploying AgroScout cloud backend onto Kubernetes.

## Deployment Steps

1. Apply Kubernetes secrets and configmaps.
2. Execute database migrations: `alembic upgrade head`.
3. Deploy PostGIS and TimescaleDB operators.
4. Deploy FastAPI core services and EMQX broker.
5. Verify ingress routing and SSL certificates.
