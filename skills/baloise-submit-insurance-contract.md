---
generated: '2026-10-09'
method: generated
name: submit-insurance-contract
description: Upload a contract's documents and then the contract itself to an insurer implementing the Baloise Corellia Contracts API.
api: openapi/baloise-corellia-contracts-openapi.yml
operations: [version, uploadDocument, uploadContract]
source: Grounded in openapi/baloise-corellia-contracts-openapi.yml (OpenAPI 3.0.1); every operationId verified verbatim.
---

# Submit an insurance contract (Corellia)

## Host and auth
The spec declares no servers and no security scheme: the base URL and credentials come from the insurer hosting the API.

## Steps
1. `version` (GET /contracts/v2/version) — optional check that the host speaks the expected API version (semver).
2. `uploadDocument` (POST /contracts/v2/documents) — call **once per document**. Keep the returned handle.
3. `uploadContract` (POST /contracts/v2) — send the contract body including the document handles from step 2.

## Rules
- Headers `X-Caller-Name` (sender) and `X-Event-ID` (unique per request) are required on steps 2-3.
- If validation fails, processing is refused: a 400 `ErrorResponse` is returned. 503 means the service is unavailable; retry later.
- The spec defines no idempotency key; use a fresh `X-Event-ID` per request.
