# Bead: sase-p3.11 — Missing-plugin gate offering to install

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.11` · **Size:** medium
**Created:** 2026-08-17 18:50:07 EDT · **Closed:** 2026-08-17 23:01:08 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

install-offer: raise one gate per project whose required plugins are missing, offering to install them interactively while agent contexts still fail closed.

## Notes

[2026-08-18T03:00:46Z · sase-p3.11] PROPOSED FOLLOW-UP: Re-keyed stale Justfile --epic-symbol sase-p1.5(glossary_entry_relations) to parent sase-p1 so just check was not red on the closed phase; sase-p1.7 still owns GlossaryPanel and should consume glossary_entry_relations.

[2026-08-18T03:01:08Z · sase-p3.11] Added the plugins_required five-minute chop and human-only PluginsRequired gate (Install/Dismiss). Install runs sase plugin install per missing name in the option command so a non-uv-tool environment fails with the same message and leaves the gate pending; dismiss is not re-offered until the missing set changes; the chop cancels when the set is satisfied. Agent/non-interactive paths still fail closed via fail_closed_required_plugins. Verified: focused gate/chop/registry tests (75 passed); just check green including escalated full scoped suite; sase bead epic-symbols sase-p3.11 empty.

[2026-08-18T03:02:08Z · sase-p3.11] Added the plugins_required five-minute chop and human-only PluginsRequired gate (Install/Dismiss). Install runs sase plugin install per missing name so a non-uv-tool environment fails with the same message and leaves the gate pending; dismiss is not re-offered until the missing set changes; the chop cancels when the set is satisfied. Agent/non-interactive paths still fail closed. Verified: focused gate/chop/registry tests (75 passed); just check green including escalated full scoped suite; sase bead epic-symbols sase-p3.11 empty.

## Dependencies

- **Blocks:** [sase-p3.14](sase-p3.14.md) ◐ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.4](sase-p3.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.11/README.md) | [sase-p3.11](sase-p3.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e4f28dd`](https://github.com/sase-org/sase/commit/e4f28dd57c9f9024d4face8cd48c3c36f2827eeb) | feat(plugins): offer a gate to install missing required plugins | [sase-p3.11](sase-p3.11.md) | 2026-08-17 23:04:14 EDT |
