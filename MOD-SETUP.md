# AI Player Companion v3.1 Setup

## What changed

Version 3.1 adds an experimental in-game **Pet Mode** for existing animals, plus reliable follow state, build plans, bounded mining and defense tasks, an autonomous mode, safer teleport handling, configurable companion name, faster local command handling, and clearer failure messages.

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
- `.ai mine [tunnel|ore]` — prepare a bounded mining route and use a supported local mining API if available.
- `.ai defend` — watch for nearby hostile entities and use a supported local attack API if available.
- `.ai auto` — enable autonomous local mode: follow, defend, mine, and generate build plans.
- `.ai halt` — stop every AI task immediately.
- `.ai pet` or `.ai pet follow` — find the nearest exposed cow, pig, sheep, chicken, wolf, cat, rabbit, or horse and try to guide it toward you.
- `.ai pet stop` — stop controlling the selected animal.
- `.ai clear` — clear conversation memory.
- `.ai status` — show model, key status, follow state, and the last build report.

The AI can also request `[BUILD:house]`, `[BUILD:tower]`, `[BUILD:bridge]`, `[MINE:tunnel]`, `[DEFEND]`, `[AUTO]`, or `[HALT]` in its response. Building only places blocks if this particular build exposes a compatible `ModAPI.world.setBlockState` or `ModAPI.world.setBlock` function with the expected signature. Mining and defense likewise depend on exposed block-breaking, entity-list, and attack APIs. Otherwise, the mod reports that a plan or API is unavailable instead of falsely claiming success.

Auto mode is intentionally bounded and can be stopped at any time with `.ai halt`. It does not automatically send arbitrary chat, spend items, bypass permissions, or use server commands.

Pet Mode does not create a new animal. It controls only an animal that already exists in the game and only when the client exposes mutable entity movement fields. On many builds, animals may be read-only; in that case the Mod reports that control is unavailable.

## Security

Do not put an API key in this repository. The key is stored in browser local storage and prompts are sent to your selected endpoint. Browser CORS must allow requests from the GitHub Pages origin. Use a proxy only if it is configured securely; never expose a server-side secret in client code.

The mod does not bypass server permissions, create server bots, join servers automatically, or guarantee compatibility with every Eaglercraft fork.
