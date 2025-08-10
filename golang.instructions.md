---
applyTo: "**/*.go"
---

This is Go code. The correct structure must always be followed:

### File Layout Rules
- One `package` declaration at the top of the file
- One `import` block immediately after `package`
- All `func`, `type`, `const`, and `var` declarations must come after imports
- Do not place `package` or `import` anywhere else in the file
- When adding a new function, insert it at the end unless told otherwise
- Never add a second import block or package declaration

### Best Practices
- After editing, always check for `#problems` in the saved file
- Linter warnings are considered real problems and must be fixed

### Tooling Conventions
- **Database migrations**: use [Goose](https://github.com/pressly/goose)
- **Testing**: use [Testify](https://github.com/stretchr/testify), including Suites
- **Logging**: use structured logging with [`log/slog`](https://pkg.go.dev/log/slog)
- **Metrics**: use Prometheus via [`prometheus/client_golang`](https://pkg.go.dev/github.com/prometheus/client_golang/prometheus)
- **Tracing**: use OpenTelemetry [`otel/trace`](https://pkg.go.dev/go.opentelemetry.io/otel/trace)
- When available, prefer the **Go standard library** over external packages
- **Linting**: use golangci-lint [`golangci-lint`](https://github.com/golangci/golangci-lint)

### Code Organization
- If a Go file grows beyond **300 lines**, split it into two files using a logical functional division
- Separate concerns clearly — e.g., handlers, logic, types, and utilities in distinct files or packages
