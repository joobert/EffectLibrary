# EffectLibrary

A C# library and CLI tool for dumping and rebuilding Nintendo particle effect files (`.ptcl` / `.eff`).

> Requires [.NET 6.0 Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/6.0)

---

## Usage

Drag and drop a `.ptcl` or `.eff` file onto `EffectConverter.exe`.

The tool produces a folder containing all emitter sets, each with their associated shaders, models, and textures. To merge effects, swap emitter set folders between dumps and drag the root folder back onto the .exe to rebuild.

---

## Compatibility

| Feature                             | Status              |
| ----------------------------------- | ------------------- |
| PTCL version ≤ 0x16                 | ✅ Supported        |
| PTCL version > 0x16                 | ❌ Not supported    |
| Compute / Vertex / Fragment shaders | ✅ Verified         |
| Other custom shader types           | ⚠️ May vary by game |
| Smash Ultimate (`.eff` / EFFN)      | ✅ Fully supported  |

Versions above 0x16 are not supported and will not be, as the format changes significantly and is not well-documented.

---

## Smash Ultimate

Smash Ultimate wraps the particle file in an EFFN container that maps emitter sets to in-game effect IDs. This extra data is exported as `NamcoFile.json` alongside the dump. **When merging effects from another file, make sure to update `NamcoFile.json`** to reflect the correct emitter set assignments.

---

## Credits

- [eff_lib](https://github.com/ultimate-research/eff_lib/tree/main) — help with figuring out the EFF header format
- KillzXGaming — original EffectConverter
