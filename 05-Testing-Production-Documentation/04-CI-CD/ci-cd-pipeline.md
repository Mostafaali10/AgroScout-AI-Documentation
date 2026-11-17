# CI/CD Pipeline Architecture

> **Module**: Project Management & QA | **Status**: Approved Baseline

GitHub Actions pipelines for automated test execution, Docker build, and Kubernetes deployment.

## Pipeline Stages

Lint -> Test -> Build Multi-Arch Docker Image -> Vulnerability Scan -> Push to Harbor Registry -> Helm Upgrade to Staging.
