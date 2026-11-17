# Design Patterns Reference

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Key architectural and object-oriented patterns applied throughout the codebases.

## Applied Patterns

- **Repository Pattern**: Abstract data access layer allowing seamless swapping between SQLite local cache and cloud REST API.
- **BLoC (Business Logic Component)**: Reactive state management in Flutter.
- **Factory Pattern**: Dynamic AI model loader for TFLite, ONNX, and TensorRT formats.
- **Circuit Breaker Pattern**: Resilience pattern safeguarding backend microservices during external LLM outages.
