# Public Source Registry — Pocket Monsters Pearl

This registry tracks public material used to reconstruct and compare Pocket Monsters Pearl without assuming access to an original ROM image.

## Rules

- Japanese earliest retail release is the historical baseline.
- Record every official region, language, and revision separately.
- Do not mark releases identical without positive evidence.
- Preserve conflicting claims and their sources.
- Record redistribution/licensing status before copying external material into this repository.
- Every research result derived from a source should link back to a registry entry.
- The registry is an exhaustive-census index, not a representative reading list. Historical, superseded, forked, archived, and conflicting public research remains in scope.

## Evidence status

- `CONFIRMED_IDENTICAL`
- `CONFIRMED_DIFFERENT`
- `UNVERIFIED`
- `CONFLICTING_EVIDENCE`

## Source registry

| ID | Source | Source type | Game | Region | Language | Revision | Component / scope | Original or derived | Redistribution status | Verification | Cross-check | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| `P-SRC-0001` | [pret/pokediamond](https://github.com/pret/pokediamond) | Public decompilation | Pearl | USA target; shared DP engine | English | matching target | Code, data, filesystem, build/reconstruction | Derived source-reconstruction project | Follow upstream terms; do not redistribute retail ROM | Strong technical reference | PPRE; scrcmd database; other DP research | Builds `pokepearl.us.nds` SHA-1 `99083bf15ec7c6b81b4ba241ee10abd9e80999ac`. Repository is shared with Diamond and must not be mistaken for evidence that all D/P assets or regional builds are identical. |
| `P-SRC-0002` | [Project Pokémon PPRE](https://github.com/projectpokemon/PPRE) | Historical ROM-editor source | Pearl / Gen IV | USA-focused | English | multiple supported games | Pokémon, text, move editing; historical format/tool lineage | Derived technical tooling | Follow upstream terms | Historical technical reference | `P-SRC-0001`, `P-SRC-0003` | PPRE began as a Diamond/Pearl editor and later supported all Gen IV mainline games. Its implementation and dependencies are evidence for historical format knowledge, not automatically authoritative over newer decompilation findings. |
| `P-SRC-0003` | [DS-Pokemon-Rom-Editor/scrcmd-database](https://github.com/DS-Pokemon-Rom-Editor/scrcmd-database) | Script-command research database | Diamond/Pearl, Platinum, HGSS | Multi-game | Technical metadata | current V2 + legacy | Script opcodes, movement commands, macros, sounds, flags/vars, comparison operators | Derived from DSPRE/decomp/community research | Follow upstream license | Strong living technical reference | PRET projects; DSPRE | V2 is declared source of truth; legacy JSON is retained for DSPRE compatibility. Diamond/Pearl data is not currently synchronized from a configured decomp source, so DP entries require independent cross-checking. |
| `P-SRC-0004` | [Project Pokémon — Gen IV BDHC terrain research](https://projectpokemon.org/home/forums/topic/37816-gen-iv-bdhc-files-terrain-settings/) | Reverse-engineering research | D/P/Pt/HGSS | Multi-game | English research notes | N/A | BDHC terrain/collision file structure | Derived community research | Citation/link only | Technical reference; reproduce before promoting | Editors/decomp projects | Documents BDHC header and section sizing rules used by Gen IV maps. Must be checked per game and per region rather than assumed universal. |
| `P-SRC-0005` | [Bulbapedia — Diamond and Pearl versions](https://bulbapedia.bulbagarden.net/wiki/Pok%C3%A9mon_Diamond_and_Pearl_Versions) | Specialist wiki / localization index | Diamond/Pearl | Multi-region | Multi-language | multiple | Regional text, graphics, censorship/localization, event-app availability | Derived | Citation/link only | Secondary index; field-by-field verification required | Official/local sources; game research | Useful lead for British-English text changes, Korean slot-machine replacement, Japanese-only Pokétch distribution, Sinnoh myth localization, graphics differences, etc. Every claim must be traced to stronger evidence where possible. |
| `P-SRC-0006` | [Bulbapedia — List of glitches in Generation IV](https://bulbapedia.bulbagarden.net/wiki/List_of_glitches_in_Generation_IV) | Specialist glitch index | D/P/Pt/HGSS | Multi-region | English | multiple | Battle, overworld, GTS, Pal Park, save, evolution and version-specific glitches | Derived | Citation/link only | Secondary index; reproduce/trace sources | Technical forums, TAS research, decomp code | Starting index only. Each glitch will receive game/revision/region conditions and independent evidence before becoming a confirmed project finding. |

## Difference registry

| ID | Japanese baseline | Compared release | Component | Difference class | Evidence status | Source IDs | Notes |
|---|---|---|---|---|---|---|---|
| `P-DIFF-0001` | Japanese Pearl | Korean Pearl | Game Corner / slot machines | `REGIONAL_LOCALIZATION_AND_GAMEPLAY_CHANGE` | `UNVERIFIED` | `P-SRC-0005` | Secondary source reports Korean D/P replaces playable slot machines with simpler coin-awarding machines. Requires direct Korean-specific technical/archival evidence before promotion. |

## Census workstreams

The exhaustive survey is organized by source class, not by a short list of “best” sources:

- official Nintendo / Pokémon / distributor sites, manuals, guides, press releases, support notices and archived pages;
- public decompilation/disassembly/source-reconstruction repositories, forks, branches, issues, PRs, commits and superseded projects;
- ROM editors, extraction/repacking utilities, graphics/text/audio/map/script tools and their source/dependencies;
- Project Pokémon and other technical forums, including old threads and attachments when public;
- preservation metadata, revision catalogs, product codes, packaging scans and checksums without acquiring ROM payloads;
- specialist databases/wikis used as leads and cross-check indexes;
- distribution-event records, Wonder Cards, Wi-Fi/GTS/Mystery Gift history and service software;
- bugs/glitches/TAS/exploit research;
- unused/debug/development remnants, demos/kiosks/betas/service software;
- regional/language/localization/censorship research;
- archived/dead-link material recoverable through public web archives.

## Coverage backlog

The registry is expected to cover release/revision inventories; executable and overlay research; ARM9/ARM7; NitroFS/NARC formats; scripts; text; maps; events; Pokémon/trainer/item/move/encounter data; graphics/sprites/models/animation; audio; save structures; local wireless/Nintendo Wi-Fi Connection/GTS/Mystery Gift; distribution/event data; bugs and fixes; unused/dummy/debug/development remnants; localization/censorship; tooling; specialist databases/wikis; and archival community research. Entries above are only the first census batch and do not define the final scope.
