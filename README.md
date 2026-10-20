# Jumia Caisse Rush 🛒

A mobile-first Black Friday mini-game. A Jumia box rides a conveyor coming toward
you — slide it left/right to catch the good deals and dodge the red traps. Score,
combos, lives, and speed that ramps up by level.

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
  superdeal.png       <- optional hero-item art
```

## Add your own item images (no code editing)
Drop transparent PNGs into these folders using these exact names and they load
automatically. Anything missing just falls back to an emoji.

**assets/products/** — `phone.png` `headphones.png` `sneakers.png` `watch.png`
`tshirt.png` `tv.png` `laptop.png` `bag.png` `beauty.png` `appliance.png`
`camera.png` `controller.png` `dress.png` `toy.png`

**assets/traps/** — `bomb.png` `fake.png` `broken.png`

**assets/superdeal.png** — the +50 hero item.

Tips: square PNGs with a transparent background, bold and readable when small, and
avoid mostly-orange/yellow bodies (they sit on orange tiles). Don't draw in any
badge or % — the game adds those.

## Swap the scene / box / badges
Replace the matching file in `assets/` (keep the same filename). To point at a
different filename instead, edit the `ASSETS` object near the top of the `<script>`
in `index.html`.

## Controls
Drag anywhere (or arrow keys on desktop) to move the box. Space / P to pause.
