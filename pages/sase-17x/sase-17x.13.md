# Bead: sase-17x.13 — Finish the \`:\` Command Line: fix landing-audit bugs and spec gaps

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.13

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.land`
**Created:** 2026-09-24 20:28:39 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

The `:` Command Line from epic sase-17x behaves as its plan specifies. Every key in the Keys table works and is configurable under `ace.keymaps.command_line`. No action crashes or silently fails. Completion reaches every candidate and every entity kind. No synchronous disk I/O runs on the UI thread. The chrome and popup match the UX specification. The missing PNG goldens exist, and CI builds a sase-core that exposes `CommandLineGrammar`.

## Notes

[2026-09-25T05:36:41Z · sase-18d.7.land] DISCOVERED ISSUE (sase-18d.7 land, 2026-09-25, master 02c4b029a, still present on origin/master c7a78904b): 'just symvision' fails with unused public CdResolution (src/sase/ace/tui/command_line/builtins.py) and PathCompletionRequest (src/sase/ace/tui/command_line/sources.py). Both were added by fad9b5d03 (sase-17x.13.6) and have no --epic-symbol entry, so every other agent's just check stops at lint (symvision). Privatize them, wire them up, or add sase-17x.13 epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.land/README.md) | [sase-17x.13](sase-17x.13.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18d.7.land][1] | Check whether the active command-line epic owns the unused CdResolution/PathCompletionRequest symbols | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.7.land/README.md

<!-- sase:referenced-by:end -->
