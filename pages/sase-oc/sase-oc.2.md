# Bead: sase-oc.2 — Zsh emitter and the sase completion command group

[Bead Pages](../README.md) / [sase-oc](README.md) / sase-oc.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04p](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04p.md) · **Assignee:** `sase-oc.2` · **Size:** medium
**Created:** 2026-08-17 08:54:23 EDT · **Closed:** 2026-08-17 10:51:59 EDT
**Plan:** [202608/cli\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/cli_completion.md)

## Description

zsh: emit a native `_arguments` compsys script from the spec with descriptions, exclusion lists, mutex groups, `-S`, and remainders, and register the `sase completion` command group with its `list`, `spec`, and `zsh` children.

## Notes

[2026-08-17T14:51:59Z · sase-oc.2] Verified: emit_zsh writes a #compdef sase script with _arguments -C -s -S, option descriptions, self+mutex exclusion lists, * repeatable options, path/dir _files, kind placeholders (:->kind), remainders as *::command:_normal, +1 as a completable command, and aliases (changespec) completable but omitted from _describe. _sase_run skips sase_<N>/.venv/bin/sase. sase completion list/spec/zsh are registered (bare completion defaults to list); spec prints the structural snapshot JSON; zsh writes stdout or -o FILE. Unit tests cover hand-built specs plus live-script assertions (helper-bridge absent, descriptions <= 60). Real zsh: zsh -n, compinit registers _comps[sase]=_sase, and a pty TAB on 'sase bead +' becomes 'sase bead +1'. just check green (ruff/mypy/symvision/toobig + scoped tests escalated to the full suite).

[2026-08-17T14:52:54Z · sase-oc.2] Verified: emit_zsh writes a #compdef sase script with _arguments -C -s -S, option descriptions, self+mutex exclusion lists, * repeatable options, path/dir _files, kind placeholders (:->kind), remainders as *::command:_normal, +1 as a completable command, and aliases (changespec) completable but omitted from _describe. _sase_run skips sase_<N>/.venv/bin/sase. sase completion list/spec/zsh are registered (bare completion defaults to list); spec prints the structural snapshot JSON; zsh writes stdout or -o FILE. Unit tests cover hand-built specs plus live-script assertions (helper-bridge absent, descriptions <= 60). Real zsh: zsh -n, compinit registers _comps[sase]=_sase, and a pty TAB on 'sase bead +' becomes 'sase bead +1'. just check green (ruff/mypy/symvision/toobig + scoped tests escalated to the full suite).

## Dependencies

- **Depends on:** [sase-oc.1](sase-oc.1.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-oc.3](sase-oc.3.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-oc.4](sase-oc.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oc.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oc.2/README.md) | [sase-oc.2](sase-oc.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1482fc1`](https://github.com/sase-org/sase/commit/1482fc1dc573af7f34dfb872110d822ee3b72eb0) | feat(completion): add native zsh emitter and sase completion CLI | [sase-oc.2](sase-oc.2.md) | 2026-08-17 10:53:53 EDT |
