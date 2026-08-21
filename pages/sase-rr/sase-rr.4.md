# Bead: sase-rr.4 — Run adversarial and live end-to-end acceptance

[Bead Pages](../README.md) / [sase-rr](README.md) / sase-rr.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.096](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.096.md) · **Assignee:** `sase-rr.4` · **Size:** medium
**Created:** 2026-08-21 13:05:43 UTC · **Closed:** 2026-08-21 19:27:10 UTC
**Plan:** [202608/retire\_pluggable\_finalizers.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_pluggable_finalizers.md)

## Description

e2e-acceptance: exercise the combined unconditional path through disposable repositories and real SASE launches, repair every in-scope defect found, inspect finalizer artifacts and postconditions, and produce the evidence required for landing and closing sase-ro.

## Notes

[2026-08-21T19:26:35Z · sase-rr.4] PROPOSED FOLLOW-UP: just check test-scoped escalated to the full suite (core-identity-changed) because this phase touched the invocation/finalizer identity path; land should run just check-full through a monitor. Full-suite remainder was 22 failures unrelated to finalizers: missing sase-xprompt-lsp binary, skills inventory chezmoi path, and contract-set budget 54 vs 53 (tests/test_xprompt_workflow_schema.py).

[2026-08-21T19:27:10Z · sase-rr.4] Adversarial/live e2e acceptance for unconditional host-owned finalizers: nine live scenarios passed against disposable Git repos and local bare remotes (clean invoke_agent completion with generic finalizer_result.json and no recovery; dirty commit excluding protected baseline dirt and pushing one stitch; %final:none with no mutation; builtin@command plus installable fixture plugin in sealed order through the isolated worker; refusal preserving dirty work; stale post-submit edit recovering once; later-finalizer dirt reactivating commit; first-repo conflict blocking then resuming; plan/monitor/question handoffs skipping the controller). External declaration payloads now invoke provider validate and worker requests carry accepted payload plus host obligations. Fakey retry e2e works after run_execution_loop publishes SASE_AGENT_NAME. Focused finalizer/fakey/live suites passed; just check lint gates green; epic-symbols: no leftovers.

## Dependencies

- **Depends on:** [sase-rr.3](sase-rr.3.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rr.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rr.4/README.md) | [sase-rr.4](sase-rr.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2800900`](https://github.com/sase-org/sase/commit/28009002d5da032104d57805a6df293ffeca6b3e) | fix(finalizers): prove live e2e acceptance and validate external payloads | [sase-rr.4](sase-rr.4.md) | 2026-08-21 19:28:17 UTC |
