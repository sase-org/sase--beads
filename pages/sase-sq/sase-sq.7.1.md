# Bead: sase-sq.7.1 — Glossary migration to a core web

[Bead Pages](../README.md) / [sase-sq.7](sase-sq.7.md) / sase-sq.7.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-sq.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.7.md) · **Assignee:** `sase-sq.7.1.land`
**Created:** 2026-08-24 18:15:34 EDT
**Plan:** [202608/glossary\_memory\_web.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_memory_web.md)

## Description

The `sase` and `bob-cli` glossaries stop living in `memory.glossary` and become file-backed core memory webs: `sase/memory/glossary.md` is a user-owned descriptor with a managed roster region, each term is a strand file under `sase/memory/glossary/`, the Rust glossary source wire addresses strand files so editor go-to-definition lands on a real Markdown note, config and files can never both be live, and `sase glossary *` survives one release as a deprecating alias over `sase memory`.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.7.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sq.7.1.land/README.md) | [sase-sq.7.1](sase-sq.7.1.md) | 0 |
