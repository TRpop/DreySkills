# Drey Skills

**English** · [한국어](README.ko.md)

Agent skills that Drey Browser adds to Claude Code and Codex sessions in its AI Agent screen. Each skill is a folder `skills/<name>/SKILL.md` in the [Agent Skills](https://agentskills.io/specification) format (front matter `name` and `description`, then instructions). The skill texts are written in Korean.

| Skill | Use it when |
|---|---|
| `debugging` | Fixing a bug, error or failing test — reproduce first, confirm the cause, then fix and re-run the same check. |
| `plan-consensus` | Starting a new feature or larger change — agree on goals and completion criteria with the user before building. |
| `update-docs` | A stage is finished or agreed — update the work documents (plan and stage files) in `docs/drey/`. |
| `workspace-setup` | Creating or tidying a project's working rules and `docs/drey/` work documents. |
| `handoff` | The user asks for a handover document, or work really moves to another session. |
| `port-check` | Checking that a port to another language or implementation gives the same results (golden-file comparison). |

## How to use

- **Inside Drey Browser** — nothing to install. Drey Browser ships these skills inside the app and adds them only to the sessions it starts (Claude Code as a session plug-in, Codex as an extra skills folder). Your global Claude Code or Codex settings are not changed.
- **Claude Code on its own** — this repository is a Claude Code plug-in (`.claude-plugin/plugin.json`). For example, start a session with `claude --plugin-dir <path to this repository>`, or install it the way the Claude Code plug-in documentation describes.
- **Codex or other agents** — copy the `skills/<name>` folders you want into that tool's skills folder, following its documentation.
- **Drey-specific parts** — some skills (`update-docs`, `workspace-setup`, `plan-consensus`) prefer Drey Browser's work-document tools (MCP `work_docs_*`, `work_task_*`, or `DreyBrowser.Mcp.exe --drey-docs`). Without Drey they explain how to edit the Markdown files by hand; the tools themselves are not available.
- **Hook (`drey-app/hooks.json`)** — calls `DreyBrowser.Mcp.exe` from the Drey Browser app folder, so it **does not work in a plain Claude Code install**. That is why it sits in `drey-app/` and not in the plug-in's default `hooks/` folder. See [drey-app/README.md](drey-app/README.md).

## Where the skills come from

This repository is an export of the single source in the Drey Browser repository (`browser/src/Browser.App/Assets/claude/drey-plugin`), from source commit `ea88256567272d7f882fad0e9051c3f9917c14f5`. The same files are bundled into the Drey Browser build made from that commit. Changes are made in that source, tested with the app, and exported here again — please do not edit this mirror directly; open an issue on [DreyBrowserRelease](https://github.com/TRpop/DreyBrowserRelease/issues) instead. Drey Browser does not download skills from this repository at run time.

## License

- Drey's own work: MIT License, Copyright (c) 2026 TRpop — [LICENSE](LICENSE).
- `debugging` and `plan-consensus` are based on skills from [obra/superpowers](https://github.com/obra/superpowers) (systematic-debugging, brainstorming): MIT License, Copyright (c) 2025 Jesse Vincent — [NOTICE.md](NOTICE.md), original text in [LICENSES/superpowers-MIT.txt](LICENSES/superpowers-MIT.txt). Both notices are kept together.
