# Supported Formats

All conversion happens in the browser; nothing is uploaded.

| # | Input shape | Output | Example | Notes |
|---|-------------|--------|---------|-------|
| 1 | Object | CSV (1 row) | `{"a":1,"b":2}` -> `a,b\n1,2` | Keys become headers |
| 2 | Array of objects | CSV (N rows) | `[{...},{...}]` | One row per item |
| 3 | Array of arrays | CSV | `[[1,2],[3,4]]` | Direct mapping |
| 4 | Nested object | Flattened CSV | `{"a":{"b":1}}` -> `a.b\n1` | Dot-path keys |
| 5 | Array of primitives | Joined cell | `[1,2,3]` -> `1,2,3` | Separator configurable |
| 6 | Mixed types | CSV | strings/numbers/booleans | Booleans -> true/false |
| 7 | Empty / null | CSV | `null` -> empty cell | Preserved as blank |

Output is UTF-8 CSV with a header row; quoting follows RFC 4180.
