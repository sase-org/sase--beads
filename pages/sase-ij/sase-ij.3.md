# Bead: sase-ij.3 — Enforce the published floor on the release branch and at publish time

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.3` · **Size:** medium
**Created:** 2026-08-09 15:18:38 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

release-lane: add a CI job that runs only on the release-please branch and validates the exact declared PyPI core floor against bindings, wire-schema probes, smokes and the contract set, and pin the floor exactly in publish.yml's install-smoke so an incompatible floor mechanically blocks the PyPI upload.

## Dependencies

- **Blocks:** [sase-ij.5](sase-ij.5.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.3/README.md) | [sase-ij.3](sase-ij.3.md) | 0 |
