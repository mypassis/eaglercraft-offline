# AI Player Companion v2.0 Setup

## What changed

Version 2.0 adds a visible bottom-right companion HUD/avatar, reliable follow state, `.ai build house`, `.ai build tower`, and `.ai build bridge` commands, build queues, safer teleport handling, configurable companion name, and clearer failure messages.

## Important compatibility truth

This is a **client-side ModAPI/EaglerForge-style mod**. A real second Minecraft player with a body that walks beside you requires the server/entity APIs to create and synchronize an entity. The current public HTML build does not expose enough verified entity-spawn information for the mod to safely create one. Therefore v2 shows a friendly companion HUD and maintains follow mode without moving your own player or pretending that a server-side avatar exists.

## Installation

1. Open the Eaglercraft build.
2. Use the compatible EaglerForge/ModAPI loader for this exact build.
3. Load `ai-player.js` as a client mod.
4. Reload the game and open the Mods menu.
5. Open **AI Player Companion → Config** and set your own OpenAI-compatible API key, endpoint, and model.
6. Type `.ai help` in chat.

Loading the JavaScript beside `index.html` is not enough.

## Commands

- `.ai <message>` — talk to the AI.
- `.ai follow` — turn follow mode on; the companion HUD shows FOLLOWING.
- `.ai stop` — turn follow mode off.
- `.ai build house` — prepare a small house plan.
- `.ai build tower` — prepare a small tower plan.
- `.ai build bridge` — prepare a short bridge plan.
- `.ai clear` — clear conversation memory.
- `.ai status` — show model, key status, follow state, and the last build report.

The AI can also request `[BUILD:house]`, `[BUILD:tower]`, or `[BUILD:bridge]` in its response. Building only places blocks if this particular build exposes a compatible `ModAPI.world.setBlockState` or `ModAPI.world.setBlock` function with the expected signature. Otherwise, the mod reports that a plan was prepared instead of falsely claiming success.

## Security

Do not put an API key in this repository. The key is stored in browser local storage and prompts are sent to your selected endpoint. Browser CORS must allow requests from the GitHub Pages origin. Use a proxy only if it is configured securely; never expose a server-side secret in client code.

The mod does not bypass server permissions, create server bots, join servers automatically, or guarantee compatibility with every Eaglercraft fork.
