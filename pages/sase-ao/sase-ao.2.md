# Bead: sase-ao.2 — Enrich the model completion catalog with alias resolution and provenance

[Bead Pages](../README.md) / [sase-ao](README.md) / sase-ao.2

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ao.2` · **Size:** medium
**Created:** 2026-07-29 11:46:25 UTC
**Plan:** [202607/model\_alias\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/model_alias_completion.md)

## Description

catalog: derive alias rows from the same AliasView data the Models panel uses, add a read-only temporary-override peek, split the catalog into a config-token-cached static build plus a cheap override overlay, and extend the LSP catalog JSON additively.

## Dependencies

- **Blocks:** [sase-ao.3](sase-ao.3.md) ◐
- **Blocks:** [sase-ao.4](sase-ao.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ao.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ao.2/README.md) | [sase-ao.2](sase-ao.2.md) | 0 |
