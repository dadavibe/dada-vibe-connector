# Public MCP prompt templates

Available in Dada Vibe Connector 1.1.3 and later. These are starting requests, not automatic macros. Your client must support MCP prompts; retrieving one performs no Logic operation. Musical actions keep the connector's normal safety and permission checks.

| Name | Purpose | Fields |
|---|---|---|
| `mix_tracks` | Request a mix adjustment for specified tracks and a musical goal. | `tracks` (required), `goal` (required) |
| `prepare_mastering` | Request suitable output processing for the current mix and its intended use. | `goal` (required) |
| `add_effect` | Request a supported effect on a named track with an intended musical result. | `track` (required), `effect` (required), `goal` (optional) |
| `automate_track` | Request supported automation for a named track, parameter and musical range. | `track` (required), `parameter` (required), `range` (required), `movement` (required) |
| `compose_midi_part` | Describe a musical part to create in the current Logic Pro project. | `brief` (required), `track` (optional) |
| `bass_compression` | Request suitable compression on a named bass track, preserving existing processing. | `track` (required), `goal` (optional) |
| `project_overview` | Read the current project and summarize its musical structure without changes. | None |
| `connection_check` | Read connection and permission status and explain any missing requirements. | None |
| `plan_next_steps` | Read the current project and propose up to three next steps for the user to choose. | None |

For example, retrieve `compose_midi_part` with a `brief` describing your style, length and intended part, and optionally a `track` name. The client turns the returned template into a request and reviews the current project before acting. Full documentation and trial: https://dadavibe.com/getting-started/ and https://dadavibe.com/trial/.
