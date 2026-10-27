# Bead: sase-1ox — Capacity inspector redesign — answer "can new work start, and who is using it?" at a glance

[Bead Pages](../README.md) / sase-1ox

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14s](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14s.md) · **Assignee:** `sase-1ox.land`
**Created:** 2026-10-27 10:48:21 EDT · **Closed:** 2026-10-27 16:22:34 EDT
**Plan:** [202610/capacity\_inspector\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/capacity_inspector_redesign.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/capacity_inspector_redesign.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/capacity_inspector_redesign.md

<!-- sase:links:end -->

## Description

Opening the capacity inspector (`,l`) answers three questions in under a second: can a new agent start right now, who is using the capacity, and who is waiting for it and why. A slot gauge, a plain-English verdict, tiered sections, and a detail strip replace the flat wall of dim text. The noise of inactive records is folded away. Every number still comes straight from the authoritative report, so nothing is estimated and nothing unknown ever reads as free.

## Notes

[2026-10-27T19:38:17Z · sase-1ox.land] FOLLOW-UP TRIAGE (landing): Reviewed all five sase-1ox.1 notes and the single notes on .2 and .3. The only PROPOSED FOLLOW-UP is .1 note 2, startup import budget. Used /sase_new_task; independently reproduced 3541 vs strict 3539 on clean daa96a5bd0; pre-epic a42eedc1c467 also measures 3541 with identical sase.* closure (+0). Corroborated existing owner sase-1ic with verified-after-close evidence; no duplicate created. Searched CI tasks and the past-week sweep; reviewed active startup epic sase-132.4/.7, with no causal evidence tying its work to this recurrence. No proposal declined. Later .1 note 5 reported a scoped check pass, which does not invalidate this focused reproduction. Remaining capacity-rendering defects found during landing belong to this epic and will be handled by a medium corrective tale whose final step closes this epic.

[2026-10-27T19:40:05Z · sase-1ox.land] LANDING REVIEW at daa96a5bd0: Read approved plan and all child notes; inspected epic commits d16b79f3c1, c8bc7a58e2, daa96a5bd0 and current view/gauge/row/text, modal/render, chip, CLI, tests, docs, and all five PNG goldens. cli_parity=adopt and inactive_records=collapsed are implemented. Verified sort/tier/gauge/verdict/JSON behavior and stable selection after the event pump drains; 82 focused capacity/lineage/roster tests pass. Remaining epic defects: invalid accounting with zero charged claims prints all 8 units are free in both TUI and CLI; modal live-clock projection makes a report-age 180s holder read 300s when viewed 120s later; row kind columns vary with name/note length; detail CSS height 3 includes the border, clipping line 3 in every golden, and narrow header facts clip; rider detail prints raw project_key; CLI styled Text is flattened through str in attention/zero/waiting/diagnostic panels. Also remove redundant verdict copies and use shared threshold constants as approved. Integration audit includes c328233430 live-PID lineage fixture since the first epic commit, plus commits since epic creation (3b99dac0a0, 353d833bf0, 2243ebc97b, 691ef46153, 8d41b72218, a42eedc1c4); queued-session refresh and lineage regressions pass with the epic. Fetch confirms origin/master=daa96a5bd0; no incoming base drift. No extra production integration consumer identified. epic-symbols is empty. Epic has no parent_bead. Holding close for one medium corrective tale with concrete closeout.

[2026-10-27T20:22:34Z · sase-1ox.land] Phases sase-1ox.1 (view-model), .2 (inspector), and .3 (CLI) are closed as done. Implementation commits: d16b79f3c1 (view), c8bc7a58e2 (inspector), daa96a5bd0 (CLI parity). This landing tale repaired the remaining presentation defects on that tip. Approved decisions remain cli_parity=adopt and inactive_records=collapsed.

Landing repairs: invalid empty charged copy is now "No known charged claims — free capacity is unknown" in TUI and CLI, while a valid empty report still shows all-free; row ages project at report.computed_at with the injectable clock only for headline freshness, reusing CAPACITY_REPORT_STALE_AFTER_SECONDS and override_long_lived; shared name/kind/age row budgets restore inherited holder notes and rider project labels via the display snapshot; detail CSS is min-height 4 (3 content lines plus border); facts count riders as at-zero (`9 running · 7 charged · 2 at 0`); verdict no longer repeats over-limit/invalid copy; CLI keeps Rich spans via _rstrip_text and paints invalid used-gauge cells with the rejected style.

Verification: focused inspector/CLI tests passed (42); related capacity/chip/opener/roster/lineage tests passed (60). Five inspector goldens updated and inspected (staggered busy ages 3h12m/2h01m/50m/18m/12m/6m/4m, inherited notes, 3-line details, queued visible at 80x32, facts wrap). TZ=UTC just fix-tui-screenshots --check: 5 passed, check clean, no unstable. TZ=America/New_York --check recaptured a wait_dependency_resolution import deadlock during tab switch with matching pixels (not golden drift). just fix clean; just symvision clean; epic-symbols empty; sase tool run check daa185c799bb0582c806e606b74c3692 succeeded. origin/master and HEAD remain daa96a5bd0; no post-epic integration drift.

Follow-up: sase-1ox.1 note 2 startup import budget independently reproduced at 3541 vs 3539; corroborated onto existing sase-1ic; no duplicate created.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1ox.1](sase-1ox.1.md) | Phase view-model: tiered capacity view, verdict, and gauge geometry | ✓ closed | medium | 2026-10-27 | 1 | 1 |
| [sase-1ox.2](sase-1ox.2.md) | Phase inspector: redesigned TUI capacity inspector | ✓ closed | medium | 2026-10-27 | 1 | 1 |
| [sase-1ox.3](sase-1ox.3.md) | Phase cli: \`sase agent load\` parity and legacy view cleanup | ✓ closed | small | 2026-10-27 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1ox: Capacity inspector redesign — answer \"can new work start, and who is using it?\" at a glance [closed]"]
    n1["sase-1ox.1: Phase view-model: tiered capacity view, verdict, and gauge geometry [closed]"]
    n2["sase-1ox.2: Phase inspector: redesigned TUI capacity inspector [closed]"]
    n3["sase-1ox.3: Phase cli: `sase agent load` parity and legacy view cleanup [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n1 -.-> n2
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ox.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ox.1.md) | [sase-1ox.1](sase-1ox.1.md) | 1 |
| [bbugyi200.athena.sase-1ox.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ox.2.md) | [sase-1ox.2](sase-1ox.2.md) | 1 |
| [bbugyi200.athena.sase-1ox.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ox.3/README.md) | [sase-1ox.3](sase-1ox.3.md) | 1 |
| [bbugyi200.athena.sase-1ox.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ox.land.md) | [sase-1ox](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d16b79f`](https://github.com/sase-org/sase/commit/d16b79f3c13c80d787e0f2975a1953e9c7479dab) | feat(capacity): add tiered view-model verdict, gauge, and durations | [sase-1ox.1](sase-1ox.1.md) | 2026-10-27 14:07:09 EDT |
| sase | [`c8bc7a5`](https://github.com/sase-org/sase/commit/c8bc7a58e20799a3a310ac397d2d79ce6739956f) | feat(tui): redesign capacity inspector | [sase-1ox.2](sase-1ox.2.md) | 2026-10-27 14:56:24 EDT |
| sase | [`daa96a5`](https://github.com/sase-org/sase/commit/daa96a5bd05c2eb23c8ce23e3dccb67af8b1afb0) | feat(cli): give sase agent load the inspector's tiered capacity view | [sase-1ox.3](sase-1ox.3.md) | 2026-10-27 15:26:16 EDT |
| sase | [`83b1822`](https://github.com/sase-org/sase/commit/83b1822411e5495f0c26b42defd46e2b07ad5629) | fix(ace): land remaining capacity inspector presentation defects | [sase-1ox](README.md) | 2026-10-27 16:26:00 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ox.1--4][1] | Need parent epic DECISIONS, plan, and remaining phases for view-model close | 1 |
| read-by | [agent:sase-1ox.3][2] | Need parent epic decisions and phase list | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ox.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ox.3/README.md

<!-- sase:referenced-by:end -->
