# System Boundaries & Constraints

> **Module**: AgroScout AI SDD | **Status**: Approved Baseline

Architectural demarcations between trusted internal zones, edge nodes, and public interfaces.

## Boundary Definition

- **Internal Cloud VPC**: Services communicate over private subnets with mutual authentication.
- **DMZ / Public Edge**: Only port 443 (HTTPS) and port 8883 (MQTTS) are exposed through the cloud load balancer.
- **Edge Hardware Sandbox**: Rover firmware isolates drive-control safety loops from high-level vision processing.
