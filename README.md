# Nimble → Dice+ Bridge

A tiny Owlbear Rodeo extension that forwards dice rolls from **Nimblesheet** to the **Dice+** extension.

## What it does

- Listens for Nimblesheet’s existing roll broadcasts (`tools.ttrpg.obr-dicelog/roll`).
- Extracts the formula and sends it to Dice+ via the official `dice-plus/roll-request` channel.
- Dice+ then performs the 3D physics roll and shows the result for everyone in the room.

## Requirements

- Nimblesheet extension installed and enabled in the room.
- Dice+ extension installed and enabled in the room.
- This bridge extension enabled in the same room.

## How to install

1. Host these files somewhere public (GitHub Pages, Cloudflare Pages, Netlify, etc.).
   The files you need are:
   - `manifest.json`
   - `index.html`
   - `icon.svg` (optional but recommended)

2. In Owlbear Rodeo go to **Manage Extensions** → **+** (Add custom extension).

3. Paste the full URL to your hosted `manifest.json`.

4. Enable the extension in your room.

5. Open the bridge popover (it should say “Listening for Nimblesheet rolls…”).

## Notes

- Results in Dice+ are rolled by Dice+ itself. They may not exactly match the number Nimblesheet calculated locally (Nimblesheet has some custom notation).
- Common Nimblesheet markers (`v` for vicious, `p`/`pm` for primary offsets) are stripped before sending so Dice+ can parse the roll.
- The bridge popover shows a live log of forwarded rolls.
- Use the **Test roll** button to verify Dice+ is receiving rolls.

## Troubleshooting

- If status says “Dice+ not found”, make sure Dice+ is enabled in the room and try reloading the page.
- Rolls only forward when Nimblesheet is actually rolling inside Owlbear (not in the standalone site).
- Both players and the GM need the bridge enabled if you want everyone’s rolls to appear in Dice+.
