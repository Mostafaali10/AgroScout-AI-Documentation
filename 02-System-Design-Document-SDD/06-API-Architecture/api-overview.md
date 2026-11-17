# API Architecture Overview

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Design standards, versioning, headers, and error handling for the AgroScout REST API.

## Standards

- Base URL: `https://api.agroscout.ai/v1`
- Content-Type: `application/json`
- Authentication: `Bearer <jwt_token>`
- Rate Limiting: 60 requests/minute per authenticated user; 600 requests/minute for edge devices.
