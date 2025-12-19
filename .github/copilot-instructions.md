# GitHub Copilot Agent Instructions (Backend)

This repository contains the Loopwish backend (REST API).

## Organization-wide standards (Loopwish)

- Keep PRs small and reviewable; avoid drive-by refactors.
- Do not commit secrets (API keys, tokens, credentials) or `.env` files.
- Prefer secure-by-default changes; avoid logging sensitive data.
- Update docs and tests when behavior changes.
- Keep CI green and run the repo’s validation commands before opening a PR.
- Follow the existing code style and architecture; copy patterns already used in the repo.

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
