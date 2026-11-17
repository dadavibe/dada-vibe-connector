# Dada Vibe Connector – Logic Pro MCP server for Logic Pro 12 & 13

**Dada Vibe Connector** is a local **MCP server** (Model Context Protocol) for **Apple Logic Pro 12 & 13** on Intel and Apple Silicon Macs. It lets AI assistants such as **Claude Desktop**, **ChatGPT for Mac (Work, Codex)** and **VS Code with GitHub Copilot** work inside your own Logic Pro project: write and edit MIDI, load instruments, set plug-in parameters in real units (Hz, dB, ms), draw automation, mix and build arrangements. You listen, decide and direct.

- Website: https://dadavibe.com/logic/
- What is MCP? Logic Pro MCP server explained: https://dadavibe.com/mcp/
- Setup guide: https://dadavibe.com/getting-started/
- Demos: https://www.youtube.com/@DadaVibeAi

**Try it free for 7 days. No card.** → https://dadavibe.com/trial/

> This repository contains documentation, client setup notes and the Claude plugin manifest. It does **not** contain the app or its source code. The app is a commercial macOS product, built on the open-source [Logic Pro MCP](https://github.com/koltyj/logic-pro-mcp) by Kolton Jacobs (MIT) plus commercially licensed Dada Vibe extensions.

## Requirements

- A Mac with Apple Silicon or Intel, macOS 15.6 or later.
- Your own **Logic Pro 12 or 13** with the English interface.
- An AI app that runs local MCP tools on the same Mac: Claude Desktop, ChatGPT for Mac in Work or Codex mode, or VS Code with GitHub Copilot.
- The **Dada Vibe Connector** app (signed and notarized macOS installer). One-time €29 + VAT, one user on two Macs, no subscription, free 1.x updates.

## Quick start

1. Install the app from https://dadavibe.com/trial/ (7-day trial) or buy a licence at https://dadavibe.com/logic/.
2. Open **Dada Vibe Connector**, choose your assistant in the Connection window and follow the setup.
3. Grant the macOS permissions the app asks for: Accessibility, input event posting, Automation for Logic Pro and System Events, and Screen Recording.
4. Run a read-only check in your assistant:
   > Use Dada Vibe Connector to read the current Logic Pro status and report any missing permissions. Do not create, close, edit or save a project, and do not start playback.

Client notes: [Claude Desktop](docs/claude-desktop.md) · [ChatGPT for Mac](docs/chatgpt.md) · [VS Code + GitHub Copilot](docs/vscode-copilot.md)

## Claude plugin (optional)

The app sets up Claude Desktop for you. If you use Claude Code, you can also install the plugin from this repository:

```
/plugin marketplace add leospajer-dotcom/dada-vibe-connector
/plugin install dada-vibe-connector@dada-vibe
```

The plugin only registers the local MCP server of the installed app (`/Applications/Dada Vibe Connector.app`). It does nothing without the app.

## What you can ask for

- "Read the open project: tempo, key and the list of tracks. Change nothing."
- "Add a software-instrument track named Pad and write a four-bar Am – F – C – G chord loop on it."
- "Set the low cut of the EQ on the vocal to 120 Hz and lower the reverb send by 3 dB."
- "Draw a filter sweep on the synth over bars 9–16."

Expect a collaborative sketching tool, not a finished production in one click: a simple step takes tens of seconds to a few minutes, and our demo videos are sped up. Save and back up your project before you try edits.

## How it works

The connector runs only on your Mac. Logic Pro has no built-in MCP server, so the connector operates Logic through macOS channels (Accessibility, MIDI, AppleScript and key commands) and reads the result back after each step. More: https://dadavibe.com/mcp/

## For plug-in developers

Send a parameter map and AI assistants can set your plug-in precisely (Hz, dB, ms, named modes): https://dadavibe.com/plugin-developers/

## Privacy

The connector has no accounts and runs locally. The only network request it makes by itself is the update check to `https://updates.dadavibe.com/logic/stable.json`; licence activation contacts our server once per Mac. Your AI assistant and its provider process the conversation under their own terms. Full notice: https://dadavibe.com/privacy/

## Support

- Bugs and questions: [open an issue](https://github.com/leospajer-dotcom/dada-vibe-connector/issues) or e-mail info@dadavibe.com
- In the app: Logic Agent window → Report a problem (you see the exact report before sending)

## Licence

Files in this repository (documentation and plugin manifest) are MIT licensed, see [LICENSE](LICENSE). The Dada Vibe Connector app is proprietary software: https://dadavibe.com/licence/

Dada Vibe is independent and not affiliated with Apple, Anthropic, OpenAI or Microsoft. Logic Pro is a trademark of Apple Inc.
