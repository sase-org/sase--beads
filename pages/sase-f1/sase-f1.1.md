# Bead: sase-f1.1 — Frozen test defaults, re-pinned tests, hardened loader

[Bead Pages](../README.md) / [sase-f1](README.md) / sase-f1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sw.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sw.f1/README.md) · **Assignee:** `sase-f1.1` · **Size:** medium
**Created:** 2026-08-03 14:46:52 EDT
**Plan:** [202608/zero\_friction\_model\_alias\_defaults.md](https://github.com/sase-org/sase--plans/blob/main/202608/zero_friction_model_alias_defaults.md)

## Description

seam: split the defaults parser from the cached resource loader, add fallback-reference, selector-grammar, and fallback-cycle validation to the parser, add a test-owned frozen defaults map installed by an autouse conftest fixture, re-pin the 39 measured value-coupled assertions to named frozen constants, and rewrite the shipped-file test module as a value-agnostic contract suite with a shape-parity guard.

## Dependencies

- **Blocks:** [sase-f1.4](sase-f1.4.md) ◐
