# Bead: sase-oc.4 — Pre-argparse candidates fast path

[Bead Pages](../README.md) / [sase-oc](README.md) / sase-oc.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04p](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04p.md) · **Assignee:** `sase-oc.4` · **Size:** medium
**Created:** 2026-08-17 08:54:24 EDT · **Closed:** 2026-08-17 11:57:51 EDT
**Plan:** [202608/cli\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/cli_completion.md)

## Description

candidates: add the `sase completion candidates` fast path ahead of argparse in entry.py, its value/description wire format, its disk cache, the project and bead providers, and the import-set and latency contract tests that keep it fast.

## Notes

[2026-08-17T15:21:02Z · sase-oc.4] PROPOSED FOLLOW-UP: sase/core/__init__.py eagerly imports changespec, patch, clipboard, glossary_facade, paths, shell, and time at package-import time (~19ms measured), so any `sase.core.*` import -- including sase.core.rust, used by every fast path -- pays for all of them. This makes the completion-candidates latency budget (epic plan sase-oc, ~20ms interpreter floor + ~1.6ms Rust-binding call) unreachable in practice; measured end-to-end wall time for `sase completion candidates project` is ~55-65ms locally. Consider splitting sase/core/__init__.py so leaf facades (rust.py, paths.py, state_write_guard.py) do not require executing the heavier siblings, or have fast-path callers import those leaves via importlib without triggering the package __init__ eagerly.

[2026-08-17T15:26:02Z · sase-oc.4--1] PROPOSED FOLLOW-UP: `just check` fails at the "SASE validation" gate ("init memory --check") in this workspace, unrelated to the candidates fast-path code -- fmt/ruff/mypy/feature-flags/pyscripts/test-waits/changelog/patch-stitch/symvision/toobig all pass. `sase validate` reports drift between canonical sase/memory/*.md (already correct per git log/status -- no local sase/memory changes) and the chezmoi-managed generated shims (~/.local/share/chezmoi/home/{AGENTS.md,CLAUDE.md,GEMINI.md,QWEN.md,OPENCODE.md,sase/memory/README.md}), each needing a small overwrite. Fixing requires running `sase memory init`, which this repo policy gates on explicit user permission granted in-conversation -- a phase worker should not do this unilaterally. Needs triage: either grant permission to run `sase memory init` to unblock `just check` repo-wide, or investigate why this workspace/chezmoi sidecar drifted.

[2026-08-17T15:57:51Z · sase-oc.4] Recovered the candidates fast-path work from lost commit e6198741c (orphaned by an aborted rebase reset to origin/master) and rebased it onto current master, which had since gained the shells phase (bash/fish emitters). Resolved 3-way conflicts in completion_handler.py, parser_completion.py, and the cli_spec.json snapshot (regenerated via 'just sync-completion-spec'). Fixed a stale tests/main/test_parser_completion.py assertion that predated the candidates subcommand. Verified: entry.py fast-path guard matches the design's exact snippet; providers.py ships project and bead candidates through sase_core_rs bindings with project-display-name rendering; protocol.py/cache.py match the wire-format and disk-cache design. Ran 'just fmt', ruff, mypy, pyscripts, test-waits, changelog, patch-stitch-terminology, symvision, and toobig gates individually -- all green. Full 'just test-scoped' escalated to the full suite (stale baseline) and passed 3507/3507 (1 unrelated skip). Manually smoke-tested 'sase completion candidates project' and 'sase completion candidates bead <prefix>' against the live CLI. 'just check' itself still fails at the feature-flags gate on live flag bead sase-om (key completion_refresh_on_update, created 12m ago by concurrently in-progress sibling phase sase-oc.7 in another workspace) -- confirmed via git stash this is pre-existing/unrelated to this phase's diff, not something to fix here.

[2026-08-17T15:58:44Z · sase-oc.4] Recovered orphaned commit e6198741c (candidates fast-path: providers.py, cache.py, protocol.py, completion_fast_path.py) via cherry-pick, resolved conflicts against master (completion_handler.py, parser_completion.py, cli_spec.json) after the shells phase (sase-oc.3) landed. Fixed a stale parser_completion test assertion. Verified entry.py fast-path guard matches design spec; providers.py wires project/bead candidates through sase_core_rs with display-name rendering; wire protocol/disk cache match spec. Ran every just check lint gate individually (all green except an unrelated pre-existing flag-lint failure from a concurrent sibling phase sase-oc.7, confirmed via git stash) plus the full test suite (3507 passed, 1 unrelated skip). Smoke-tested the CLI directly.

## Dependencies

- **Depends on:** [sase-oc.2](sase-oc.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-oc.5](sase-oc.5.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oc.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oc.4/README.md) | [sase-oc.4](sase-oc.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`24d892b`](https://github.com/sase-org/sase/commit/24d892b4de80ef1cc77849217352d91dbbcdfc39) | feat(completion): add pre-argparse candidates fast path | [sase-oc.4](sase-oc.4.md) | 2026-08-17 11:59:30 EDT |
