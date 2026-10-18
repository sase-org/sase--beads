# Bead: sase-1m3.7 — Code snapshot, role classifier, tokei gate, and records tier

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.7` · **Size:** large
**Created:** 2026-10-16 22:05:24 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

core-code: measure role-classified lines over each code repo's committed tree with a per-blob incremental cache, run the tokei dependency gate (falling back to non-blank lines), and summarize the records tier.

## Notes

[2026-10-17T06:52:07Z · sase-1m3.7] PROPOSED FOLLOW-UP: Stats attribution decision record deferred — the parent epic selected stats_decision_record=no without human review; no decisions-web record or other memory edit is authorized for this phase.

[2026-10-18T17:58:58Z · sase-1m3.7.1.5--4] MEASUREMENT EVIDENCE (child phase sase-1m3.7.1.5): tokei 15.0.0 default-features=false passed both required release gates (+0.159 MiB wheel; 0.980x clean build time). Production SLOC and parser-sensitive cache tests pass (126 core, 7 binding); actual release binding verifies real sase plus plans metadata, records no-content reads, unknown vs zero, policy consistency, and ambient-config independence. Final source tree c4299924ba07377277914e4c7b6304b3f1ec90e7 has 14,477 tracked files / 12,432 code files / 2,414,148 SLOC. Same-tip median 37.187 ms meets <150 ms; cold 7.628 s (fixture 6.397–8.571 s) misses <=5 s, changed-tip 0.922 s misses <0.5 s. Audit proves zero same-tip and exactly one changed-tip blob, with changed result equal to cold. PROPOSED FOLLOW-UP: Profile cold parsing and shared changed-tip tree/attribute/cache reconstruction; nonblank baseline also took 0.616 s changed-tip. Instrumented changed-tip Git work was 0.575 s (0.177 ls-tree, 0.336 committed attributes, 0.005 cat-file); do not equate audit-wrapper latency with uninstrumented runtime. Final report/evidence and whole-repo check results will be linked from the child phase. No ancestor closure or memory edits performed.

[2026-10-18T18:33:47Z · sase-1m3.7.1.5--4] GATE CORRECTION from child sase-1m3.7.1.5: withdraw the earlier clean-build-time PASS claim (0.980x). The experiment inherited CARGO_BUILD_BUILD_DIR, sharing compilation intermediates despite distinct CARGO_TARGET_DIR paths. Candidate logs omit baseline-compiled dependencies (106 versus 206 compiled packages; no proc-macro2); target dirs lack intermediate fingerprints. Wheel-size evidence (+0.159 MiB) remains valid, but clean timing requires a corrected isolated pair before tokei adoption/phase closure. The child has prepared fresh target/build directories per variant and will measure them through monitor. Production correctness tests and runtime benchmark results remain valid; core whole check also passed unchanged on retry after tracked flake sase-1gz. No ancestor is closed.

[2026-10-18T22:09:09Z · sase-1m3.7.1.5--6] MEASUREMENT COMPLETE for child sase-1m3.7.1.5: corrected isolated tokei gate PASSED, wheel growth 159,459 bytes (0.152072 MiB), clean time 1,867.069330 to 2,068.594694 s (1.107937x). Adopted tokei 15.0.0 with explicit config and parser-sensitive cache reuse. Old shared-build-dir timing remains invalid. Durable report file:explicit:f8fc12f54cb3f9b647451035; reproducible evidence file:explicit:cf0a3ec863e10c52c0785b78. Actual binding same-tip 37.187 ms meets target; cold 7.628 s and changed-tip 0.922 s remain the previously recorded performance follow-up. Zero same-tip/one changed-tip blobs, cold equality, records metadata/no-content reads and availability/counter invariants verified. Targeted core/binding tests and core whole retry pass. Primary check remains exit 1 (56,389 passed, 33 skipped, 21 failed): 17 nodes have independent known witnesses; three initially NEW TUI nodes reproduce identically on clean-primary/pre-phase nonblank core; update-toast passes both focused retries. Baseline and worker/selection caveats, failure logs and JUnit are retained. Follow-ups are on the child for land-agent triage; no new beads or ancestor closure. Host finalization will commit both repositories and advance the primary core pin.

## Dependencies

- **Blocks:** [sase-1m3.10](sase-1m3.10.md) ◐ · ⧖ 2026-10-16
- **Blocks:** [sase-1m3.11](sase-1m3.11.md) ◐ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.4](sase-1m3.4.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.md) | [sase-1m3.7](sase-1m3.7.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.7.1.5--6][1] | Verify parent received final phase evidence and runtime follow-ups | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.1.5.md

<!-- sase:referenced-by:end -->
