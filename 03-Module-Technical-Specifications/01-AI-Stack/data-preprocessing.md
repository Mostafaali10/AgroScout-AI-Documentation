# Data Preprocessing & Augmentation Pipeline

> **Module**: Technical Specifications | **Status**: Approved Baseline

Image normalization, color space transforms, and albumentations augmentations.

## Pipeline Stages

- Resizing to 640x640 with letterboxing to preserve aspect ratio.
- Albumentations: Random sun flare, shadows, motion blur, CLAHE (Contrast Limited Adaptive Histogram Equalization).
- AutoAugment policy optimized for foliar disease texture retention.
