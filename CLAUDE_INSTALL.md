# Install Hardcore Vanilla+ with Claude

Copy everything in the box below and paste it into Claude Code (the desktop app's Code tab or the `claude` CLI) on the computer you play Minecraft on. Claude will install Prism Launcher and set up the modpack. You'll still need to sign in to your own Microsoft account, and send your Minecraft username to the server owner so they can whitelist you.

````text
Please set up the "Hardcore Vanilla+" Minecraft modpack on this computer in Prism Launcher. It's a packwiz pack. Prism runs packwiz-installer before every launch, so the mods install and stay up to date automatically.

Pack facts:
- Minecraft 26.2, Fabric Loader 0.19.5, Java 25
- Pack URL: https://raw.githubusercontent.com/cherring0011-eng/hardcore-vanilla-plus/main/pack.toml
- Instance name: Hardcore Vanilla+

Steps:
1. Detect my OS. Install Prism Launcher if it's missing: macOS `brew install --cask prismlauncher`; Windows `winget install PrismLauncher.PrismLauncher`; Linux use Flatpak `org.prismlauncher.PrismLauncher` or my distro's package. Tell me before anything that needs an admin password.
2. Make sure a Java 25 JDK is available, e.g. Eclipse Temurin 25 (macOS `brew install --cask temurin@25`, or a user-level tarball from api.adoptium.net if that needs a password; Windows `winget install EclipseAdoptium.Temurin.25.JDK`; Linux the Adoptium package or tarball). Find the full path to its java executable (javaw.exe on Windows).
3. Quit Prism Launcher if it's running. It rewrites instance files when it closes, so it must be closed while you edit them. Find Prism's data folder: macOS `~/Library/Application Support/PrismLauncher`, Windows `%APPDATA%\PrismLauncher`, Linux `~/.local/share/PrismLauncher` or the Flatpak one `~/.var/app/org.prismlauncher.PrismLauncher/data/PrismLauncher`. If it doesn't exist yet, open Prism once so it creates it, finish its first-run setup, then quit it again.
4. Create the folder `instances/Hardcore Vanilla+/minecraft` inside it.
5. Download https://github.com/packwiz/packwiz-installer-bootstrap/releases/latest/download/packwiz-installer-bootstrap.jar into that `minecraft` folder.
6. Write `instances/Hardcore Vanilla+/mmc-pack.json`:
   {
       "components": [
           { "uid": "net.minecraft", "version": "26.2", "important": true },
           { "uid": "net.fabricmc.intermediary", "version": "26.2", "dependencyOnly": true },
           { "uid": "net.fabricmc.fabric-loader", "version": "0.19.5" }
       ],
       "formatVersion": 1
   }
7. Write `instances/Hardcore Vanilla+/instance.cfg`. IMPORTANT: this is a Qt INI file. The PreLaunchCommand value must be wrapped in quotes with its inner quotes backslash-escaped exactly as shown, or Prism mangles it into "$INST_JAVA-jar" and every launch fails with "Pre-Launch command failed with code 0". Replace <JAVA_PATH> with the java path from step 2 (on Windows write it with forward slashes), and set MaxMemAlloc to 6144, or 4096 if this computer has 8 GB of RAM or less:
   [General]
   ConfigVersion=1.2
   InstanceType=OneSix
   name=Hardcore Vanilla+
   iconKey=default
   OverrideCommands=true
   PreLaunchCommand="\"$INST_JAVA\" -jar packwiz-installer-bootstrap.jar https://raw.githubusercontent.com/cherring0011-eng/hardcore-vanilla-plus/main/pack.toml"
   OverrideJavaLocation=true
   JavaPath=<JAVA_PATH>
   OverrideMemory=true
   MinMemAlloc=1024
   MaxMemAlloc=6144
8. Test the pack install without the GUI: from inside the instance's `minecraft` folder, run `<java> -jar packwiz-installer-bootstrap.jar -g -s client <pack URL>`. It should end with "Finished successfully!". Check that `mods/` holds about 36 jars and `shaderpacks/` holds 2 zips.
9. Open Prism Launcher. Don't sign in for me. Tell me to add my Microsoft account (Accounts, top right, then Manage Accounts, then Add Microsoft), then select "Hardcore Vanilla+" and click Launch.
10. If the launch fails, read Prism's log (`logs/` in the Prism data folder) and the instance log (`instances/Hardcore Vanilla+/minecraft/logs/latest.log`), fix the cause, and tell me what was wrong.

Don't change anything outside Prism, Java and this instance. When you're done, give me a short summary, and remind me to send my Minecraft Java username to the server owner for the whitelist and to ask them for the server address.
````
