PKHEX Emerald Legacy Enhanced by Krona
=====
PKHeX modified for the Emerald Legacy Enhanced romhack. Properly reads and edits bag inventory.

## Changes from upstream PKHeX

- **Gen 3 data replaced with Emerald Legacy Enhanced (base patch) values.** Base stats, types, abilities, EV yields, catch rates, held items, egg cycles, level-up learnsets, egg moves, TM/HM and tutor compatibility now come from `Pokemon_Emerald_Legacy_Enhanced`. This applies to Ruby/Sapphire, FireRed/LeafGreen and Emerald tables, so standard Gen 3 saves will be checked against Enhanced data.
- **New items 377–400** added to the Gen 3 item list: 21 Mints, Ability Capsule, EXP. All and Shiny Charm. Ability Capsule, Mints and Shiny Charm sit in the Items pocket; EXP. All sits in Key Items.
- **Emerald save layout updated for Enhanced.** Enhanced adds an 8-byte `secretBaseWarp` field to SaveBlock1, so all SaveBlock1 offsets after it are shifted by 8 bytes. Standard Emerald saves will not read correctly with this build.
- **Window title** changed to `PKHEX Emerald Legacy Enhanced by Krona`.

- **Evolutions** replaced with Enhanced `evolution.h` values (22 species changed).
- **Species and item names** checked against the Enhanced source. Four move names keep PKHeX's official spelling.
- **Emerald trainer header** shifted by 4 bytes (`HeaderShift`) to match Enhanced saves, and the security key is read from 0xB0.

## Status

- Core test suite: 368 passed, 1 failed (`TestPublicFiles` on a Gen 4 transfer file: Camerupt's Gen 3 ability changed in Enhanced), 1 skipped.

## To do

- [ ] Translated item names for the new Enhanced items (Mints, Ability Capsule, EXP. All, Shiny Charm, Brick Piece) in non-English languages. English names are used for now.
- [ ] E-Reader trainer data for Enhanced Emerald saves.

## Download

Go to the **Releases** page of this repository and download `PKHeX-Emerald-Legacy-Enhanced.zip` from the latest release. No GitHub login is needed.

1. Unzip the file anywhere you like.
2. Run `PKHeX.exe`.

You need the [.NET 9 Desktop Runtime](https://dotnet.microsoft.com/download/dotnet/9.0) (Windows x64). If the app won't start, install it and try again.

To get a build of the latest code without a release, open the **Actions** tab, click the latest **Build PKHeX Emerald Legacy Enhanced** run on `master`, and download the **PKHeX-Emerald-Legacy-Enhanced** artifact. Artifacts need you to be signed in to GitHub.

**Warning:** this build reads Emerald saves using the Enhanced layout. Standard Emerald saves will not load correctly.

## Build your own copy with GitHub Actions

You can build this project yourself on GitHub without installing anything locally.

1. **Fork the repository.** Click **Fork** at the top of the repository page and create a copy under your account.
2. **Enable Actions on your fork.** Open the **Actions** tab. If GitHub asks, click **I understand my workflows, go ahead and enable them**.
3. **Run the build.** Go to **Actions → Build PKHeX Emerald Legacy Enhanced**, click **Run workflow**, and choose the `master` branch. The workflow also runs automatically each time you push to `master`.
4. **Download the result.** When the run finishes (a few minutes), open it and download the **PKHeX-Emerald-Legacy-Enhanced** artifact from the bottom of the page. Unzip it and run `PKHeX.exe`. You need to be signed in to GitHub to download artifacts.
5. **Make a release (optional).** Push a version tag such as `v1.0.0` to your fork, either from GitHub Desktop or with `git tag v1.0.0` and `git push origin v1.0.0`. The workflow then publishes the zip on your fork's **Releases** page, where anyone can download it without signing in.

To change the code, edit it on your fork (or clone it and push your changes). Each push to `master` rebuilds the app.

## Credits

- **cp1835** — created the PKHeX Emerald Legacy fork this project builds on.
- **Kurt (Kaphotics)** — original PKHeX author.
- **Krona (Kronabyss)** — Emerald Legacy Enhanced changes in this fork.
