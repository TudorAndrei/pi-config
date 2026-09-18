# Herdr interactive subagents

A Herdr-native port of [`amosblomqvist/pi-interactive-subagents`](https://github.com/amosblomqvist/pi-interactive-subagents). It is auto-discovered as `pi/extensions/subagents/index.ts`.

## Requirements

- Pi must run in a Herdr pane (`HERDR_ENV=1`).
- Herdr must recognize Pi agents and expose its `pane` and `agent` CLI commands.

The extension creates a sibling pane using `herdr pane split --current --no-focus`, starts the child Pi process there, and uses the Herdr agent surface to steer follow-up messages. It never changes focus and only closes panes it created.

## Features

- `subagent` — asynchronously launch an agent in a sibling Herdr pane.
- `subagent_message` — steer a running child or resume its persisted session.
- `subagents_list` and `/subagent <agent> <task>`.
- Per-session name registry, sandbox/loadout snapshots, tool allowlists, status widget, activity tracking, automatic result delivery, and `ask_question`.
- Bundled `scout`, `researcher`, and `worker` profiles in `pi/extensions/agents/`.

Agent profiles can override bundled profiles from `.pi/agents/` or `~/.pi/agent/agents/`, matching the upstream extension.

`config.json` controls the live status widget; set `status.enabled` to `false` to disable it.
