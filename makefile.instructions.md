---
applyTo: "**/Makefile"
---

This is a Makefile used for task automation, project bootstrapping, or build pipelines.

### Syntax & Format
- Use tabs, not spaces, for command indentation
- Target names must be left-aligned with no extra whitespace
- Use `.PHONY` to declare non-file targets

### Style Guidelines
- Group related targets (build, test, lint, deploy, clean) together
- Document each target with a comment above it
- Use environment variables and flags when appropriate (`GOOS`, `GOARCH`, `DEBUG`, etc.)

### Common Targets
- `all`: default build/test/verify pipeline
- `build`: compile binaries
- `test`: run all tests (unit + integration if applicable)
- `lint`: run static analysis tools (e.g., `golangci-lint`)
- `clean`: remove build artifacts
- `run`: run the application locally
- `help`: auto-generate help from comments

### Reusability
- Use variables for directories, binaries, and flags (`BINARY=app`, `SRC=./cmd`)
- Use pattern rules (`%.o: %.c`) for compile chains where needed

### Lint & Safety
- Validate with `make --dry-run` and `shellcheck -f make` (where available)
- Avoid hard-coded paths or assumptions about user environments
