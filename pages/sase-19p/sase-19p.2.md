# Bead: sase-19p.2 — Python close actor, facade, merge, glyph precedence, and CLI parity

[Bead Pages](../README.md) / [sase-19p](README.md) / sase-19p.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s0.md) · **Assignee:** `sase-19p.2` · **Size:** small
**Created:** 2026-09-25 14:05:30 EDT · **Closed:** 2026-09-25 19:13:40 EDT
**Plan:** [202609/agent\_closed\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_closed_beads.md)

## Description

plumbing: move the sase-core pin, make `sase bead close` always pass the acting agent, parse the new close record through the facade into BeadTouchEntry, promote closed above created in the shared glyph precedence, and expose the record in `sase bead touched --json`.

## Notes

[2026-09-25T23:13:16Z · sase-19p.2--6] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on this workspace HEAD (1cea18e00) because closed flag bead sase-19a still has a surviving tool_failure_triage definition in src/sase/feature_flags/registry.py — identical on the clean base tree with no plumbing-phase edits to that file. Origin master already removed it in 49c32e19e (sase-18j.9); rebase/merge origin rather than re-removing the flag in this phase.

[2026-09-25T23:13:40Z · sase-19p.2--6] Plumbing phase: core pin 24579137fa, close always passes acting agent, BeadTouchClose through facade/merge, closed>created glyph precedence, touched --json close record. Verified 97 plumbing tests green (facade, merge, glyphs, touched JSON, e2e close-without-note credits agent-b). epic-symbols: none leftover. just check lint-flags red on unmodified HEAD (closed sase-19a / surviving tool_failure_triage); recorded PROPOSED FOLLOW-UP citing 49c32e19e.

## Dependencies

- **Depends on:** [sase-19p.1](sase-19p.1.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19p.3](sase-19p.3.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19p.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19p.2.md) | [sase-19p.2](sase-19p.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ed548d3`](https://github.com/sase-org/sase/commit/ed548d3e26ca95ef01dda40d2488ff21529cb974) | feat(bead): surface agent close records through Python plumbing | [sase-19p.2](sase-19p.2.md) | 2026-09-25 19:24:39 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19o.3--1][1] | Need Python schema alignment scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19o.3.md

<!-- sase:referenced-by:end -->
