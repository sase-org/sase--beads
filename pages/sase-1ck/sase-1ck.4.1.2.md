# Bead: sase-1ck.4.1.2 — Close, update, +1, and attach

[Bead Pages](../README.md) / [sase-1ck.4.1](sase-1ck.4.1.md) / sase-1ck.4.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ck.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.4.md) · **Assignee:** `sase-1ck.4.1.2` · **Size:** medium
**Created:** 2026-09-29 12:24:49 EDT · **Closed:** 2026-09-29 14:12:25 EDT
**Plan:** [202609/note\_cli.md](https://github.com/sase-org/sase--plans/blob/main/202609/note_cli.md)

## Description

attach_verbs: run the authoring service from close -n, update -n, and +1 -n, and add sase bead attach including stdin.

## Notes

[2026-09-29T18:11:41Z · sase-1ck.4.1.2] PROPOSED FOLLOW-UP: +1 evidence cannot record attachments at sase-core pin 43f744be — TaskPlusOneEvidenceWire has no manifest field, non-wake +1 with manifest is refused (plus_one_snooze.rs), and the wake path fails the token/manifest one-to-one check because the generated wake note carries no @attachment tokens; CLI passes note_attachments through per plan and surfaces the core refusal with nothing written (pinned by test_plus_one_note_attachments_refused*), so a later sase-1ck phase needs core support before +1 -n can attach

[2026-09-29T18:11:53Z · sase-1ck.4.1.2] PROPOSED FOLLOW-UP: just check stays red on the clean base tree — _lint-patch-stitch-terminology fails byte-identically on sase-core fixture at_bearing_notes.jsonl lines, _lint-symvision reports stale --epic-symbol entries for closed bead sase-1cj.7 (Justfile untouched by this phase), 5 tests/main/test_bead_fast_path* failures and 22 test_cli_work_* failures + 2 errors reproduce identically with this phase stashed; no existing task bead found tracking them

[2026-09-29T18:12:25Z · sase-1ck.4.1.2] attach_verbs done: close/+1/update -n run read_note_text_value + authoring service with -S, manifests passed only when non-empty; update ingests once and composes per bead (authoring before field mutation so failures write nothing); new sase bead attach (-a/-n/-N/-S, stdin via ingest_stream) registered in parser, cli exports, entry map + usage. Verified: new tests/test_bead/test_cli_attach_verbs.py 17 passed; neighbors (note_attachments, at_path_values, parser help) 78 passed incl. attach free-text classification; just fix clean; sase tool run check green except pre-existing terminology lint (byte-identical on base); symvision/validate/test-scoped show only pre-existing base failures (sase-1cj.7 symbols, 5 fast-path, 22 work +2). Noted on bead: +1 manifests unrecordable at core pin 43f744be (refusal pinned by tests, needs later core phase). No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1ck.4.1.1](sase-1ck.4.1.1.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1ck.4.1.3](sase-1ck.4.1.3.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.4.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.4.1.2/README.md) | [sase-1ck.4.1.2](sase-1ck.4.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9cc4570`](https://github.com/sase-org/sase/commit/9cc4570cdd5b0823359523ae8bea814002505dfa) | feat(bead): add attach verbs with sensitive gating | [sase-1ck.4.1.2](sase-1ck.4.1.2.md) | 2026-09-29 14:16:02 EDT |
