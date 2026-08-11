# Bead: sase-jo.5 — origin filter and CLI flag

[Bead Pages](../README.md) / [sase-jo](README.md) / sase-jo.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xv](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xv/README.md) · **Assignee:** `sase-jo.5` · **Size:** medium
**Created:** 2026-08-11 06:59:28 EDT · **Closed:** 2026-08-11 09:08:50 EDT
**Plan:** [202608/stitch\_origin\_badges.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_origin_badges.md)

## Description

filter: add the repeatable, negatable `origin:` key to the Stitches filter query language with completions and canonical rendering, plus the matching `sase stitch log --origin` flag and post-collection filtering.

## Notes

[2026-08-11T12:52:24Z · sase-jo.5] PROPOSED FOLLOW-UP: Design/implementation mismatch in the origin taxonomy. plans:202608/stitch_origin_badges.md specifies a closed 3-value taxonomy (stitch/auto/manual) driven by SASE_TYPE= footer precedence rules (TYPE=stitch -> stitch; TYPE=<other> -> auto; legacy AGENT=/BEAD=/PLAN=-only -> stitch; otherwise -> manual). The core phase (sase-jo.1, closed) instead implemented a simpler 2-value CommitOriginWire enum in sase-core (crates/sase_core/src/vcs_log/origin.rs): Manual/Sase, classified purely by "does parse_commit_footer find any tag at all" - no TYPE= precedence, no auto/manual split. The Python wire (sase-jo.3, closed) mirrors this 2-value type (sase.core.vcs_log_wire.CommitOrigin = Literal["manual","sase"]). This filter phase (sase-jo.5) implemented origin:manual/origin:sase filtering against the actual 2-value wire since that is what exists and type-checks; it does not implement the 3-value grammar the design doc describes. The still-open render phase (sase-jo.4) and docs phase (sase-jo.6) will hit the same mismatch - the design's glyph/legend table and detail-panel wording assume 3 values (including an auto-vs-stitch distinction and reading the TYPE value for auto, e.g. "auto . sase init"), which the current wire cannot produce. The still-open invariant phase (sase-jo.2) stamps SASE_TYPE=stitch specifically, but classify_commit_origin() never reads TYPE, so that stamp does not affect classification. Epic land agent should decide: (a) update the plan doc + render/docs phases to match the shipped 2-value reality, or (b) file a task bead to redo the core classifier to implement the originally-specified 3-value TYPE= precedence taxonomy before render/docs land.

[2026-08-11T13:08:50Z · sase-jo.5] Verified via 'just check' (exit 0): all lint gates passed (fmt, ruff, mypy, pyscripts, symvision, etc.) and the test suite (scoped, escalated to full) passed. Implemented origin: filter key (repeatable/negatable) in filter_query.py with completions and canonical token rendering, --origin CLI flag in parser_stitch.py wired through stitch_handler.py, render-side origin summary/empty-message text in _render_util.py, commit_filter_bar.py UI wiring, and sase.schema.json update. Added/extended tests in test_vcs_log_filter_query.py, test_stitch_parser.py, test_vcs_log_render_pretty.py, test_external_mirror_issues.py. Filters against the actual 2-value CommitOriginWire (manual/sase) per sase-jo.3; see prior PROPOSED FOLLOW-UP note on this bead re: 3-value taxonomy mismatch with the design doc for render/docs phases to address.

## Dependencies

- **Depends on:** [sase-jo.3](sase-jo.3.md) ✓ · ⧖ 2026-08-11
- **Blocks:** [sase-jo.6](sase-jo.6.md) ◐ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jo.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jo.5/README.md) | [sase-jo.5](sase-jo.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e1b39c7`](https://github.com/sase-org/sase/commit/e1b39c72cc47309676c4bff76c8769da2a8f260f) | feat(vcs-log): add origin filter key and --origin CLI flag | [sase-jo.5](sase-jo.5.md) | 2026-08-11 09:09:34 EDT |
