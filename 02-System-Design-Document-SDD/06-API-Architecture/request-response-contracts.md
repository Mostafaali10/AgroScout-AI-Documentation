# Request & Response Contracts

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Specific schemas for critical endpoints including AI diagnosis and farm management.

## Sample Contract

### POST /api/v1/ai/diagnose
**Request Payload**:
```json
{
  "parcel_id": "b526d5c6-2c1f-4d9f-a89e-29e2f6946001",
  "latitude": 30.0444,
  "longitude": 31.2357,
  "image_url": "https://s3.agroscout.ai/raw/leaf_10293.jpg",
  "crop_type": "Tomato"
}
```
**Response 200 OK**:
```json
{
  "diagnosis_id": "d73a98e1-5182-4f3b-b271-987654321000",
  "primary_disease": "Tomato Early Blight (Alternaria solani)",
  "confidence": 0.964,
  "severity_percentage": 18.5,
  "recommended_actions": ["Apply copper-based fungicide", "Prune lower infected foliage"]
}
```
