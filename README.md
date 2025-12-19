# Loopwish · Backend

![Loopwish banner](https://raw.githubusercontent.com/loopwish/shared/main/assets/logos/loopwish-banner.svg)

Loopwish er en ønskeliste-app som lar deg dele ønsker med familie og venner. Ønsk. Del. Få. Sammen.

Dette repoet inneholder backend-tjenesten (REST API) for Loopwish.

## Teknologi-stack

- Go 1.21+
- Gin (HTTP router)
- PostgreSQL (planlagt/tilkobling via config)
- REST API

## Kom i gang

### Forutsetninger

- Go 1.21+

### Installering

```bash
git clone https://github.com/loopwish/backend.git
cd backend
```

### Kjør lokalt

```bash
go test ./...
go run ./cmd/api
```

Standard kjøring starter server på `http://localhost:8080`.

### Endepunkter

- `GET /health` → `{ "status": "ok" }`

## Prosjektstruktur

```text
cmd/
  api/
    main.go
internal/
  handlers/
  middleware/
  models/
  services/
pkg/
configs/
go.mod
go.sum
```

## Bidra

Se [CONTRIBUTING.md](CONTRIBUTING.md).

## Lisens

Lisensiert under MIT. Se [LICENSE](LICENSE).

## Relaterte repositories

- https://github.com/loopwish/apple
- https://github.com/loopwish/android
- https://github.com/loopwish/windows
- https://github.com/loopwish/web
- https://github.com/loopwish/backend
- https://github.com/loopwish/shared
