# STICKMAN LEGENDS

A polished, responsive 2D anime-inspired stickman fighting game for mobile,
built with HTML5, CSS, JavaScript ES modules, and the Canvas 2D API.
No external dependencies, no paid services. Optimized for lower-end Android
devices (particle pooling, zero allocations in the hot loop, no expensive
shadowBlur per frame).

## How to run

1. Open `index.html` in a modern browser.
   - Double-click `index.html`, or serve the folder (recommended for mobile
     testing / service-worker-free local play):
     ```
     python3 -m http.server 8000
     # then open http://localhost:8000 on your phone or desktop
     ```
2. Tap or press **SPACE** to start from the menu.
3. Win 3 rounds to win the match. Tap to rematch after game over.

## Controls

### Keyboard (desktop / shared-screen two-player)

| Action | Player 1 (left side) | Player 2 / Enemy (right side) |
|--------|----------------------|-------------------------------|
| Move left/right | A / D or ← / → | ← / → |
| Jump (double jump airborne) | W / ↑ | ↑ |
| Block (hold) | S / ↓ | ↓ |
| Punch | J | J |
| Kick | K | K |
| Dash | Shift | Shift |
| Dodge | Q | U |
| Charge energy | E | I |
| Beam attack | Space | L |

### Touchscreen (landscape-first)

- **Left side:** virtual joystick for movement.
- **Right side:** large action buttons — Jump, Beam, Punch, Kick, Block, Dash.
- Multi-touch is supported (move + attack simultaneously).
- Browser scrolling and pull-to-refresh are disabled during gameplay.

## Features

- Responsive left/right movement, jumping (incl. double jump), dashing, dodging
- Punches, kicks, blocking, ground combos (P → P → K finisher), aerial combos
- Proper hitboxes/hurtboxes with one-hit-per-window tracking
- Hit stun, knockback, recovery, attack cooldowns, dash/dodge cooldowns
- Energy meter: passive regen + charging + gained on hit/landed hits
- Projectiles and beam attacks (energy cost)
- Destructible-looking impact effects (particles, flashes, screen shake)
- Energy auras at high energy, attack anticipation, procedural animation
- Enemy AI with offensive and defensive behavior (approach, back off, block,
  dodge, jump, dash, charge, beam)
- Health and energy bars, round timer, round management, victory conditions
- Landscape-first layout, virtual joystick, multi-touch, large buttons
- Tab visibility handling (auto-pause when switching tabs), resize handling
- Hitbox debug overlay (press `H`)

## Project structure

```
index.html          # Entry page + viewport meta for mobile
src/main.js         # Bootstraps Game + Controls
src/game.js         # Main loop, round state, victory, HUD, render, pause
src/fighter.js      # Fighter entity, state machine, combat commands, drawing
src/controls.js     # Keyboard + virtual-joystick touch input
src/combat.js       # Hitbox/hurtbox collision, damage, knockback, hitstop
src/ai.js           # Enemy AI (offensive + defensive)
src/effects.js      # Particle pool, screen shake, energy aura, flashes
src/projectile.js   # Bolt + beam projectiles
src/constants.js    # Game tuning constants
src/style.css       # Responsive landscape-first UI
```

## Quality notes

- Stable fixed-timestep (60 FPS) game loop with delta-time capping
- Input, combat, physics, rendering, and AI are separated into modules
- Particle pool reuses objects — zero allocations during gameplay
- Hitboxes/hurtboxes are mutated in place, not created each frame
- Prevents attacks registering repeatedly in one hit window
- Handles tab switching (pause/resume), resizing, and visibility change

## Limitations (v2)

- No sound effects or music (dependency-free, no external assets)
- No persistent high score / localStorage
- Single CPU difficulty (scalable); no online multiplayer
- Visual rendering functionally tested in Node; not yet validated in a real
  browser on-device

## License

MIT
