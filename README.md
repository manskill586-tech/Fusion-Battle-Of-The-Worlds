# Fusion: Battle Of The Worlds

Single-file offline merge-shooter in retro pixel style.

## About
`Fusion: Battle Of The Worlds` combines:
- merge mechanics (drag units to merge),
- lane defense/shooter combat,
- endless wave progression,
- persistent local campaign progression.

Everything runs from one file: `index.html`.

## Core Features
- 2x4 unit board on the left + combat field on the right.
- 7 unit archetypes with leveling and hybrid merges.
- Auto-merge with configurable cap.
- Abilities: Nova, Shield, Overdrive.
- Mini-boss every 3 waves, major boss every 10 waves.
- Enemy attacks can damage and destroy your units.
- Permanent local progression with autosave.
- Defeat rollback by 2 waves with snapshot restore logic.
- Daily quests, local weekly season, offline rewards.
- Procedural audio (SFX + adaptive music), no external assets.

## Controls
### Desktop
- Drag & drop unit: move/merge.
- Drag unit to Trash: delete (short undo window).
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

## Beginner Guide
### Quick Start (2-3 minutes)
1. Press **New Campaign**.
2. In the left panel, press **Buy Unit** 2-3 times.
3. Merge matching units by dragging one onto another.
4. If base HP drops, press **Repair Base**.
5. Use abilities (`1 / 2 / 3` or right-panel buttons) during pressure spikes.
6. On defeat, choose **Rollback 2 Waves** if you do not want to spend gems.

### Core Combat Loop
1. Units fire automatically.
2. You scale power through buying, merging, and tech upgrades.
3. You can assist manually via pulse shot in the combat area.
4. Balance economy between expansion (buy/merge) and stability (repair/upgrades).

## Full Button and UI Guide
### Top HUD
| Element | Meaning |
| --- | --- |
| `Wave / Chapter` | Current wave and chapter |
| `Coins / Energy` | Currency for purchases and session energy |
| `Gems / XP` | Premium currency and account experience |
| `Base HP / Lives` | Base durability and remaining lives |

### Left Panel (Command Market)
| Button | Effect | Typical Use |
| --- | --- | --- |
| `Buy Unit` | Buys a new unit into a free board slot | Early and mid-wave scaling |
| `Tech: Damage` | Global damage upgrade for all units | When enemies become too tanky |
| `Tech: Fire Rate` | Global fire-rate upgrade | When sustained DPS is too low |
| `Tech: Coin Boost` | Improves coin economy | Faster long-term scaling |
| `Tech: Energy Max` | Increases max energy and utility progression | Longer campaign sessions |
| `Auto Merge: ON/OFF` | Enables/disables auto-merge | Convenience and faster board cleanup |
| `Auto Cap: Lx` | Sets max level for auto-merge | Keep control of high-level units |
| `Repair Base` | Heals base and increases max HP growth path | Base survival recovery |
| `Claim Offline Rewards` | Claims offline income | After returning to the game |
| `Sell Selected` | Sells selected unit for coins | Emergency economy boost |
| `Trash Selected` | Deletes selected unit | Remove unwanted unit safely |
| `Heal Selected` | Heals selected unit | Preserve high-value units |
| `Reset Progress` | Full campaign reset (double-confirm) | Start from clean state |

### Right Panel (Tactical Systems)
| Button | Effect | Typical Use |
| --- | --- | --- |
| `1 Nova` | Heavy AoE burst | Dense waves, emergency clears |
| `2 Shield` | Temporary base protection | Before boss burst or heavy projectile phases |
| `3 Overdrive` | Fire-rate spike buff | Burst windows, boss pressure |
| `Pause` | Pauses gameplay | Break or tactical planning |
| `Settings` | Opens settings UI | Audio and accessibility adjustments |
| `Undo Trash` | Restores recently trashed unit | Immediate misclick recovery |

### Other UI Elements
| Element | Meaning |
| --- | --- |
| `TRASH ZONE` | Drop a dragged unit here to remove it |
| `Audio Mix` | Quick volume control (Master/Music/Effects/Ambience/UI) |
| `Tips / Status / Log` | Hints, priority messages, recent event history |
| `Daily quests / Weekly season` | Local meta progression and rewards |

### Defeat Screen
| Button | Effect |
| --- | --- |
| `Continue (Gems)` | Continue immediately by spending gems |
| `Rollback 2 Waves` | Roll back two waves and restore stored snapshot state |

## Unit Labels
| Code | Type |
| --- | --- |
| `SNG` | Single |
| `BST` | Burst |
| `SNP` | Sniper |
| `SHT` | Shotgun |
| `RCK` | Rocket |
| `LSR` | Laser |
| `MTR` | Mortar |

## Practical Starter Tips
1. In early waves, prioritize `Buy Unit` plus fast merges to stabilize DPS.
2. Do not merge blindly: two mid-level units can outperform one over-merged unit in some wave states.
3. Keep a coin reserve for emergency `Repair Base` and a quick buy.
4. Use `Nova` on clustered enemies; save `Shield` for incoming burst phases.
5. If you accidentally delete a unit, use `Undo Trash` immediately.
6. During boss waves, spending abilities early is usually better than holding them too long.

## Progression and Economy
- Resources: Coins, Gems, XP, Energy.
- Account level unlocks stronger unit types.
- Tech upgrades improve combat, economy, and utility.
- Buy level distribution scales by chapter (low-level drop chance decreases over time).

## Save System
The game uses `localStorage` with active + backup strategy:
- `fusion_space_merge_active_v1`
- `fusion_space_merge_backup_v1`
- `fusion_space_merge_meta_v1`
- `fusion_space_merge_settings_v1`

Autosave triggers on key events (buy, merge, upgrade, wave transitions, rollback, pause, visibility change).

Rollback note: defeat rollback restores a stored state from two waves earlier, including units and their snapshot stats/state.

## Run Locally
1. Open `index.html` in a modern browser.
2. Click **New Campaign**.
3. Play fully offline.

No server and no external CDN assets are required.

## Mobile UX Notes
- Layout automatically switches to drawer mode on smaller/coarse-pointer devices.
- Safe-area insets are used for notched phones.
- Canvas scales to viewport while preserving `16:9` and pixel rendering.

## Reset Progress
Use **Reset Progress** in menu/panel (double-confirm flow).  
This clears campaign and local meta save data.
