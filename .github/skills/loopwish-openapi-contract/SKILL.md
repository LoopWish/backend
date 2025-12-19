---
name: loopwish-openapi-contract
description: Keep the backend REST API and the shared OpenAPI spec in sync. Use when adding/changing endpoints so the contract in the shared repo stays accurate.
---

# Loopwish OpenAPI Contract (Backend Pointer) Skill

Use this skill when working in the Loopwish **backend repository** and making changes that affect the public API.

## Source of truth

- The OpenAPI spec lives in the **shared repo** at `shared/api-spec/openapi.yaml`.

## When to use

- Adding/changing an endpoint, request body, response body, status codes, or error shapes.
- Changing semantics (authorization rules, pagination, filtering, field meanings).

## Workflow

1. Implement the backend change (follow existing patterns under `internal/handlers` and `internal/services`).
2. Update the OpenAPI spec in the shared repo (`shared/api-spec/openapi.yaml`) so it matches real behavior.
3. Prefer additive, backwards-compatible changes.
4. Validate backend locally:

```bash
go test ./...

go build ./...
```

## Quick review checklist

- Document success + common error responses (4xx/5xx) where relevant.
- Ensure schemas match actual JSON (types, required vs optional).
- Avoid “aspirational” fields that aren’t implemented.

## Example prompts

- “I changed the response shape of `GET /health` — update the OpenAPI spec in shared.”
- “Add a new endpoint and update the shared OpenAPI contract accordingly.”
