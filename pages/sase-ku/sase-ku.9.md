# Bead: sase-ku.9 — Monitor documentation and skill hazards

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.9` · **Size:** small
**Created:** 2026-08-13 09:03:26 EDT · **Closed:** 2026-08-13 13:14:53 EDT
**Plan:** 202608/monitor\_hardening.md

## Description

docs: document the new supervision guarantees, states, and flags in `docs/monitors.md`, and tighten the `/sase_monitor` skill with the hazard list and the flags it never mentioned.

## Notes

[2026-08-13T17:04:42Z · sase-ku.9] PROPOSED FOLLOW-UP: home memory/provider shims are out of sync — `just check` currently fails at `sase validate` / `init memory --check`, which wants to overwrite managed chezmoi AGENTS/provider shim files outside this docs phase scope.

[2026-08-13T17:14:25Z · sase-ku.9] PROPOSED FOLLOW-UP: escalated `just test-scoped` currently fails 32 full-suite tests — failures cluster in SDD plan reference/link association tests plus monitor supervisor hardening rows (`tests/monitor/test_monitor_supervise.py`), unrelated to this docs/skill wording change but blocking a clean full-suite signal.

[2026-08-13T17:14:53Z · sase-ku.9] Updated docs/monitors.md and the generated sase_monitor skill source for supervision guarantees, settlement/lost/reconciliation semantics, idle timeout, next-output, and hazards; added lost CLI status glyph and refreshed the skill-source phrase contract. Verified: just install passed; sase skill init --diff passed; git diff --check passed; pytest tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers -q passed; render sanity status_text('lost') == '? lost'. just check passed fmt/lint stages but stopped at existing init memory --check home-shim drift; escalated test-scoped full suite reported unrelated SDD/monitor failures, both recorded as PROPOSED FOLLOW-UP notes.

[2026-08-13T17:15:51Z · sase-ku.9] Updated monitor docs and skill guidance; verified just install, sase skill init --diff, git diff --check, skill source phrase test, and lost status render sanity; just check is blocked by existing init memory --check home-shim drift after lint/format stages.

## Dependencies

- **Blocks:** [sase-ku.10](sase-ku.10.md) ◐ · ⧖ 2026-08-13
- **Depends on:** [sase-ku.5](sase-ku.5.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-ku.6](sase-ku.6.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-ku.7](sase-ku.7.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-ku.8](sase-ku.8.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.9/README.md) | [sase-ku.9](sase-ku.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a7433cf`](https://github.com/sase-org/sase/commit/a7433cfe70a450efeba5bb7a056be586ef978ef4) | fix(monitor): document hardened supervision behavior | [sase-ku.9](sase-ku.9.md) | 2026-08-13 13:16:31 EDT |
