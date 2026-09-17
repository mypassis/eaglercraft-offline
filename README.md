# Eaglercraft Offline + AI Player Companion

This public repository contains a standalone Eaglercraft HTML build and the experimental **AI Player Companion v4.2** mod.

## Files

- `index.html` — standalone Eaglercraft build.
- `ai-player.js` — updated ModAPI/EaglerForge-style companion mod.
- `MOD-SETUP.md` — installation, commands, compatibility, and security notes.

## GitHub Pages

https://mypassis.github.io/eaglercraft-offline/

The mod is not automatically injected into the game. Load it through a compatible ModAPI/EaglerForge loader.

## New commands

Use `.ai agent <task>` to give the AI a natural-language task, for example `.ai agent walk forward, jump, turn right, place a block, then build a house`. v4.2 lets the agent control your current player through continuous movement, looking, flying, sprinting, sneaking, jumping, placing, attacking, and breaking actions. Use `.ai halt` to take control back immediately. It also includes `.ai queue add`, optional `.ai vision on`, and `.ai voice`. See `MOD-SETUP.md` for compatibility details.
