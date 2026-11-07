# Bead: sase-1rs.2 — Package skeleton, shared foundation, tooling, and CI

[Bead Pages](../README.md) / [sase-1rs](README.md) / sase-1rs.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19n.md) · **Assignee:** `sase-1rs.2` · **Size:** medium
**Created:** 2026-11-07 10:55:59 EST · **Closed:** 2026-11-07 12:44:27 EST
**Plan:** [202611/spotify\_agent\_access.md](https://github.com/sase-org/sase--plans/blob/main/202611/spotify_agent_access.md)

## Description

scaffold: build the package skeleton with every dependency declared, and implement the shared foundation modules: paths, config, errors, the JSON envelope, the UI kit, actor detection, and the SASE bridge. Add CLI stubs, guarded tooling, CI, and doc stubs, then set the GitHub metadata.

## Notes

[2026-11-07T17:44:03Z · sase-1rs.2] Scaffold contract notes for later phases (deviations from the plan text, all scaffold-owned): (1) CI and pr-title trigger on `main`, the repo default branch created by sase project create, not `master`; rollout should check main CI. (2) errors.py adds one code, `config_invalid` (exit 3), for bad config files; every other code is exactly the contract table. (3) coverage fail_under=90: the scaffold measured 95.7%, already above the epic target, so propose phase "raise to 90" is satisfied. (4) TokenProvider lives in the new scaffold module tokens.py as access_token(scopes=(), *, force_refresh=False) -> str; force_refresh is the single post-401 retry. StaticTokenProvider is a test double. (5) cli/common.py (scaffold) holds parser helpers; -j/-r/-a use SUPPRESS defaults so they work at any level, so read them via json_requested()/refresh_requested() or args after app.main fills defaults. Hidden commands: auth complete -p/--pending; changes apply -b/--bundle -g/--group; changes check -b; changes close -b -s/--status {revise_requested,rejected}. --version also -V. (6) sase_bridge.notify always sends -p with -k (sase requires it), defaulting to the first note; sase dedup actions are created|plus_oned, and -S supersedes only on the create branch. (7) tests/fakes/sase_cli.py is a stateful fake sase plus a fake_sase fixture. The autouse isolated_env fixture strips every SASE_* var and relocates HOME/XDG. (8) default_config.yml ships as a comment-only (empty) layer so sase never logs "failed to load plugin default_config.yml"; skills/ holds only .gitkeep until skill-docs. (9) ui.safe_text strips all Unicode Cf (bidi, zero-width, tag-block smuggling) except ZWJ/ZWNJ.

[2026-11-07T17:44:13Z · sase-1rs.2] PROPOSED FOLLOW-UP: Re-home sase-spotify AGENTS.md guidance after `sase init` — the scaffold hand-wrote AGENTS.md (plus CLAUDE.md = [AGENTS.md]) because sase init has not run in the repo (no sase/memory/). When Bryan runs `sase init -p gh_sase-org__sase-spotify` (repo-phase follow-up), init may plan a legacy-AGENTS.md migration; move the guidance into sase/memory notes via /sase_memory_write in that repo, keeping the opening /sase_spotify line, instead of letting init overwrite it. Related to the existing repo-phase sase-init follow-up on sase-1rs.1.

[2026-11-07T17:44:27Z · sase-1rs.2] Verified in sase-org/sase-spotify (changes pending host commit): `sase tool run check` succeeded (ruff, format, mypy --strict on 55 files, codespell, 267 pytest passing at 95.7% coverage, fail_under=90); the same suite plus mypy pass on Python 3.12 and 3.14; `just test-contract` passes 6 bridge-flag checks against the installed sase; raw `just check` is refused inside an agent. uv build + twine check --strict pass, and tools/check_wheel.py confirms every package file (default_config.yml, py.typed, skills/) and all 5 entry points ship. Foundation fully implemented and tested: paths (0700/0600, atomic, traversal-safe), config (typed defaults, YAML, env, flags, did-you-mean, origins, set_config_values), errors (full code table), output (envelope, untrusted_text, panels), ui (single-cell glyphs + ASCII fallback, formatters, safe_text property-tested), actor, invocation, sase_bridge (stateful fake sase), TokenProvider. Every CLI command (incl. hidden) is a stub exiting 1 naming its owner. Every later-phase module is a typed stub. uv.lock committed. Repo files, docs stubs, CI, and pr-title are in place. GitHub topics set (sase--plugin, spotify, cli, python, sase); description and read-only workflow permissions confirmed.

## Attachments

- 🌐 AGENTS.md · text/markdown · 20.3057 KiB

## Dependencies

- **Depends on:** [sase-1rs.1](sase-1rs.1.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rs.3](sase-1rs.3.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rs.4](sase-1rs.4.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rs.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.2/README.md) | [sase-1rs.2](sase-1rs.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rs.2][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1rs.4][2] | Need scaffold phase notes for api phase work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.4/README.md

<!-- sase:referenced-by:end -->
