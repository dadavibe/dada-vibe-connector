# Dada Vibe Connector for Logic Pro 12 & 13

## Short description

A local MCP connector for Logic Pro 12 & 13 on Intel and Apple Silicon Macs. Write MIDI, arrange regions, control supported plug-ins, automate, mix, analyze audio and export. Seven-day free trial, no card.

## Full description

**Less clicking. More music.**

Dada Vibe Connector connects a compatible AI client to your own Logic Pro project on your Mac. Give instructions by text, or by voice when your client supports it, and direct the session while the connector carries out supported Logic operations.

### MIDI composition and editing

Create melodies, chord progressions, bass lines and drum patterns as MIDI. Read and edit existing notes, including pitch, timing, duration and velocity. Transpose parts, shape accents, build variations and import MIDI into an existing instrument track.

### Arrangement and track organization

Create and revise supported regions: repeat, split, join, move and duplicate musical parts. Name and organize tracks, set track colours, and work with markers and song sections.

### Instruments, effects and automation

Load available instruments and sounds, insert effects, and adjust supported native Logic and third-party Audio Units parameters in meaningful units such as Hz, dB and ms. Work with available presets, effect order and bypass. Create supported volume and plug-in automation, such as a filter sweep over a chosen range.

### Mixing and sidechain

Adjust supported faders, pan, mute and solo. Work with sends, buses, Aux and output processing. Set up supported compressor sidechain routing and adjust timing and dynamics controls.

### Audio measurement and reference analysis

Capture a requested section of Logic audio, measure track levels and use measurement-assisted mix balancing. Measure integrated LUFS, loudness range and true peak on a captured mix or audio file. Analyze reference audio for tempo, spectral balance and musical structure to inform your own production decisions.

### Projects and export

Create, open, save and use Save As on the active project. Export audio, MIDI and supported individual-track audio. Plan an audio export, inspect the resulting files and resume an existing export job.

### A ready-to-install Mac app

- One signed and notarized installer for Intel and Apple Silicon Macs.
- Required runtime included; no separate Python installation or Swift compilation.
- Connection and macOS permission checks.
- Logic Agent activity window and an in-app problem-reporting option.
- Built-in app updater.
- Seven-day free trial starting at activation in the app, with no payment card required.
- Continue in the same installed app by entering a purchased licence key.

### Testing and verification

Development combines live workflow tests in Logic Pro 12 on Intel and Logic Pro 13 on Apple Silicon with automated regression checks. Coverage includes areas such as MIDI editing, supported plug-in controls, automation, export results, client startup, licensing policy and audio analysis. Each live result is specific to the tested workflow, version and build.

Release 1.1.2 passed 26 reference-audio regression tests. Its release checks also included local MCP Inspector protocol and schema validation, verification of both architecture payloads, Developer ID signing, Apple notarization and Gatekeeper acceptance. These checks have different scopes; protocol and package checks are separate from live musical testing.

Use the seven-day trial to confirm the workflows needed in your own setup.

### Example requests

- "Create a four-bar chord progression on the Pad track."
- "Write an eight-bar bass variation and soften the last two notes."
- "Set the vocal EQ low cut to 120 Hz."
- "Create a rising filter sweep over bars 9–16."
- "Set up gentle bass ducking triggered by the kick."
- "Measure the mix and report its LUFS and true peak."
- "Export the whole current song as a 24-bit audio file."

### Requirements and scope

Requires macOS 15.6 or later, your own Logic Pro 12 or 13 with the English interface, a compatible local MCP client, and the required macOS permissions. Documented clients include Claude Desktop, ChatGPT for Mac in Work or Codex mode, and VS Code with GitHub Copilot. Logic Pro, AI services and third-party plug-ins are separate products.

Function availability depends on the Logic version, track type, plug-in and exposed controls. Support covers specific workflows rather than every Logic feature or every Audio Unit. Some operations require Logic in the foreground, and tasks can take tens of seconds to minutes. Review musical results and keep project backups. Demo videos are sped up.

Dada Vibe is the MCP connector; your AI client provides the conversation and musical interpretation. The connector runs locally, while the AI client's handling of the conversation and returned data follows that provider's terms. Privacy details: https://dadavibe.com/privacy/

The app is commercial software built on Kolton Jacobs' open-source Logic Pro MCP (MIT), with commercially licensed Dada Vibe extensions. This public repository contains documentation and integration files.

### Links

- Free trial: https://dadavibe.com/trial/
- Product and current pricing: https://dadavibe.com/logic/
- Setup guide: https://dadavibe.com/getting-started/
- Demo videos: https://www.youtube.com/@DadaVibeAi
- Public repository: https://github.com/dadavibe/dada-vibe-connector
- Support: info@dadavibe.com

Independent project; not affiliated with Apple or AI providers. Logic Pro is a trademark of Apple Inc.
