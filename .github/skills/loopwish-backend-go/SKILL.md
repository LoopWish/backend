---
name: loopwish-backend-go
description: Workflows for the Loopwish Go backend (Gin): run locally, add/modify REST endpoints, and validate with go test/build and golangci-lint.
---

# Loopwish Backend (Go) Skill

Use this skill when working in the Loopwish **backend repository**.

## When to use

- Adding or changing API endpoints/handlers.
- Investigating failing backend CI checks.
- Running the backend locally.

## Key paths

- Entry point: `cmd/api/main.go`
- Handlers: `internal/handlers/`
- Services: `internal/services/`
- Models: `internal/models/`

## Run locally

From the repo root:

```bash
go test ./...

go run ./cmd/api
```

The server runs at `http://localhost:8080` by default.

## Validation (matches CI intent)

From the repo root:

```bash
go mod download

go build ./...

go test ./...

golangci-lint run --timeout=3m
```

If `golangci-lint` isn’t installed locally (macOS):

```bash
brew install golangci-lint
```

## Adding an endpoint checklist

1. Add the route in the router setup (follow existing structure).
2. Implement handler in `internal/handlers`.
3. Keep handler thin; move business logic to `internal/services` when it grows.
4. Add/adjust tests (`*_test.go`).
5. If it’s a public API change, update the OpenAPI spec in the **shared repo** at `shared/api-spec/openapi.yaml`.
6. Run `go test ./...` and `golangci-lint run`.

## Example prompts

- “Add `GET /v1/wishes` and stub response; add tests.”
- “Refactor this handler to move logic into `internal/services` without changing behavior.”
- “Why is `golangci-lint` failing in CI? Fix the underlying issue.”
