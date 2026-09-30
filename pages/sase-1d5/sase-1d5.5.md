# Bead: sase-1d5.5 — Publish, unpublish, and audience-aware doctor

[Bead Pages](../README.md) / [sase-1d5](README.md) / sase-1d5.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tz.md) · **Assignee:** `sase-1d5.5` · **Size:** medium
**Created:** 2026-09-30 01:57:15 EDT · **Closed:** 2026-09-30 13:28:56 EDT
**Plan:** [202609/public\_bead\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/public_bead_attachments.md)

## Description

publish_lifecycle: add the human-only (gate-compatible) sase bead attachment publish and the narrowing unpublish, both editing manifests through NoteEdited. Add doctor rescans keyed to the scanner rules version, store growth, push access, and a private-store-is-anonymously-readable finding.

## Notes

[2026-09-30T17:28:19Z · sase-1d5.5--1] PROPOSED FOLLOW-UP: `sase tool run check` fails in `_setup` at `tools/validate_sase_core_rs` on the clean base tree too — the installed sase_core_rs 0.36.1 (linked sase-core checkout ahead of pyproject `>=0.35.0,<0.36.0` window) returns confident=False for the "help me implement" prompt-prediction probe, but the validator requires confident=True. Environment/version-skew issue, unrelated to publish_lifecycle. Related closed-bead note: sase-1df.6 observed the same confident=False symptom.

[2026-09-30T17:28:56Z · sase-1d5.5--1] publish/unpublish CLIs, NoteEdited manifest edits, rules-version rescans, store growth/push-access/private-readable findings all landed and verified: new publish-lifecycle suite 9/9 pass, full tests/test_bead 2626 pass, ruff/ruff-format/mypy clean.  cannot pass in this workspace due to a pre-existing sase-core 0.36.1 vs validator skew (confident=False probe) that reproduces identically on the clean base tree; recorded as PROPOSED FOLLOW-UP. No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1d5.4](sase-1d5.4.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d5.8](sase-1d5.8.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d5.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d5.5.md) | [sase-1d5.5](sase-1d5.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e1f10ca`](https://github.com/sase-org/sase/commit/e1f10caaf0bc5d58801a9056816f5772677c96bf) | feat(bead-attachments): add publish/unpublish lifecycle and audience-aware doctor | [sase-1d5.5](sase-1d5.5.md) | 2026-09-30 13:31:21 EDT |
