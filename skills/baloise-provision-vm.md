---
generated: '2026-10-09'
method: generated
name: provision-vm
description: Order a VM from the Baloise oneIT marketplace (OIM) and follow the order until the VM can be inspected.
api: openapi/baloise-oim-openapi.yml
operations: [api.calls_phs.vm_post, api.calls_phs.order_get, api.calls_phs.order_get_detail, api.calls_phs.vm_get]
source: Grounded in openapi/baloise-oim-openapi.yml (OpenAPI 3.0.0, v0.8, work in progress); operationIds verified verbatim.
---

# Provision a VM (OIM)

Base path is relative (`/v0.8`); no public host or security scheme is published.

1. `api.calls_phs.vm_post` (POST /vm) — request a VM; returns an order id (202 accepted, 400 bad parameters). Optionally pass a customer reference.
2. `api.calls_phs.order_get` (GET /order/{id}) — check order status; 404 if unknown.
3. `api.calls_phs.order_get_detail` (GET /order/{id}/details) — order details.
4. `api.calls_phs.vm_get` (GET /vm/{name}) — inspect the VM.

Modify with `api.calls_phs.vm_patch` (409 on conflict) or remove with `api.calls_phs.vm_delete` (202).
