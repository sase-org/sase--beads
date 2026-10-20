# Bead: sase-1n6.1 — Core-cut resilience and the in-flight retention source

[Bead Pages](../README.md) / [sase-1n6](README.md) / sase-1n6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11y](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11y.md) · **Assignee:** `sase-1n6.1` · **Size:** medium
**Created:** 2026-10-19 16:40:08 EDT · **Closed:** 2026-10-19 17:58:00 EDT
**Plan:** [202610/e2\_release\_train\_steward.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_release_train_steward.md)

## Description

core-release: in sase-core, the release-plz merge job reruns failed checks once and emits a typed CORE_CUT_RED, and retention also protects the exact core pins of sase tags not yet on PyPI.

## Notes

[2026-10-19T21:20:07Z · sase-1n6.1] Verification (2026-10-19): sase-core offline release-merge, retention, and cadence acceptance suites passed; full `sase tool run check` passed (ToolRun 673b5b6f3b6688cc82f78425fb6a973d). Live `plan --keep 30` matched E1 V-E1a: 0.42.0 and 0.42.1 remain protected with five files each, with the sase 0.18.0 requirement named; no in-flight exact-pin tag entries were present. The next daily cut run log is pending host landing; no scheduled cut using this helper ran before phase close.

[2026-10-19T21:58:00Z · sase-1n6.1] Implemented the bounded typed core-release retry and in-flight exact-pin retention source. Offline acceptance suites and  passed (ToolRun 673b5b6f3b6688cc82f78425fb6a973d); live plan --keep 30 matches E1 V-E1a with 0.42.0/0.42.1 protected, and no in-flight exact-pin tags. Next scheduled cut run remains pending host landing.

[2026-10-19T22:01:20Z · sase-1n6.1] PROPOSED FOLLOW-UP: Full check ToolRun 5c9b9df420c1c63117acc5c135007675 ran on clean SASE root HEAD 4e5b7d2eb6; exact rerun ToolRun 35e996fe7b22e9d04e0b2307e09ff9e1 reproduced all three failed nodes. The stats-project argparse goldens are already recorded by sase-1n6.2#3 and the sase-1m3 landing notes; related cross-version argparse task: sase-14p. The contract-manifest node is recorded by sase-1m3.12#5 and routed in sase-1m3#7 to the sase-1my landing; re-triage if the mismatch remains after that refresh.

## Dependencies

- **Blocks:** [sase-1n6.7](sase-1n6.7.md) ✓ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.1/README.md) | [sase-1n6.1](sase-1n6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3f0920f`](https://github.com/sase-org/sase-core/commit/3f0920f89d70f307469d6826fd94bda1c9b441d4) | feat(release): add bounded core-cut retries and in-flight retention | [sase-1n6.1](sase-1n6.1.md) | 2026-10-19 18:02:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.1][1] | Verify phase closure and the clean-base follow-up note | 6 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.1/README.md

<!-- sase:referenced-by:end -->
