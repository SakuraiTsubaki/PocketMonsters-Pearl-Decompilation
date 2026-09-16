# Analysis: ROM identity baseline

## Target and applicability

This record applies only to the selected Pokémon Pearl Version input identified by the
complete-file hashes below. The user-supplied ROM remains outside Git.

## Claim

The repository target is the USA English Nintendo DS build with
game code `APAE` and raw header ROM-version byte `5`.
Complete-file SHA-1 matches the documented pokepearl.us.nds build target.

## Evidence

| Field | Observed value |
| --- | --- |
| Header title | `POKEMON P` |
| Game code | `APAE` |
| Maker code | `01` |
| Unit code | `0` |
| Device-capacity exponent | `9` |
| Nominal and actual size | `67108864` bytes |
| Header ROM version | `5` |
| Header CRC-16 | stored `a80c`, calculated `a80c`, valid |
| SHA-256 | `2dcc471033d1757ee572415f5773a77af67b350ad59e2aeb3fc28c1402c3a84c` |
| SHA-1 | `99083bf15ec7c6b81b4ba241ee10abd9e80999ac` |
| MD5 | `e5da92c8cfabedd0d037ff33a2f2b6ba` |

## Method

Recorded environment: Windows `10.0.26200`, PowerShell Core `7.6.5`, Python
`3.12.14`. The reusable standard-library tool is maintained in
[`SakuraiTsubaki/Decompilation`](https://github.com/SakuraiTsubaki/Decompilation/tree/a9b6a98ab90304c34b8049cf3c157a9db9045b71/tools/nds_rom_inventory).

```console
python tools/nds_rom_inventory/rom_inventory.py /path/to/input.nds
```

The tool streams the complete file through SHA-256, SHA-1, and MD5; parses the
first 512 bytes; and recalculates the Nintendo DS header CRC over
`0x0000..0x015D`. It does not modify or extract the ROM.

## Findings

- Actual size equals the nominal capacity derived from the header.
- Stored and calculated header CRC values agree.
- The raw ROM-version byte is reported without inferring undocumented content
  differences.
- Public comparison status: **matched** against
  [pret/pokediamond](https://github.com/pret/pokediamond).

## Confidence

**Confirmed.** The local whole-file SHA-1 matches the independently documented public build target, and the locally recalculated header CRC matches the stored value.

## Verification

The observed values are stored in `config/target.json`. Re-running the shared
tool on the selected input must reproduce every complete-file hash and header
field in this record.

## Unknowns

Secure-area validation, ARM9/ARM7 ranges, FNT/FAT, overlay tables, banner,
NitroFS inventory, padding, and per-file hashes remain for the next analysis
unit.
