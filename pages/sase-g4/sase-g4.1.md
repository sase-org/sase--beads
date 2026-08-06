# Bead: sase-g4.1 — A header-block validity rule in the Rust plan validator

[Bead Pages](../README.md) / [sase-g4](README.md) / sase-g4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ty](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ty/README.md) · **Assignee:** `sase-g4.1` · **Size:** medium
**Created:** 2026-08-06 09:05:22 EDT · **Closed:** 2026-08-06 09:22:49 EDT
**Plan:** [202608/plan\_header\_validation.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_header_validation.md)

## Description

core-diagnostic: teach `plan_validate` in sase-core to emit an error diagnostic when the document's leading plan-header block does not parse, carrying the parser's reason and the offending bullet's line, without touching the plan-header block wire schema; then land it and let release-plz publish the wheel.

## Notes

[2026-08-06T13:54:42Z · sase-g4.1] Verified: `plan_validate` now emits one `error` diagnostic, code `header-invalid`, field_path empty, `line` = the offending bullet 1-based in the whole document including frontmatter, message = parser reason + canonical form. Landed as feat 508d5d9 on sase-core master; CI green; release-plz published **sase-core-rs 0.18.4** (PyPI 200) — that is the version core-adopt (sase-g4.3) should raise the pyproject floor to, and it stays inside the existing `<0.19.0` cap. Wire untouched: PLAN_HEADER_BLOCK_WIRE_SCHEMA_VERSION still 3 and the parse payload keys are unchanged, confirmed against the published wheel. Rust tests cover trailing text on PARENT/PLAN/BEAD, duplicate section, unknown section key, malformed link, a bad list entry, canonical header, absent header, and header-shaped bullets in prose and inside a fence (no diagnostic); plus a test that the rule does not short-circuit frontmatter diagnostics. Corpus sweep over 4648 markdown files (committed plans store + ~/.sase/plans) reports exactly one invalid header: selection_soundness.md line 63, the plan already failing at its archive step. No Python changes, per the phase non-goals.

[2026-08-06T13:55:25Z · sase-g4.1] PROPOSED FOLLOW-UP: flaky sase-core test — `editor::completion::tests::commit_inventory_skips_sidecars_before_reporting_the_row_cap` failed in CI run 31099595038 with `git commit failed: fatal: could not parse HEAD`, then passed on re-run of the same tree; it builds a git fixture and is sensitive to an empty/unborn HEAD.

[2026-08-06T13:56:07Z · sase-g4.1] PROPOSED FOLLOW-UP: an unknown header key can only be reported when it follows a known one — `first_header_candidate` requires the block to start with a known key, so a leading `- **NOPE:** [x](x.md)` bullet is treated as prose and no header block is detected at all. Worth deciding whether a leading unknown bolded-key bullet should be diagnosed rather than silently ignored.

## Dependencies

- **Blocks:** [sase-g4.3](sase-g4.3.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-g4.5](sase-g4.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g4.1/README.md) | [sase-g4.1](sase-g4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@508d5d9`](https://github.com/sase-org/sase-core/commit/508d5d99f4ba81ef405a2421662fef6ad9d4a9e1) | feat(plan): reject a malformed plan header block during validation | [sase-g4.1](sase-g4.1.md) | 2026-08-06 09:23:14 EDT |
