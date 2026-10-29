<h1 align="center">MCP — Mod Coder Pack</h1>

<p align="center">
  An archive of MCP releases, each matched to the Minecraft client and server version it decompiles.
</p>

<p align="center">
  <a href="#downloads">Downloads</a> •
  <a href="#requirements">Requirements</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#commands">Commands</a> •
  <a href="#credits">Credits</a>
</p>

---

## Downloads

Pick the release that matches your Minecraft version. Client and server versions are always the same.

| MCP | Minecraft | Download |
| :-- | :-- | :-- |
| 9.40 | 1.12 | [`mcp940.zip`](mcp940.zip) |
| 9.37 | 1.11.2 | [`mcp937.zip`](mcp937.zip) |
| 9.31 | 1.10 | [`mcp931.zip`](mcp931.zip) |
| 9.28 | 1.9.4 | [`mcp928.zip`](mcp928.zip) |
| 9.18 | 1.8.8 | [`mcp918.zip`](mcp918.zip) |
| 9.08 | 1.7.10 | [`mcp908.zip`](mcp908.zip) |

> **Tip:** MCP is version-locked. 9.40 will not work on 1.11.2, and 9.08 will not work on 1.8.8. Match the row exactly.

---

## Requirements

- **Java JDK 8** — the JDK, not just the JRE. `javac -version` should print a version.
- **Python 2.7** — required by the MCP scripts.
- A copy of the matching Minecraft version, already run once through the launcher.
- Roughly 2 GB of free disk space per workspace.

---

## Getting Started

**1. Extract**

Unzip your chosen release into a folder with **no spaces in the path**.

```
C:\mcp940\        ✅
C:\My Mods\mcp\   ❌
```

**2. Add the game files**

Copy these from your `.minecraft` folder into `jars/`:

```
versions/<version>/<version>.jar
versions/<version>/<version>.json
libraries/
assets/
```

**3. Decompile**

From the MCP folder, run:

```bash
decompile.bat        # Windows
./decompile.sh       # macOS / Linux
```

This takes a few minutes. When it finishes, the source is in `src/minecraft/`.

**4. Edit, then build**

Make your changes, then:

```bash
recompile.bat
reobfuscate.bat
```

Your output lands in `reobf/`, ready to drop into a jar.

---

## Commands

| Script | What it does |
| :-- | :-- |
| `decompile` | Turns the game jars into readable source |
| `recompile` | Compiles your edited source |
| `reobfuscate` | Converts names back to obfuscated form for release |
| `updatemd5` | Rebuilds checksums so only changed classes are reobfuscated |
| `startclient` | Launches the client from your compiled source |
| `startserver` | Launches the server from your compiled source |
| `cleanup` | Wipes the workspace back to a fresh extract |

---

## Troubleshooting

**`javac` not found** — You have the JRE but not the JDK, or Java isn't on your `PATH`.

**Decompile fails immediately** — Check for spaces in your folder path, and confirm the jar and json in `jars/` match the MCP version.

**Nothing changes after editing** — Run `updatemd5` once, then recompile.

**Python errors** — MCP needs Python 2.7. Python 3 will not run these scripts.

---

## Credits

MCP is the work of **Searge**, **ProfMobius**, **Fesh0r**, **ZeuX**, **R4wk**, **Bspkrs** and the rest of the MCP team. This repository only mirrors their releases for archival convenience — all rights and credit belong to the original authors, and the terms in each archive's own license file apply.

Minecraft is a trademark of Mojang Studios. This project is not affiliated with or endorsed by Mojang or Microsoft.
