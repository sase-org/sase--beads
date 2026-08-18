# Bead: sase-pw.3 — ace.current\_project configuration

[Bead Pages](../README.md) / [sase-pw](README.md) / sase-pw.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.062.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.062.f1.md) · **Assignee:** `sase-pw.3` · **Size:** small
**Created:** 2026-08-18 11:30:32 EDT · **Closed:** 2026-08-18 12:16:58 EDT
**Plan:** [202608/current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/current_project.md)

## Description

config: add the `ace.current_project` config block (indicator, seed_filters, seed_agents_query), its JSON-schema entry, a typed reader on the app, and its configuration docs.

## Notes

[2026-08-18T16:16:33Z · sase-pw.3] PROPOSED FOLLOW-UP: Justfile _lint-symvision still has seven --epic-symbol sase-pq(...) entries (TaskTypeGateDisplay and six helpers) after I re-keyed them off the closed sase-pq.5 bead so just check would go green; drop or consume them once sase-pq later phases have non-test callers.

[2026-08-18T16:16:58Z · sase-pw.3] Added ace.current_project (indicator=true, seed_filters=true, seed_agents_query=false) to default_config.yml and sase.schema.json; parse_current_project_settings on AceApp as _current_project_settings, documented in docs/configuration.md. Verified defaults, per-field overrides, non-mapping/non-boolean fallbacks, schema accept/reject of the documented block, and AceApp wiring from merged config. just check passed (scoped escalated to the full suite: Justfile + default_config.yml). sase bead epic-symbols sase-pw.3 reported no leftovers.

[2026-08-18T16:18:17Z · sase-pw.3] Verified ace.current_project config: defaults, per-field overrides, malformed fallbacks, schema accept/reject of the documented block, and AceApp loading from merged config. just check passed (scoped lane escalated to full suite). sase bead epic-symbols sase-pw.3 reported no leftovers.

## Dependencies

- **Blocks:** [sase-pw.4](sase-pw.4.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.5](sase-pw.5.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.6](sase-pw.6.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.7](sase-pw.7.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pw.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.3/README.md) | [sase-pw.3](sase-pw.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`54083ca`](https://github.com/sase-org/sase/commit/54083ca47c3b1fa07ff4b435a443945da1a3a2c4) | feat(ace): add typed ace.current\_project config | [sase-pw.3](sase-pw.3.md) | 2026-08-18 12:19:58 EDT |
