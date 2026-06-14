# 10 ROOMS

> A first-person wave shooter built entirely in the browser with Three.js — no installs, no engine, just pure chaos across ten escalating rooms.
>
> *by mufarrizz*

---

## Play

Open `https://mufarrizz.github.io/10rooms/` in any modern browser. Click to lock your mouse and start shooting.

---

## Objective

Fight through **10 hand-crafted rooms**, each with its own layout, lighting theme, and enemy composition. Clear every enemy in a room to unlock the green portal, then walk through it to advance. Survive all ten rooms to win.

---

## Controls

| Input | Action |
|---|---|
| `W A S D` | Move |
| `Mouse` | Aim |
| `Left Click` | Shoot |
| `Right Click (hold)` | Scope / Zoom |
| `Shift` | Sprint (drains stamina) |
| `Space` | Jump |
| `R` | Reload from reserve |
| `G` | Throw grenade |

---

## HUD

| Element | What it shows |
|---|---|
| **Health bar** (bottom-left) | Current HP out of 100, colour shifts green → orange → red as you take damage |
| **Armor bar** (thin bar below health) | Damage absorption — absorbs 60% of incoming hits before health is touched |
| **Stamina bar** | Sprint fuel — regenerates automatically when you stop sprinting |
| **Ammo** (bottom-right) | Magazine / max, plus reserve count below |
| **Grenades** | Pip count next to ammo |
| **Enemy counter** (top-centre) | Enemies remaining in the current room |
| **Room** (top-left) | Current room out of 10 |
| **Score** (top-left) | Running score, boosted by kill streaks |
| **Threat level** (top-right) | LOW → MODERATE → HIGH → EXTREME → LETHAL as rooms progress |
| **Boss bar** (below enemy counter) | Only visible in Room 10 — tracks the Final Guardian's HP |
| **Minimap** (bottom-right) | Top-down view: white arrow = you, red dots = enemies, green square = exit portal |
| **Kill feed** (right side) | Rolling log of kills; turns gold during a streak |
| **Streak popup** (centre) | TRIPLE KILL / QUAD KILL / RAMPAGE / UNSTOPPABLE flashes at 3+ streak |

---

## Weapons & Combat

### Gun
- **Magazine:** 24 rounds
- **Reserve:** 90 rounds (up to 120 with pickups)
- **Reload:** Press `R` — pulls from reserve, takes ~0.7 seconds
- **Scoped shot:** Hold right-click to zoom in; scoped hits deal **2× damage**
- **Muzzle flash** and **bullet trail** on every shot
- **Hit marker** confirms a hit; enemy flashes orange

### Grenades
- Start with **3 grenades**; press `G` to throw
- Physics-based arc with a fuse timer
- Explosion radius of 6 units — damages all enemies inside, with falloff
- Can damage yourself if you're too close (stay back)

---

## Enemy Types

| Type | Colour | Behaviour | Threat |
|---|---|---|---|
| **Grunt** | Red | Standard advance-and-shoot soldier | Low |
| **Scout** | Orange | Fast, light, fires quickly at close range | Medium |
| **Heavy** | Purple | Slow, heavily armoured, high HP, hits hard | High |
| **Sniper** | Blue | Hangs back, keeps distance, low fire rate but punishing hits | High |
| **Berserker** | Bright Red | No gun — rushes you with wrist blades, extremely fast | High |
| **Final Guardian** | Orange/Fire | Boss. Large, strafes, dual shoulder cannons, glowing core | Lethal |

All enemies:
- Only **alert** when you enter their detection range
- **Navigate around obstacles** — they slide along walls and find angles rather than walking through cover
- Only **shoot when they have a clear line of sight** to you — hiding behind a pillar actually blocks their shots
- Have **type-specific movement patterns** (sniper backs away, berserker charges, boss strafes)

---

## Pickups

Dropped randomly by killed enemies:

| Pickup | Colour | Effect |
|---|---|---|
| **Health Pack** | Green cross | +35 HP (up to 100) |
| **Ammo Pack** | Orange box | +18 reserve ammo (up to 120) |
| **Armor Shard** | Blue plate | +30 armor (up to 60) |

Walk over them to collect. All pickups float and rotate so they're easy to spot.

Between rooms you automatically receive **+20 reserve ammo** as a transition bonus.

---

## Rooms

| Room | Theme | Hazard |
|---|---|---|
| 1 | Open blue-grey arena | None — tutorial pacing |
| 2 | Narrow teal corridor with alternating cover | Tight angles |
| 3 | Dark red 4-pillar arena with central block | Getting flanked |
| 4 | Green maze of tall thin walls | Navigation |
| 5 | Purple multi-level platforms and ramp barriers | Mixed range |
| 6 | Dark blue with raised sniper nests at each end | Long sightlines |
| 7 | Lava/fire room — **hazard floor** | Standing on the ground deals damage |
| 8 | Crimson Berserker horde room | Melee swarm |
| 9 | Cyan elite mix — all five types | Everything at once |
| 10 | Boss room — the Final Guardian | Endgame |

---

## Scoring

- Each kill awards the enemy's base score value
- A **kill streak multiplier** kicks in when you kill multiple enemies quickly:

| Streak | Multiplier | Popup |
|---|---|---|
| 2 | ×2 | — |
| 3 | ×3 | TRIPLE KILL |
| 4 | ×4 | QUAD KILL |
| 5 | ×5 | RAMPAGE |
| 6+ | ×5 (cap) | UNSTOPPABLE |

The streak resets if too much time passes between kills.

The **end screen** shows your final score, total kills, and best kill streak.

---

## Tech

- Built with [Three.js r128](https://threejs.org/) — no other dependencies
- Procedural audio via the **Web Audio API** (no sound files)
- Single self-contained HTML file — no server required
- Runs in any Chromium or Firefox-based browser

---

## Known Limitations

- No saving — progress resets on page refresh
- Mobile not supported (requires keyboard + mouse)
- Pointer lock required for mouse aiming — click the window to activate it

---

*Made as a solo browser game experiment. All rooms, enemies, and systems handcrafted.*
