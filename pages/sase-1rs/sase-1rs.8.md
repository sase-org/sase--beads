# Bead: sase-1rs.8 — Gate-only apply executor

[Bead Pages](../README.md) / [sase-1rs](README.md) / sase-1rs.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19n.md) · **Assignee:** `sase-1rs.8` · **Size:** medium
**Created:** 2026-11-07 10:56:01 EST · **Closed:** 2026-11-07 15:18:56 EST
**Plan:** [202611/spotify\_agent\_access.md](https://github.com/sase-org/sase--plans/blob/main/202611/spotify_agent_access.md)

## Description

apply: implement the gate-only executor: re-checks, journaling, chunks of at most 100 URIs, reconciliation of ambiguous writes, verification, outcome notifications, and the drift check. Add write-side live tests and Spotify-semantics probes.

## Notes

[2026-11-07T20:18:21Z · sase-1rs.8] Phase notes (apply, in sase-org/sase-spotify): implemented changes/journal.py, apply.py, verify.py, outcome.py, drift.py and the hidden gate-only `changes apply`/`changes check` in cli/changes.py (only run_apply/run_check touched). FOR PROPOSE (sase-1rs.9): journal API is Journal.for_change(StoredChange) with record_proposed(frozen_sha256=frozen.sha256), record_gate_created(**descriptor), record_closed(status) (statuses REJECTED/REVISE_REQUESTED/EXPIRED/SUPERSEDED exported); store.journal_status reads the last closed record. Bundle wrappers must exec `python -m sase_spotify changes apply --bundle . --group <id>` and `... changes check --bundle .` WITHOUT -j: they print the bare gate value from the plan table (-j wraps it in apply-result@1/check-result@1). Both refuse unless the change is in the local store with a proposed record whose frozen_sha256 equals sha256 of the bundle changeset.json bytes, so write changeset.json as exactly frozen.data. Apply posts the single superseding outcome row itself (dedup key spotify-apply:<cs-id>:<n>, sender sase-spotify). Test builders for apply live in tests/fakes/applying.py. MINIMAL CROSS-PHASE EDIT: tests/test_cli.py dropped the two apply leaves from the stub list, as earlier phases did.

[2026-11-07T20:18:27Z · sase-1rs.8] PROPOSED FOLLOW-UP: run the live write tests and probes on athena — tests/live/test_writes.py (create + 150 adds + rename + describe on a disposable private playlist, plus probes for URI-wide DELETE, refresh-token rotation, and a revocation endpoint probed with an invalid token) never ran here (no live login; the epic worker runs in the public-chat sase project). Teardown tries DELETE /playlists/{id}/followers, then falls back to DELETE /me/library?uris=…; confirm which one the Feb 2026 API accepts during rollout (sase-1rs.11).

[2026-11-07T20:18:32Z · sase-1rs.8] PROPOSED FOLLOW-UP: confirm the Mermaid lifecycle diagram in docs/changesets.md renders on GitHub — mmdc could not launch a browser on athena, so it was checked for syntax and against the source only (skill-docs, sase-1rs.10, or rollout).

[2026-11-07T20:18:38Z · sase-1rs.8] PROPOSED FOLLOW-UP: harden outcome-row supersession in changes/outcome.py — each group posts spotify-apply:<cs-id>:<n> superseding only <n-1>, so if one post fails (the bridge warns and apply still succeeds) an older row can stay visible beside the newest one; superseding every earlier key, or keying on the last posted n from the journal, would keep exactly one row.

[2026-11-07T20:18:56Z · sase-1rs.8] Gate-only apply executor landed in sase-spotify: journal, re-check table, ≤100-URI chunks with intent/result journaling, reconciliation of ambiguous add/create/details writes (never blind-retried), resume from the journal, verification, one superseding outcome notification, and the read-only drift check; hidden changes apply/check refuse every non-gate actor with exit 7. Verified with 'sase tool run check' in the sase-spotify checkout: ruff, format check, mypy --strict (55 files), codespell, 1071 tests passed, 98.04% coverage, including a Hypothesis interleaving property (mutation-checked against both a broken rename re-check and ignoring present URIs). Live write tests and probes are written but not run here (see follow-ups).

## Dependencies

- **Depends on:** [sase-1rs.3](sase-1rs.3.md) ✓ · ⧖ 2026-11-07
- **Depends on:** [sase-1rs.6](sase-1rs.6.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rs.9](sase-1rs.9.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rs.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.8/README.md) | [sase-1rs.8](sase-1rs.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rs.6][1] | Check parallel phases' assumptions about the changesets API (frozen doc, store, render) | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.6/README.md

<!-- sase:referenced-by:end -->
