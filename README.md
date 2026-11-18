# Dada Vibe Connector – Logic Pro MCP server for Logic Pro 12 & 13

**Dada Vibe Connector** is a local **MCP server** (Model Context Protocol) for **Apple Logic Pro 12 & 13** on Intel and Apple Silicon Macs. It lets AI assistants such as **Claude Desktop**, **ChatGPT for Mac (Work, Codex)** and **VS Code with GitHub Copilot** work inside your own Logic Pro project: write and edit MIDI, load instruments, set plug-in parameters in real units (Hz, dB, ms), draw automation, mix and build arrangements. You listen, decide and direct.

- Website: https://dadavibe.com/logic/
- What is MCP? Logic Pro MCP server explained: https://dadavibe.com/mcp/
- Setup guide: https://dadavibe.com/getting-started/
- Demos: https://www.youtube.com/@DadaVibeAi

**Try it free for 7 days. No card.** → https://dadavibe.com/trial/

> This repository contains documentation, client setup notes and the Claude plugin manifest. It does **not** contain the app or its source code. The app is a commercial macOS product, built on the open-source [Logic Pro MCP](https://github.com/koltyj/logic-pro-mcp) by Kolton Jacobs (MIT) plus commercially licensed Dada Vibe extensions.

## What you can do in Logic Pro

Use text instructions, or voice when your MCP client supports it, to work on your own Logic Pro project. Your AI client interprets the musical request; Dada Vibe connects it to supported operations in Logic. You listen, decide and direct.

### Write and edit MIDI parts

- Create melodies, bass lines, chord progressions and drum patterns as MIDI in Logic.
- Read notes from existing regions and change pitch, timing, duration and velocity.
- Transpose parts, shape accents, create variations and remove selected notes.
- Import MIDI parts into an existing instrument track and continue editing them.

**Example:** "Create a four-bar Am–F–C–G chord progression on the Pad track, then make the last chord quieter."

### Build and revise an arrangement

- Create, select, repeat, split, join and move supported regions.
- Duplicate a part or extend a musical section.
- Name and organize tracks, set track colours, and work with markers and song sections.

**Example:** "Repeat the bass part for the next eight bars and add a marker called Breakdown."

### Load instruments and work with effects

- Add software-instrument and audio tracks and load available instruments or sounds.
- Insert effects and work with supported native Logic and third-party Audio Units controls.
- Read and adjust available parameters using meaningful values such as Hz, dB and ms.
- Work with available presets, effect order, bypass and output effects.

**Example:** "Insert Channel EQ on the vocal and set its low cut to 120 Hz."

Parameter access depends on the particular plug-in, its interface and the controls it exposes. Third-party plug-in support is specific to supported workflows; it is not a promise that every Audio Unit or every parameter can be controlled.

### Write automation

- Create and edit automation for supported track and plug-in controls.
- Build volume changes and filter movements over a chosen musical range.
- Read back available automation data and revise a supported envelope.

**Example:** "Create a rising cutoff sweep on this synth over bars 9–16."

Automation availability depends on the track type, parameter and Logic version.

### Mix, route and set up sidechain processing

- Adjust supported track and output levels, pan, mute and solo.
- Work with supported sends, buses and Aux routing.
- Insert effects on tracks, buses and the output.
- Set up supported compressor sidechain routing and adjust its timing and dynamics controls.

**Example:** "Set up gentle ducking on the bass, triggered by the kick."

### Measure audio and refine a mix

- Capture a requested section of Logic audio for analysis.
- Measure track levels and use measurement-assisted mix balancing.
- Measure integrated LUFS, loudness range and true peak on a captured mix or audio file.
- Analyze reference audio for properties such as tempo, spectral balance and musical structure.
- Compare audio measurements to help guide EQ, level and mastering decisions.

**Example:** "Measure the loudest section of the mix and report its LUFS and true peak before changing anything."

A measurement of a short section describes that section. Musical decisions and reference analysis still need your judgment.

### Save projects and export your work

- Create, open, save and use Save As on the active project.
- Export audio and MIDI through supported Logic workflows.
- Export supported individual-track audio.
- Plan an audio export, inspect its result and resume an existing export job.
- Check resulting files so an export request has a tangible output to review.

**Example:** "Export the whole current song as a 24-bit audio file into the folder I choose."

### Stay informed while you work

- Read the current project, track, transport and available mixer state.
- Check the connection and required macOS permissions.
- Follow activity in the Logic Agent window and send a technical problem report from the app.
- Receive app updates through the built-in updater.

A single signed and notarized installer supports Intel and Apple Silicon Macs and includes the required runtime. You do not need to install Python or compile Swift yourself.

## More example requests

- "Read the open project: tempo, time signature and tracks. Change nothing."
- "Write an eight-bar bass variation on the existing Bass track."
- "Make the hi-hat velocities less uniform while keeping the rhythm."
- "Transpose the selected MIDI part up an octave."
- "Lower the pad level and move it slightly to the left."
- "Add reverb through a supported send and keep the lead clear."
- "Build a supported EQ, compressor and limiter chain on the output."
- "Analyze this reference track and describe its tempo and spectral balance."
- "Measure the mix first, then suggest the next three improvements."
- "Save this project under a new name and export a preview."

Examples illustrate requests to your AI client. The client may need to clarify the target, choose a supported operation or ask for permission before changing the project.

## Testing and verification

Development combines **live Logic Pro workflow tests**, **automated regression tests** and **release-package checks**.

- **Live workflow testing:** documented scenarios have been exercised in Logic Pro 12 on Intel and Logic Pro 13 on Apple Silicon. Tested areas include MIDI note and region editing, supported instrument and effect controls, automation, mixing and export. Evidence belongs to the particular workflow, Logic version and build; coverage differs between the two setups.
- **Automated regression coverage:** checks cover areas such as MIDI handling, export-job results, client startup and discovery, licensing policy and audio analysis. For release 1.1.2, the reference-audio regression suite passed 26 tests.
- **MCP protocol checks:** release validation uses the local MCP Inspector to check connection and tool schemas. Protocol checks and live musical-operation tests are separate checks.
- **macOS distribution checks:** the 1.1.2 installer was checked for both Intel and Apple Silicon payloads, signed with Developer ID, notarized by Apple and verified with Gatekeeper.

Supported operations check available results and can report incomplete verification. Use the seven-day trial to confirm the workflows you need with your own Mac, Logic version, client and plug-ins.

## Optional MCP prompt templates (1.1.3 and later)

Nine reusable request templates help you get started: **Mix selected tracks**, **Prepare mastering**, **Add an effect**, **Automate a track**, **Compose a MIDI part**, **Bass compression**, **Project overview**, **Connection check**, and **Plan next steps**.

Your MCP client can discover them with `prompts/list` and retrieve a template with `prompts/get`. Fill in the requested fields, such as a track name, musical brief, effect or automation range. Retrieving a template only prepares a request; it does not start Logic, change the project or bypass the normal tool permissions and checks. The AI client then interprets your request and uses supported connector operations. Prompt menus depend on your client; free-form text and voice requests remain available as supported by that client.

[Prompt names and fields](docs/prompt-templates.md)

## Working well with the connector

Give a clear target, musical range and intended result. A coherent request such as "write an eight-bar bass variation on the existing Bass track" gives your client more useful direction than an ambiguous "fix everything." Break a large production into manageable stages and review the musical result between them.

**Compatibility and scope.** The app supports Logic Pro 12 and 13 with the English interface on macOS 15.6 or later. Individual operations can differ between Logic versions, track types and plug-ins. Logic features such as Flex Time/Pitch editing are outside the documented supported workflows.

**Execution and feedback.** Some operations need Logic in the foreground. Follow the app's instructions and let an active automation step finish before using the same Mac's keyboard or mouse. Supported operations include result checks; a command can report an incomplete result or refuse an unsupported target instead of completing the requested task.

**Timing and musical results.** Allow tens of seconds to minutes depending on the task. AI reasoning, Logic dialogs and verification all contribute to the time needed. Demo videos are sped up. Review results and keep project backups; an AI client's interpretation of a musical request can need revision.

**Try your own setup.** Use the seven-day free trial to check your Mac, Logic version, client and plug-ins. The seven days begin when you activate the trial in the app, with no payment card required. Enter a purchased licence key in the same app to continue after the trial.

[Watch the demos](https://www.youtube.com/@DadaVibeAi) · [Download the trial](https://dadavibe.com/trial/) · [Read the setup guide](https://dadavibe.com/getting-started/)

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

## Claude plugin

This repository is a Claude plugin. It adds the Logic Pro MCP server of the installed app to Claude:

```
/plugin marketplace add dadavibe/dada-vibe-connector
/plugin install dada-vibe-connector@dada-vibe
```

What the plugin runs: one small shell script, [`bin/dada-vibe-connector`](bin/dada-vibe-connector). It checks that the app is installed and starts the app's local MCP server (`/Applications/Dada Vibe Connector.app/Contents/Resources/payload/bin/start-mcp`) over stdio. The plugin itself contains no other code, sends nothing and fetches nothing. Without the app it only prints how to install it.

## Local MCP installation configuration

Install the signed and notarized macOS app first: [Download the 7-day free trial](https://dadavibe.com/trial/). The trial starts when activated in the app; no payment card is required. Use the same installer on Intel and Apple Silicon Macs.

For a local MCP client that accepts a JSON server configuration, use the installed app's stdio entry point. The exact executable command is `/Applications/Dada Vibe Connector.app/Contents/Resources/payload/bin/start-mcp`, with no arguments. `Dada Vibe Connector.app` by itself names an application bundle directory and is not an executable MCP command. Do not substitute the app name for the full executable path below:

```json
{
  "mcpServers": {
    "dada-vibe-connector": {
      "command": "/Applications/Dada Vibe Connector.app/Contents/Resources/payload/bin/start-mcp",
      "args": []
    }
  }
}
```

Keep the app installed at `/Applications/Dada Vibe Connector.app`. The command starts the app's local MCP connection; it is not a hosted HTTP endpoint. The app includes its runtime, so a separate Python, Node.js or Swift installation is not required. Open the app to activate the trial or enter a licence key, complete the requested macOS permissions, and follow the [Getting Started guide](https://dadavibe.com/getting-started/). Your client must support local stdio MCP servers; the command is not a browser URL.

The repository's `lhm.plugin.json` declares the public MCP tool names and input shapes for directory discovery. It contains no implementation source or internal operation recipes.

## How it works

The connector runs locally on your Mac. Your MCP client sends requests to the installed app, which operates supported Logic workflows through macOS integration and checks available results. The AI client handles the conversation and musical interpretation. More: https://dadavibe.com/mcp/

## For plug-in developers

Send a parameter map and AI assistants can set your plug-in precisely (Hz, dB, ms, named modes): https://dadavibe.com/plugin-developers/

## Privacy Policy

Full notice: https://dadavibe.com/privacy/ · Controller: Leoš Pajer (Dada Vibe), IČO 72446757, Prague, Czech Republic · Contact: info@dadavibe.com

**Data collection and use.** The connector runs locally on your Mac and has no user accounts. To carry out your requests it reads the state of Logic Pro (project and track names, mixer and plug-in values, transport) and, when your assistant operates a graphical plug-in and you allow Screen Recording, an image of that plug-in window. It returns these results only to the AI app that asked. It does not read your chat history, memory or uploaded files and does not profile users.

**Storage.** Local files stay on your Mac (`~/Library/Caches/logic-pro-studio`, `~/Library/Application Support/DadaVibe`): activity log, error records, saved recipes, learned plug-in data and backups of AI client settings. You can delete them at any time.

**What leaves your Mac.**
1. Update check: an HTTPS request to `https://updates.dadavibe.com/logic/stable.json` without cookies or an account identifier.
2. Licence or trial activation, once per Mac, sent to `updates.dadavibe.com`: a purchased licence key is checked with Payhip; a trial needs no e-mail or card.
3. Problem report, only if you click Send in the app: you see the exact text first; it contains no project, track or plug-in names, paths, music, audio, screenshots or your instructions. Sent to `report.dadavibe.com`.
4. Anonymous usage statistics, only if you agree in the app: at most one message a day without any identifier.

**Third-party sharing.** Your AI app and its provider (for example Anthropic, OpenAI or GitHub/Microsoft) process the conversation and the connector's results under their own terms; we do not receive them. Our servers are hosted by ACTIVE 24 (Czech Republic). Purchases are handled by Payhip (payments by Stripe or PayPal). We do not sell data.

**Retention.** Problem reports: 90 days, then deleted. Aggregate daily usage counts: at most 800 days. Backups at the hosting provider: up to 14 more days after deletion. Order records: as required for tax and accounting (Payhip keeps transaction records for VAT for 10 years). Support e-mails: normally deleted or anonymised within 12 months.

**Contact.** info@dadavibe.com

## Support

- Bugs and questions: [open an issue](https://github.com/dadavibe/dada-vibe-connector/issues) or e-mail info@dadavibe.com
- In the app: Logic Agent window → Report a problem (you see the exact report before sending)

## Licence

Files in this repository (documentation and plugin manifest) are MIT licensed, see [LICENSE](LICENSE). The Dada Vibe Connector app is proprietary software: https://dadavibe.com/licence/

Dada Vibe is independent and not affiliated with Apple, Anthropic, OpenAI or Microsoft. Logic Pro is a trademark of Apple Inc.
