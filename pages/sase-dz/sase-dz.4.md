# Bead: sase-dz.4 — Skip the prompt-archive check when its context is unavailable

[Bead Pages](../README.md) / [sase-dz](README.md) / sase-dz.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rm](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rm/README.md) · **Assignee:** `sase-dz.4` · **Size:** medium
**Created:** 2026-08-02 10:46:01 UTC
**Plan:** [202608/ci\_green\_restoration.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restoration.md)

## Description

validate-skip: teach the prompt-archive validation an explicit unavailable-context outcome and have `sase validate` report it as skipped rather than failed, so a clean host without a project registry or agents-sidecar clone can still run the aggregate validation.

## Dependencies

- **Blocks:** [sase-dz.6](sase-dz.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dz.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.4/README.md) | [sase-dz.4](sase-dz.4.md) | 0 |
