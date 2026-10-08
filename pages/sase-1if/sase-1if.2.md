# Bead: sase-1if.2 — sase-listen becomes a command plugin

[Bead Pages](../README.md) / [sase-1if](README.md) / sase-1if.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0n.linker.w0.md) · **Assignee:** `sase-1if.2` · **Size:** medium
**Created:** 2026-10-08 15:26:23 EDT · **Closed:** 2026-10-08 15:48:54 EDT
**Plan:** [202610/plugin\_commands.md](https://github.com/sase-org/sase--plans/blob/main/202610/plugin_commands.md)

## Description

listen-adapter: in the sase-listen repo, add the sase_command adapter and entry point, thread the program name through the CLI and hints, fix buildinfo and the feed-host remote command for plugin-only hosts, and rewrite the standalone stance.

## Notes

[2026-10-08T19:48:54Z · sase-1if.2] listen-adapter done in sase-listen checkout: sase_commands entry point + stdlib-only sase_command adapter; prog threading (cli/app/build_parser/add_parser) with invocation-based hints; buildinfo returns 'sase plugin update listen' in sase tool envs; SSH remote prefers standalone then 'sase listen' with exit-127 install hint and tightened receive-only too-old detection; dead cli.py removed; stance rewritten in AGENTS/CONTRIBUTING/README/docs (9 pages) + guide {{prog}} token; sase_completion=path on 9 slots. Verified: sase tool run check green (381 passed, 4 skipped; ruff+mypy-strict+codespell clean), mkdocs --strict builds, epic-symbols empty. No memory edits (records land in acceptance). Uncommitted per host-owned completion.

## Dependencies

- **Blocks:** [sase-1if.8](sase-1if.8.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1if.9](sase-1if.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1if.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.2/README.md) | [sase-1if.2](sase-1if.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-listen | [`sase-listen@8c57128`](https://github.com/sase-org/sase-listen/commit/8c5712886833b527bdb39197513c4701af225e74) | feat(listen): ship sase listen as a first-class command plugin | [sase-1if.2](sase-1if.2.md) | 2026-10-08 15:52:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1if.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.2/README.md

<!-- sase:referenced-by:end -->
