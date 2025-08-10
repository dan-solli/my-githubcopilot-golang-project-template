---
applyTo: "**/*_test.go"
---

This is Go code for unit and integration tests. The correct structure must always be followed:

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
- **Testing**: use [Testify](https://github.com/stretchr/testify), including Suites
- **Logging**: use structured logging with [`log/slog`](https://pkg.go.dev/log/slog)
- **Metrics**: use Prometheus via [`prometheus/client_golang`](https://pkg.go.dev/github.com/prometheus/client_golang/prometheus)
- **Tracing**: use OpenTelemetry [`otel/trace`](https://pkg.go.dev/go.opentelemetry.io/otel/trace)
- When available, prefer the **Go standard library** over external packages
- Tests should be, whenever possible, table-driven.
- Integration tests should, as far as it is possible use the [testcontainer framework](https://golang.testcontainers.org/), and preferably stretchr/testify/suite to set up and teardown properly.

### Code Organization
- If a Go file grows beyond **300 lines**, split it into two files using a logical functional division
