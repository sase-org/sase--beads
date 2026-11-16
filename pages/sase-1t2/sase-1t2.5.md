# Bead: sase-1t2.5 — TUI ingress uses the backend decision: precise toasts, container retargeting, redirects

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.5` · **Size:** medium
**Created:** 2026-11-15 20:00:10 EST · **Closed:** 2026-11-16 01:04:04 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

tui_ingress: replace agent_can_offer_hijack with an asynchronously cached backend decision for the selected row; gate ,k, its footer chip, and the kill modal's h on it; toast code + message + next action; run non-destructive redirects; mirror hijack_record onto collapsed session rows; log refusal codes; add a TUI/backend parity test.

## Notes

[2026-11-16T06:04:04Z · sase-1t2.5] TUI ingress now uses an off-thread cached resolve_and_decide for the selected Agents row (keyed by identity + roster generation). ,k, the leader footer chip, and kill-modal h follow immediate/latched/redirect vs stop modes; refusals toast code+message+next_action and log agent_hijack_tui_refused; redirects open recovery, Enter-style gate review, lone clan member retarget, remote copy, or active-hijack toast; hijack submits the occupant name; collapsed sessions mirror hijack_record. Parity test covers workflow/session/clan/remote/monitor/gate loader rows vs CLI --explain. just check ebc79ce0e3085d1877ad365085d2b940 passed; no leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1t2.12](sase-1t2.12.md) ✓ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.4](sase-1t2.4.md) ✓ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.7](sase-1t2.7.md) ◐ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.5/README.md) | [sase-1t2.5](sase-1t2.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d26b581`](https://github.com/sase-org/sase/commit/d26b581253780c3c1417839c6af08c1294885328) | feat(agent-hijack): cache backend decisions for TUI hijack ingress | [sase-1t2.5](sase-1t2.5.md) | 2026-11-16 01:27:04 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t2.5][1] | Need remaining description, notes, and design details | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.5/README.md

<!-- sase:referenced-by:end -->
