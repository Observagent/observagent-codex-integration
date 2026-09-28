# Observagent integration for Codex CLI

This folder contains the configuration template users need to send Codex
OpenTelemetry logs to Observagent.

## Install

1. Back up the user-level Codex configuration at `~/.codex/config.toml`.
2. Open `config.example.toml` from this folder.
3. Replace `YOUR_OBSERVAGENT_PROJECT_KEY` with a project key that has
   `telemetry:write` permission.
4. Merge the `[otel]` settings into the existing user-level configuration.
   Do not overwrite unrelated settings or create a second `[otel]` table.
5. Restart Codex and create a new test session.

Telemetry routing settings are ignored in a project-local
`.codex/config.toml`, so this configuration must be added to the user-level
file. Keeping `log_user_prompt = false` prevents raw user prompt text from
being exported. It does not necessarily suppress the metadata-only
`codex.user_prompt` event.

Never commit a real Observagent project key.

## License

MIT. See [LICENSE](LICENSE).
