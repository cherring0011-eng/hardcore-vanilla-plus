# Hardcore Vanilla+

A hardcore **"Vanilla+ Lite"** modpack for **Minecraft 26.2** on **Fabric** (loader 0.19.5), managed with [packwiz](https://packwiz.infra.link/).

The goal is vanilla gameplay that looks, sounds and runs better, plus a shared-health hardcore twist. No mod in this pack adds new blocks or biomes.

## Mods

| Category | Mod | Side |
|---|---|---|
| Core | Shared Health | server |
| Core | Fabric API | both |
| Core | AppleSkin | both |
| Core | VeinMiner (Miraculixx) | both |
| Performance | Sodium | client |
| Performance | Lithium | both |
| Performance | FerriteCore | both |
| Performance | ImmediatelyFast | client |
| Performance | Entity Culling | client |
| Performance | C2ME (Concurrent Chunk Management Engine) | both |
| Visuals | Iris Shaders | client |
| Visuals | Subtle Effects | client |
| Visuals | Falling Leaves | client |
| Visuals | Particle Effects | client |
| Visuals | Imprint | client |
| Visuals | First-person Model | client |
| Visuals | ItemPhysic Lite | client |
| Sound | AmbientSounds | client |
| Sound | Sound Physics Remastered | client |
| GUI / QoL | Spatial GUI (tastytrash) | client |
| GUI / QoL | Mod Menu | client |
| GUI / QoL | Cloth Config API | client |
| GUI / QoL | Controlling | client |
| GUI / QoL | Mouse Tweaks | client |
| GUI / QoL | Leaves Be Gone | both |
| GUI / QoL | JEI (Just Enough Items) | both |
| Map | Xaero's Minimap | client |
| Map | Xaero's World Map | client |

**Shader packs** (in `shaderpacks/`, select in-game via Options → Video Settings → Shader Packs): Complementary Shaders – Unbound, BSL Shaders.

**Libraries pulled in automatically:** Fabric Language Kotlin, Fzzy Config, CreativeCore, Not Enough Animations, Text Placeholder API, Searchables, Forge Config API Port, Puzzles Lib.

**Skipped (no 26.2 Fabric build):** Enhanced Block Entities, Traveler's Titles, YUNG's Better Caves, YUNG's Better Mineshafts, YUNG's Better Dungeons. They'll be added if official 26.2 builds are released.

**Replaced:** EMI has no 26.2 build, so the pack uses **JEI** as its recipe viewer. JEI is also installed on the server, because since 1.21.2 the server must send recipe data to clients.

## Coming later

Planned custom work, not started yet:

- **Particulate** (waterfall and splash particles): port from 1.21.11 to 26.2.
- **Diet** (food groups): port from 1.20.1 to 26.2.
- **Food Buffs**, a custom mod: cooked foods give status buffs, with 3 buff slots per player.

## Installing (friends): Prism Launcher

The pack auto-updates every time you launch, using [packwiz-installer](https://github.com/packwiz/packwiz-installer).

1. Install [Prism Launcher](https://prismlauncher.org/).
2. **Add Instance** → Vanilla → **26.2**. Name it `Hardcore Vanilla+` → OK.
3. Select the instance → **Edit** → **Version** → **Install Loader** → **Fabric** → pick **0.19.5** → OK.
4. Download `packwiz-installer-bootstrap.jar` from the [latest release](https://github.com/packwiz/packwiz-installer-bootstrap/releases/latest).
5. In the instance, click **Folder** to open the instance directory. Open the `minecraft` folder (called `.minecraft` on some setups) and put `packwiz-installer-bootstrap.jar` in it.
6. **Edit** → **Settings** → **Custom commands** → tick **Custom commands** and set **Pre-launch command** to:

   ```
   "$INST_JAVA" -jar packwiz-installer-bootstrap.jar https://raw.githubusercontent.com/cherring0011-eng/hardcore-vanilla-plus/main/pack.toml
   ```

7. Close the settings and **Launch**. On the first launch packwiz-installer downloads all mods. Accept any prompts it shows. Later launches pull in updates automatically.

Server-only mods (Shared Health) are not installed on clients. They run on the server.

## Server

The server (itzg/minecraft-server) will install the same pack with:

```
PACKWIZ_URL=https://raw.githubusercontent.com/cherring0011-eng/hardcore-vanilla-plus/main/pack.toml
```

Only mods tagged `server` or `both` are installed there. See [TODO.md](TODO.md) for pending server settings.

## Maintaining the pack

```bash
packwiz modrinth add <slug>   # add a mod
packwiz update --all          # update everything
packwiz refresh               # rebuild index.toml after manual edits
```

Commit and push after every change. Clients and the server pick up updates on their next launch or restart.
