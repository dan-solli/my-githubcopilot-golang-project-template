---
applyTo: "**/*.sql"
---

This is SQL code used for schema migrations, queries, or view definitions.

### Style & Structure
- End every statement with a `;`
- Use uppercase for SQL keywords (`SELECT`, `INSERT`, `WHERE`, etc.)
- Use lowercase for table and column names unless quoting is required
- Always alias subqueries and derived tables with readable names

### Comments
- Use `--` for inline comments
- Use block comments `/* */` only when necessary

### Query Rules
- Prefer `JOIN` syntax over implicit joins
- Avoid `SELECT *` — list all columns explicitly
- For migrations, write idempotent statements whenever possible
- Include `IF EXISTS` or `IF NOT EXISTS` when altering or dropping objects
- If using Goose, each migration must include `-- +goose Up` and `-- +goose Down` markers

### Safety & Consistency
- Avoid raw deletes or updates without `WHERE`
- Always include primary keys and indexes when creating tables
- For DDL, group `CREATE TABLE` statements by section (e.g., entities, lookup tables)
- Avoid mixing DDL and DML in the same migration