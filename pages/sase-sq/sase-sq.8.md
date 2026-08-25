# Bead: sase-sq.8 — Retire the config glossary

[Bead Pages](../README.md) / [sase-sq](README.md) / sase-sq.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0cb](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0cb.md) · **Assignee:** `sase-sq.8` · **Size:** large
**Created:** 2026-08-24 09:32:19 EDT · **Closed:** 2026-08-25 02:49:09 EDT
**Plan:** [202608/memory\_webs.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_webs.md)

## Description

retire: delete the config-backed glossary package, schema, completion source, and CLI group, fold the ACE glossary pane into the memory pane, and finish the docs.

## Notes

[2026-08-25T06:50:20Z · sase-sq.8.1.land] PARENT-PHASE VERIFICATION (sase-sq.8.1.land). This phase auto-closed as 'delegated work landed' when its sole child epic sase-sq.8.1 closed, so that close carries no verification of its own. Recording it here. sase-sq.8's description asked for four things and I confirmed each against the landed tree at 882ba36f5, not against phase notes: (1) the config-backed glossary package, schema block, completion source, and CLI group are deleted — src/sase/glossary/ and glossary_config.py are gone from git, memory.glossary is rejected by sase.schema.json, ValueKind.GLOSSARY and the sase.yml-mtime completion candidate source are gone, and '.venv/bin/sase glossary' now errors with "invalid choice: 'glossary'"; (2) the ACE glossary pane is folded into the memory pane — every glossary_pane/glossary_panel* module and the Config-hub Glossary subtab are deleted, the prompt gG shortcut posts a resolved glossary:<slug> identity that opens the Memory subtab, and MemoryPane gained strand add/delete over a new atomic sase.memory.web.mutation engine that shares one closure graph with the CLI; (3) the docs are finished — docs/{memory,cli,completion,configuration,ace,init,getting_started,xprompt}.md and the sase_memory_read skill source describe the two-axis model, and the skill is deployed from this canonical tree with matching provenance (chezmoi c70d9c83, SASE_SOURCE_REVISION=882ba36f5); (4) the parent plan's extra landing conditions hold — 'sase memory init --check' is clean for sase, bob-cli, and home, and the glossary keymap scope stays accepted but inert with a sase doctor warning at config.keymap_glossary. Also completed the parent plan's own step-5 instructions for this phase: 'sase bead epic-symbols sase-sq.8' reports no entries and 'just symvision' shows a clean epic whitelist (its only failure is the unrelated chat_fork private-import blocker, sase-tb). Every check-full gate passes individually; the full suite is 36781 passed with 9 pre-existing failures, all dispositioned in sase-sq.8.1's close note. Per that plan and my land prompt I am closing only this phase and leaving sase-sq to its own land agent.

## Dependencies

- **Depends on:** [sase-sq.6](sase-sq.6.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-sq.7](sase-sq.7.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.8.md) | [sase-sq.8](sase-sq.8.md) | 0 |
