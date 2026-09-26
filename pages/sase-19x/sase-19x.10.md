# Bead: sase-19x.10 — User docs for card blocks

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s4.md) · **Assignee:** `sase-19x.10` · **Size:** small
**Created:** 2026-09-25 20:37:54 EDT · **Closed:** 2026-09-26 14:07:36 EDT
**Plan:** [202609/agent\_data\_card\_blocks.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_data_card_blocks.md)

## Description

card-blocks-docs: document the deck -> card -> block hierarchy, the newest-block landing and triage loop, the rail, the [ / ] keys (and the Ctrl+Shift+J/K override caveat) and block_spread_max_screens in docs/ace.md and docs/configuration.md. Record proposed glossary-strand text as a follow-up note, without editing memory.

## Notes

[2026-09-26T18:02:00Z · sase-19x.10] PROPOSED FOLLOW-UP: glossary strand for card block — Card block: one titled, stably identified unit inside an agent data card (deck -> card -> block); a session Reply card holds one block per concrete sase shell, with newest-block landing, [ / ] stepping, and a one-row block rail timeline.

[2026-09-26T18:07:25Z · sase-19x.10] PROPOSED FOLLOW-UP: just check symvision flags _legacy_sase_shell_syntax_enabled private import in src/sase/agent/legacy_sase_shell_syntax.py; pre-existing (only docs/ touched here), fails identically on base tree.

[2026-09-26T18:07:36Z · sase-19x.10] Documented card blocks in docs/ace.md (hierarchy, newest landing + triage loop, rail, [ / ] keys + Ctrl+Shift caveat, block_spread_max_screens) and docs/configuration.md (new field row); navigation key table row added; glossary strand proposed as follow-up note; prettier markdown clean; just check otherwise green except pre-existing symvision failure untouched by this bead.

## Dependencies

- **Depends on:** [sase-19x.9](sase-19x.9.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19x.10/README.md) | [sase-19x.10](sase-19x.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3c8596b`](https://github.com/sase-org/sase/commit/3c8596b61007ecc1c57b3dce8f1f36eefef3e26c) | docs(ace): document card blocks for session Reply cards (sase-19x.10) | [sase-19x.10](sase-19x.10.md) | 2026-09-26 14:09:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19i.7.3.3.1--1][1] | check later phase scope for block rail symbols | 1 |
| read-by | [agent:sase-19x.10][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19x.10/README.md

<!-- sase:referenced-by:end -->
