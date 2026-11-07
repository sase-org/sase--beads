# Bead: sase-1rs.9 — Changeset gate, propose and history commands

[Bead Pages](../README.md) / [sase-1rs](README.md) / sase-1rs.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19n.md) · **Assignee:** `sase-1rs.9` · **Size:** medium
**Created:** 2026-11-07 10:56:01 EST · **Closed:** 2026-11-07 16:03:49 EST
**Plan:** [202611/spotify\_agent\_access.md](https://github.com/sase-org/sase--plans/blob/main/202611/spotify_agent_access.md)

## Description

propose: build the custom gate turn from a frozen changeset. Add the propose, repropose, list, and show commands and the dashboard changes line, plus golden gate tests and an end-to-end contract test against a real sase.

## Notes

[2026-11-07T21:03:22Z · sase-1rs.9] Phase notes (propose, in sase-org/sase-spotify): implemented changes/gate.py (schema-v3 request: query "(groups AND-joined) OR revise OR reject", primary branch = groups, "Apply to Spotify" group button for 2+ groups, v/c actions, turn block for agents only with next.prompt null and revise/reject/timeout branches, request_id spotify-<cs-id>, sh wrappers baking sys.executable + XDG/SASE_SPOTIFY_* env), changes/propose.py (Proposer: validate -> unknown --supersede refused -> write-scope check -> resolve/freeze -> store + journal proposed BEFORE gate create -> gate (rolled back on SASE refusal) -> gate_created -> supersede cancel/close -> retention purge), changes/history.py (statuses reconciled with sase gate show; timeout journals closed expired), cli/changes.py (propose, repropose, list, show [-s], hidden close + new hidden diff for the v action), and the dashboard changes line (dashboard@1 data.changes). DESIGN CHOICE: preview.md is an attachment, not a "preview" resource: a live TUI capture showed the preview role squeezes the notes into a narrow column and pushes the decision below; as an attachment the notes stay full width and the diff is one keypress (v). MINIMAL CROSS-PHASE EDITS: tests/test_cli.py (dropped the propose stub leaves; replaced the two stub tests with a direct test of not_implemented; moved the changes -j case to its own test) and cli/dashboard.py (the planned changes line).

[2026-11-07T21:03:28Z · sase-1rs.9] PROPOSED FOLLOW-UP: make preview.md escape only what Markdown needs — changes/render.py md_escape escapes every . : - ( etc., and the SASE TUI shows the v action (and any preview resource) as highlighted Markdown SOURCE, so the full diff reads "shortens the name\." and "Long sessions\."; seen in a live sase screenshot of the demo gate.

[2026-11-07T21:03:34Z · sase-1rs.9] PROPOSED FOLLOW-UP: drop the hanging indent on wrapped "Why:" lines in render.gate_notes — the TUI and Telegram re-wrap notes, so the 5-space continuation shows up mid-paragraph ("built from instrumental /      tracks already in Liked Songs"); visible in docs/assets/gate-tui.png.

[2026-11-07T21:03:39Z · sase-1rs.9] PROPOSED FOLLOW-UP: exercise the agent gate-turn path end to end during rollout (sase-1rs.11) — real `sase gate create --turn` refuses without a calling agent, so tests/contract/test_changeset_gate.py covers the human gate (create, v/c actions, apply both groups, stale group, reject, one outcome row); the agent request (turn block, revise branch) was validated with sase GateSpec.from_mapping + validate_gate_spec only, and Telegram rendering of the gate was not checked.

[2026-11-07T21:03:49Z · sase-1rs.9] Propose phase landed in sase-org/sase-spotify (gate.py, propose.py, history.py, changes CLI, dashboard line, docs gate + changes sections, docs/assets/gate-tui.png). Verified: 'sase tool run check' green (ruff, format, mypy --strict 56 files, codespell, 1247 tests, 98.46% coverage, fail_under 90); golden gate JSON for single/multi/human; contract tests against real sase under a throwaway SASE_HOME with all agent markers stripped: 10 passed (new: gate create accepted, v/c actions, both groups applied via sase gate answer -D with fake Spotify on loopback, stale group + check, reject, exactly one outcome row, bundle changeset.json byte-identical to the journaled frozen bytes); agent turn request validated with sase's GateSpec + validate_gate_spec; live TUI screenshot of the demo gate captured under the temp SASE_HOME.

## Dependencies

- **Blocks:** [sase-1rs.10](sase-1rs.10.md) ◐ · ⧖ 2026-11-07
- **Depends on:** [sase-1rs.5](sase-1rs.5.md) ✓ · ⧖ 2026-11-07
- **Depends on:** [sase-1rs.8](sase-1rs.8.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rs.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.9/README.md) | [sase-1rs.9](sase-1rs.9.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rs.6][1] | Check parallel phases' assumptions about the changesets API (frozen doc, store, render) | 1 |
| read-by | [agent:sase-1rs.8][2] | Coordinate journal API with parallel propose phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.6/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.8/README.md

<!-- sase:referenced-by:end -->
