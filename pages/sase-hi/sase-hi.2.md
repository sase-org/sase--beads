# Bead: sase-hi.2 — Python builtin source layout and loading

[Bead Pages](../README.md) / [sase-hi](README.md) / sase-hi.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-hf.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hf.land.w2/README.md) · **Assignee:** `sase-hi.2` · **Size:** medium
**Created:** 2026-08-08 11:50:10 EDT · **Closed:** 2026-08-08 13:09:14 EDT
**Plan:** [202608/xprompt\_skill\_singular\_namespace.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_skill_singular_namespace.md)

## Description

builtin_skill_source_exception: move only bundled Markdown skill assets beneath xprompts and update Python discovery, placement, packaging, and deployment guards.

## Notes

[2026-08-08T17:08:54Z · sase-hi.2] PROPOSED FOLLOW-UP: publish/version compatible sase-core-rs singular skill contract - linked core exposes schema 4 and package:xprompts/skills while the published 0.20.1 wheel can still resolve to old schema 3/package:skills; land agent should ensure release-plz publishes a bumped binding before primary repo landing.

[2026-08-08T17:09:14Z · sase-hi.2] Moved bundled Markdown skill sources to src/sase/xprompts/skills; updated Python builtin discovery/rendering/LSP, manifest/source-integrity/package tests, and dependency floor; verified focused pytest, installed-wheel resource smoke, sase skill list, sase skill init --dry-run/--diff, and just check (full-suite escalation passed).

[2026-08-08T17:10:20Z · sase-hi.2] Verified focused pytest, installed-wheel resource smoke, sase skill list/init dry-run and diff, and just check escalated to the full suite and passed.

## Dependencies

- **Depends on:** [sase-hi.1](sase-hi.1.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-hi.3](sase-hi.3.md) ✓ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hi.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hi.2/README.md) | [sase-hi.2](sase-hi.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`92f0ff3`](https://github.com/sase-org/sase/commit/92f0ff3774ca867ee971cedb092045d2a4824262) | feat(xprompts): load bundled skills from xprompt resources | [sase-hi.2](sase-hi.2.md) | 2026-08-08 13:11:31 EDT |
