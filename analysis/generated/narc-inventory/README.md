# NARC and member inventory

## Provenance

- Input: `Pokémon Pearl Version (USA, APAE, header ROM version 5)`
- ROM SHA-256: `2dcc471033d1757ee572415f5773a77af67b350ad59e2aeb3fc28c1402c3a84c`
- Tool: `narc_inventory 1.0.0`
- ROM bytes committed: **no**

## Confirmed totals

| Metric | Count |
| --- | ---: |
| Top-level NARC candidates | 149 |
| Valid top-level NARCs | 149 |
| Malformed top-level NARCs | 0 |
| Nested NARCs | 0 |
| Total members, including nested containers | 33953 |
| Named members | 0 |
| Compression-marker members (Probable or Confirmed) | 3462 |
| Structurally decoded LZ10/LZ11 members (Confirmed) | 1885 |
| Invalid LZ-like leading markers | 286 |
| Huffman/RLE markers not decoded in this phase | 1291 |
| Unknown members | 23233 |

## Evidence language

Offsets, sizes, hashes, block layouts, and successful structural checks are **Confirmed**. A leading magic or compression marker without complete structural validation remains **Probable**. No semantic field names are inferred from payload shape alone.

No raw member payload is retained. `narc-inventory.json` and the CSV files preserve the complete reproducible structure and hash evidence.
