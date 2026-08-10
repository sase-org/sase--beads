# Bead: sase-ik.2 — Publish a sase-core-rs release containing the matcher change

[Bead Pages](../README.md) / [sase-ik](README.md) / sase-ik.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ws](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ws/README.md) · **Assignee:** `sase-ik.2` · **Size:** small
**Created:** 2026-08-09 15:54:35 EDT · **Closed:** 2026-08-10 07:28:21 EDT
**Plan:** [202608/glossary\_line\_break\_matching.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_line_break_matching.md)

## Description

core-release: land the release-plz version bump for sase-core, record the published version, and confirm the wheel resolves from PyPI.

## Notes

[2026-08-10T12:54:09Z · sase-ik.land] LAND VERIFICATION: core commit 4012af5b871a9550210f87e9af133259b430bdcc is an ancestor of release tag v0.22.0; the v0.22.0 sase_core changelog names glossary line-break matching, and a fresh isolated PyPI install of sase-core-rs==0.22.0 passes tools/smoke_sase_core_rs_glossary_line_break. An unrelated breaking tale-size change then shipped v0.23.0, and sase now correctly declares >=0.23.0,<0.24.0; the exact current floor also passed the smoke and published-minimum validation.

## Dependencies

- **Depends on:** [sase-ik.1](sase-ik.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ik.3](sase-ik.3.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ik.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ik.2/README.md) | [sase-ik.2](sase-ik.2.md) | 0 |
