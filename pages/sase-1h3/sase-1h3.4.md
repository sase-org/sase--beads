# Bead: sase-1h3.4 — \`sase instructions render\` preview and legacy parity checks

[Bead Pages](../README.md) / [sase-1h3](README.md) / sase-1h3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0xc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xc.md) · **Assignee:** `sase-1h3.4` · **Size:** medium
**Created:** 2026-10-06 12:43:29 EDT · **Closed:** 2026-10-06 16:44:14 EDT
**Plan:** [202610/e2\_instruction\_bundles\_shadow\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_instruction_bundles_shadow_mode.md)

## Description

render-cli: add the render subcommand (agent, fact, json, no-cache, parity, sections) and the legacy parity checker, with CI parity tests for sase-, bob-cli-, and actstat-shaped fixtures and this repo's committed AGENTS.md.

## Notes

[2026-10-06T20:43:59Z · sase-1h3.4] PROPOSED FOLLOW-UP: just check symvision gate stays red on KNOWN _runs private-import findings in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py (triaged KNOWN, witness 22778c601b3c983292d19516826709e8); needs an owner to make those imports public or allowlist them

[2026-10-06T20:44:14Z · sase-1h3.4] render-cli done: render subcommand (-a/-f/-j/-N/-p/-s) plus legacy_parity checker land with CI parity tests for sase/bob-cli/actstat-shaped fixtures and the committed AGENTS.md. Verified: sase tool run check passes every stage except the pre-existing KNOWN symvision pair in two untouched files (recorded as PROPOSED FOLLOW-UP); sase instructions render -p exits 0 in this checkout; codex/grok share common_digest; targeted suites 67 passed.

## Dependencies

- **Depends on:** [sase-1h3.3](sase-1h3.3.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h3.7](sase-1h3.7.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h3.4/README.md) | [sase-1h3.4](sase-1h3.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8e4543b`](https://github.com/sase-org/sase/commit/8e4543bd43a34c429782df8ca441f2438335ce11) | feat(instructions): add render CLI with parity preview and section filtering | [sase-1h3.4](sase-1h3.4.md) | 2026-10-06 17:09:44 EDT |
