---
generated: '2026-10-09'
method: generated
name: provision-postgres-database
description: Order a PostgreSQL database from the Baloise oneIT marketplace (OIM) and track the order.
api: openapi/baloise-oim-openapi.yml
operations: [api.calls_phs.pgsql_post, api.calls_phs.order_get, api.calls_phs.pgsql_get, api.calls_phs.pgsql_list]
source: Grounded in openapi/baloise-oim-openapi.yml (OpenAPI 3.0.0, v0.8, work in progress); operationIds verified verbatim.
---

# Provision a PostgreSQL database (OIM)

1. `api.calls_phs.pgsql_post` (POST /dbpg) — request a database; returns an order id (202 accepted, 400 bad parameters).
2. `api.calls_phs.order_get` (GET /order/{id}) — check order status.
3. `api.calls_phs.pgsql_get` (GET /dbpg/{dbid}) or `api.calls_phs.pgsql_list` (GET /dbpg, `filter`/`limit`) — inspect.

Relative server `/v0.8` only; no security scheme published.
