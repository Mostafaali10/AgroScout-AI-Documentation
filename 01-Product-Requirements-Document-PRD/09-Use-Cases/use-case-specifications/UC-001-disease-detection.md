# Use Case Specification: UC-001 On-Field Disease Diagnosis

> **Module**: AgroScout AI PRD | **Status**: Approved Baseline

Detailed nominal and exception flows for detecting foliar disease via mobile.

## Actors

Primary: Field Scout. Supporting: On-Device AI Engine, Geospatial Service.

## Preconditions

Scout is logged into AgroScout mobile app; camera permission granted.

## Main Success Scenario

1. Scout selects current farm parcel and taps 'Scan Crop'.
2. Scout frames plant leaf inside visual guideline box and captures image.
3. Mobile on-device neural network executes inference.
4. Screen displays detected class (e.g. Potato Early Blight), confidence (97%), and severity score.
5. Scout confirms and saves record with current GPS tag.
6. Record is persisted locally and queued for cloud synchronization.

## Alternative Flows

- **Low Lighting**: App advises activating camera flash or moving to shaded daylight.
- **Uncertain Diagnosis (<60% confidence)**: App flags image for expert agronomist cloud review.
