# Eaglercraft Offline + AI Player Companion

This public repository contains a standalone Eaglercraft HTML build and the experimental **AI Player Companion v4.1** mod.

## Files

- `index.html` — standalone Eaglercraft build.
- `ai-player.js` — updated ModAPI/EaglerForge-style companion mod.
- `MOD-SETUP.md` — installation, commands, compatibility, and security notes.

## GitHub Pages

https://mypassis.github.io/eaglercraft-offline/

The mod is not automatically injected into the game. Load it through a compatible ModAPI/EaglerForge loader.

## New commands

Use `.ai agent <task>` to give the AI a natural-language task, for example `.ai agent walk forward, break the block, then build a house`. v4.1 lets the agent control your current player through movement and click actions. Use `.ai halt` to take control back immediately. It also includes `.ai queue add`, optional `.ai vision on`, and `.ai voice`. Other bounded commands include `.ai pet`, `.ai pet stop`, `.ai mine`, `.ai defend`, and `.ai auto`. See `MOD-SETUP.md` for compatibility details.
