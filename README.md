PKHEX Emerald Legacy Enhanced by Krona
=====
PKHeX modified for the Emerald Legacy Enhanced romhack. Properly reads and edits bag inventory.

## Changes from upstream PKHeX

- **Gen 3 data replaced with Emerald Legacy Enhanced (base patch) values.** Base stats, types, abilities, EV yields, catch rates, held items, egg cycles, level-up learnsets, egg moves, TM/HM and tutor compatibility now come from `Pokemon_Emerald_Legacy_Enhanced`. This applies to Ruby/Sapphire, FireRed/LeafGreen and Emerald tables, so standard Gen 3 saves will be checked against Enhanced data.
- **New items 377–400** added to the Gen 3 item list: 21 Mints, Ability Capsule, EXP. All and Shiny Charm. Ability Capsule, Mints and Shiny Charm sit in the Items pocket; EXP. All sits in Key Items.
- **Emerald save layout updated for Enhanced.** Enhanced adds an 8-byte `secretBaseWarp` field to SaveBlock1, so all SaveBlock1 offsets after it are shifted by 8 bytes. Standard Emerald saves will not read correctly with this build.
- **Security key moved to SaveBlock2 0x1F8** for Emerald saves (previously 0xAC). This fixes bag, money and coin decoding.
- **Window title** changed to `PKHEX Emerald Legacy Enhanced by Krona`.

Known gaps: evolutions and species/move/ability name lists have not yet been checked against the Enhanced source, and the test suite still expects standard Gen 3 data.
