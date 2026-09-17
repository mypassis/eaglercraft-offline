# Eaglercraft Offline + AI Player Companion

This public repository contains a standalone Eaglercraft HTML build and the experimental **AI Player Companion v5.0** mod.

## Files

- `index.html` — standalone Eaglercraft build.
- `ai-player.js` — updated ModAPI/EaglerForge-style companion mod.
- `MOD-SETUP.md` — installation, commands, compatibility, and security notes.

## GitHub Pages

https://mypassis.github.io/eaglercraft-offline/

The mod is not automatically injected into the game. Load it through a compatible ModAPI/EaglerForge loader.

## New commands

Use `.ai agent <task>` to give the AI a natural-language task, for example `.ai agent walk forward, jump, turn right, place a block, then build a house`. v5.0 adds continuous player control, action verification, stuck detection, emergency stops, Creative actions, inventory probing, task memory, debug mode, queues, optional vision, and voice. Use `.ai halt` to take control back immediately. See `MOD-SETUP.md` for compatibility details.
