# Bead: sase-1n6.7.1.5 — Replace the watcher CLI and install the observe-only host

[Bead Pages](../README.md) / [sase-1n6.7.1](sase-1n6.7.1.md) / sase-1n6.7.1.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.7.md) · **Assignee:** `sase-1n6.7.1.5` · **Size:** medium
**Created:** 2026-10-19 19:56:23 EDT
**Plan:** [202610/release\_steward\_observe.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_steward_observe.md)

## Description

cli-host: switch release_watch to the new reconciler, migrate legacy tests, and add the scheduled observe-only workflow with pinned Rust runtime and structured output.

## Notes

[2026-10-20T05:20:32Z · sase-1n6.7.1.5] LIVE --once --json (read-only, local gh auth, 2026-10-20): typed state core_lag pin=e0ddc100eb32097393daa0fd099b3017b1b1cfee, process_exit=0, train_action dispatch_core_cut disposition=already_satisfied, escalation proposed install_broken linux (not executed). Full JSON: {"blocker_duration_uncertain":false,"details":"no complete published core contains the source pin","escalation":{"disposition":"proposed","key":"esc-open:install_broken:release-steward:install_broken:linux","operation":{"body":"immediate install_broken linux","family":"install_broken","identity_marker":"release-steward:install_broken:linux","kind":"open","labels":["release-steward"],"title":"release-steward: install_broken (linux)"},"severity":"immediate"},"evidence":[],"primary":{"kind":"core_lag","pin":"e0ddc100eb32097393daa0fd099b3017b1b1cfee"},"process_exit":0,"schema_version":1,"secondary":[{"detail":"contracted linux canary result is missing","state":{"kind":"install_broken","member":"linux"}},{"detail":"contracted macos canary result is missing","state":{"kind":"install_broken","member":"macos"}}],"train_action":{"action":{"kind":"dispatch_core_cut","source_pin":"e0ddc100eb32097393daa0fd099b3017b1b1cfee"},"argv":["gh","workflow","run","release-plz.yml","-f","dry_run=false"],"disposition":"already_satisfied","key":"core-cut:pin=e0ddc100eb32097393daa0fd099b3017b1b1cfee","preconditions":["no complete published core contains the pin"],"reason":"applicable core cut already completed"}}

[2026-10-20T05:20:46Z · sase-1n6.7.1.5] PROPOSED FOLLOW-UP: handover sase-1n6.9 must rewrite docs/contribute/rust-backend.md — it still documents tools/release_watch --version/--fixed-sha/--once/--dry-run and names _release_watch_api.py plus _release_watch_engine.py, which this phase deleted.

[2026-10-20T05:20:51Z · sase-1n6.7.1.5] HANDOVER: RELEASE_STEWARD_MERGE_ENABLED is unset (disabled). Local --once used interactive gh, not secrets.SASE_RELEASE_TOKEN. Core Actions reads succeeded with that token; workflow-dispatch write permission was not probed. Missing contracted install-canary linux/macos artifacts produced INSTALL_BROKEN secondaries. Observe-only did not open the proposed install_broken issue.

## Dependencies

- **Depends on:** [sase-1n6.7.1.1](sase-1n6.7.1.1.md) ✓ · ⧖ 2026-10-19
- **Depends on:** [sase-1n6.7.1.2](sase-1n6.7.1.2.md) ✓ · ⧖ 2026-10-19
- **Depends on:** [sase-1n6.7.1.3](sase-1n6.7.1.3.md) ✓ · ⧖ 2026-10-19
- **Depends on:** [sase-1n6.7.1.4](sase-1n6.7.1.4.md) ✓ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.7.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.7.1.5.md) | [sase-1n6.7.1.5](sase-1n6.7.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`812cdd9`](https://github.com/sase-org/sase/commit/812cdd9e21ae5bc164d6d149b34ab9866207db03) | feat(release): replace release\_watch with an observe-only steward tick | [sase-1n6.7.1.5](sase-1n6.7.1.5.md) | 2026-10-20 01:29:29 EDT |
