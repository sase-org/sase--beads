# Bead: sase-aq.5 — Migrate existing xprompt swarms

[Bead Pages](../README.md) / [sase-aq](README.md) / sase-aq.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aq.5` · **Size:** small
**Created:** 2026-07-29 13:07:44 UTC · **Closed:** 2026-07-29 14:38:56 UTC
**Plan:** [202607/agent\_name\_key\_markers.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_name_key_markers.md)

## Description

migrate: convert the bare `@` markers in this repo's `reads` swarm and the chezmoi `research_swarm` swarm to the keyed syntax, including the prose references.

## Notes

[2026-07-29T14:38:56Z · sase-aq.5] Migrated both bare-@ swarm xprompts to keyed markers: sase/xprompts/reads.md (4 %id + 3 %wait -> reads.{@1}) and chezmoi home/sase/xprompts/research_swarm.md (%clan, %id, 3x clan=, %wait x4, #fork, and the step-1 prose reference -> research.{@1}); reflowed the prose line to stay under 120 cols. Re-swept src/sase/xprompts/, src/sase/default_xprompts/, sase/xprompts/, chezmoi home/sase/xprompts/ and both sase.yml files: no other swarm bodies use a bare @ agent-name marker, and %model/%m @alias values were left alone (incl. old_research_swarm.md). Verified end-to-end with a throwaway script driving the real loader + expand_xprompt_swarms_with_metadata + resolve_agent_name_key_markers over the actual files: each swarm yields 4 segments carrying one qualified key, resolution unifies every %id/%clan/clan=/%wait/#fork/prose occurrence onto a single hood (reads.1, research.q), and two references in one dispatch get distinct keys and distinct hoods. just check: fmt/lint stages pass, full test suite 23523 passed 7 skipped; the two SDD validate errors (202607/axe_chop_reports.md prompt link) and the init-skills drift reproduce on a clean stash and are unrelated. The chezmoi edit is left uncommitted in the linked checkout; chezmoi update -a --force still needs to run after it is committed.

## Dependencies

- **Depends on:** [sase-aq.4](sase-aq.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-aq.5 | [sase-aq.5](sase-aq.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`48dc29b`](https://github.com/bbugyi200/dotfiles/commit/48dc29b1bc0d53b9ee4b68c62affa97736f709ef) | refactor: use keyed name markers in the research swarm | [sase-aq.5](sase-aq.5.md) | 2026-07-29 14:42:36 |
