---
generated: '2026-10-09'
method: generated
name: cancel-insurance-contract
description: Cancel a previously uploaded contract through the Baloise Corellia Contracts API.
api: openapi/baloise-corellia-contracts-openapi.yml
operations: [cancelContract]
source: Grounded in openapi/baloise-corellia-contracts-openapi.yml (OpenAPI 3.0.1); operationId verified verbatim.
---

# Cancel an insurance contract (Corellia)

1. `cancelContract` (POST /contracts/v2/cancellations) with a `Cancellation` body referencing the contract.

## Rules
- Required headers: `X-Caller-Name`, `X-Event-ID` (unique per request).
- Validation failure refuses processing with 400 `ErrorResponse`; 503 = unavailable.
- No server or auth scheme is published; use the host's base URL and credentials.
