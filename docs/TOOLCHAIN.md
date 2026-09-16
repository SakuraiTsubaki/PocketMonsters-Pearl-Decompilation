# Toolchain — Pearl

Install the common Nintendo DS reverse-engineering stack with:

```sh
bash tools/bootstrap_nds_toolchain.sh
source "$HOME/.local/share/pokemon-gen4-nds-toolchain/toolchain.env"
python3 tools/check_toolchain.py
```

The bootstrap covers Git/Python/build tools, Clang/LLVM/LLD, GNU Arm binutils and GDB, Wine, libpng/pkg-config/pugixml, ndstool, devkitPro `nds-dev`/devkitARM/libnds, Python RE helpers, melonDS, and optional DeSmuME/xdelta3/bsdiff.

Primary emulator is **melonDS 1.1**. The official Ubuntu x86_64 asset SHA-256 is `99465129f5413b2aad332e4377e523cf3cda905dc329d47dcb1ad01ce2cb3f66`.

External US Diamond/Pearl matching references use MWCC 2.0/sp1 plus 1.2/sp2p3 and NitroSDK 3.2-060901. Treat those versions as reference evidence for the current USA target until each matching-build assumption is independently verified. Proprietary MWCC/NitroSDK files are never auto-downloaded or committed; point `MWCCARM_ROOT` and `NITROSDK_ROOT` at user-supplied copies when needed.

BIOS, firmware, retail ROMs, and proprietary console material remain local only.
