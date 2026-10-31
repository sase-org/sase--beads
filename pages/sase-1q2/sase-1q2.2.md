# Bead: sase-1q2.2 — A complete published sase-core-rs contains master's core revision, and master pins it

[Bead Pages](../README.md) / [sase-1q2](README.md) / sase-1q2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.16e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.16e.md) · **Size:** medium
**Created:** 2026-10-30 12:37:06 EDT · **Closed:** 2026-10-30 15:02:50 EDT
**Plan:** [202610/v0\_19\_0\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_19_0_release.md)

## Description

core-publish: get a complete sase-core-rs that contains the source pin onto PyPI (one rerun of the failed 0.43.2 upload, or a wait for the daily cut), then ratchet master's exact pin and prove the bindings.

## Notes

[2026-10-30T17:56:10Z · sase-1q2.2] Reran sase-core release-plz run 41077488562 --failed (publish-to-PyPI Rekor HTTP 502, attempt 1, all builds green); new publish job 124222014164 in progress. Waiting on PyPI for sase-core-rs 0.43.2 containing pin 17e79c8c. -r record rerun evidence for follow-up

[2026-10-30T19:02:50Z · sase-1q2.2--2] core-publish complete: ratcheted master exact pin sase-core-rs==0.43.2 (pyproject.toml + uv.lock only, sase-core-revision.txt=17e79c8c unchanged). origin/master check reports PINNED(0.43.2, 5 files) ratchet 0.42.7->0.43.2 pending exit 2, local diff resolves it. Bindings: sase_core_rs 0.43.2 exposes all 901 bindings (exit 0, both .venv and /tmp/release-core-floor). validate_sase_core_rs exit 0. Floor smoke 7/7 OK (telemetry, at-reference-file-gate, bead-resolution, feature-flag-state, plan-header, glossary-line-break, tool-runs). Notes already on sase-1pi.1 #8 (v0.43.2, peeled tag SHA 0ec67fdcebccd0154a84168ad54e45e6c5793c1d, five PyPI filenames) and sase-1oe.4 #12 (complete containing core + exact pin ratchet). just fix exit 0, no extra dirty. sase tool run check 89b3e471fc76ddef97318418db6b00f9 succeeded exit 0 34m32s (escalated to full suite, all stages green). epic-symbols empty.

## Dependencies

- **Depends on:** [sase-1q2.1](sase-1q2.1.md) ✓ · ⧖ 2026-10-30
- **Blocks:** [sase-1q2.7](sase-1q2.7.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q2.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q2.2.md) | [sase-1q2.2](sase-1q2.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a41907`](https://github.com/sase-org/sase/commit/1a419071c20f3953562b4576d432700745d4cea6) | chore(core): ratchet sase-core-rs to 0.43.2 | [sase-1q2.2](sase-1q2.2.md) | 2026-10-30 15:04:39 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1q2.2--2][1] | verify before close | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q2.2.md

<!-- sase:referenced-by:end -->
