# AI Player Mod Setup

## Can it work with Eaglercraft?

This script is written for a **ModAPI/EaglerForge-style EaglercraftX 1.8 build**. The uploaded `index.html` includes `ModAPI` symbols, so it appears to be based on a compatible build. However, compatibility is not guaranteed until the mod loader successfully loads the script in-game.

It will **not** work by simply opening `ai-player.js` or by placing it next to `index.html`. The script expects the loader to provide:

- `ModAPI.meta`
- `ModAPI.player`
- `ModAPI.world`
- `ModAPI.addEventListener`
- `ModAPI.displayToChat`
- `ModAPI.require`

## Installation

1. Open the GitHub Pages game site.
2. Use the compatible EaglerForge/ModAPI mod-loader workflow for this build.
3. Load `ai-player.js` as a client mod.
4. Reload the game and check the Mods menu for **AI Player**.
5. Configure the endpoint and model, then use `.ai help` in chat.

If the Mods menu or ModAPI loader is not present, this script will not run.

## Commands

- `.ai help` — show commands
- `.ai <message>` — ask the AI something
- `.ai follow` — enable the experimental movement loop
- `.ai stop` — stop following
- `.ai clear` — clear conversation memory
- `.ai status` — show configuration status

## Security and privacy

This is a **bring-your-own-key** script. Do not put an API key into a public repository or share a screenshot containing it. The key is stored in the browser's local storage, and prompts are sent to the configured endpoint.

The default endpoint is OpenAI-compatible. Browser CORS rules must allow requests from the GitHub Pages origin. If requests fail with a CORS error, use a permitted endpoint or a properly configured proxy; do not expose a secret server-side key in public client code.

The script can send chat messages and modify player movement. The block-placement function is currently only best-effort and may announce an attempted placement without actually placing a block.

## Limitations

- The script does not create an AI-controlled server-side player or bot.
- It does not automatically join servers or bypass server permissions.
- It is experimental and may require changes for a different Eaglercraft/EaglerForge version.
