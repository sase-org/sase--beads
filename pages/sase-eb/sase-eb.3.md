# Bead: sase-eb.3 — Rich rendering of the show layout

[Bead Pages](../README.md) / [sase-eb](README.md) / sase-eb.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.s3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.s3/README.md) · **Assignee:** `sase-eb.3` · **Size:** medium
**Created:** 2026-08-02 15:50:14 UTC · **Closed:** 2026-08-02 17:31:42 UTC
**Plan:** [202608/xprompt\_show.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_show.md)

## Description

render: build the Rich renderables for the header, properties, inputs, local xprompts, body with a line-number gutter and role styling, workflow steps, references, and hints; add the shared CLI chrome palette.

## Notes

[2026-08-02T17:20:59Z · sase-eb.3] PROPOSED FOLLOW-UP: Remove stale sase-e6(XpromptSourceRecord) symvision allowance — just check fails because XpromptSourceRecord now has a production consumer, but the xprompt-show design explicitly requires phase workers to leave pre-existing sase-e6 entries untouched.

[2026-08-02T17:31:42Z · sase-eb.3] Implemented the shared CLI chrome palette and Rich xprompt show renderer for headers, properties, inputs, local helpers, workflow steps, highlighted/guttered definitions, references, warnings, and hints. Verified 91 focused renderer/highlight/resolver/bead-detail tests, then the full suite: 25493 passed and 7 skipped. Formatting, keep-sorted, Ruff, mypy, pyscripts, changelog, toobig, SASE validation, and committed-plan validation passed. just check's sole failure is the pre-existing stale sase-e6(XpromptSourceRecord) symvision allowance, recorded on this bead as a PROPOSED FOLLOW-UP because the design explicitly says not to modify sase-e6 entries.

[2026-08-02T17:33:14Z · sase-eb.3] Implemented the shared CLI chrome palette and Rich xprompt show renderer for headers, properties, inputs, local helpers, workflow steps, highlighted/guttered definitions, references, warnings, and hints. Verified 91 focused renderer/highlight/resolver/bead-detail tests, then the full suite: 25493 passed and 7 skipped. Formatting, keep-sorted, Ruff, mypy, pyscripts, changelog, toobig, SASE validation, and committed-plan validation passed. just check's sole failure is the pre-existing stale sase-e6(XpromptSourceRecord) symvision allowance, recorded on this bead as a PROPOSED FOLLOW-UP because the design explicitly says not to modify sase-e6 entries.

## Dependencies

- **Depends on:** [sase-eb.1](sase-eb.1.md) ✓
- **Depends on:** [sase-eb.2](sase-eb.2.md) ✓
- **Blocks:** [sase-eb.4](sase-eb.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-eb.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-eb.3/README.md) | [sase-eb.3](sase-eb.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`d26d663`](https://github.com/sase-org/sase/commit/d26d6635febfe1ace3a6d60d07cfe8ba76f5c4d7) | feat(xprompt): add rich show renderer | [sase-eb.3](sase-eb.3.md) | 2026-08-02 17:33:50 |
