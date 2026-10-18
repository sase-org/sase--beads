# Bead: sase-1ml.2 — Swarm diagrams flag and linker placement

[Bead Pages](../README.md) / [sase-1ml](README.md) / sase-1ml.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.21.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.21.linker.w0.md) · **Assignee:** `sase-1ml.2` · **Size:** medium
**Created:** 2026-10-18 11:53:27 EDT · **Closed:** 2026-10-18 15:24:32 EDT
**Plan:** [202610/research\_swarm\_mermaid\_diagrams.md](https://github.com/sase-org/sase--plans/blob/main/202610/research_swarm_mermaid_diagrams.md)

## Description

swarm-diagram-handoff: add the nullable `diagrams` swarm input, run `#research/diagrams` after `#research/image` in the image segment, and teach the linker to read, bind before restructuring, place verbatim, gate, and report diagram proposals, with the render matrix tests and docs.

## Notes

[2026-10-18T17:28:14Z · sase-1ml.2] PROPOSED FOLLOW-UP: bob-cli vault-free `bob ref diagrams check <file.md> --json` — report per-diagram ok/error/width_pt/height_pt/scale, flag fitted heights above about half the text box, exit non-zero on failure, and fit figures to the text height minus a heading allowance. Once it exists, switch #research/diagrams to it and drop the -P dependency.

[2026-10-18T17:28:29Z · sase-1ml.2] PROPOSED FOLLOW-UP: Pilot after plugin release and reinstall — measure about 20 swarms for share of runs with at least one diagram and skip reasons, linker omissions and reasons, bob rendered N of M lines and warnings in hook output, and the image agent added runtime. Reopen the design under the report Rollout and reopen conditions.

[2026-10-18T19:24:32Z · sase-1ml.2] Verified swarm diagrams handoff in sase-research-artifacts: nullable diagrams input, run_visual image segment with #research/diagrams after #research/image, linker waits/bind/place/fail-open text, six-way diagrams×image matrix, launch-time diagrams render, diagrams-off table-sub and lead-Mermaid rules. sase tool run check 6b6afbb6153b4ee41d924e413d7b0c46 passed (130 tests, 4 deselected). Recorded plan follow-ups for vault-free bob ref diagrams check and a post-release ~20-swarm pilot. Parent epic sase-1ml left open.

## Dependencies

- **Depends on:** [sase-1ml.1](sase-1ml.1.md) ✓ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ml.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ml.2/README.md) | [sase-1ml.2](sase-1ml.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-research-artifacts | [`sase-research-artifacts@da1c380`](https://github.com/sase-org/sase-research-artifacts/commit/da1c3809ca8880ae6d54c08f6bcb05a141db5f22) | feat(research-swarm): add diagrams flag and linker placement | [sase-1ml.2](sase-1ml.2.md) | 2026-10-18 15:27:00 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ml.2][1] | Need full phase description, notes, and remaining work | 5 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ml.2/README.md

<!-- sase:referenced-by:end -->
