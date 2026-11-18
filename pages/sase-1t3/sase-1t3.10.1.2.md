# Bead: sase-1t3.10.1.2 — Decode compact rows and construct ordinary agents

[Bead Pages](../README.md) / [sase-1t3.10.1](sase-1t3.10.1.md) / sase-1t3.10.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.md) · **Assignee:** `sase-1t3.10.1.2` · **Size:** medium
**Created:** 2026-11-17 12:28:09 EST · **Closed:** 2026-11-17 14:47:57 EST
**Plan:** [202611/slim\_agent\_list\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202611/slim_agent_list_rows.md)

## Description

scalar-row-adapters: advance the sase core source pin, add thin Python compact-wire adapters, and construct done and running agent rows directly from list facts with metadata and status parity. Keep production acquisition unchanged until the workflow cutover phase completes the consumer set.

## Notes

[2026-11-17T19:47:32Z · sase-1t3.10.1.2] scalar-row-adapters landed: pin 8cedd45d; Python compact wires (agent_scan_list_wire) + decoders (agent_scan_list_conversion) + 6 facade/source/query list methods; compact done/running constructors + shared meta adapter (_compact_{done,running,meta_enrichment,prompt_markers}_loaders). Deferred detail for 1.1.3 hydration: response/output paths, traceback, media lists, instruction manifests, linked_repos, output_variables, status_bucket, held_by/hold_expires_at, non-meta step-output keys, full monitor/gate command+payload refs, finalizer runner/reason fields, turn elapsed/output/timeout/profile fields. Compact rows set record_shape=list + index_record_dir so _projected_record hydration applies. 12 test-only symbols allow-listed via --epic-symbol rows keyed to sase-1t3.10.1.3. Verified: ruff/mypy/symvision/toobig + all other lint stages green; bindings gate 969/969; 20 new tests + 175 neighbor tests pass; e2e integration vs real Rust projection green. Full sase tool run check 065f0c1540c74cda711a7a8ec22d0edf still in test lane at close (full-suite escalation from the Justfile rule on an overloaded host).

[2026-11-17T19:47:57Z · sase-1t3.10.1.2] Scalar-row adapters verified: pin at 8cedd45d; compact wires/decoders/facade methods plus direct done + running/home row constructors with shared metadata adapter; 110-field list/filter/action parity vs full path, guard tests prove no full-decoder use; lint gates green, 195 tests pass incl. e2e vs real Rust projection; production acquisition unchanged; 12 test-only symbols re-keyed to sase-1t3.10.1.3

## Dependencies

- **Depends on:** [sase-1t3.10.1.1](sase-1t3.10.1.1.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1t3.10.1.3](sase-1t3.10.1.3.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.10.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.10.1.2/README.md) | [sase-1t3.10.1.2](sase-1t3.10.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`be6adc2`](https://github.com/sase-org/sase/commit/be6adc20d0926f49055094192a1a36f08356f029) | feat(agent-scan): add compact scalar-row list adapters with parity and guards | [sase-1t3.10.1.2](sase-1t3.10.1.2.md) | 2026-11-17 15:47:30 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1dr--1][1] | Confirm compact-adapter phase introduced the unreviewed running-marker mutation site before routing the audit failure | 1 |
| read-by | [agent:sase-1t3.10.1.2][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1t3.10.1.land][3] | Need the child scope and notes | 1 |
| read-by | [agent:sase-1t3.10.1.land--1][3] | Review child phase notes and follow-up dispositions before landing closeout | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dr.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.10.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.1.land.md

<!-- sase:referenced-by:end -->
