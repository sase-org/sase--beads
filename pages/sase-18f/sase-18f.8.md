# Bead: sase-18f.8 — Cache sase-xprompt-lsp builds and dedupe concurrent core builds

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.8` · **Size:** medium
**Created:** 2026-09-24 17:19:02 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

lsp-build-cache: add a host-wide content-addressed cache for the sase-xprompt-lsp binary, keyed like the sase_core_rs wheel cache, and use it in rust-lsp-install. Add a per-identity build lock so concurrent workspaces build each new sase-core source identity once.

## Dependencies

- **Blocks:** [sase-18f.9](sase-18f.9.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-18f.8.md) | [sase-18f.8](sase-18f.8.md) | 0 |
