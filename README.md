# hello-go 🐹🐳

A simple Go application that prints a greeting, OS/architecture info, and an optional sum — built to demonstrate CI/CD with Docker image publishing to GitHub Container Registry (GHCR).

[![Go CI/CD](https://github.com/TEgor1212/hello-go/actions/workflows/ci.yml/badge.svg)](https://github.com/TEgor1212/hello-go/actions/workflows/ci.yml)

## How to run

```bash
go run .
```

Or pass arguments:

```bash
go run . -- foo bar
```

## Docker image

The CI/CD workflow builds and pushes a Docker image to GHCR on every push to `main`:

```bash
docker pull ghcr.io/TEgor1212/hello-go:latest
```

## CI/CD

- **Lint:** `go vet ./...` + `gofmt` format check
- **Test:** `go test ./...`
- **Build:** Statically linked binary via `CGO_ENABLED=0 go build`
- **Publish:** Docker image built and pushed to `ghcr.io/TEgor1212/hello-go`