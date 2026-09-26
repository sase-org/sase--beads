# Bead: sase-1ap — Make agent-filed beads explain themselves in Context

[Bead Pages](../README.md) / sase-1ap

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sv](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sv.md) · **Assignee:** `sase-1ap.land`
**Created:** 2026-09-26 11:35:47 EDT · **Closed:** 2026-09-26 16:58:39 EDT
**Plan:** [202609/bead\_creation\_reasons.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_creation_reasons.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/bead_creation_reasons.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/bead_creation_reasons.md

<!-- sase:links:end -->

## Description

Every new bead records why it was created, and agent-created beads are recognizable and informative in the Context card.

## Notes

[2026-09-26T18:30:11Z · sase-1ap.land] LAND AUDIT (before child plan): Reviewed all three phase notes, linked plan, e579d1d core commit and d588a461b/7606e5d8c sase commits. Phase 1 SQLite-compat proposal was completed in phase 2 (schema, migration, row/JSONL/mirror wiring), so no task. Phase 2 flag-lint proposal was external drift already resolved: later tool_receipts and card_blocks retirement commits removed the definitions, and both flag beads are closed; no duplicate task. Phase 3 SASE validation proposal is stale local sase-core-rs 0.34.71 versus the pinned linked e579d1d binding, a routine reinstall rather than a distinct product task. Phase 3 visual proposal remains epic work: both created-bead PNG goldens are absent and both visual tests fail before render on the stale binding. A child epic plan will refresh the binding, capture/inspect goldens, and verify. Intervening gate-turn and card-block commits do not alter the creation-reason renderer; the child will recheck visual integration. No --epic-symbol entries remain for sase-1ap.

[2026-09-26T20:58:39Z · sase-1ap.4.land] Rechecked sase-1ap after child epic sase-1ap.4 closed. Every descendant is closed: phases sase-1ap.1, sase-1ap.2, and sase-1ap.3, plus child epic sase-1ap.4. The previous landing note left only the created-bead PNG gap open. That gap is closed: both goldens are committed in 752edf9fc, the wide card shows CREATED, why:, CLOSED-plus-created, and assigned, and just test-visual passed the created wide, created narrow, and closed-narrow nodes. Phase 1's SQLite follow-up is present in src/sase/bead/_db_migrations.py (_migrate_add_creation_reason) with row and JSONL wiring, and the linked sase-core wire still carries creation_reason. Phase 2's flag-lint follow-up stays resolved: the tool_receipts and card_blocks flag definitions are gone and sase-1am and sase-1ad are closed. No --epic-symbol entries for sase-1ap. Commits since the epic started do not change the creation-reason renderer. The generated sase/memory/sase_beads.md regression from f583cd509 is recorded on open epic sase-19x.11. The 14 collection ImportErrors and private _legacy_sase_shell_syntax_enabled are recorded on open epic sase-1ab. just symvision is red on that import and on _sync_scrollbar_position from sase-19x.11.1; the live whitelist names only open bead sase-18i.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1ap.1](sase-1ap.1.md) | Persist and index the bead creation reason in sase-core | ✓ closed | medium | 2026-09-26 | 1 | 1 |
| [sase-1ap.2](sase-1ap.2.md) | Require reasons in user creation flows and supply them in generated flows | ✓ closed | medium | 2026-09-26 | 1 | 1 |
| [sase-1ap.3](sase-1ap.3.md) | Give created and assigned beads distinct, polished Context treatments | ✓ closed | medium | 2026-09-26 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1ap: Make agent-filed beads explain themselves in Context [closed]"]
    n1["sase-1ap.1: Persist and index the bead creation reason in sase-core [closed]"]
    n2["sase-1ap.2: Require reasons in user creation flows and supply them in generated flows [closed]"]
    n3["sase-1ap.3: Give created and assigned beads distinct, polished Context treatments [closed]"]
    n4["sase-1ap.4: Complete creation-reason Context visuals [closed]"]
    n5["sase-1ap.4.1: Restore the visual test runtime [closed]"]
    n6["sase-1ap.4.2: Capture and inspect the created-bead goldens [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n4 --> n5
    n4 --> n6
    n1 -.-> n2
    n2 -.-> n3
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ap.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.1/README.md) | [sase-1ap.1](sase-1ap.1.md) | 1 |
| [bbugyi200.athena.sase-1ap.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ap.2.md) | [sase-1ap.2](sase-1ap.2.md) | 1 |
| [bbugyi200.athena.sase-1ap.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.3/README.md) | [sase-1ap.3](sase-1ap.3.md) | 1 |
| [bbugyi200.athena.sase-1ap.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.4.1/README.md) | [sase-1ap.4.1](sase-1ap.4.1.md) | 0 |
| [bbugyi200.athena.sase-1ap.4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.4.2/README.md) | [sase-1ap.4.2](sase-1ap.4.2.md) | 1 |
| [bbugyi200.athena.sase-1ap.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.4.land/README.md) | [sase-1ap.4](sase-1ap.4.md) | 1 |
| [bbugyi200.athena.sase-1ap.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ap.land.md) | [sase-1ap](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e579d1d`](https://github.com/sase-org/sase-core/commit/e579d1d120b29e54d492e4cbeecd34bddfebe06d) | feat(beads): persist and index the bead creation reason | [sase-1ap.1](sase-1ap.1.md) | 2026-09-26 12:07:17 EDT |
| sase | [`d588a46`](https://github.com/sase-org/sase/commit/d588a461bc9e5201b5abf42c9a5c7f875f2b29c9) | feat(beads): require creation reasons in user flows and supply them in generated flows | [sase-1ap.2](sase-1ap.2.md) | 2026-09-26 13:27:18 EDT |
| sase | [`7606e5d`](https://github.com/sase-org/sase/commit/7606e5d8c7b1493ba7764929ef837739deb5531f) | feat(beads): distinct created/assigned Context treatments with filing reasons (sase-1ap.3) | [sase-1ap.3](sase-1ap.3.md) | 2026-09-26 14:15:00 EDT |
| sase | [`752edf9`](https://github.com/sase-org/sase/commit/752edf9fc80637572c7668e68585205f743ecc40) | test(visual): capture created-bead Context goldens (sase-1ap.4.2) | [sase-1ap.4.2](sase-1ap.4.2.md) | 2026-09-26 16:35:10 EDT |
| sase--plans | [`sase--plans@59563ec`](https://github.com/sase-org/sase--plans/commit/59563ecd8a5a7a8bf29f4b9df085031c184a89d9) | docs(plans): mark the creation-reason epic plans done | [sase-1ap.4](sase-1ap.4.md) | 2026-09-26 17:00:40 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ap.1][1] | epic scope | 1 |
| read-by | [agent:sase-1ap.3][2] | parent epic status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.3/README.md

<!-- sase:referenced-by:end -->
