# AI Model Benchmark Results

> **Module**: Project Management & QA | **Status**: Approved Baseline

Detailed confusion matrices, mAP scores, and latency benchmarks.

## Benchmark Results Table

| Model Variant | Target Device | Top-1 Acc | mAP@0.5 | Latency (ms) | Model Size |
| :--- | :--- | :--- | :--- | :--- | :--- |
| YOLOv11n (INT8) | Android Snapdragon 778 | 94.8% | 86.2% | 185 ms | 14.2 MB |
| YOLOv11m (FP16) | Jetson Orin Nano | 96.5% | 90.1% | 45 ms | 48.5 MB |
| ConvNeXt-Base | Cloud NVIDIA A10G | 98.2% | 93.4% | 18 ms | 180 MB |
