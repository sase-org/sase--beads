# Bead: sase-1q2.2 — A complete published sase-core-rs contains master's core revision, and master pins it

[Bead Pages](../README.md) / [sase-1q2](README.md) / sase-1q2.2

**Status:** ◎ claimed · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.16e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.16e.md) · **Assignee:** `sase-1q2.2--mon` · **Size:** medium
**Created:** 2026-10-30 12:37:06 EDT
**Plan:** [202610/v0\_19\_0\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_19_0_release.md)

## Description

core-publish: get a complete sase-core-rs that contains the source pin onto PyPI (one rerun of the failed 0.43.2 upload, or a wait for the daily cut), then ratchet master's exact pin and prove the bindings.

## Notes

[2026-10-30T17:56:10Z · sase-1q2.2] Reran sase-core release-plz run 41077488562 --failed (publish-to-PyPI Rekor HTTP 502, attempt 1, all builds green); new publish job 124222014164 in progress. Waiting on PyPI for sase-core-rs 0.43.2 containing pin 17e79c8c. -r record rerun evidence for follow-up

## Dependencies

- **Depends on:** [sase-1q2.1](sase-1q2.1.md) ✓ · ⧖ 2026-10-30
- **Blocks:** [sase-1q2.7](sase-1q2.7.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q2.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q2.2.md) | [sase-1q2.2](sase-1q2.2.md) | 0 |
