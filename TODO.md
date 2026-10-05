# TODO

## Config (do not create these files until the mods have generated them)
- [ ] **VeinMiner**: set activation to **keybind**, and cut the hunger/exhaustion cost by **50%**. Launch once, find the generated config (and check whether Miraculixx's VeinMiner needs its separate client addon for keybind activation), then commit the config under `config/`.

## Server (itzg/minecraft-server, set up later)
- [ ] `VIEW_DISTANCE=20`
- [ ] `SIMULATION_DISTANCE=10`
- [ ] `HARDCORE=true`
- [ ] `PACKWIZ_URL=https://raw.githubusercontent.com/cherring0011-eng/hardcore-vanilla-plus/main/pack.toml`

## Mods to port to 26.2 Fabric (check each license before redistributing)
- [ ] Enhanced Block Entities
- [ ] Traveler's Titles
- [ ] YUNG's Better Caves
- [ ] YUNG's Better Mineshafts
- [ ] YUNG's Better Dungeons

## Replaced
- EMI → **JEI** 30.29.0.201 (stable). EMI's last release targets 1.21.1; there is an unmerged 1.21.11 port in emilyploszaj/emi#1169.
- [ ] JEI: newer 26.2 builds are beta and require Mezz Config. Stay on stable unless a fix is needed.

## Pre-release builds to upgrade when stable
- [ ] C2ME: `0.4.2-alpha.0.56` (alpha)
- [ ] Sound Physics Remastered: `1.5.1+26.2` (beta)
- [ ] Text Placeholder API: `3.1.0-beta.1` (beta)
