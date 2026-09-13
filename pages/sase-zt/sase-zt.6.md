# Bead: sase-zt.6 — Finish queue capacity persistence, authoring and display

[Bead Pages](../README.md) / [sase-zt](README.md) / sase-zt.6

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zt.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.land.md) · **Assignee:** `sase-zt.6.land`
**Created:** 2026-09-13 07:09:17 EDT
**Plan:** [202609/queue\_capacity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_landing_repairs.md)

## Description

Preserve authored queue budgets through real scans, history and continuations, present them truthfully, and complete the missing acceptance evidence for sase-zt.

## Notes

[2026-09-13T18:28:21Z · sase-zt.6.land] LANDING AUDIT at main a6f6ae5c / core 23f19f0 (2026-09-13): reviewed sase-zt.6, all four child beads and every child note, linked plan plan:202609/queue_capacity_landing_repairs.md, preserved audit file:explicit:49e1cedbfb0962c856bb2e22, original parent plan/live evidence, all four epic commits, and actual current main/core source. Phases .1-.3 substantially landed what they reported: core ba651fe carries scan wire 9/index 29 canonical+legacy capacity fields, canonical-wins aliases, explicit-zero normalization, flag-aware queue metadata and PyO3/LSP plumbing; main fa84150/bb68af0 pin/adopt those fields, write canonical markers, preserve continuation budgets, and delete may_start; 84a3ea2 adds numeric u32-safe gold/quiet row and detail presentation. Phase .4 commit 7f22623 adds the promised capacity visual fixture/golden, and real scan/index/render tests cover canonical metadata after waiting-marker removal. The code and commit trailers identify every child bead.

Not complete. Confirmed remaining epic work: (1) core build_directive_completion_candidates_with_flags still constructs the %queue name candidate from unflagged DIRECTIVES, so enabled LSP name-row docs incorrectly say weighted-load threshold while argument/recipe metadata says capacity budget; (2) post-start core commits 1b122287/b79accb3 advance full-history completeness and machine provenance to index schema 30 and 23f19f0 adds continuation_decide_resume_adoption/retention, while post-start main commits 5beda061/1cd445ae/a6f6ae5c consume those contracts, but sase-core-revision.txt remains 17947a05 (schema 29 and missing continuation bindings), so a clean pinned cohort cannot satisfy current Python; (3) the required combined live TUI smoke was not completed. sase-zt.6.4's retry never produced durable smoke rows and relied on sase-zt.5 admission evidence plus a preconstructed visual fixture. Current Rust source and tests parse queue_capacity into AgentUnitWire and rebuild canonical %queue during approved typed dispatch, so the reported sase-run queue drop is not yet proven; the actual LaunchApproval request->typed plan->dispatch->ordinary metadata path needs a regression and live resolution.

Post-start drift reviewed: 798933f's admission split was integrated before bb68af0; 654335d/5beda061/1cd445ae preserve capacity in wire conversion, source reconciliation, full-history reuse and machine candidate filtering; 897147ea/a6f6ae5c overlap continuation but do not replace queue prefix policy; core 23f19f0 resolves the missing binding source gap. Later pager, cache, Cargo build-dir, clan-row and memory changes do not require queue adoption. Preserve schema 30, machine provenance, source reconciliation, continuation exactly-once/retention, and the queue behavior when advancing the pin.

All PROPOSED FOLLOW-UP dispositions: .1 #2 gateway seeded-row failure is unrelated and exact existing ready CI task sase-10a; recorded an independent +1 identifying proposer and isolation evidence. .2 #1 flag-aware queue name documentation is caused by this epic and remains plan work. .2 #2 machines-pane KeyError under the 14-worker lane passed in isolation, had no exact task match, and was recorded on causally matching active flake epic sase-j7. .3 #1 and .4 #3 missing continuation binding are unrelated queue work; core 23f19f0 now implements it and active sase-zl.13.11.6 owns released-package/combined acceptance, so no task was created. .4 #1 broad visual drift is unrelated and matches ready CI task sase-x5; added +1 with the version-subtitle diff evidence. .4 #2's creator-handoff ImportError remains existing sase-106; its alleged queue loss stays epic acceptance work until the production path proves or repairs it. .4 #4 is an intermediate status superseded by final note #5, except for the still-missing combined live smoke noted above.

Authored sase_plan_queue_capacity_final_integration.md with parent_bead sase-zt.6 and phases core-completion, pin-and-launch, acceptance. It passed required validate --explain correction and final validation with 0 warnings. The plan contains only remaining work; it does not include epic close, epic-symbol cleanup, post-close Symvision, or parent-plan status changes. Leave sase-zt.6 and sase-zt open until the child completes and landing is re-audited.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.6.land.md) | [sase-zt.6](sase-zt.6.md) | 0 |
