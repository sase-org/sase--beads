# Bead: sase-1aq.3 — Finish released runtime adoption for remote dispatch

[Bead Pages](../README.md) / [sase-1aq](README.md) / sase-1aq.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0sw` · **Assignee:** `sase-1aq.3` · **Size:** medium
**Created:** 2026-09-26 11:53:28 EDT · **Closed:** 2026-09-26 12:19:41 EDT
**Plan:** [202609/finish\_blocking\_epics\_and\_memory.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_blocking_epics_and_memory.md)

## Description

dispatch_runtime: publish and install matching repaired SASE and core builds on both machines.

## Notes

[2026-09-26T16:19:23Z · sase-1aq.3] PROPOSED FOLLOW-UP: Decide whether fleet hosts should cut from pin-built editable installs to PyPI-wheel installs (sase update -t pypi) now that published core v0.34.73 contains the dispatch repairs -r dispatch_runtime: file install-mode follow-up for land triage

[2026-09-26T16:19:41Z · sase-1aq.3] dispatch_runtime done 2026-09-26: closed sase-xe.16.11.7.14.6.7.4 with full evidence (published core v0.34.73 contains all .7.1/.7.2/.7.3 repairs per tag ancestry + isolated-wheel probe; Athena+Apollo both on matching sase 0.17.1+1524.gfedf207c1 / core 0.34.73+40.g9f86897f8 from pin 9f86897; Apollo hello ok gateway 0.34.73 schema v6 no skew; gateways+scheduler running both hosts; skills 147/147 current; doctor+core-health green). Epic-symbols clean. One PROPOSED FOLLOW-UP filed on install-mode cutover for land triage.

## Dependencies

- **Depends on:** [sase-1aq.1](sase-1aq.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1aq.4](sase-1aq.4.md) ✓ · ⧖ 2026-09-26
