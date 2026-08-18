# Bead: sase-p8.5 — The \`/sase\_pipe\` skill and user documentation

[Bead Pages](../README.md) / [sase-p8](README.md) / sase-p8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05f.md) · **Assignee:** `sase-p8.5` · **Size:** small
**Created:** 2026-08-17 19:01:02 EDT · **Closed:** 2026-08-17 22:31:59 EDT
**Plan:** [202608/agent\_pipe.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_pipe.md)

## Description

skill: author the bundled skill source, wire it into the skill enumeration tests, and document the command across the CLI, monitor, and xprompt docs.

## Notes

[2026-08-18T02:31:32Z · sase-p8.5] PROPOSED FOLLOW-UP: `sase doctor -C config.file_hooks` fails host-wide with "unknown file-hook provider 'research-highlights'" because the sase-research-artifacts plugin is not installed in this venv/workspace; reproduced identically on master before this phase's changes via git stash, so it is unrelated to sase-p8.5. Also: docs/xprompt.md's bundled-skills table is missing pre-existing rows for sase_monitor and sase_new_task (unrelated to pipe); and docs/configuration.md has no ### max_agent_pipe_chain field-reference entry even though other config fields like max_running_agents get one (introduced by phase sase-p8.4, not this phase).

[2026-08-18T02:31:59Z · sase-p8.5] Added src/sase/xprompts/skills/sase_pipe.md (Core Rule / Canonical Invocation / When To Pipe / Options / Hazards, 63-line body), wired it into tests/main/test_init_skills_sources.py's skill enumeration (passes), and documented sase pipe in docs/xprompt.md (bundled-skills row), docs/cli.md (Automation table row + cross-reference), docs/monitors.md (new 'Pipe vs. monitor' section retiring the sleep 1 --next workaround), and docs/agent_families.md (pipe noted alongside the --mon suffix as an in-process family-successor mechanism). Verified: sase bead epic-symbols sase-p8.5 has no entries; tests/main/test_init_skills_sources.py full file passes (32 passed); just check's fmt/lint/symvision/toobig/validate-committed-plans/test-scoped all pass (32763 passed) except doctor config.file_hooks, which fails identically on master pre-change (confirmed via git stash) due to an unrelated missing host plugin -- recorded as a PROPOSED FOLLOW-UP along with two other discovered doc gaps. Also re-keyed a stale sase-p1.5 --epic-symbol Justfile entry to still-open sase-p1 so just check is green for other agents.

[2026-08-18T02:32:38Z · sase-p8.5] Added /sase_pipe skill (src/sase/xprompts/skills/sase_pipe.md), wired into skill enumeration test, documented sase pipe in docs/xprompt.md, docs/cli.md, docs/monitors.md, docs/agent_families.md; fixed stale sase-p1.5 epic-symbol Justfile entry re-keyed to open parent sase-p1. Verified: skill enumeration tests pass, just check (fmt/lint/symvision/toobig/validate-committed-plans/test-scoped) green; sase doctor config.file_hooks failure confirmed pre-existing on master via git stash.

## Dependencies

- **Depends on:** [sase-p8.4](sase-p8.4.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p8.6](sase-p8.6.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p8.5/README.md) | [sase-p8.5](sase-p8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bdf9a67`](https://github.com/sase-org/sase/commit/bdf9a67f0b90e9b65838e0696442af663464060b) | docs(pipe): add /sase\_pipe skill and document sase pipe | [sase-p8.5](sase-p8.5.md) | 2026-08-17 22:34:01 EDT |
