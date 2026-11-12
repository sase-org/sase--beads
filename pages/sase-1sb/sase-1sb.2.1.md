# Bead: sase-1sb.2.1 — Digest-pinned trust for project-local commands

[Bead Pages](../README.md) / [sase-1sb.2](sase-1sb.2.md) / sase-1sb.2.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1sb.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.md) · **Assignee:** `sase-1sb.2.1.land`
**Created:** 2026-11-11 20:34:37 EST
**Plan:** [202611/local\_config\_digest\_trust.md](https://github.com/sase-org/sase--plans/blob/main/202611/local_config_digest_trust.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/local_config_digest_trust.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:f7ff68994727a64108f4cdd2 | attached via sase artifact create --bead |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/local_config_digest_trust.md

<!-- sase:links:end -->

## Description

Require human acknowledgment of a project's current executable config before host-side hooks or config-defined workflows can run, while preserving ordinary local configuration.

## Notes

[2026-11-12T10:30:38Z · sase-1sb.2.1.land] LANDING AUDIT: NOT READY TO CLOSE. Read epic (no prior own notes), all four child beads and every child note, approved plan, all five sase epic commits 2e7ce5cea1/181b213e8c/7710dd0bc6/021cd73021/ea4121387b, and core e7647bf7/233cb41d. Inspected Rust classifier/digest/store/bindings and Python identity/CLI/loaders/execution boundaries. Pin 233cb41d6bb7186a711e75999394570e9ad9943e contains required exports. Digest-trust decision, human acknowledgment, and default-On sunset flag are implemented, but runtime acceptance is incomplete.

Independent verification: four trust suites together = 51 passed in 8.54s. No check-full. Safe deterministic probes in file:explicit:f7ff68994727a64108f4cdd2 demonstrate: (1) ordinary macro loader attaches approved snapshot B's descriptor to retained code A; (2) revoke between rebase merged-load and reevaluation yields retained local command with trust=None and reaches mocked execute_gate; (3) explicitly local file-hook run without descriptor is allowed; (4) Off-loaded workflow passes script guard after flag becomes On without approval; (5) revoked local embedded pre-step executes a temporary sentinel through a user-origin parent, while the direct child check correctly blocks; (6) merged config cache returns the same revoked command mapping after revoke; (7) acknowledged sparse local input override is discarded and returns user default/source without local provenance. File-hook dispatch also rereads ambient config instead of carrying original hook trust; loader evaluation exceptions fail open. These are remaining epic work, not task follow-ups.

Integration: fetched origin, HEAD=origin/master=ea4121387b. Non-child commits since first trust commit are d0dc942c16 (sibling prompt provenance) and 1e4bcb5f38 (docs refresh); reviewed shared embedded/rendering paths and docs. Preserve their safeguards while repairing snapshot propagation; no core drift after the two core epic commits. Required full landing checks will follow repairs.

Symbol readiness: epic-symbols lists six ROOT-epic entries despite phase-local empty reports: LocalCommandDigest, LocalCommandTrustError, LocalTrustDecision, LocalTrustFilterResult, digest_local_commands, local_command_trust_wire_schema_version. Planned disposition: privatize the three in-module-only classes; delete unused Python digest wrapper/return type and version wrapper, retaining consumed projection/direct Rust wire tests and Rust ABI; remove six Justfile exemptions.

FOLLOW-UP TRIAGE COMPLETE: the sole proposal, .3 note #1 edit-lock concurrency flake, was searched across all-status tasks and recent tasks and checked against active epic scope. Deterministically reproduced two owners from an empty-lock publication window in .5's code; recorded DISCOVERED ISSUE on causal active parent epic sase-1sb with the evidence ref. No duplicate/new task; declined quarantine/retry because this is a real ownership race. No other child proposals. Proposing one medium tale to fix the bounded trust integration gaps, rerun checks, clean symbols, close this epic normally, mark plan:202611/local_config_digest_trust.md done, and close only delegated parent phase sase-1sb.2. Do not close containing epic sase-1sb.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.2.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.land.md) | [sase-1sb.2.1](sase-1sb.2.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`681de35`](https://github.com/sase-org/sase/commit/681de3542bdd024f8aa3ccfe247a9f1aa4b42ef2) | fix(config): enforce local command trust provenance | [sase-1sb.2.1](sase-1sb.2.1.md) | 2026-11-12 11:06:29 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1sb.2.1.1--1][1] | Check parent epic scope | 1 |
| read-by | [agent:sase-1sb.2.1.4][2] | Need parent epic DECISIONS, phases, and remaining child work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.2.1.4/README.md

<!-- sase:referenced-by:end -->
