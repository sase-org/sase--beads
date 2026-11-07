# Bead: sase-1rs.5 — Dashboard, playlists, podcasts, search, and doctor

[Bead Pages](../README.md) / [sase-1rs](README.md) / sase-1rs.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19n.md) · **Assignee:** `sase-1rs.5` · **Size:** medium
**Created:** 2026-11-07 10:56:00 EST · **Closed:** 2026-11-07 14:40:48 EST
**Plan:** [202611/spotify\_agent\_access.md](https://github.com/sase-org/sase--plans/blob/main/202611/spotify_agent_access.md)

## Description

reads: ship the dashboard, playlists, podcasts, search, and doctor commands with quiet terminal output and the versioned JSON contract, plus read-side live tests.

## Notes

[2026-11-07T19:40:04Z · sase-1rs.5] Reads contract notes for later phases (sase-spotify, uncommitted until host finalize): (1) New reads-owned module cli/reading.py is the shared read plumbing: open_reader(args, config, guard=, use_cache=) builds TokenBroker + Library and closes both; envelope()/emit() build and print the -j envelope; print_table(console, table, flexible={col: floor}) shrinks only free-text columns (URIs never truncate); block()/indent()/warning() indent with hanging wrap and trim the trailing spaces Rich pads cells with. reading.now() and reading.client_options() are the test seams (pinned clock; transport to the fake). (2) propose: the dashboard "changes" line belongs in dashboard._render_library, with a new field on the Dashboard dataclass set in build() and exported from Dashboard.to_data(). (3) skill-docs: tests/reads_support.py has the NOW pin and fixtures that screenshots can reuse; human goldens live in tests/golden/reads/ (regenerate with SASE_SPOTIFY_UPDATE_GOLDEN=1 just test). (4) Behaviors: the dashboard exits 0 in every designed state (onboarding, logged out, needs_reauth with the renewal-tab hint, wrong account, unreadable, expired estimate) and reports data.state; doctor always exits 0 and reports data.summary/healthy; playlists show on a followed playlist prints a ⊘ panel and exits 8 (JSON: playlist_items_forbidden envelope); playlist@1 truncated by -n is complete:false, podcast@1 truncated stays complete; search in_library soft-fails to null with in_library_checked:false. (5) Privacy: the dashboard runs the guard before showing even the saved login name; doctor withholds account identity from refused agents, and its JSON carries a bypassed key only when a bypass is in effect.

[2026-11-07T19:40:10Z · sase-1rs.5] Scaffold/other-phase file edits (unavoidable, minimal): tests/test_cli.py LEAVES dropped the 10 reads stubs, and test_hints_name_the_invoked_binary plus test_python_m_hints_name_the_plugin_command now check the not-configured `playlists -j` hint (exit 3, auth setup) instead of a reads stub message; tests/test_entry_points.py test_sase_command_contract got the same change; AGENTS.md architecture-map row now lists cli/reading.py. No pyproject.toml or uv.lock change.

[2026-11-07T19:40:22Z · sase-1rs.5] PROPOSED FOLLOW-UP: Make the search in_library check cheap on a warm cache — Library.library_index() calls contents() per owned playlist, and contents() always re-fetches GET /playlists/{id} for snapshot S1 even when the contents cache is warm, so every track or episode search costs about one request per owned playlist plus the Liked Songs probe. With many owned playlists, a few agent searches can approach the 200-request budget or Spotify rate limits. Search degrades in_library to null rather than failing. Suggested fix in api-owned library.py: let library_index look up contents by the snapshot_ids of a fresh cached inventory (5 min TTL) before falling back to live S1 fetches.

[2026-11-07T19:40:28Z · sase-1rs.5] PROPOSED FOLLOW-UP: Decide whether `auth status` should withhold account identity from agents the privacy guard refuses — today it shows the Spotify display name and account ID to any actor, including an agent in a public-chat project, while the dashboard (guard first) and doctor (redacts) now do not. It is not library data, so this is consistency, not a leak of playlists or songs.

[2026-11-07T19:40:33Z · sase-1rs.5] Live probes: tests/live/test_reads.py (marker live, SASE_SPOTIFY_LIVE=1, never in CI) reads the inventory, one owned playlist, the first 60 Liked Songs, shows plus episodes, and search, and runs the CLI end to end. It records followed_items_status (does GET /playlists/{followed}/items return 403), followed_total_reported (does /me/playlists report items.total for followed playlists), and market_from_token_ok as test properties, which covers sase-1rs.4 proposed follow-up #3. Rollout should run `SASE_SPOTIFY_LIVE=1 just test-live -rA` after login and align the fake with what it reports.

[2026-11-07T19:40:48Z · sase-1rs.5] reads phase done in sase-org/sase-spotify (uncommitted until host finalize): bare sase spotify dashboard (about 4 requests; onboarding checklist; renewal-tab hint on a refused login; exit 0 in every designed state), playlists [list] and show REF (-n/-a, liked, friendly ⊘ panel and exit 8 for followed, honest truncated/complete), podcasts [list] and show REF (-n), search (types, URI column, in_library with a soft fallback), and doctor (12 rows: config, login, token store, live API latency, limits, Premium, drift, privacy, agent access, cache, skill, plugin; -r re-checks privacy). All take -j with the versioned envelopes. Verified: sase tool run check succeeded (ruff, format, mypy --strict on 56 files, codespell, 762 passed, coverage 98.92%); the read tests (144) also pass on Python 3.12; the suite is clean under -W error. Golden human output in tests/golden/reads/ covers every not-configured state, a followed playlist, changed_during_read, budget exhaustion, and malicious control or prompt text staying inert. Live read tests in tests/live/test_reads.py are opt-in. No epic symbols.

## Dependencies

- **Blocks:** [sase-1rs.10](sase-1rs.10.md) ◐ · ⧖ 2026-11-07
- **Depends on:** [sase-1rs.3](sase-1rs.3.md) ✓ · ⧖ 2026-11-07
- **Depends on:** [sase-1rs.4](sase-1rs.4.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rs.9](sase-1rs.9.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rs.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.5/README.md) | [sase-1rs.5](sase-1rs.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rs.4][1] | Check parallel phases' notes for API assumptions on the api phase | 1 |
| read-by | [agent:sase-1rs.5][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1rs.6][3] | Check parallel phases' assumptions about the changesets API (frozen doc, store, render) | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.5/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.6/README.md

<!-- sase:referenced-by:end -->
