# Bead: sase-z4.6.5.4.5 — Prove actual released floors and retire the rollout flag

[Bead Pages](../README.md) / [sase-z4.6.5.4](sase-z4.6.5.4.md) / sase-z4.6.5.4.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.6.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.5.land.md) · **Assignee:** `sase-z4.6.5.4.5` · **Size:** medium
**Created:** 2026-09-10 17:42:18 EDT · **Closed:** 2026-09-12 05:31:32 EDT
**Plan:** [202609/weighted\_capacity\_remaining\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_remaining_acceptance.md)

## Description

published-floors: establish releases containing the repaired core and host work, verify the exact published wheels in a clean environment, ratchet floors and pins, and close the weighted_queue_capacity flag bead only after the release proof succeeds.

## Notes

[2026-09-10T23:21:34Z · sase-z4.6.5.4.5] BLOCKED: rechecked published floors on 2026-09-10. PyPI JSON and Python 3.12 pip index show installable latest versions remain sase-core-rs 0.33.0, sase 0.17.1, and sase-research-artifacts 0.2.0. Opened sase-core and sase-research-artifacts through sase repo open and read both AGENTS.md files. Core origin/master is 7d6dfcf; no tag contains required lineage-wire commit 120556a, and GitHub releases still stop at v0.33.0. The latest core Release-plz run https://github.com/sase-org/sase-core/actions/runs/34540097125 failed on the same release-pr package check: crates/sase_core_py/Cargo.toml dependency sase_gateway does not specify a version, even though plain local cargo package --workspace --allow-dirty --no-verify passes. SASE HEAD is 3e39ebd; no tag contains it, GitHub releases still stop at v0.17.1, and open release PR #299 for 0.17.2 has failing CI run https://github.com/sase-org/sase/actions/runs/34541199302 because release-core-floor-smoke installs CORE_MINIMUM=0.33.0 and reports sase_core_rs 0.33.0 missing 10 required bindings. Research plugin HEAD is 8f00896; no tag contains it, GitHub releases still stop at v0.2.0, and open release PR #2 for 0.3.0 has failing CI run https://github.com/sase-org/sase-research-artifacts/actions/runs/34474054629 with 8 tests/test_xprompt_loading.py failures from No existing agent name found for template research.{@1}.cdx. Local proof: ./.venv/bin/python tools/probe_core_floor --advisory reports blocked_unpublished for declared floor 0.33.0, naming 10 missing capabilities with no containing core release tag; a scratch Python 3.12 install of sase-core-rs==0.33.0 imports but lacks agent_artifact_index_schema_version. Ran sase bead epic-symbols sase-z4.6.5.4.5: no --epic-symbol entries. No code changes, floor ratchets, wheel-only smoke, or flag close were made; per the phase plan, this bead and flag bead sase-z5 must stay open until the release chain publishes and the positive/negative wheel proof succeeds.

[2026-09-12T10:25:52Z · sase-z4.6.5.4.land] LANDING CORRECTION, 2026-09-12 at primary 96c3877e0: core has released through 0.34.19 and v0.34.0 contains lineage commit da0a7389, but this phase is not functionally complete. PyPI still serves host 0.17.1 and research plugin 0.2.0; no compatible published host/plugin cohort exists. Research HEAD 5aaa244 requires core >=0.33.0,<0.34.0, disjoint from host >=0.34.15,<0.35.0. Release PR #2 CI 34664698929 fails on that conflict before tests; wheel assertions also hard-code 0.33.*. Host release PR #299 floor smoke is green but the release remains unpublished. Flag sase-z5 was administratively closed earlier for the already-deleted registry/Off branch, not because package proof passed. These remaining acceptance obligations are in the proposed child epic under sase-z4.6.5.4; no phase-success assertion is inferred from this bead close. Audit: file:explicit:d4190118a754296843815658.

## Dependencies

- **Depends on:** [sase-z4.6.5.4.1](sase-z4.6.5.4.1.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-z4.6.5.4.2](sase-z4.6.5.4.2.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-z4.6.5.4.3](sase-z4.6.5.4.3.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-z4.6.5.4.4](sase-z4.6.5.4.4.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.5.4.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.6.5.4.5/README.md) | [sase-z4.6.5.4.5](sase-z4.6.5.4.5.md) | 0 |
