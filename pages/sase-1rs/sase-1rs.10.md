# Bead: sase-1rs.10 — The /sase\_spotify skill, README, and documentation

[Bead Pages](../README.md) / [sase-1rs](README.md) / sase-1rs.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19n.md) · **Assignee:** `sase-1rs.10` · **Size:** medium
**Created:** 2026-11-07 10:56:01 EST · **Closed:** 2026-11-07 16:45:23 EST
**Plan:** [202611/spotify\_agent\_access.md](https://github.com/sase-org/sase--plans/blob/main/202611/spotify_agent_access.md)

## Description

skill-docs: write the /sase_spotify skill, the README, and the docs pages, with generated terminal screenshots. Then finalize AGENTS.md and CONTRIBUTING.

## Notes

[2026-11-07T21:42:53Z · sase-1rs.10] Phase notes (skill-docs, in sase-org/sase-spotify): added src/sase_spotify/skills/sase_spotify.md (106 generated lines; front matter name/skill/description per plan; sase_gmail-style rules for privacy exit 9, -j reads in order, summarize, nothing durable, untrusted_text, one heredoc changeset then /sase_final, never apply/Web API/auth.json, exit-code table 3-9). Verified with the plugin wheel on PYTHONPATH: `sase skill list` shows /sase_spotify sourced from plugin:sase_spotify/sase_spotify.md (not deployed: deploy waits for rollout from a landed revision). tools/screenshots.py (`just screenshots`) renders 14 scenes (help, onboarding, dashboard, auth status, playlists, playlist show, podcasts, podcast show, search, doctor, changes list/show/propose, privacy refusal) against the fake Spotify on loopback + fake sase in a throwaway sandbox, with a real propose -> gate apply -> propose history; each scene has an expected-text marker so a degraded run fails instead of writing a bad SVG; output is deterministic (doctor latency pinned). Docs: README (hero, quickstart, safe changes, privacy box, links), agents.md, architecture.md (Mermaid ownership diagram + condensed rationale + plan/research commit permalinks), privacy-and-terms.md (AI clause quoted, posture A, claude.ai connector caveat, retention table, trust boundary, agent_access:false, bypass for Bryan only), roadmap.md (deferred table + live probe table, status pending), screenshots in commands/getting-started, CONTRIBUTING and AGENTS.md finalized; all stub markers gone; skills/.gitkeep removed. Tests: tests/test_docs.py parses all 25 `sase spotify` bash examples and runs the 16 non-interactive ones against the fake (agent pages as an agent in +spotify), checks links+anchors, skill shape, no orphan screenshots; tests/test_screenshots.py runs the script.

[2026-11-07T21:43:00Z · sase-1rs.10] PROPOSED FOLLOW-UP: fill the live probe results table in sase-spotify docs/roadmap.md during rollout (sase-1rs.11) — every row reads "pending" until `SASE_SPOTIFY_LIVE=1 just test-live -rA` runs on athena after `auth login --write` (same probes as sase-1rs.8 follow-up #2 and sase-1rs.5 note #5); record the booleans/counts only, then align tests/fakes/spotify.py with any surprise.

[2026-11-07T21:43:05Z · sase-1rs.10] PROPOSED FOLLOW-UP: recapture sase-spotify docs/assets/gate-tui.png after fixing the "Why:" hanging indent (sase-1rs.9 follow-up #3) — the README now shows that PNG as the "Changing playlists safely" hero, so the mid-paragraph indent is visible on the repo front page; tools/screenshots.py does not produce it (it was a live `sase screenshot` capture).

[2026-11-07T21:43:11Z · sase-1rs.10] Resolves sase-1rs.8 follow-up #3: rendered both Mermaid diagrams (docs/changesets.md lifecycle and the new docs/architecture.md ownership diagram) with mmdc on athena using the cached puppeteer chrome-headless-shell (-p with executablePath + --no-sandbox); both render cleanly. GitHub Markdown API (mode=markdown) render of README, CONTRIBUTING, AGENTS.md, agents, architecture, privacy-and-terms, roadmap: no leaked Markdown, tables render.

[2026-11-07T21:45:23Z · sase-1rs.10] skill-docs landed in sase-org/sase-spotify (committed by host finalize): /sase_spotify skill (sourced from plugin:sase_spotify per sase skill list with the built wheel), README, every docs stub filled (agents, architecture with Mermaid + permalinks, privacy-and-terms, roadmap), CONTRIBUTING + AGENTS.md finalized, tools/screenshots.py + 14 docs/assets SVGs. Verified: sase tool run check green twice (ruff, format, mypy --strict 56 files, codespell, 1312 passed, 98.39% coverage); new tests (docs examples run against the fake, links/anchors, skill shape, screenshots script) also pass on Python 3.12; uv build + twine check --strict + check_wheel ok; GitHub markdown render clean; both Mermaid diagrams render with mmdc. No epic symbols.

## Dependencies

- **Blocks:** [sase-1rs.11](sase-1rs.11.md) ◐ · ⧖ 2026-11-07
- **Depends on:** [sase-1rs.5](sase-1rs.5.md) ✓ · ⧖ 2026-11-07
- **Depends on:** [sase-1rs.7](sase-1rs.7.md) ✓ · ⧖ 2026-11-07
- **Depends on:** [sase-1rs.9](sase-1rs.9.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rs.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.10/README.md) | [sase-1rs.10](sase-1rs.10.md) | 0 |
