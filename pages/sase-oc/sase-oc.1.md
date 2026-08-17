# Bead: sase-oc.1 — Completion spec model and argparse walker

[Bead Pages](../README.md) / [sase-oc](README.md) / sase-oc.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04p](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04p.md) · **Assignee:** `sase-oc.1` · **Size:** medium
**Created:** 2026-08-17 08:54:22 EDT · **Closed:** 2026-08-17 10:01:18 EDT
**Plan:** [202608/cli\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/cli_completion.md)

## Description

spec: build the sase-owned CompletionSpec model, the argparse tree walker that produces it, help shortening, alias/hidden policy, the value-kind resolver, and the checked-in structural snapshot that makes grammar drift a reviewable diff.

## Notes

[2026-08-17T13:44:05Z · sase-oc.1] PROPOSED FOLLOW-UP: just _lint-symvision/just check fails repo-wide (pre-existing, unrelated to sase-oc.1) — the Justfile epic-symbol entry `sase-oc.8(set_completion_kind)`... wait wrong text

[2026-08-17T13:44:49Z · sase-oc.1] PROPOSED FOLLOW-UP (correction to prior garbled note): just check / just _lint-symvision fails repo-wide, pre-existing and unrelated to sase-oc.1 work. The Justfile epic-symbol entry --epic-symbol "sase-o8.4(PlaceholderRankingMetadata)" is stale (bead sase-o8.4 is closed); symvision now reports PlaceholderRankingMetadata in src/sase/ace/tui/widgets/placeholder_completion.py as needing the standard unused-symbol decision (delete/private/pragma/new epic-symbol). Verified pre-existing via git stash on a clean master checkout before starting this phase.

[2026-08-17T14:00:58Z · sase-oc.1] PROPOSED FOLLOW-UP: tests/test_models_panel_edit_outcomes.py::test_on_alias_edited_offers_commit_when_in_repo failed once during the full just test-scoped run for sase-oc.1 (unrelated ACE TUI models-panel test, no relation to the completion module) but passes cleanly in isolation — looks like flakiness under parallel/shared-CPU load rather than a real bug; worth a flaky-test investigation.

[2026-08-17T14:01:18Z · sase-oc.1] Verified in-turn: 43 new completion tests pass (model round-trip, alias collapsing, hidden-subtree pruning, 15 mutex groups, remainder positionals, default-list-child, kind-resolution precedence, shortening incl. the 271-char string, snapshot drift gate). ruff, mypy (incl. tools/sync_completion_spec via typecheck_extensionless_tools), pyscripts, toobig, patch/stitch terminology audit, and tools/sync_completion_spec --check (no drift) all pass. Full just test-scoped: 32024 passed, 1 unrelated flaky ACE TUI test (passes in isolation, recorded as follow-up). Only remaining red gate is the pre-existing unrelated stale symvision --epic-symbol entry for closed bead sase-o8.4, already recorded as a follow-up on this bead.

## Dependencies

- **Blocks:** [sase-oc.2](sase-oc.2.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oc.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oc.1/README.md) | [sase-oc.1](sase-oc.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`48856bc`](https://github.com/sase-org/sase/commit/48856bc891f0a3f30dc5e3805c53f6bd2c840c18) | feat(completion): add the CompletionSpec model and argparse tree walker | [sase-oc.1](sase-oc.1.md) | 2026-08-17 10:03:17 EDT |
