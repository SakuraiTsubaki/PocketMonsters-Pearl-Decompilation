# Core data Phase 1 — Pearl baseline and Generation IV deltas

## Target status

The locally observed Pokémon Pearl Version image is the USA Rev 5 build (`APAE`, ROM version 5) and matches the PRET whole-ROM SHA-1 target exactly: `99083bf15ec7c6b81b4ba241ee10abd9e80999ac`.

See `manifests/clean_reference.json` and `manifests/observed_rom_baseline.json`.

## Core NARC inventory

| Dataset | Pearl members | Record form |
| --- | ---: | --- |
| personal | 501 | 44-byte fixed records |
| evolution | 501 | 44-byte fixed records |
| level-up learnsets | 501 | packed 16-bit variable-length records + `0xFFFF` sentinel |
| move table | 471 | 16-byte fixed records |
| item table | 442 | 34-byte fixed records |
| growth tables | 8 | 404-byte fixed records |

## Pearl ↔ Diamond

Only six personal records differ; the evolution, level-up learnset, move, item, and growth archives are byte-identical.

| Species ID | Species | Pearl held slots | Diamond held slots |
| ---: | --- | --- | --- |
| 125 | Electabuzz | rare Electirizer | common Electirizer |
| 126 | Magmar | common Magmarizer | rare Magmarizer |
| 239 | Elekid | rare Electirizer | common Electirizer |
| 240 | Magby | common Magmarizer | rare Magmarizer |
| 466 | Electivire | rare Electirizer | common Electirizer |
| 467 | Magmortar | common Magmarizer | rare Magmarizer |

No other fields differ in those records.

## Pearl → Platinum

Shared-index comparison:

- personal: 6 changed records (114, 126, 240, 352, 357, 467) plus 7 extra Platinum form records.
- evolution: 0 shared changes plus 7 zero-filled form records.
- level-up learnsets: 81 shared changes plus 7 form learnsets.
- moves: only move 95 (Hypnosis), accuracy `70 → 60`.
- growth: byte-identical.
- items: raw index comparison shows 242 differing records and 4 additional Platinum records, but insertion/index realignment is present and semantic item deltas must be produced after name-based alignment.

Pearl-side personal changes to Platinum are Safari flee-rate additions for Tangela/Kecleon/Tropius and Magmarizer relocation from the common to rare slot for Magmar, Magby, and Magmortar.

## Platinum form expansion

The seven new personal/learnset form slots at indexes 501–507 are Giratina Origin, Shaymin Sky, and the five Rotom appliance forms. Their evolution records are all zero-filled.

## Verification status

The Pearl whole-ROM target is a verified local exact match. Platinum observations are content-level observations against the preserved Korean comparison image and are not whole-ROM clean-match claims.
