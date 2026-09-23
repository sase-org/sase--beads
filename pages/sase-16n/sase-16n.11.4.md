# Bead: sase-16n.11.4 — Deterministic tag PNG golden coverage

[Bead Pages](../README.md) / [sase-16n.11](sase-16n.11.md) / sase-16n.11.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16n.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.land.md) · **Assignee:** `sase-16n.11.4` · **Size:** small
**Created:** 2026-09-23 08:51:49 EDT · **Closed:** 2026-09-23 13:30:10 EDT
**Plan:** [202609/project\_tags\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags_landing_gaps.md)

## Description

tag-goldens: pin a fixture tag catalog in the visual harness, add prompt-highlighting and AGENT XPROMPT tag cases, and capture and inspect their goldens plus any tag-surface drift with fix-tui-screenshots.

## Notes

[2026-09-23T17:13:01Z · sase-16n.11.4--2] PROPOSED FOLLOW-UP: prompt_search_count_pill_flexoki golden is stale independent of tag work (orange vs purple `/` sigil in status pill); drifts with and without the tag-catalog pin, so it predates sase-16n.11.4 — needs its own regen/inspect pass

[2026-09-23T17:23:19Z · sase-16n.11.4--2] PROPOSED FOLLOW-UP: agents_retry_e2e goldens (countdown/running_fallback/completed_chain) embed unseeded random hex in agent-delta artifact IDs and drift between runs; unrelated to tags, needs harness seeding, goldens left untouched

[2026-09-23T17:29:28Z · sase-16n.11.4--2] PROPOSED FOLLOW-UP: symvision gate fails on master for unused public ExpandedLaunchSegments in src/sase/agent/launch_cwd_segments.py; reproduces with this phase stashed, unrelated to tag goldens

[2026-09-23T17:30:10Z · sase-16n.11.4--2] Tag goldens captured and inspected: fixed the fixture pin (startup warm bypassed the loader stub via package bindings and clobbered the cache with a home-only catalog; fixture now also stubs _build_catalog), strengthened prompt-test span assertions (sase accented x1, home+oldproj neutral x2, unknown x1), recaptured 4 tag goldens (sase green accent, home/oldproj neutral gray, unknown warning underline, fenced literal inert — pixels verified), applied 5 tag-caused drift goldens (history+stash sase cells now fixture-green). Tag-adjacent suites clean (9 unchanged); full visual suite otherwise clean except pre-existing flexoki pill flake and unseeded retry_e2e IDs (both noted as follow-ups, goldens untouched). sase tool run check green except symvision ExpandedLaunchSegments failure proven pre-existing on stashed tree (noted).

## Dependencies

- **Depends on:** [sase-16n.11.3](sase-16n.11.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.11.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.11.4.md) | [sase-16n.11.4](sase-16n.11.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`848a90a`](https://github.com/sase-org/sase/commit/848a90a1ba6550faca8c29b8d9dcde81d4decb65) | fix(ace-tui): pin project-tag catalog in PNG snapshot fixtures | [sase-16n.11.4](sase-16n.11.4.md) | 2026-09-23 13:31:59 EDT |
