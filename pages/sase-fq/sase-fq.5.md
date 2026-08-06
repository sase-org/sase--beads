# Bead: sase-fq.5 — Keep CI's prebuilt core wheel installed for every just recipe in a job

[Bead Pages](../README.md) / [sase-fq](README.md) / sase-fq.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tq/README.md) · **Assignee:** `sase-fq.5` · **Size:** medium
**Created:** 2026-08-05 21:06:00 EDT
**Plan:** [202608/ci\_master\_red\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_master_red_recovery.md)

## Description

ci-wheel-pin: stop later just recipes from silently re-resolving sase-core-rs back to a published wheel, so source lanes really do test the sase-core commit that build-core built, and add CI-shape coverage that locks the behavior in.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.5/README.md) | [sase-fq.5](sase-fq.5.md) | 0 |
