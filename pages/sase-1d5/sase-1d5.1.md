# Bead: sase-1d5.1 — Core audience wire, decision table, and secret scanner (sase-core)

[Bead Pages](../README.md) / [sase-1d5](README.md) / sase-1d5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tz.md) · **Assignee:** `sase-1d5.1` · **Size:** large
**Created:** 2026-09-30 01:57:08 EDT · **Closed:** 2026-09-30 08:50:32 EDT
**Plan:** [202609/public\_bead\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/public_bead_attachments.md)

## Previously Closed

> ↺ Closed 2026-09-30T06:56:18Z · done
>
> (none)
>
> Reopened 2026-09-30T11:04:23Z by `sase bead open`

## Description

core_audience: add the optional descriptor visibility field (absent means private), the ordered attachment_audience_decision rule table with SASE zone and secret-file tables, the streaming secret scanner, the canonical MIME extension table and public object layout, and visibility on the roster and reference queries, plus Python bindings and tests that use only synthetic secrets.

## Notes

[2026-09-30T06:56:18Z · sase-1d5.1] Implemented core attachment audience in sase-core: visibility wire with private fallback plus effective_visibility, roster/reference queries covering IssueCreated notes and +1 evidence with plus-one:reporter keys and visibility/source fields, ordered 10-rule audience decision with SASE zone/secret tables and widening, streaming secret scanner (rules v1, known-value/credential/env-dump detectors, chunk-safe, bounded long lines), canonical MIME extension table with public/old path round-trip, and six new Python bindings with round-trip tests. Evidence: just test -p sase_core attachment 74 passed; just test -p sase_core_py note_attachment 6 passed; sase tool run check succeeded (run 5b8f2d8a34a20d18ea842e074cd57212).

[2026-09-30T10:28:33Z · sase-1d6.2] UNLANDED PRIOR ATTEMPT: agent sase-1d5.1's completion note (bead note #1) describes verified sase-core work that NEVER LANDED. The host commit finalizer failed on the sase-core stitch with missing_bead_action (the pinned-sibling commit regression; fix is epic sase-1d6 phase sase-1d6.1). No commit from this run exists in sase or sase-core origin/master. Salvage held workspace sase_13 (claim ace(run)-260930_015851) read-only; nothing there was staged, committed, moved, or cleaned.

Attached patch (verified with git apply --check against a pristine checkout of the base SHA):
🔒 sase-1d5.1-core.patch
- repo: sase-core, base SHA a354a8a96c06443fb2ed47b5699e9ae2142862d7, 20 files, 111224 bytes (13 tracked modifications + 7 new files incl. note_attachment/audience.rs, public_objects.rs, scanner.rs, zones.rs). sase side was clean.
- intended sase-core commit message: feat(attachments): core attachment audience policy and scanner
- approved phase plan: plan:202609/core_attachment_audience.md

Instructions to the relaunched agent: apply onto current origin/master with git apply --3way, resolve any conflicts (master has moved), then RE-RUN verification (just test -p sase_core attachment; sase_core_py note_attachment; sase tool run check) instead of trusting the old note. Reuse the approved plan; do not re-plan from scratch.

[2026-09-30T11:05:16Z · sase-1d6.3] REOPENED: bead closed before its verified work landed (pinned-sibling commit regression). Fix is live on host (63bde575f0, sase 0.17.1+1852.g63bde57). Relaunched agent must apply the UNLANDED PRIOR ATTEMPT patches with git apply --3way, resolve conflicts against current master, and re-verify.

[2026-09-30T12:30:28Z · sase-1d5.1--1] Salvage re-verification (sase-core cfc6385, patch applied, staged): just test -p sase_core attachment 74 passed; just test -p sase_core_py note_attachment 6 passed. Full sase-core gate running in monitor; will close on green. Prior sase-repo just check failure is cross-repo prompt_prediction skew (sase validator expects confident ghost, core HEAD behavior differs) — out of scope for this phase, sase tree untouched.

[2026-09-30T12:50:32Z · sase-1d5.1--2] Salvage verified and green. sase-core HEAD cfc6385 with the UNLANDED PRIOR ATTEMPT patch applied (staged, 20 files: sase_core audience/scanner/zones/public_objects + bindings/tests). Evidence: cargo test -p sase_core attachment 74 passed; just test -p sase_core_py note_attachment 6 passed; full sase tool run check PASSED (run c56a2231b4dcb643fbdb480873d7970a, exit 0). The 4 sase_gateway fleet failures in the earlier monitored gate (run 80ec0a53c3c43fad57ba324e01f5f7d4, exit 101) were load-induced flakes unrelated to the patch (patch touches only sase_core/sase_core_py, no gateway files): all 4 passed on in-place retry with the patch applied. Sase repo tree untouched. Epic sase-1d5 left open.

## Attachments

- 🔒 sase-1d5.1-core.patch · text/plain · 108.617 KiB (private attachment)

## Dependencies

- **Blocks:** [sase-1d5.3](sase-1d5.3.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d5.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d5.1.md) | [sase-1d5.1](sase-1d5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7806f58`](https://github.com/sase-org/sase-core/commit/7806f587b0971816fe2623db835dde4582925063) | feat(attachments): core attachment audience policy and scanner | [sase-1d5.1](sase-1d5.1.md) | 2026-09-30 08:51:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0ub--1][1] | Verify attachment span fix renders colored bead detail | 1 |
| read-by | [agent:sase-1d5.1--2][2] | inspect phase status after failed sase-core gate | 1 |
| read-by | [agent:sase-1d5.land][3] | Need the child scope and notes | 1 |
| read-by | [agent:sase-1d6.land][4] | Need salvage notes, reopen notes, and current status of the five recovered beads | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ub.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d5.1.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d5.land/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d6.land/README.md

<!-- sase:referenced-by:end -->
