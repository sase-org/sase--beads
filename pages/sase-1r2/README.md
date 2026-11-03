# Bead: sase-1r2 — Green Full CI on master, a containing published core, and sase v0.19.0 confirmed on PyPI

[Bead Pages](../README.md) / sase-1r2

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.178.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.178.w0.md) · **Assignee:** `sase-1r2.land`
**Created:** 2026-11-03 11:09:30 EST
**Plan:** [202611/v0\_19\_0\_green\_full\_ci\_release.md](https://github.com/sase-org/sase--plans/blob/main/202611/v0_19_0_green_full_ci_release.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/v0_19_0_green_full_ci_release.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/v0_19_0_green_full_ci_release.md

<!-- sase:links:end -->

## Description

Full CI is green in every job on master. sase-core's master CI is green, and a complete published sase-core-rs contains master's source pin. A release.yml rehearsal at master is accepted. Release-please PR #322 merges, and sase 0.19.0 is confirmed on PyPI. The lander that observes the release records the evidence as an artifact.

## Notes

[2026-11-03T16:22:16Z · sase-1r2.1] WATCHDOG installed for sase-1r2.
Cron line: 23 * * * * sh /home/bryan/.local/state/sase-epic-watchdog/sase-1r2/watchdog.sh >> /home/bryan/.local/state/sase-epic-watchdog/sase-1r2/watchdog.log 2>&1 # sase-epic-watchdog:sase-1r2
Paths: D=/home/bryan/.local/state/sase-epic-watchdog/sase-1r2 (watchdog.sh, boot_id, installed_at, watchdog.log, crontab.before). Primary checkout baked into the script: /home/bryan/projects/github/sase-org/sase (workspace 0).
Removal: sh /home/bryan/.local/state/sase-epic-watchdog/sase-1r2/watchdog.sh remove
Proof: sh -n ok; WATCHDOG_DRY=1 with boot_id=test found live agent sase-1r2.land and took no action; real run exited 0 with "same boot; no action"; crontab gained exactly that one line.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1r2.1](sase-1r2.1.md) | A reboot cannot strand this epic | ✓ closed | small | 2026-11-03 | 1 | 0 |
| [sase-1r2.2](sase-1r2.2.md) | Master Gate is green at master HEAD | ✓ closed | small | 2026-11-03 | 1 | 0 |
| [sase-1r2.3](sase-1r2.3.md) | The blocking test lanes stop flaking | ◐ in_progress | medium | 2026-11-03 | 1 | 0 |
| [sase-1r2.4](sase-1r2.4.md) | Full CI's advisory jobs pass | ✓ closed | medium | 2026-11-03 | 1 | 1 |
| [sase-1r2.5](sase-1r2.5.md) | A complete published sase-core-rs contains master's source pin | ◐ in_progress | medium | 2026-11-03 | 1 | 0 |
| [sase-1r2.6](sase-1r2.6.md) | One Full CI run on master is green in every job | ◐ in_progress | medium | 2026-11-03 | 1 | 0 |
| [sase-1r2.7](sase-1r2.7.md) | An accepted release.yml rehearsal at master | ◐ in_progress | small | 2026-11-03 | 1 | 0 |
| [sase-1r2.8](sase-1r2.8.md) | sase v0.19.0 reaches PyPI under a self-closing watcher | ◐ in_progress | small | 2026-11-03 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1r2: Green Full CI on master, a containing published core, and sase v0.19.0 confirmed on PyPI [in_progress]"]
    n1["sase-1r2.1: A reboot cannot strand this epic [closed]"]
    n2["sase-1r2.2: Master Gate is green at master HEAD [closed]"]
    n3["sase-1r2.3: The blocking test lanes stop flaking [in_progress]"]
    n4["sase-1r2.4: Full CI's advisory jobs pass [closed]"]
    n5["sase-1r2.5: A complete published sase-core-rs contains master's source pin [in_progress]"]
    n6["sase-1r2.6: One Full CI run on master is green in every job [in_progress]"]
    n7["sase-1r2.7: An accepted release.yml rehearsal at master [in_progress]"]
    n8["sase-1r2.8: sase v0.19.0 reaches PyPI under a self-closing watcher [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n2 -.-> n6
    n2 -.-> n7
    n3 -.-> n6
    n3 -.-> n7
    n4 -.-> n6
    n5 -.-> n7
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r2.1/README.md) | [sase-1r2.1](sase-1r2.1.md) | 0 |
| [bbugyi200.athena.sase-1r2.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r2.2/README.md) | [sase-1r2.2](sase-1r2.2.md) | 0 |
| [bbugyi200.athena.sase-1r2.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r2.3.md) | [sase-1r2.3](sase-1r2.3.md) | 0 |
| [bbugyi200.athena.sase-1r2.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r2.4/README.md) | [sase-1r2.4](sase-1r2.4.md) | 1 |
| [bbugyi200.athena.sase-1r2.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r2.5.md) | [sase-1r2.5](sase-1r2.5.md) | 0 |
| [bbugyi200.athena.sase-1r2.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r2.6/README.md) | [sase-1r2.6](sase-1r2.6.md) | 0 |
| [bbugyi200.athena.sase-1r2.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r2.7/README.md) | [sase-1r2.7](sase-1r2.7.md) | 0 |
| [bbugyi200.athena.sase-1r2.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r2.8/README.md) | [sase-1r2.8](sase-1r2.8.md) | 0 |
| [bbugyi200.athena.sase-1r2.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r2.land/README.md) | [sase-1r2](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d3b0480`](https://github.com/sase-org/sase/commit/d3b0480636cdfbc7eb979144ea2a71702b18fae0) | fix(ci): make Full CI advisory lanes pass locally | [sase-1r2.4](sase-1r2.4.md) | 2026-11-03 13:55:35 EST |
