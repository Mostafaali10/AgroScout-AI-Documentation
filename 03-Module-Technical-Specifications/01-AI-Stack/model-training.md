# Model Training Pipeline & Hyperparameters

> **Module**: Technical Specifications | **Status**: Approved Baseline

Training environment, loss functions, learning rate schedules, and optimization.

## Training Setup

- Optimizer: AdamW with cosine annealing learning rate schedule.
- Batch size: 32 per GPU; trained on 4x NVIDIA A100 SXM4 80GB.
- Loss: Complete IoU (CIoU) loss for boxes, Focal Loss for class imbalance.
