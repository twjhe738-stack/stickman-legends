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
