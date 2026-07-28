# Bead: sase-af.2 — Plumb wait\_runners through sase and inject the directive

[Bead Pages](../README.md) / [sase-af](README.md) / sase-af.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-af.2` · **Size:** medium
**Created:** 2026-07-28 12:54:18 UTC · **Closed:** 2026-07-28 13:33:06 UTC
**Plan:** [202607/lumberjack\_wait\_runners.md](https://github.com/sase-org/sase--plans/blob/main/202607/lumberjack_wait_runners.md)

## Description

sase_plumbing: add `wait_runners` to `LumberjackConfig`, parse it, add it to the bundled JSON schema and the AXE entry editor basics, thread it from the lumberjack down to `prepare_chop_proposals`, emit the `%wait(runners=N)` line from `scaffolded_prompt` unless the proposal already declares one, show it in `sase axe lumberjack list`, and cover it with tests and docs.

## Notes

[2026-07-28T13:32:37Z · sase-af.2] Implemented lumberjack wait_runners config parsing/schema/editor/CLI display, threaded the default through scheduled/CLI/ACE chop execution, injected protected %wait(runners=N) directives into prepared proposal prompts with proposal overrides preserved, and documented scope/semantics. Verification: just install; formatting, ruff, mypy, pyscripts, symvision, toobig, and committed-plan validation passed; 187 focused tests passed; full suite reached 22,986 passed and 7 skipped, with only an unrelated AF_UNIX temp-path length failure that passed in isolation using a short basetemp. Full just check remains blocked only by two unrelated shared SDD prompt-link validation errors for xprompt_identity_landing.md.

[2026-07-28T13:33:27Z · sase-af.2] Implemented lumberjack wait_runners config parsing/schema/editor/CLI display, threaded the default through scheduled/CLI/ACE chop execution, injected protected %wait(runners=N) directives into prepared proposal prompts with proposal overrides preserved, and documented scope/semantics. Verification: just install; formatting, ruff, mypy, pyscripts, symvision, toobig, and committed-plan validation passed; 187 focused tests passed; full suite reached 22,986 passed and 7 skipped, with only an unrelated AF_UNIX temp-path length failure that passed in isolation using a short basetemp. Full just check remains blocked only by two unrelated shared SDD prompt-link validation errors for xprompt_identity_landing.md.

## Dependencies

- **Depends on:** [sase-af.1](sase-af.1.md) ✓
- **Blocks:** [sase-af.3](sase-af.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-af.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-af.2/README.md) | [sase-af.2](sase-af.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`bd630ec`](https://github.com/sase-org/sase/commit/bd630ec7316770881d33fb16b8b822e9a2a25948) | feat(axe): gate lumberjack launches by runner capacity (sase-af.2) | [sase-af.2](sase-af.2.md) | 2026-07-28 13:36:16 |
