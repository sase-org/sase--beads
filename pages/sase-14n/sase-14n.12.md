# Bead: sase-14n.12 — Keep the declared shell block through gate creation

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.12` · **Size:** medium
**Created:** 2026-09-20 17:14:21 EDT · **Closed:** 2026-09-20 22:29:46 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

gate_shell_row: find and fix the seam that records continuation_mode none for a custom gate whose request declares a shell block, so its gate-shell row is registered and the gate stays listed.

## Notes

[2026-09-21T02:28:38Z · sase-14n.12] PROPOSED FOLLOW-UP: full-suite check under heavy box load (avg 44+) flaked 4 gate-unrelated tests that pass in isolation — test_prompt_artifact_staging concurrent manifest, sdd git-identity empty-HOME subprocess, tmp-env-leak guard wiring, plugins-browser mixed-update pane

[2026-09-21T02:29:46Z · sase-14n.12] Shell-block custom gate now records derived continuation gate_shell instead of none (repro before: envelope shell present, mode none, no row; after: mode gate_shell). GateSpec rejects shell plus explicit none call it invalid_request. Tests in tests/gate_shell/test_model_shell.py cover derive, reject, explicit-mode passthrough, none default, and recorded mode plus gate-shell row presence. Recorded just check: all lint gates green, 44232 passed; only 4 unrelated load-flake failures, each green in isolation.

## Dependencies

- **Depends on:** [sase-14n.1](sase-14n.1.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14n.3](sase-14n.3.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.12/README.md) | [sase-14n.12](sase-14n.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c041716`](https://github.com/sase-org/sase/commit/c04171670c35ebc86361fc8f7ecc7569d9a586fc) | fix(gate): keep declared shell block through gate creation | [sase-14n.12](sase-14n.12.md) | 2026-09-20 22:32:16 EDT |
