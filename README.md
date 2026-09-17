# Eaglercraft Offline + AI Player Companion

This public repository contains a standalone Eaglercraft HTML build and the experimental **AI Player Companion v4.0** mod.

## Files

- `index.html` — standalone Eaglercraft build.
- `ai-player.js` — updated ModAPI/EaglerForge-style companion mod.
- `MOD-SETUP.md` — installation, commands, compatibility, and security notes.

## GitHub Pages

https://mypassis.github.io/eaglercraft-offline/

The mod is not automatically injected into the game. Load it through a compatible ModAPI/EaglerForge loader.

## New commands

Use `.ai agent <task>` to give the AI a natural-language task, for example `.ai agent follow me and defend me`. v4.0 also includes `.ai queue add`, optional `.ai vision on`, and `.ai voice`. You can stop everything with `.ai halt`. Other bounded commands include `.ai pet`, `.ai pet stop`, `.ai mine`, `.ai defend`, and `.ai auto`. Pet Mode attempts to guide an existing in-game animal; it does not create a fake HUD character. See `MOD-SETUP.md` for compatibility details.
