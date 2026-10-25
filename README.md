# Enchant Decrypt

![Enchant Decrypt icon](icon.png)

Enchant Decrypt by MR Ransaz is a passive Minecraft mod that previews enchanting-table offers before you spend your levels and lapis. Hover an offer to see the predicted enchantments, using Minecraft's own names and level formatting. It can reconstruct results with only the client installed on a vanilla server, gaining certainty as you manually try different items; when a compatible server also has the mod, its authoritative exact preview takes priority. Fabric is the established implementation; the NeoForge build is experimental and still needs in-world client compatibility sign-off.

## What it does

- Shows a full enchantment list when the server supplies an exact result or all remaining client candidates agree.
- Shows only shared enchantments and a short uncertainty hint when a result is partial.
- Keeps the vanilla tooltip while searching or when no reliable preview is available.
- Preserves vanilla's lapis/level requirements and their colors, including red unmet requirements.
- Includes English and Russian text, with enchantment names and levels supplied by the game.
- Does not move items, automate inventory actions or send extra container clicks.

## How it works

### Client-side reconstruction on vanilla servers

The client observes the item, synchronized offer costs and clues. It narrows the possible player enchantment seeds across observations and compares their outcomes. This reconstruction adds no preview packets or inventory automation; you place and swap items yourself.

Use a **book swap to calibrate**: put a book in the table, then return to the item you want to enchant. If the hint remains, try other different items, such as a chestplate and bow, before returning to your pickaxe. Do not enchant between observations. Each item adds constraints for the same player seed; another table can also help. Calibration improves the evidence, but does not guarantee a unique seed or a full result.

Knowledge is held only in memory. A real enchant starts a new seed, so calibration starts over. Disconnecting, changing worlds or contradictory observations also clear knowledge. Closing the table, changing hotbar slots or switching tables preserves completed observations.

### Optional exact server mode

For server-authoritative exact results, install the matching mod build on the compatible server as well as the client. The server uses its actual enchanting selection path and full inputs. Those results take priority over reconstruction. Normal singleplayer also has the mod on its integrated server, so it normally uses exact mode.

Client-only certainty means agreement under the vanilla enchanting model. Hidden server plugins or mods that change the later enchant action can invalidate that model; no universal guarantee is made for altered rules.

## Requirements

These are the tested build profiles, not a promise of compatibility with every later loader release.

| Requirement | Fabric build | NeoForge build |
| --- | --- | --- |
| Minecraft | 26.3 | 26.3 |
| Java | 25 | 25 |
| Loader | Fabric Loader 0.19.5 | NeoForge 26.3.0.99 |
| Required API | Fabric API 0.164.0+26.3 | Included NeoForge platform; no Fabric API |
| Validation status | Unit, server and in-world graphics tests | Native server tests and client startup smoke; in-world client sign-off pending |

No settings library or configuration screen is required. Forge, Quilt and other Minecraft versions are not supported claims.

## Download

Download the latest build from the **Releases section of this repository** (right sidebar, or the Releases tab). Choose the jar for your loader:

- **Fabric:** `mrransazenchantreveal-0.1.0+mc26.3-fabric.jar`
- **NeoForge, experimental:** `mrransazenchantreveal-0.1.0+mc26.3-neoforge.jar`

Release assets include `SHA256SUMS.txt` for integrity checking. If the Releases section is empty, no GitHub release has been published yet. Prepared copies are included in this repository's `release/` folder. Do not install both loader jars together.

## Installation

1. Use Minecraft 26.3 with Java 25 and install the loader matching your chosen jar.
2. For Fabric, install Fabric API as well. Do not add Fabric API to a NeoForge profile.
3. Put the chosen Enchant Decrypt jar in that profile's `mods` folder, then launch the game.
4. Open an enchanting table, insert an item and hover an active offer. On a vanilla server, try the book-swap calibration described above.
5. For optional server-exact mode, install the same loader's mod build on the server too. A Fabric server also needs Fabric API. Client reconstruction does not require a server installation.

## Honest limitations

- Tools, armor and weapons can remain ambiguous after one or several observations. Books often provide more useful clues, but a full preview is not guaranteed.
- Enchanting changes the player seed. Previous calibration cannot predict the next seed.
- Reconstruction assumes vanilla selection rules and synchronized data. Server-only changes, custom enchanting menus or unusual mod hooks may prevent a preview or produce behavior outside that model.
- Datapack and registered-item fixtures have automated coverage; arbitrary enchantment mods, tooltip mods, custom fonts and remote modpacks do not have universal compatibility sign-off.
- NeoForge remains experimental: native server parity and client startup checks passed, but live client tooltips, exact networking and vanilla-server fallback still need manual in-world sign-off.
- Very tall or unavailable results fall back to vanilla. A partial list never presents an arbitrary candidate as certain.

## FAQ

**Does the server need the mod?**

No for client reconstruction. Yes for the server-authoritative exact mode. A server without the mod can still be used for client inference, subject to the vanilla-model limits above; NeoForge's live client path remains experimental.

**Why do books show more than my pickaxe?**

Their offers can provide more distinctive constraints. Swap a book in and return to the pickaxe, then try other items without enchanting if it is still uncertain.

**Does a full client preview mean the hidden seed is known?**

Not necessarily. Several seeds may remain while all of them give the same outcome for that offer. Certainty concerns the outcome under the client model.

**Why is singleplayer immediately exact?**

The integrated server runs the installed mod and supplies the optional exact result.

**Is this an inventory macro?**

No. It is a passive preview. You perform every item swap and enchant yourself; the mod adds no automated container clicks. Server rules about preview mods still apply.

**Is my calibration saved?**

No. Learned candidates stay in memory and are cleared on disconnect or world change. They are not written to a player-history file.

**Where are the source files?**

This showcase contains public documentation, the author's icon and compiled distribution jars. It contains no source tree or private development history.

## Credits and license

Enchant Decrypt is an independent implementation by **MR Ransaz**, inspired by the behavior of [Enchantment Reveal by CrownSheep](https://github.com/CrownSheep/Enchantment-Reveal), which is MIT-licensed. No code or artwork from that project is included. This project is not affiliated with CrownSheep's project, Mojang or Microsoft.

Enchant Decrypt is distributed under the [MIT License](LICENSE). The icon is handmade by the author; no AI-generated images are included.

## Development disclosure

The mod was developed with AI coding assistance from **OpenAI Codex**. Design, testing and verification are led by the author, **MR Ransaz**. This disclosure concerns code assistance; the supplied icon is the author's handmade artwork.
