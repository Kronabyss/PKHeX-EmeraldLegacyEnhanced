PKHEX Emerald Legacy Enhanced by Krona
=====
PKHeX modified for the Emerald Legacy Enhanced romhack. Properly reads and edits bag inventory.

## Changes from upstream PKHeX

- **Gen 3 data replaced with Emerald Legacy Enhanced (base patch) values.** Base stats, types, abilities, EV yields, catch rates, held items, egg cycles, level-up learnsets, egg moves, TM/HM and tutor compatibility now come from `Pokemon_Emerald_Legacy_Enhanced`. This applies to Ruby/Sapphire, FireRed/LeafGreen and Emerald tables, so standard Gen 3 saves will be checked against Enhanced data.
- **New items 377–400** added to the Gen 3 item list: 21 Mints, Ability Capsule, EXP. All and Shiny Charm. Ability Capsule, Mints and Shiny Charm sit in the Items pocket; EXP. All sits in Key Items.
- **Emerald save layout updated for Enhanced.** Enhanced adds an 8-byte `secretBaseWarp` field to SaveBlock1, so all SaveBlock1 offsets after it are shifted by 8 bytes. Standard Emerald saves will not read correctly with this build.
- **Security key moved to SaveBlock2 0x1F8** for Emerald saves (previously 0xAC). This fixes bag, money and coin decoding.
- **Window title** changed to `PKHEX Emerald Legacy Enhanced by Krona`.

- **Evolutions** replaced with Enhanced `evolution.h` values (22 species changed).
- **Species and item names** checked against the Enhanced source. Four move names keep PKHeX's official spelling.
- **Emerald trainer header** shifted by 4 bytes (`HeaderShift`) to match Enhanced saves, and the security key is read from 0xB0.

## Status

- Core test suite: 368 passed, 1 failed (`TestPublicFiles` on a Gen 4 transfer file: Camerupt's Gen 3 ability changed in Enhanced), 1 skipped.

## To do

- [ ] Confirm the trainer name, trainer ID, money and bag counts display correctly in the app on a real Enhanced save.
- [ ] Update or remove the Camerupt test file so it matches Enhanced's ability data.
- [ ] Check the remaining SaveBlock2 fields (E-Reader trainer data and other offsets not covered by the Joyful Jump check).
- [ ] Translate the new item names (Mints, Ability Capsule, EXP. All, Shiny Charm, Brick Piece) for non-English languages; the English name is used for now.
- [ ] Decide whether to rename `PKHeX.exe` to match the window title.

## Download

Go to the **Releases** page of this repository and download `PKHeX-Emerald-Legacy-Enhanced.zip` from the latest release. No GitHub login is needed.

1. Unzip the file anywhere you like.
2. Run `PKHeX.exe`.

You need the [.NET 9 Desktop Runtime](https://dotnet.microsoft.com/download/dotnet/9.0) (Windows x64). If the app won't start, install it and try again.

To get a build of the latest code without a release, open the **Actions** tab, click the latest **Build PKHeX Emerald Legacy Enhanced** run on `master`, and download the **PKHeX-Emerald-Legacy-Enhanced** artifact. Artifacts need you to be signed in to GitHub.

**Warning:** this build reads Emerald saves using the Enhanced layout. Standard Emerald saves will not load correctly.

## Credits

- **cp1835** — created the PKHeX Emerald Legacy fork this project builds on.
- **Kurt (Kaphotics)** — original PKHeX author.
- **Krona (Kronabyss)** — Emerald Legacy Enhanced changes in this fork.
