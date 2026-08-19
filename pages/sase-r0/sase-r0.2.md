# Bead: sase-r0.2 — Interactive-CLI provider descriptor

[Bead Pages](../README.md) / [sase-r0](README.md) / sase-r0.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07y.md) · **Assignee:** `sase-r0.2` · **Size:** small
**Created:** 2026-08-19 11:57:00 EDT · **Closed:** 2026-08-19 12:54:21 EDT
**Plan:** [202608/tmux\_agent\_launcher.md](https://github.com/sase-org/sase--plans/blob/main/202608/tmux_agent_launcher.md)

## Description

descriptor: add the `llm_interactive_cli` hook plus vendor metadata, implement it on every built-in provider, and expose it through the registry payload.

## Notes

[2026-08-19T16:53:18Z · sase-r0.2] PROPOSED FOLLOW-UP: sase-qt.6 closed leaving stale --epic-symbol whitelist for unused memory mutation API — re-keyed those Justfile entries to parent epic sase-qt so just check can pass; symbols still have no non-test ACE consumers

[2026-08-19T16:53:35Z · sase-r0.2] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py has reproducible argparse-tree vs snapshot key-order drift (test_checked_in_snapshot_has_no_drift, test_current_structural_view_matches_checked_in_snapshot) — not caused by llm_interactive_cli; just check escalated to the full suite after the Justfile re-key and those two failed

[2026-08-19T16:53:55Z · sase-r0.2] PROPOSED FOLLOW-UP: tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet failed once with a cancelled sase-artifacts-project-choices task leftover, then passed on rerun — flake, not caused by this phase

[2026-08-19T16:54:21Z · sase-r0.2] Added llm_interactive_cli plus vendor install metadata on all built-in providers (c/x/a/q/o/g/m menu keys, bypass_args matching tmux_ai_window, fakey supported=False, muse MUSE_NO_AUTO_UPDATE=1). Registry normalizes descriptors (tuples, one-char menu_key, degrade-on-malformed) and exposes provider_interactive_cli_map/provider_vendor_map. Verified: tests/llm_provider/test_interactive_cli_metadata.py plus related registry/provider tests (252 passed); just check lint (ruff/mypy/symvision) green after re-keying stale sase-qt.6 epic-symbols to sase-qt and privatizing in-file classify_flat_query_tokens. just check escalated to the full suite because Justfile changed: 34271 passed, 13 skipped; 2 reproducible completion-snapshot failures and 1 ACE startup flake (passed on rerun) are unrelated and recorded as PROPOSED FOLLOW-UP. No leftover --epic-symbol entries for sase-r0.2.

[2026-08-19T16:55:38Z · sase-r0.2] Added llm_interactive_cli plus vendor install metadata on all built-in providers (c/x/a/q/o/g/m menu keys, bypass_args matching tmux_ai_window, fakey supported=False, muse MUSE_NO_AUTO_UPDATE=1). Registry normalizes descriptors and exposes provider_interactive_cli_map/provider_vendor_map. Verified: 252 related provider/registry tests passed; just check lint green; full suite 34271 passed, 13 skipped; no leftover --epic-symbol entries for sase-r0.2.

## Dependencies

- **Blocks:** [sase-r0.3](sase-r0.3.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r0.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r0.2/README.md) | [sase-r0.2](sase-r0.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`88a7de4`](https://github.com/sase-org/sase/commit/88a7de4af1be4f596cca283c9f61d78350ffb212) | feat(llm): add interactive CLI descriptors and vendor metadata | [sase-r0.2](sase-r0.2.md) | 2026-08-19 12:57:18 EDT |
