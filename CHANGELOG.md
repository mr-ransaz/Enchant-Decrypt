# Enchant Decrypt changelog

## 0.1.0 — prepared build, not yet published

### Added

- Enchanting-offer hover previews with Minecraft's enchantment names and level formatting.
- Client-only inference that combines observations from manually swapping items, including book-swap calibration.
- Optional server-authoritative exact previews when the mod is installed on both sides.
- Full, partially certain and vanilla-fallback tooltip states, with English and Russian text.
- An experimental NeoForge build alongside the Fabric build.

### Changed

- Public name is Enchant Decrypt; existing mod IDs and jar naming remain unchanged.
- Partial-result hints explain that trying another item can narrow the prediction.
- Uses the author's handmade 128x128 icon.

### Fixed

- Preserve accumulated knowledge across ordinary remote item swaps, table closure, hotbar changes and table changes.
- Retain knowledge after rejected enchant attempts while clearing it after a confirmed new seed.
- Preserve vanilla requirements, colors and compatible tooltip additions.
- Correct NeoForge startup initialization.

### Known limitations

- Client inference can remain ambiguous and assumes vanilla enchanting rules.
- NeoForge has native server and client startup coverage; in-world client behavior and live networking still need manual sign-off.
- External modpacks, custom fonts and altered server enchanting rules require separate compatibility checks.
