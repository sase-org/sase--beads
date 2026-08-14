# Bead: sase-lz.2 — Parse-based selector detection and prefilled custom input

[Bead Pages](../README.md) / [sase-lz](README.md) / sase-lz.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.014](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.014.md) · **Assignee:** `sase-lz.2` · **Size:** small
**Created:** 2026-08-14 10:49:30 EDT
**Plan:** [202608/models\_panel\_pool\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/models_panel_pool_authoring.md)

## Description

selector-edit-plumbing: add a shared TUI selector helper module over the existing llm_provider API, replace the substring selector sniffing in the alias Edit flow with real parsing plus per-member safety checks, and give the custom-model input an initial value so editing an existing selector no longer means retyping it.

## Dependencies

- **Depends on:** [sase-lz.1](sase-lz.1.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-lz.3](sase-lz.3.md) ◐ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lz.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lz.2/README.md) | [sase-lz.2](sase-lz.2.md) | 0 |
