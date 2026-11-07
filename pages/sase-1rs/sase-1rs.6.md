# Bead: sase-1rs.6 — Changeset document, resolution, diffs, and preview renderers

[Bead Pages](../README.md) / [sase-1rs](README.md) / sase-1rs.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19n.md) · **Assignee:** `sase-1rs.6` · **Size:** medium
**Created:** 2026-11-07 10:56:00 EST · **Closed:** 2026-11-07 14:29:51 EST
**Plan:** [202611/spotify\_agent\_access.md](https://github.com/sase-org/sase--plans/blob/main/202611/spotify_agent_access.md)

## Description

changesets: implement the changeset v1 document and its validation with precise errors. Add playlist and track resolution, grouping, snapshot pinning, diffs, the frozen-changeset store, and the plain-text, Markdown, and terminal preview renderers.

## Notes

[2026-11-07T19:29:21Z · sase-1rs.6] Phase notes (changesets, landed in sase-spotify): pipeline is schema.read_source/load(text, config.limits) -> resolve.resolve(changeset, library) -> store.ChangeStore().allocate() -> freeze.freeze(resolved, change_id=change.id, source_sha256=source.sha256, proposer=freeze.proposer_of(actor), limits=config.limits) -> store.save(change, source=source.text, frozen=frozen); previews are render.gate_title/gate_notes/option_label/preview_md/terminal. Frozen contract (freeze.py docstring): groups[] with id p-/n-<slug>, kind existing|create, playlist_id, base_snapshot_id/base_name/base_description/base_count, ops {add, rename, describe, create:{name,description}}, skipped_present[], skipped_repeats[], unchanged[], entries[], display, external_url; top-level noop[] lists playlists where nothing changes. For apply: reuse diff.plan_additions for the add-only-still-absent re-check; Frozen.group(id); load_frozen(bytes) hashes the stored bytes. Journal lines must be JSON objects with a "type" field ("proposed", "closed" with "status") so store.journal_status and purge read them (or pass status_of=). MINIMAL CROSS-PHASE EDITS: api/endpoints.py gained get_track/get_episode (single-item GETs that survived Feb 2026; they name URI adds in the review) and tests/fakes/spotify.py gained GET /tracks/{id} and /episodes/{id} routes. New test builders live in tests/fakes/changesets.py; goldens in tests/golden/changes (regenerate with UPDATE_GOLDEN=1).

[2026-11-07T19:29:34Z · sase-1rs.6] PROPOSED FOLLOW-UP: size the propose request budget for URI lookups — each add URI not already in a target or the library costs one GET /tracks|/episodes/{id}; with the default limits.request_budget (200) a changeset of ~150+ new URIs now fails fast with changeset_too_large, though changeset_max_tracks allows 500. propose (sase-1rs.9) could build its client with a larger budget (e.g. limits.apply_request_budget) or the defaults could be reconciled.

[2026-11-07T19:29:40Z · sase-1rs.6] PROPOSED FOLLOW-UP: call ChangeStore.purge(days=config.retention.changes_days) opportunistically from propose or history — retention purge (30 days, keeping pending and outcome_unknown) is implemented and tested in changes/store.py but nothing invokes it yet.

[2026-11-07T19:29:51Z · sase-1rs.6] Implemented changes/schema.py, resolve.py, diff.py, freeze.py, store.py, render.py and filled docs/changesets.md 'Format and vocabulary' in sase-org/sase-spotify. Verified with 'sase tool run check' in the sase-spotify checkout: ruff, ruff format --check, mypy --strict (55 files), codespell, and 880 tests passed with 98.48% coverage. New tests cover: schema validation with every error in one pass (paths, did-you-mean suggestions, unsupported_operation, too large, duplicate keys); the resolution matrix against the stateful fake (exact, prefix, ambiguous, not owned, protected, Liked, library-first, ISRC-unique, ISRC-split, URI lookups, budget fail-fast, privacy guard); grouping, pinning, no-op handling, limits, and canonical JSON + sha256; the store (id allocation, 0600/0700 files, journal status, history, retention purge); golden files for every renderer (mockup, single group, long names, malicious names, 500 tracks, eight groups, ASCII terminal); and Hypothesis properties for deterministic freezing, valid unique group ids, and notes within 25 lines / 3,000 chars.

## Dependencies

- **Depends on:** [sase-1rs.4](sase-1rs.4.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rs.8](sase-1rs.8.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rs.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.6/README.md) | [sase-1rs.6](sase-1rs.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rs.4][1] | Check parallel phases' notes for API assumptions on the api phase | 1 |
| read-by | [agent:sase-1rs.6][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.6/README.md

<!-- sase:referenced-by:end -->
