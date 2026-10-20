# Jumia Caisse Rush 🛒

A mobile-first Black Friday mini-game. A Jumia box rides a conveyor coming toward
you — slide it left/right to catch the good deals and dodge the red traps. Score,
combo multipliers, lives, level-ups, and speed that ramps up as you go.

## Run it
- **Locally:** just open `index.html` in a browser (double-click).
- **Online (GitHub Pages):** push this folder to a repo, then in the repo go to
  **Settings → Pages → Build from branch → main / root**. Your game is live at
  `https://<your-user>.github.io/<repo>/`.

## Folder structure
```
index.html            the whole game (HTML + CSS + JS in one file)
assets/
  scene-bg.jpg        store backdrop
  scene-belt.jpg      conveyor texture
  scene-horizon.jpg   glowing storefront at the vanishing point
  screen-start.jpg    start-screen background
  screen-gameover.jpg game-over background
  box.png             the player's cart
  badge-orange.png    corner badge on gold deals
  badge-black.png     corner badge on the Super Deal
  products/           <- drop product PNGs here (optional)
  traps/              <- drop trap PNGs here (optional)
  superdeal.png       <- optional hero-item art (or assets/products/superdeal.png)
```

## Add your own item images (no code editing)
Drop transparent PNGs into these folders using these exact names and they load
automatically. Anything missing just falls back to an emoji.

**assets/products/** — `phone.png` `headphones.png` `sneakers.png` `watch.png`
`tshirt.png` `tv.png` `laptop.png` `bag.png` `beauty.png` `appliance.png`
`camera.png` `controller.png` `dress.png` `toy.png`

**assets/traps/** — `bomb.png` `fake.png` `broken.png`

**assets/superdeal.png** or **assets/products/superdeal.png** — the +50 hero item.

Tips: square PNGs with a transparent background, bold and readable when small, and
avoid mostly-orange/yellow bodies (they sit on orange tiles). Don't draw in any
badge or % — the game adds those. Keep them around 320×320 px: everything is
preloaded before the first run, so big files slow down the loading screen on phones.

## Swap the scene / box / badges
Replace the matching file in `assets/` (keep the same filename). To point at a
different filename instead, edit the `ASSETS` object near the top of the `<script>`
in `index.html`.

## Gameplay
- **+10** per product, **+25** for gold deals, **+50** for the black Super Deal.
- Every 5 catches in a row raises the multiplier (x2, x3…). Missing a good deal resets it.
- Red traps cost one of your 3 lives. A rare green ❤️ item gives one back.
- A new level every 15 seconds: faster belt, more traps, items that drift sideways.
- The glowing lane in front of the box shows where you'll catch, and it turns red when a trap is lined up.

## Controls
- **Phone:** drag anywhere. The box moves with your finger's movement, so your finger never covers it.
- **Desktop:** the box follows the mouse, or use ← → (also A/D or Q/D).
- **Space / P / Esc** to pause. The game also pauses by itself when you switch tabs.
