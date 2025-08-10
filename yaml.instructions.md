---
applyTo: "**/*.yaml"
---

This is a YAML file. It must be well-formed and consistently structured.

### General Rules
- Indentation must be 2 spaces (never tabs)
- Always use `key: value` format with a space after the colon
- Lists should use `-` at the same indent level as the parent key
- Avoid trailing whitespace and empty keys

### Style
- Use lowercase keys with kebab-case (`some-key-name`)
- Group related settings under clear parent keys
- Quote values only when required (e.g., strings starting with `:` or `@`)

### Use Cases
- For Kubernetes manifests:
  - Group by `apiVersion`, `kind`, `metadata`, `spec`
  - Include labels for every object
  - Use multi-document files (`---`) for multiple resources
- For CI/CD configs (e.g., GitHub Actions, Ansible):
  - Comment every major step
  - Collapse repeat patterns into anchors or reusable blocks

### Validation
- This file must be valid YAML — validate it before commit
- Prefer human-readability over optimization