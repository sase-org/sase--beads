# Bead: sase-oc.3 — Bash and fish emitters

[Bead Pages](../README.md) / [sase-oc](README.md) / sase-oc.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04p](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04p.md) · **Assignee:** `sase-oc.3` · **Size:** medium
**Created:** 2026-08-17 08:54:24 EDT · **Closed:** 2026-08-17 11:30:43 EDT
**Plan:** [202608/cli\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/cli_completion.md)

## Description

shells: add bash and fish emitters over the same spec plus their `sase completion bash` and `sase completion fish` children, so every supported shell shares one grammar, one alias policy, and one description pass.

## Notes

[2026-08-17T15:30:14Z · sase-oc.3] PROPOSED FOLLOW-UP: sase validate / init memory --check fails on this host because chezmoi home memory README and provider shims (AGENTS.md, CLAUDE.md, GEMINI.md, QWEN.md, OPENCODE.md) are stale — pre-existing drift, not caused by the bash/fish emitters.

[2026-08-17T15:30:43Z · sase-oc.3] Verified: emit_bash writes complete -o default -F _sase sase with a COMP_WORDS walker, aliases matched but not offered, +1 quoted, choices via compgen -W, path/dir/unknown slots fall through to -o default, and kinded slots call the __sase_candidates stub. emit_fish writes complete -c sase directives conditioned on __sase_cmd /path, -d descriptions, -a '+1', quoted '\'' and $ in descriptions, and (__sase_candidates KIND) placeholders. sase completion bash/fish sit alphabetically beside list/spec/zsh with -o/--output; list now reports generators for all three shells. Unit tests cover hand-built specs plus live-script assertions (helper-bridge absent, changespec not offered). bash --norc smoke: bash -n, root offers bead/patch not changespec, 'sase bead +' completes to +1, --format offers json/text, changespec walks to patch options. Latency (this host): emit_bash 4.0 ms / 89 KB; emit_fish 5.7 ms / 219 KB; bash source 6.7 ms; in-process _sase 1–2 ms; new-process source+invoke median 5.8 ms. fish not on PATH so source/TAB unmeasured. just check lint gates green (ruff/mypy/symvision/toobig); scoped tests escalated to the full suite — 2868 passed, 1 skipped. sase validate init-memory --check failed on pre-existing chezmoi shim drift (PROPOSED FOLLOW-UP).

[2026-08-17T15:31:55Z · sase-oc.3] Verified: emit_bash writes complete -o default -F _sase sase with a COMP_WORDS walker, aliases matched but not offered, +1 quoted, choices via compgen -W, path/dir/unknown slots fall through to -o default, and kinded slots call the __sase_candidates stub. emit_fish writes complete -c sase directives conditioned on __sase_cmd /path, -d descriptions, -a '+1', quoted '\'' and $ in descriptions, and (__sase_candidates KIND) placeholders. sase completion bash/fish sit alphabetically beside list/spec/zsh with -o/--output; list now reports generators for all three shells. Unit tests cover hand-built specs plus live-script assertions (helper-bridge absent, changespec not offered). bash --norc smoke: bash -n, root offers bead/patch not changespec, 'sase bead +' completes to +1, --format offers json/text, changespec walks to patch options. Latency (this host): emit_bash 4.0 ms / 89 KB; emit_fish 5.7 ms / 219 KB; bash source 6.7 ms; in-process _sase 1-2 ms; new-process source+invoke median 5.8 ms. fish not on PATH so source/TAB unmeasured. just check lint gates green; scoped tests escalated to the full suite — 2868 passed, 1 skipped. sase validate init-memory --check failed on pre-existing chezmoi shim drift (PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-oc.2](sase-oc.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-oc.6](sase-oc.6.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-oc.7](sase-oc.7.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oc.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oc.3/README.md) | [sase-oc.3](sase-oc.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c3da174`](https://github.com/sase-org/sase/commit/c3da174ea12448497bafe9ace114e4bcd7e6c513) | feat(completion): emit bash and fish scripts from the shared spec | [sase-oc.3](sase-oc.3.md) | 2026-08-17 11:32:38 EDT |
