# Bead: sase-jo.6 — Docs, help modal, and configuration reference

[Bead Pages](../README.md) / [sase-jo](README.md) / sase-jo.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xv](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xv/README.md) · **Assignee:** `sase-jo.6` · **Size:** small
**Created:** 2026-08-11 06:59:47 EDT · **Closed:** 2026-08-11 09:30:01 EDT
**Plan:** [202608/stitch\_origin\_badges.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_origin_badges.md)

## Description

docs: document the origin taxonomy, glyphs, provenance invariant, and `origin:` filter across the ACE guide, commit-workflow guide, CLI reference, configuration reference, and the ACE help modal.

## Notes

[2026-08-11T13:29:38Z · sase-jo.6] PROPOSED FOLLOW-UP: update the declared sase-core-rs floor — just check reports installed floor 0.24.0 is missing published 0.24.4/0.24.5 capabilities while the linked checkout builds 0.24.5

[2026-08-11T13:30:01Z · sase-jo.6] Updated ACE, commit-workflow, CLI/VCS, configuration, Rust-backend docs and the ACE help modal for stitch/auto/manual origins; fixed the stale origin filter/parser/help values to match the canonical taxonomy; verified with uv run pytest tests/test_vcs_log_filter_query.py tests/main/test_stitch_parser.py tests/test_vcs_log_render_pretty.py and just check.

[2026-08-11T13:31:18Z · sase-jo.6] Verified origin documentation/help/filter/schema/parser updates with focused pytest suite and just check

## Dependencies

- **Depends on:** [sase-jo.2](sase-jo.2.md) ✓ · ⧖ 2026-08-11
- **Depends on:** [sase-jo.4](sase-jo.4.md) ✓ · ⧖ 2026-08-11
- **Depends on:** [sase-jo.5](sase-jo.5.md) ✓ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jo.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jo.6/README.md) | [sase-jo.6](sase-jo.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`295f4e9`](https://github.com/sase-org/sase/commit/295f4e994102cc5ac3c61cfd7a127d6af1177e1f) | fix(stitch): align origin filters with canonical values | [sase-jo.6](sase-jo.6.md) | 2026-08-11 09:32:09 EDT |
