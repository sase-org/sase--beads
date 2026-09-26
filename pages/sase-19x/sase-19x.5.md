# Bead: sase-19x.5 — Block-paged projection, newest landing and the card\_blocks flag

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s4.md) · **Assignee:** `sase-19x.5` · **Size:** medium
**Created:** 2026-09-25 20:37:45 EDT
**Plan:** [202609/agent\_data\_card\_blocks.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_data_card_blocks.md)

## Description

block-paged-view: create the card_blocks beta flag. Add DeckPanelBlocksMixin and the MainDeckView block mixin, which decide the block mode for a card shown alone, render one block per page, and land on the newest block. They also follow new shells, keep the reader's block by id, and expose cycle/select and a cached navigable predicate. Add the sticky-Reply bench fixture.

## Dependencies

- **Depends on:** [sase-19x.2](sase-19x.2.md) ✓ · ⧖ 2026-09-25
- **Depends on:** [sase-19x.3](sase-19x.3.md) ◐ · ⧖ 2026-09-25
- **Blocks:** [sase-19x.6](sase-19x.6.md) ◐ · ⧖ 2026-09-25
- **Blocks:** [sase-19x.7](sase-19x.7.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19x.5/README.md) | [sase-19x.5](sase-19x.5.md) | 0 |
