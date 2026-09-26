# Bead: sase-19x.3 — Session Reply cards emit one block per sase shell

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s4.md) · **Assignee:** `sase-19x.3` · **Size:** medium
**Created:** 2026-09-25 20:37:42 EDT
**Plan:** [202609/agent\_data\_card\_blocks.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_data_card_blocks.md)

## Description

session-reply-blocks: make the agent-session Reply builder wrap each concrete shell phase in a CardBlock whose BlockMeta matches the JUMP roster, in both hint and non-hint modes. Remove the vestigial blank + rule + blank prefix that opens every Reply/Output card, update the test walkers, and regenerate the affected goldens.

## Dependencies

- **Depends on:** [sase-19x.1](sase-19x.1.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19x.4](sase-19x.4.md) ◐ · ⧖ 2026-09-25
- **Blocks:** [sase-19x.5](sase-19x.5.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19x.3/README.md) | [sase-19x.3](sase-19x.3.md) | 0 |
