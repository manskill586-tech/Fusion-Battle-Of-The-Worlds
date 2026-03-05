# Fusion: Battle Of The Worlds

Single-file offline merge-shooter in retro pixel style.

## About
`Fusion: Battle Of The Worlds` is a browser game that combines:
- merge mechanics (drag units to merge),
- lane defense/shooter combat,
- endless wave progression,
- persistent local campaign.

The whole game runs from one file: `index.html`.

## Core Features
- 2x4 unit board on the left + combat field on the right.
- 7 unit archetypes with leveling and hybrid merges.
- Auto-merge with configurable cap.
- Abilities: Nova, Shield, Overdrive.
- Mini-boss every 3 waves, major boss every 10 waves.
- Enemy projectiles can damage and destroy units.
- Permanent local progression with autosave.
- Rollback on defeat: fallback by 2 waves with snapshot restore logic.
- Daily quests, weekly local season, offline rewards.
- Procedural audio (SFX + adaptive music) without external files.

## Controls
### Desktop
- Drag & drop unit: move/merge.
- Drag unit to Trash: delete (with short undo window).
- Left click in combat area: pulse shot.
- `1 / 2 / 3`: abilities.
- `Space`: pause.
- `A`: toggle auto-merge.
- `C`: cycle auto-merge cap.

### Mobile
- Drag & drop with touch.
- Left/Right drawer buttons open side panels.
- Quick bottom actions for Buy / Auto / Repair.
- Tap combat field for pulse shot.

## Progression and Economy
- Resources: Coins, Gems, XP, Energy.
- Account level unlocks stronger unit types.
- Tech upgrades affect damage, fire rate, economy and utility.
- Buy chances scale by chapter (low-level drops become less likely later).

## Save System
The game uses `localStorage` with active + backup strategy:
- `fusion_space_merge_active_v1`
- `fusion_space_merge_backup_v1`
- `fusion_space_merge_meta_v1`
- `fusion_space_merge_settings_v1`

Autosave triggers on key actions (buy, merge, upgrades, wave transitions, rollback, pause, tab visibility change).

## Run Locally
1. Open `index.html` in a modern browser.
2. Click **New Campaign**.
3. Play fully offline.

No server and no external CDN assets are required.

## Mobile UX Notes
- Layout automatically switches to drawer mode on smaller/coarse-pointer devices.
- Safe-area insets are used for notched phones.
- Canvas scales with viewport (`16:9`) while preserving pixel look.

## Reset Progress
Use **Reset Progress** in menu/panel (double-confirm flow).
This clears campaign and local meta save data.
