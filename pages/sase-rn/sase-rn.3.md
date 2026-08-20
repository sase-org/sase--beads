# Bead: sase-rn.3 — Feature flag, repository baselines, registry, and launch selection

[Bead Pages](../README.md) / [sase-rn](README.md) / sase-rn.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08y.md) · **Assignee:** `sase-rn.3` · **Size:** medium
**Created:** 2026-08-20 16:35:03 EDT · **Closed:** 2026-08-20 18:07:10 EDT
**Plan:** [202608/pluggable\_finalizers.md](https://github.com/sase-org/sase--plans/blob/main/202608/pluggable_finalizers.md)

## Description

host-foundation: create the beta flag through `sase flag new`, capture late-opened repository baselines atomically, add keyed configuration and `sase_finalizers` discovery with source provenance, parse ordered `%final` operations, reject invalid selected plans at launch, and persist the resolved plan without changing the flag-off commit finalizer path.

## Notes

[2026-08-20T21:47:25Z · sase-rn.3] PROPOSED FOLLOW-UP: stale admin_center_config_hub flag definition blocks just check — tools/check_feature_flags reports closed flag bead sase-rk still has a surviving admin_center_config_hub definition.

[2026-08-20T21:49:19Z · sase-rn.3] PROPOSED FOLLOW-UP: stale Symvision pragmas block just check — symvision reports unnecessary pragmas for SnippetsPaneSessionState, SnippetsPaneHost, and SnippetsPane in src/sase/ace/tui/modals/snippets_panel.py.

[2026-08-20T22:05:01Z · sase-rn.3] PROPOSED FOLLOW-UP: contract manifest is stale and over budget — pytest -m contract selects tests/test_core_finalizer_facade.py, but adding it to tests/contract_manifest.txt makes the contract set 53 entries against the 52-entry budget and needs the curation procedure from plans/202608/test_suite_tier1.md.

[2026-08-20T22:07:10Z · sase-rn.3] Implemented host-foundation pluggable finalizers behind pluggable_finalizers, late-opened repo baseline capture, finalizer config/plugin discovery, ordered %final parsing, launch plan persistence, and flag-gated controller handoff. Verified epic-symbols empty; 232 focused finalizer/directive/flag/marker tests passed; git diff --check passed; just check passed fmt, Ruff, and mypy before stopping on pre-existing closed flag bead sase-rk/admin_center_config_hub, with Symvision and contract-manifest follow-ups recorded on this phase.

[2026-08-20T22:08:26Z · sase-rn.3] Verified no epic-symbol leftovers; focused finalizer/directive/flag/marker suites passed with 232 tests; git diff --check passed; just check passed fmt, Ruff, and mypy before stopping on unrelated closed-flag blocker admin_center_config_hub/sase-rk; unrelated follow-ups recorded on the phase.

## Dependencies

- **Depends on:** [sase-rn.2](sase-rn.2.md) ✓ · ⧖ 2026-08-20
- **Blocks:** [sase-rn.4](sase-rn.4.md) ✓ · ⧖ 2026-08-20
- **Blocks:** [sase-rn.5](sase-rn.5.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rn.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rn.3/README.md) | [sase-rn.3](sase-rn.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b1c6bb1`](https://github.com/sase-org/sase/commit/b1c6bb105fd82239c6624115ea58fa5af423657c) | feat(finalizers): add beta finalizer foundation | [sase-rn.3](sase-rn.3.md) | 2026-08-20 18:09:37 EDT |
