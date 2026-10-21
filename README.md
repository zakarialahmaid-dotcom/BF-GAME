# Jumia Caisse Rush 🛒

A mobile-first Black Friday mini-game. Products ride a 3-lane conveyor toward
you — slide your finger to move the Jumia box between lanes, catch the good
deals and dodge the red traps. Score,
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
  scene-bg.jpg        store backdrop (shown dimmed and blurred behind the track)
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
- **A new challenge every 15 seconds** (after a 15s warm-up), on a loop:
  - **Vente Flash ⚡**: points x2 and lots of gold deals, but items come faster.
  - **Mission 🎯**: catch 3 of the product marked 🎯 for +100 and an extra life.
  - **Crazy Hour 🔥**: a rain of Super Deals worth x3, with more traps.
  A pill at the top shows the current challenge and how much time is left.
- Red traps cost one of your 3 lives. A rare green ❤️ item gives one back.
- A new level every 15 seconds: a faster belt, more traps, and pairs of items from level 2. Most rounds end within about a minute; only skilled players get much further.
- Fair hitbox: deals count if they touch the box (even a beat late), traps only if they clearly hit it.
- The glowing lane in front of the box shows where you'll catch, and it turns red when a trap is lined up.
- Fair by design: a trap never shares a lane with a deal arriving at the same time, so there's always a way out.
- Calm by design: no scrolling stripes, screen shake or looping wiggles, to avoid motion sickness.
- Clean track: three flat dark lanes with a dimmed backdrop, so only the items and the box stand out.

## Controls
- **Phone:** slide your finger anywhere. The box follows it (without sitting under your finger) and settles into the nearest lane when you let go.
- **Desktop:** the box follows the mouse, or press ← → (also A/D or Q/D) to hop one lane.
- The lit-up lane always shows which lane will catch.
- **Space / P / Esc** to pause. The game also pauses by itself when you switch tabs.
