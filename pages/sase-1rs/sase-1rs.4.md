# Bead: sase-1rs.4 — Web API client, cache, library service, privacy guard, and fake Spotify

[Bead Pages](../README.md) / [sase-1rs](README.md) / sase-1rs.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19n.md) · **Assignee:** `sase-1rs.4` · **Size:** medium
**Created:** 2026-11-07 10:56:00 EST · **Closed:** 2026-11-07 13:46:58 EST
**Plan:** [202611/spotify\_agent\_access.md](https://github.com/sase-org/sase--plans/blob/main/202611/spotify_agent_access.md)

## Description

api: implement the thin Web API client, with typed models for both item shapes, pagination, and rate-limit, quota, and budget handling. Add the snapshot-keyed cache, the library service with reference resolution, the privacy guard, and the stateful fake Spotify that every test uses.

## Notes

[2026-11-07T18:46:14Z · sase-1rs.4] API contract notes for later phases (sase-spotify, uncommitted until host finalize): (1) Build reads with `library.open_library(config, tokens, refresh=…, use_cache=True, actor=…, guard=…, transport=…, budget=…)` (a context manager). `Library` exposes me(), account_id, inventory(refresh=), liked_probe(), resolve_playlist(ref) (never-guess: ID/URI/URL/`liked`; exact case-insensitive name, then unique prefix; ambiguous_reference or not_found carry details.candidates), fetch_playlist(id) (live and uncached, for apply re-checks), contents(ref|Playlist) (S1, then cache or pages, then S2; 2 retries, then changed_during_read; followed playlists raise playlist_items_forbidden), liked(), library_index() (LibraryIndex.find(title, artist), contains, playlists_with; owned + Liked only), invalidate(playlist_id), shows(), resolve_show(ref), episodes(show, n), search(q, kind, n), annotate_in_library(results). (2) Models carry the JSON contract: to_contract() on Playlist/PlaylistContents(limit=)/Item/Show/Episode/SearchHit, and Freshness.envelope_fields() for output.success. Positions are 0-based. Followed playlists serialize items: null with unreadable_reason and hint. (3) Writes live in api/endpoints.py: create_playlist (always public: false), add_items (1..100 URIs, returns WriteResult with snapshot_id), change_details (name and description only). Scope tuples are READ_SCOPES and WRITE_SCOPES. (4) Apply: catch api.client.AmbiguousWriteError (5xx or a lost response after send) and reconcile; never retry it. Pass budget=RequestBudget(cfg.limits.apply_request_budget, setting="limits.apply_request_budget"). Gate and job actors may wait out Retry-After for up to 5 min. (5) Doctor: PrivacyGuard.evaluate(use_cache=, as_agent=, project_key=).to_dict(); HealthLog().snapshot() gives premium_lapse_suspected(), drift, last 429, and quota; Cache().stats(). Logout: Cache().clear() and PrivacyGuard.forget(). (6) Tests: fakes.spotify.FakeSpotify with fake.client(), fake.library(), fake.config(), and fake.serve() (a loopback server; server.config() and server.environ() give the URLs). It has faults (rate_limit, quota_exceeded, server_error, network_error, timeout_after_write, invalid_grant, expire_access_tokens, login_as), after() hooks for concurrent edits, and the accounts flow: approve(authorize_url) gives a landing URL; /api/token does PKCE S256 with rotating refresh tokens; CLIENT_ID and STATIC_TOKEN are constants. (7) Demo artist renamed "Mara Vell" to "Mara Venn" because codespell flags "Vell". Every scenario is listed in the demo_library docstring. (8) Verified: `sase tool run check` passed (ruff, format, mypy --strict on 55 files, codespell, 533 tests at 97.9% coverage), and tests plus mypy also pass on Python 3.12.

[2026-11-07T18:46:35Z · sase-1rs.4] PROPOSED FOLLOW-UP: Create the private sase-org/sase-spotify--agents repo before the rollout acceptance launch — `sase repo list` shows that sidecar remote, but `gh api repos/sase-org/sase-spotify--agents` returns 404 today, so the fail-closed privacy guard refuses every +spotify agent with unknown_transcripts (exit 9) until the repo exists; the rollout phase should create it private through its install gate (or confirm SASE creates it private on first publish) and re-check with `sase spotify doctor`.

[2026-11-07T18:46:41Z · sase-1rs.4] PROPOSED FOLLOW-UP: Add two reads live probes — whether `GET /me/playlists` reports items.total for followed playlists (the fake omits it, so reads must render a missing count), and whether `market=from_token` works without the user-read-private scope (endpoints send it on items, Liked Songs, shows, episodes, and search).

[2026-11-07T18:46:46Z · sase-1rs.4] PROPOSED FOLLOW-UP: Have auth/scopes.py reuse api.endpoints.READ_SCOPES and WRITE_SCOPES (or the reverse) so login and per-request scope checks cannot drift apart; the api phase defined them in endpoints.py because auth ran in parallel.

[2026-11-07T18:46:58Z · sase-1rs.4] api phase done in sase-org/sase-spotify. It adds the guarded httpx client: the privacy guard and budget run before every request, a 401 gets one refresh, 429 and quota stops follow the actor's policy, a 403 on own data feeds health.json, and writes that may have landed are never blindly retried. It adds the February 2026 endpoints and fields, defensive parsing of both item shapes with drift counters, contract serializers, the account-keyed SQLite cache, the Library service (snapshot-consistent contents, Liked Songs fingerprint, never-guess resolution, podcasts, search, library index), the fail-closed privacy guard (any_private branch, 6 h allow cache, bypass), the stateful fake Spotify (MockTransport and loopback server, PKCE accounts, injectable faults), the invented demo library, and docs (architecture module map, data flow, cache table; privacy-guard section). Verified: sase tool run check passed (ruff, format, mypy --strict, codespell, 533 tests, 97.9% coverage); the suite and mypy also pass on Python 3.12. No epic symbols.

## Dependencies

- **Depends on:** [sase-1rs.2](sase-1rs.2.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rs.5](sase-1rs.5.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rs.6](sase-1rs.6.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rs.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.4/README.md) | [sase-1rs.4](sase-1rs.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rs.4][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1rs.5][2] | Check dependency phases' notes for seams and API assumptions the reads phase builds on | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.5/README.md

<!-- sase:referenced-by:end -->
