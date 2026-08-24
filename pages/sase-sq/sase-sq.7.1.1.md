# Bead: sase-sq.7.1.1 — File-backed glossary source wire

[Bead Pages](../README.md) / [sase-sq.7.1](sase-sq.7.1.md) / sase-sq.7.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-sq.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.7.md) · **Assignee:** `sase-sq.7.1.1` · **Size:** medium
**Created:** 2026-08-24 18:15:34 EDT · **Closed:** 2026-08-24 19:16:45 EDT
**Plan:** [202608/glossary\_memory\_web.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_memory_web.md)

## Description

wire: generalize sase-core's GlossarySourceWire from config_path/config_key_path to source_path plus an optional key_path with keyword_range/body_range, bump GLOSSARY_WIRE_SCHEMA_VERSION to 2 keeping v1 keys accepted on read, and update the Python GlossarySource adapter and its readers to emit new names and accept both.

## Notes

[2026-08-24T23:15:48Z · sase-sq.7.1.1] PROPOSED FOLLOW-UP: repair home memory init drift blocking just check — primary just check fails in sase validate because init memory --check wants to update ~/.local/share/chezmoi/home/sase/memory/sase.md and ~/.local/share/chezmoi/home/sase/memory/README.md; requires explicit memory update permission.

[2026-08-24T23:15:50Z · sase-sq.7.1.1] PROPOSED FOLLOW-UP: investigate full-suite plan approval hang/failure — test-scoped escalated to the full suite for core-identity-changed, showed one failure marker, then hung in tests/test_plan_approval_launch_reliability_integration.py::test_combined_tale_approval_to_coder_link_lifecycle waiting for a gate response; run was interrupted after a py-spy stack snapshot.

[2026-08-24T23:15:52Z · sase-sq.7.1.1] PROPOSED FOLLOW-UP: ratchet sase-core-rs floor after release — v2 GlossarySourceWire now lands in sase-core; once released, run tools/ratchet_core_window so the published floor exposes source_path/key_path/keyword_range/body_range.

[2026-08-24T23:16:45Z · sase-sq.7.1.1] Implemented v2 GlossarySourceWire and Python v2/tolerant adapter. Verified focused pytest 31 passed; cargo test -p sase_core glossary --lib 21 passed; sase-core just check passed with PYO3_PYTHON/LD_LIBRARY_PATH. Primary just check passed lints before failing in SASE validation only on home memory init drift; validate-committed-plans and core-floor advisory passed separately; test-scoped escalated to full suite and was interrupted after unrelated plan approval integration hang.

## Dependencies

- **Blocks:** [sase-sq.7.1.3](sase-sq.7.1.3.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.7.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sq.7.1.1/README.md) | [sase-sq.7.1.1](sase-sq.7.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`af27e67`](https://github.com/sase-org/sase/commit/af27e67e06f1e9e185bc08e1581832e4cdd4f743) | feat(glossary): emit v2 source wire fields | [sase-sq.7.1.1](sase-sq.7.1.1.md) | 2026-08-24 19:19:45 EDT |
