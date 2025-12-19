# GitHub Copilot Agent Instructions (Backend)

This repository contains the Loopwish backend (REST API).

## Stack

- Go 1.21+
- Gin
- Lint: golangci-lint

## Goals

- Keep the service buildable and testable.
- Prefer small PRs.
- Respect the project layout: `cmd/`, `internal/`, `pkg/`, `configs/`.

## Coding conventions

- Run `gofmt` on Go files (Go tooling typically handles this automatically).
- Keep HTTP handlers thin; move business logic into `internal/services` as it grows.
- Avoid global state where possible; prefer dependency injection via constructors.

## Validation

Before opening a PR, run:

```bash
go test ./...
golangci-lint run
go build ./...
```

## Safety

- Never commit `.env` or secrets.
- Avoid logging sensitive data.
