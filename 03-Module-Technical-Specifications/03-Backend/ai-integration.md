# Backend AI Integration & Triton Client

> **Module**: Technical Specifications | **Status**: Approved Baseline

gRPC integration between FastAPI backend and Triton Inference Server.

## Inference Client

Asynchronous gRPC client connecting to Triton server with health-check fallback to local ONNX runtime.
