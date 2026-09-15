# ARM9 `NitroMain` analysis

## Verified target
- Game: Pokémon Pearl
- Game code: `APAE`
- Region/language: USA / English
- ROM identity: `manifests/rom-baseline.json`

## Entry and boundary
- `_start` loads `0x02000C55`; bit 0 selects Thumb state.
- `NitroMain` Thumb entry: `0x02000C54`.
- Observed main-function instruction/literal boundary: `0x02000C54..0x02000DCF`.
- Literal pool begins at `0x02000DD0`.
- Code span size: `0x17C` (380) bytes.
- SHA-256 of that observed code span: `5692ce498a0043e64315558ef7fc303ead87b3fcfeeafd7a2f369444887d24e7`.
- Call sites in the observed body: 46 total, including one register-indirect `BLX` callback site.

## Matched high-level flow
The local machine code has the same `NitroMain` layout as the Diamond target: system/graphics/input initialization, backlight/RTC work, overlay state initialization, fonts, save data, sound/timer setup, WFC/save checks, reset-parameter based first-overlay selection, RNG/brightness/play-time setup, then the permanent frame loop.

## Cross-version result
The complete observed `NitroMain` span is byte-for-byte identical to the uploaded Diamond USA target, including every direct branch/call encoding in this range. This is stronger than structural similarity: for these two targets, the main routine itself is the same binary payload.

## Evidence
- Local target disassembly produced from the uploaded ROM.
- Direct byte comparison against the uploaded Diamond target.
- Symbol/name cross-check against the matching D/P reconstruction lineage in `pret/pokediamond`.

## Next mapping pass
1. Assign verified names to all direct-call targets.
2. Separate common D/P engine code from version-exclusive data/overlay behavior.
3. Follow the title/start overlay path.
4. Add a D/P function-equivalence table before expanding through ARM9 and overlays.
