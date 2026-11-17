# Cloud Deployment Architecture

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Kubernetes orchestration, container topology, autoscaling, and multi-region setup.

## Cloud Infrastructure

- **Containerization**: Docker multi-stage builds for all microservices.
- **Orchestration**: Managed Kubernetes (EKS / GKE) with Horizontal Pod Autoscaler (HPA).
- **Database Cluster**: Managed PostgreSQL with multi-AZ replication.
- **Edge Deployment**: OTA (Over-the-Air) firmware updates managed via BalenaCloud / Mender.
