# ROM structure inventory: Pokémon Pearl Version (USA, APAE, header ROM version 5)

## Provenance

- Tool: `nds_rom_analyzer 1.0.0`
- Input basename: `Pokemon_Pearl_USA_NDS-LGC.nds`
- Input SHA-256: `2dcc471033d1757ee572415f5773a77af67b350ad59e2aeb3fc28c1402c3a84c`
- ROM bytes committed: no
- Confidence: **Confirmed** for directly parsed offsets, fields, hashes, and CRC results.

## Core structure

| Field | Value |
| --- | --- |
| Game code | `APAE` |
| ROM/header size | `67108864` / `16384` bytes |
| ARM9 ROM / RAM / entry / size | `0x4000` / `0x02000000` / `0x02000800` / `1079076` |
| ARM7 ROM / RAM / entry / size | `0x30d000` / `0x02380000` / `0x02380000` / `168732` |
| FNT / FAT files / directories | `0x336400` / `356` / `70` |
| ARM9 / ARM7 overlays | `87` / `0` |
| NARC archives | `149` |
| Recognized signatures | `208` |
| Header/logo CRC valid | `True` / `True` |
| Structural validation checks | `True` |
| Secure-area raw encrypted bytes / decrypted CRC validation | `ce9b7cedb2dabc9e45cf2b47b9b8b28138c1ad21da36ead6c4938415501fbca3` / `not performed` |

## Outputs

- `structure.json`: complete machine-readable inventory.
- `nitrofs-files.csv`: every FAT file with path, offsets, size, SHA-256, extension, and detected signature.
- `directories.csv`: complete FNT directory table.
- `overlays-arm9.csv` and `overlays-arm7.csv`: complete overlay tables and RAM placement.
- `unreferenced-ranges.csv`: physical gaps and trailing padding. `unreferenced` does not prove unused.

## Reproduction

```console
python tools/nds_rom_analyzer/analyzer.py /path/to/input.nds --output analysis/generated/rom-structure --label "Pokémon Pearl Version (USA, APAE, header ROM version 5)"
```

## Unknowns

The secure-area bytes and header checksum field are recorded, but decrypted secure-area CRC validation is not performed; a mismatch against CRC of encrypted raw bytes is not corruption evidence. Magic detection identifies only known leading signatures and compression markers. Unknown or extensionless files remain unclassified rather than receiving inferred names. Semantic analysis of NARC members, text, maps, scripts, Pokémon, moves, and items is deferred.
