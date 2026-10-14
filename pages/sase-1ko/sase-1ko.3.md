# Bead: sase-1ko.3 — Scoreboard sees dismissed agents, and the new sase instructions show command

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.3` · **Size:** medium
**Created:** 2026-10-13 18:10:35 EDT · **Closed:** 2026-10-13 21:42:43 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

run-discovery: make verify and render enumerate and resolve hidden (dismissed) agents. Fail loudly when an agent name resolves to nothing. Teach the manifest reader about helper manifests, and fix the per-purpose coverage denominator. Add `sase instructions show NAME`, which prints an agent's recorded bundle and manifest and checks the stored bytes against the manifest digest.

## Notes

[2026-10-14T01:42:25Z · sase-1ko.3] PROPOSED FOLLOW-UP: ACE TUI agent-session display tests fail identically on clean HEAD e8ec9cb291 — test_session_collapsed_detached_macro_skips_markers, test_agent_session_conversation_sections_are_always_full, and test_hint_mode_renders_raw_prompt_for_terminal_agent. Not caused by run-discovery; do not block this phase.

[2026-10-14T01:42:43Z · sase-1ko.3] Verified run-discovery: enumerate_runs queries the artifact index with include_hidden=True (full history when --since is set); -a NAME / show NAME resolve through find_named_agent so dismissed agents are not dropped by --since; unknown names exit 2. Helper manifests (NN-<provider>.helper.json) are separate reader records; purpose denominators keep unmatched sessions on ordinary. sase instructions show NAME (-H/-j/-l/-n/-s) checks sha256 (run copy then store_path). Live: show research.0f.cdx (dismissed) reports bytes match; show unknown exits 2; verify -a research.0f.cdx reports 1 codex run. Tests: test_run_discovery, test_show_cli, scoreboard purpose rows, completion kind coverage. sase tool run check lint/mypy/ruff green; remaining ACE TUI agent-session NEW failures reproduce on clean HEAD (see PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1ko.4](sase-1ko.4.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.6](sase-1ko.6.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.3/README.md) | [sase-1ko.3](sase-1ko.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c5e4da7`](https://github.com/sase-org/sase/commit/c5e4da7065cc40a5e81163a949a499713994db06) | feat(instructions): enumerate dismissed runs and add instructions show | [sase-1ko.3](sase-1ko.3.md) | 2026-10-13 21:44:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ko.3][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.3/README.md

<!-- sase:referenced-by:end -->
