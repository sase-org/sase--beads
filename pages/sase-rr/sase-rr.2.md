# Bead: sase-rr.2 — Make pluggable finalizers unconditional and delete the old path

[Bead Pages](../README.md) / [sase-rr](README.md) / sase-rr.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.096](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.096.md) · **Assignee:** `sase-rr.2` · **Size:** medium
**Created:** 2026-08-21 09:05:42 EDT
**Plan:** [202608/retire\_pluggable\_finalizers.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_pluggable_finalizers.md)

## Description

retire-legacy: delete the pluggable_finalizers flag and Off branch, extract any still-needed reconciliation helpers from the deprecated controller, remove beta-only config, environment, baseline, metric, and artifact writers, and preserve only deliberate historical readers.

## Dependencies

- **Depends on:** [sase-rr.1](sase-rr.1.md) ✓ · ⧖ 2026-08-21
- **Blocks:** [sase-rr.3](sase-rr.3.md) ◐ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rr.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rr.2/README.md) | [sase-rr.2](sase-rr.2.md) | 0 |
