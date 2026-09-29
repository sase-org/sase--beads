# Bead: sase-1ck.4.1.1 — Flag, authoring service, and note verb

[Bead Pages](../README.md) / [sase-1ck.4.1](sase-1ck.4.1.md) / sase-1ck.4.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ck.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.4.md) · **Assignee:** `sase-1ck.4.1.1` · **Size:** medium
**Created:** 2026-09-29 12:24:47 EDT · **Closed:** 2026-09-29 13:22:19 EDT
**Plan:** [202609/note\_cli.md](https://github.com/sase-org/sase--plans/blob/main/202609/note_cli.md)

## Description

note_authoring: add the beta flag, the note attachment model, and the shared authoring service, and wire them into sase bead note and the TUI add-note modal.

## Notes

[2026-09-29T17:21:49Z · sase-1ck.4.1.1] PROPOSED FOLLOW-UP: patch-stitch-terminology audit fails on clean tree too (sase-core fixture at_bearing_notes.jsonl ChangeSpec lines) — needs a sase-core-side or audit-baseline fix, out of scope for note_authoring.

[2026-09-29T17:22:01Z · sase-1ck.4.1.1] PROPOSED FOLLOW-UP: bead-work launch-family tests (test_partial_launch_cleanup, test_cli_work_*) fail identically on the clean tree in this sandbox (origin-kwarg TypeError, doctor/publish errors) — environmental, needs a launch-infra owner.

[2026-09-29T17:22:19Z · sase-1ck.4.1.1] note_authoring landed: bead_note_attachments beta flag (bead sase-1cl) with registry+schema sync; BeadNoteAttachment model+codec (empty manifests omit the key); attachments threading through facade and note/edit/close/+1 mixins; read_note_text_value (256 KiB cap, @@ passthrough, TTY confirm); authoring service (scan/resolve/caret diagnostics/ingest-once/classify/probe/origin/uniquify/compose, local-only echo); sase bead note wiring with -S and mental-model help; note fast-path @-anywhere rule; TUI add-note service call with modal retry. Verified: just fix clean; ruff/mypy/symvision/flags/pyscripts/waits/changelog/fmt gates pass; 20 new tests + note/fast-path/codec/config/flag/CAS neighbors green; full test_bead 2466 passed (launch-family + terminology failures reproduce identically on clean tree, filed as follow-ups); epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1ck.4.1.2](sase-1ck.4.1.2.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1ck.4.1.3](sase-1ck.4.1.3.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.4.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.4.1.1/README.md) | [sase-1ck.4.1.1](sase-1ck.4.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7226499`](https://github.com/sase-org/sase/commit/7226499078638432f3c868dc53772fae77f31b45) | feat(beads): note authoring for bead note attachments beta | [sase-1ck.4.1.1](sase-1ck.4.1.1.md) | 2026-09-29 13:24:09 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ck.4.1.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.4.1.1/README.md

<!-- sase:referenced-by:end -->
