# Conversion Rules

1. **Local-only.** Input is parsed in the browser; no network upload.
2. **Header row.** Built from the union of all keys found across records, in first-seen order.
3. **Flattening.** Nested objects become dot-path columns (`a.b.c`).
4. **Arrays.**
   - Array of objects -> rows.
   - Array of primitives -> single cell, joined by the chosen separator (default comma).
   - Array of arrays -> columns.
5. **Missing values.** Absent keys render as empty cells; `null` -> blank.
6. **Types.** Numbers and booleans keep their native form; booleans export as `true`/`false`.
7. **Encoding.** Output is UTF-8 CSV, RFC 4180 quoting.
