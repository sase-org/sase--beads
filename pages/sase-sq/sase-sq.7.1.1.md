# Bead: sase-sq.7.1.1 — File-backed glossary source wire

[Bead Pages](../README.md) / [sase-sq.7.1](sase-sq.7.1.md) / sase-sq.7.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-sq.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.7.md) · **Assignee:** `sase-sq.7.1.1` · **Size:** medium
**Created:** 2026-08-24 18:15:34 EDT
**Plan:** [202608/glossary\_memory\_web.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_memory_web.md)

## Description

wire: generalize sase-core's GlossarySourceWire from config_path/config_key_path to source_path plus an optional key_path with keyword_range/body_range, bump GLOSSARY_WIRE_SCHEMA_VERSION to 2 keeping v1 keys accepted on read, and update the Python GlossarySource adapter and its readers to emit new names and accept both.

## Dependencies

- **Blocks:** [sase-sq.7.1.3](sase-sq.7.1.3.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.7.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sq.7.1.1/README.md) | [sase-sq.7.1.1](sase-sq.7.1.1.md) | 0 |
