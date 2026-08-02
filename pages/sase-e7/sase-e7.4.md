# Bead: sase-e7.4 — Correct the directory-map asset and the prompt docs

[Bead Pages](../README.md) / [sase-e7](README.md) / sase-e7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rt](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rt/README.md) · **Assignee:** `sase-e7.4` · **Size:** small
**Created:** 2026-08-02 13:28:54 UTC · **Closed:** 2026-08-02 14:49:31 UTC
**Plan:** [202608/finish\_dh\_canonical\_archive.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_dh_canonical_archive.md)

## Description

docs-assets: remove prompt snapshots from the plans directory-map source, regenerate its PNG, and bring the prompt documentation in line with the canonical archive and the export decision.

## Notes

[2026-08-02T14:48:34Z · sase-e7.4] PROPOSED FOLLOW-UP: Full just check flaky under concurrent workspace test load — one run failed in unrelated artifact-files modal and bead contention tests; the exact three failing tests passed in focused rerun (3 passed in 11.90s).

[2026-08-02T14:49:31Z · sase-e7.4] Updated the plans directory-map source/PNG and prompt docs for the canonical agents archive and retired prompt export --sdd. Verified .venv CLI help shows archive/retired-sdd wording, full-size and 900px PNG previews show no prompt-snapshot or bead-state node, init repo --check is clean, git diff --check is clean, and the exact three unrelated full-suite failures pass in focused rerun (3 passed in 11.90s); full just check passed fmt/lint/SASE validation/committed-plan stages but the test stage failed once under concurrent workspace load.

## Dependencies

- **Depends on:** [sase-e7.2](sase-e7.2.md) ✓
- **Blocks:** [sase-e7.5](sase-e7.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e7.4/README.md) | [sase-e7.4](sase-e7.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`af0a6b8`](https://github.com/sase-org/sase/commit/af0a6b818f6b53102d81b5623079f304b253c7f4) | docs: update prompt archive docs and plans map | [sase-e7.4](sase-e7.4.md) | 2026-08-02 14:51:55 |
