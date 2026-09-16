# JSON to CSV Converter — Reference & Samples

A small reference repository for the browser-based JSON to CSV converter at
https://jsontocsvtool.com (conversion runs entirely in your browser, nothing is uploaded).

## What this repository contains

- `SUPPORTED_FORMATS.md` — the input/output shapes the converter accepts, as a table.
- `conversion-rules.md` — how nested objects and arrays are flattened into rows.
- `sample-data.csv` and `sample-data.json` — a tiny worked example you can paste in.

## Supported formats (summary)

| Input shape | Output | Notes |
|-------------|--------|-------|
| JSON object | CSV (1 row) | Keys become headers |
| JSON array of objects | CSV (N rows) | One row per element |
| JSON array of arrays | CSV | Direct column mapping |
| Nested object | Flattened CSV | Dot-path keys, e.g. `user.name` |
| Array of primitives | Joined cell | Comma-joined by default |

See `SUPPORTED_FORMATS.md` for the full list.

## Conversion rules (summary)

1. The converter never sends your data to a server — everything is parsed locally.
2. Nested objects are flattened using dot notation.
3. Arrays are expanded into rows/columns or joined, depending on shape.
4. The header row is the union of all keys across records.

Full detail in `conversion-rules.md`.
