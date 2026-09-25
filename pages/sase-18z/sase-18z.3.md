# Bead: sase-18z.3 — Keep bead note previews compact in split Context cards

[Bead Pages](../README.md) / [sase-18z](README.md) / sase-18z.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-18z.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-18z.land.md) · **Assignee:** `sase-18z.3.land`
**Created:** 2026-09-25 10:45:27 EDT · **Closed:** 2026-09-25 13:30:43 EDT
**Plan:** [202609/bead\_note\_split\_layout.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_note_split_layout.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-19n][1] | Epic that made note previews and read reasons card-width aware; this row is the remaining non-width-aware piece |

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-19n/README.md

<!-- sase:links:end -->

## Description

Make the agent-authored bead note preview readable and bounded by three visible body lines in narrow and split Main deck Context cards.

## Notes

[2026-09-25T17:30:43Z · sase-18z.3.land] Verified sase-18z.3.1 (204a4993e: ResponsiveBeadTouchesSection re-wraps note previews at the Context-card width, attribution/overflow/earlier-count/hints preserved) and sase-18z.3.2 (7a5559cc7: 24-cell min note width, golden refreshed); 24 bead-row tests pass and the golden shows a 3-line body. Integration: the 4 commits landed since (command-line, fork waits, retry-countdown golden) don't touch this code, so nothing needed. Land fix: append_context_reason now gives up indent to keep 24 content cells, so the bead read-reason line no longer hard-breaks words (Context-ca/rd) in narrow cards; added test_read_reason_yields_indent_before_words_in_narrow_cards (fails without the fix), refreshed and inspected agents_bead_note_preview_120x40.png, and 6516 widgets/actions/modals tests pass. sase tool run check: every lint gate and SASE validation passed; the scoped test stage escalated to the full suite and was killed at my 50m timeout (run b2334260). Follow-ups: 18z.3.1 and 18z.3.2 prompt-archive validate failure = duplicate of sase-17u, which 18z.3.1 already +1'd, so no new task (validate now passes). Filed sase-19n (medium bug) for the pre-existing narrow-card lane-row wrap, which this epic did not cause. No epic-symbols.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18z.3.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18z.3.land/README.md) | [sase-18z.3](sase-18z.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`982209d`](https://github.com/sase-org/sase/commit/982209db994c2c9b9c45025e0e1c0b9ac3275b49) | fix(ace-tui): keep bead read reasons readable in narrow Context cards | [sase-18z.3](sase-18z.3.md) | 2026-09-25 13:53:22 EDT |
