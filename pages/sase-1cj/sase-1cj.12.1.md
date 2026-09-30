# Bead: sase-1cj.12.1 — Core tokenizer, support, and origin correctness in sase-core

[Bead Pages](../README.md) / [sase-1cj.12](sase-1cj.12.md) / sase-1cj.12.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1cj.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.land.md) · **Assignee:** `sase-1cj.12.1` · **Size:** medium
**Created:** 2026-09-29 18:29:14 EDT · **Closed:** 2026-09-30 07:21:26 EDT
**Plan:** [202609/finish\_prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_prompt_next_word_prediction.md)

## Previously Closed

> ↺ Closed 2026-09-29T23:16:22Z · done
>
> (none)
>
> Reopened 2026-09-30T11:04:42Z by `sase bead open`

## Description

core-correctness: block structural and alternation tails at query time, treat alternation spans as excluded regions, count support once per row instead of adding project partitions, replace the invented origin markers with a real inventory, make casing canonicalization deterministic, and add the missing gate, blocked-context, and boundary tests.

## Notes

[2026-09-29T23:16:22Z · sase-1cj.12.1] core-correctness done in sase-core: structural/alternation tails block at query (keep-tail tokenizer, alternation excluded spans, unclosed_alternation), rank_prefix mirrors block, support counts once per row (project adds mass only; replay mirrors; sase_core_py fixture +2 rows to reach support 4), origin drops invented %swarm/%lead and direct-matches #bd/work_task #bd/land_epic with tests, BTreeMap deterministic casing, closing punctuation keeps sentence boundary. Verified: sase tool run check in sase-core green (b263c1dcffe04ad53effaef1349566fe), prompt_prediction 81 passed/1 ignored, binding 5 passed, epic-symbols clean for sase-1cj.12.1. rows_generated_skipped: fixture corpus 0/6 used; real-history SWARM/LEAD zero hits per grep, WORK_TASK/LAND_EPIC direct is strict superset (full replay recalibration deferred to core-perf/recalibrate).

[2026-09-30T10:29:23Z · sase-1d6.2] UNLANDED PRIOR ATTEMPT: agent sase-1cj.12.1's completion note (bead note #1) describes verified sase-core work that NEVER LANDED. The host commit finalizer failed on the sase-core stitch with missing_bead_action (the pinned-sibling commit regression; fix is epic sase-1d6 phase sase-1d6.1). No commit from this run exists in sase or sase-core origin/master. Salvage held workspace sase_14 (claim ace(run)-260929_183051) read-only; nothing there was staged, committed, moved, or cleaned.

Attached patch (verified with git apply --check against a pristine checkout of the base SHA):
@attachment:sase-1cj.12.1-core.patch
- repo: sase-core, base SHA 1e51ff3ce9c53ee1a4bc9f52c3642ac4eea8f423, 7 files, 35280 bytes (6 prompt_prediction paths + sase_core_py prompt_prediction tests). sase side was clean.
- intended sase-core commit message: fix(prompt-prediction): block structural tails, count support once, real origin inventory

Instructions to the relaunched agent: apply onto current origin/master with git apply --3way, resolve any conflicts (master has moved), then RE-RUN verification in sase-core (sase tool run check; prompt_prediction suite; bindings) instead of trusting the old note.

[2026-09-30T11:05:41Z · sase-1d6.3] REOPENED: bead closed before its verified work landed (pinned-sibling commit regression). Fix is live on host (63bde575f0, sase 0.17.1+1852.g63bde57). Relaunched agent must apply the UNLANDED PRIOR ATTEMPT patches with git apply --3way, resolve conflicts against current master, and re-verify.

[2026-09-30T11:21:26Z · sase-1cj.12.1] Salvaged unlanded patch onto current origin/master (a354a8a): git apply --3way clean on all 7 files, 522+/60-. Verified in sase-core: sase tool run check green (run 6b4d9877fe5a949d2d62453b70696a08, 336s), prompt_prediction 81 passed/1 ignored, sase_core_py binding 5 passed, epic-symbols clean. Structural/alternation tails block at query + rank_prefix mirrors, support counted once per row (replay mirrors), real origin inventory (zero %swarm/%lead hits in sase src), BTreeMap deterministic casing, closing-punctuation boundary kept. Changes left in sase-core working tree for host finalizer commit.

## Attachments

- 🔒 sase-1cj.12.1-core.patch · text/plain · 34.4531 KiB (private attachment)

## Dependencies

- **Blocks:** [sase-1cj.12.3](sase-1cj.12.3.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.12.4](sase-1cj.12.4.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.12.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.1/README.md) | [sase-1cj.12.1](sase-1cj.12.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cfc6385`](https://github.com/sase-org/sase-core/commit/cfc6385b8a86e9e625c6e85fba37cb16fec86c8f) | fix(prompt\_prediction): salvage unlanded core-correctness patch onto origin/master | [sase-1cj.12.1](sase-1cj.12.1.md) | 2026-09-30 07:24:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0ub--1][1] | Verify attachment span fix renders colored bead detail | 1 |
| read-by | [agent:sase-1cj.12.1][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1d6.land][3] | Need salvage notes, reopen notes, and current status of the five recovered beads | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ub.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d6.land/README.md

<!-- sase:referenced-by:end -->
