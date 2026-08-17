# Bead: sase-oc.4 — Pre-argparse candidates fast path

[Bead Pages](../README.md) / [sase-oc](README.md) / sase-oc.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04p](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04p.md) · **Assignee:** `sase-oc.4` · **Size:** medium
**Created:** 2026-08-17 08:54:24 EDT
**Plan:** [202608/cli\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/cli_completion.md)

## Description

candidates: add the `sase completion candidates` fast path ahead of argparse in entry.py, its value/description wire format, its disk cache, the project and bead providers, and the import-set and latency contract tests that keep it fast.

## Notes

[2026-08-17T15:21:02Z · sase-oc.4] PROPOSED FOLLOW-UP: sase/core/__init__.py eagerly imports changespec, patch, clipboard, glossary_facade, paths, shell, and time at package-import time (~19ms measured), so any `sase.core.*` import -- including sase.core.rust, used by every fast path -- pays for all of them. This makes the completion-candidates latency budget (epic plan sase-oc, ~20ms interpreter floor + ~1.6ms Rust-binding call) unreachable in practice; measured end-to-end wall time for `sase completion candidates project` is ~55-65ms locally. Consider splitting sase/core/__init__.py so leaf facades (rust.py, paths.py, state_write_guard.py) do not require executing the heavier siblings, or have fast-path callers import those leaves via importlib without triggering the package __init__ eagerly.

[2026-08-17T15:26:02Z · sase-oc.4--1] PROPOSED FOLLOW-UP: `just check` fails at the "SASE validation" gate ("init memory --check") in this workspace, unrelated to the candidates fast-path code -- fmt/ruff/mypy/feature-flags/pyscripts/test-waits/changelog/patch-stitch/symvision/toobig all pass. `sase validate` reports drift between canonical sase/memory/*.md (already correct per git log/status -- no local sase/memory changes) and the chezmoi-managed generated shims (~/.local/share/chezmoi/home/{AGENTS.md,CLAUDE.md,GEMINI.md,QWEN.md,OPENCODE.md,sase/memory/README.md}), each needing a small overwrite. Fixing requires running `sase memory init`, which this repo policy gates on explicit user permission granted in-conversation -- a phase worker should not do this unilaterally. Needs triage: either grant permission to run `sase memory init` to unblock `just check` repo-wide, or investigate why this workspace/chezmoi sidecar drifted.

## Dependencies

- **Depends on:** [sase-oc.2](sase-oc.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-oc.5](sase-oc.5.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oc.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-oc.4.md) | [sase-oc.4](sase-oc.4.md) | 0 |
