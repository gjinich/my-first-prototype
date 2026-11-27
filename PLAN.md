# Rubber Duck Catch: Plan

A gentle, Duck Hunt-style game for a 7-year-old. Rubber ducks float across a bathtub or pond and you tap them to catch them with a net. Nobody shoots anything, and you can't lose.

## Constraints
- Plain HTML, CSS and JavaScript. No build step, no dependencies, no framework.
- Hosted on GitHub Pages from the repo root (main branch, `/`).
- Built for **iPhone Safari, portrait, touch**. It should still work with a mouse on a computer.

## Files
- `index.html`: page shell, viewport meta (`width=device-width, viewport-fit=cover`), start/end screens
- `style.css`: full-screen portrait layout, safe-area insets, no text selection or tap highlight, no pinch zoom or scroll bounce
- `game.js`: game loop (`requestAnimationFrame`), ducks, input, scoring, high score
- Ducks are **inline SVG** drawn in code, so they stay crisp on Retina and are easy to recolor. No image files.

## Gameplay
- **Start screen:** a large ▶ button and the best score so far.
- **Round:** 60 seconds. Ducks bob across the water at different heights and speeds.
- **Catch:** tap a duck. A net swoops down and the duck pops into a bucket. Score +1 and a "+1" floats up.
- **Missed ducks** just float off the screen. No lives, no penalties, no "game over" message.
- **End screen:** the ducks caught, a cheerful message ("Great job!"), a ⭐ if it's a new best, and a big ↻ to play again.
- **Text:** as little as possible. Mostly icons and numbers (🦆 counter, ⏱ timer bar).

## Special ducks
- **Golden duck:** rare, slightly faster, worth 3.
- **Tiny duck:** smaller and quicker, worth 2.
- **Normal yellow duck:** worth 1.
- Spawn rate rises a little over the round, but stays easy enough for a 7-year-old.

## Kid-friendly touch details
- Hit areas bigger than the drawn duck (about 60px or more) for small fingers.
- Use `pointerdown` so a tap registers instantly. Block double-tap zoom.
- Bright, soft colours and smooth bobbing animation.

## Persistence
- Players kept in `localStorage` (`duckPlayers`) on this device: each has a name, a duck avatar (colour + hat) and their own best score.
- Start screen: tap a player card to pick who's playing, **+** to add a player, **hold** a card to edit or delete it.
- End screen: 👥 goes back to the player picker.

## Out of scope (v1)
Sound, levels, leaderboards, landscape layout.

## Steps
1. Scaffold `index.html`, `style.css`, `game.js`. Show the water scene and start screen.
2. SVG rubber duck and a floating/bobbing movement loop.
3. Tap to catch, with the net animation, score and bucket.
4. 60s timer, end screen, high score.
5. Add the special ducks and tune difficulty.
6. Test on an iPhone (Safari) and in the desktop browser's device emulation.
7. Turn on GitHub Pages (Settings → Pages → main, `/ (root)`).
