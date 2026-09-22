# Bead: sase-165.7 — Incremental check/clippy through the athena rustc wrapper

[Bead Pages](../README.md) / [sase-165](README.md) / sase-165.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0p2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0p2.md) · **Assignee:** `sase-165.7` · **Size:** medium
**Created:** 2026-09-22 08:18:28 EDT · **Closed:** 2026-09-22 12:09:50 EDT
**Plan:** [202609/sase\_core\_p0\_agent\_maintainability.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_p0_agent_maintainability.md)

## Description

incremental-check: sase-rustc-wrapper runs metadata-only incremental units directly and strips incremental from codegen units before sccache, and chezmoi drops incremental=false. A new sase config opt-in replaces the forced CARGO_INCREMENTAL=0 and athena enables it. Measure a ≤30 s edit→check.

## Notes

[2026-09-22T16:40:25Z · sase-165.land] Measured by the sase-165 land agent on athena 2026-09-22 (64 cores, load avg 16-20), sase-core 035851e, fresh CARGO_TARGET_DIR+CARGO_BUILD_BUILD_DIR, RUSTC_WRAPPER=~/bin/sase-rustc-wrapper (deployed chezmoi 034c594b), CARGO_INCREMENTAL=1, via ./scripts/check.sh: cold 'check' 1m35s; append comment to crates/sase_core/src/host_liveness.rs -> re-check 22.07s (target <=30s: MET); incremental dir 2.1G after check, 3.1G after clippy (+ test --no-run adds none). 'check.sh test --no-run' made 220 sccache invocations (PATH shim logging args), 0 carried -C incremental/-Cincremental (214 had --emit ...link). Also verified: 100 targeted tests incl. tests/test_axe_chop_agents_env.py pass; ruff clean. Runtime config loader does not reject unknown keys (installed sase lacking e081abe1c already runs with athena's agent_cargo_incremental: true), so no apply ordering constraint.

## Dependencies

- **Depends on:** [sase-165.6](sase-165.6.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-165.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-165.7.md) | [sase-165.7](sase-165.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e081abe`](https://github.com/sase-org/sase/commit/e081abe1cb9168a20b9ff5a989956d0beb1d96c8) | feat(config): add managed\_tmp.agent\_cargo\_incremental opt-in for agent cargo incremental | [sase-165.7](sase-165.7.md) | 2026-09-22 11:36:45 EDT |
| chezmoi | [`chezmoi@034c594`](https://github.com/bbugyi200/dotfiles/commit/034c594bd4621a306688adad76f306ce8544de36) | feat(cargo): split incremental units via sase-rustc-wrapper for sccache | [sase-165.7](sase-165.7.md) | 2026-09-22 11:40:24 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.29.cld][1] | Audit whether beads whose agents were killed mid-wait were left open (headless early-exit research) | 2 |
| read-by | [agent:sase-165.7--1][2] | finish bead: record measurement results and close | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.29.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-165.7.md

<!-- sase:referenced-by:end -->
