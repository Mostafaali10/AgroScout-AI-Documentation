# Inference Pipeline & Runtime Optimization

> **Module**: Technical Specifications | **Status**: Approved Baseline

Edge TensorRT, ONNX Runtime, and TFLite execution environments.

## Runtime Strategy

- Cloud: NVIDIA Triton Inference Server using TensorRT FP16 engines.
- Edge Rover: ONNX Runtime with OpenVINO backend on Intel/ARM CM4.
- Mobile: TensorFlow Lite with INT8 post-training quantization.
