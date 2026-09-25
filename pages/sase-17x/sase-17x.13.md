# Bead: sase-17x.13 — Finish the \`:\` Command Line: fix landing-audit bugs and spec gaps

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.13

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.land`
**Created:** 2026-09-24 20:28:39 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

The `:` Command Line from epic sase-17x behaves as its plan specifies. Every key in the Keys table works and is configurable under `ace.keymaps.command_line`. No action crashes or silently fails. Completion reaches every candidate and every entity kind. No synchronous disk I/O runs on the UI thread. The chrome and popup match the UX specification. The missing PNG goldens exist, and CI builds a sase-core that exposes `CommandLineGrammar`.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.land/README.md) | [sase-17x.13](sase-17x.13.md) | 0 |
