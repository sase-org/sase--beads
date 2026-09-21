# Bead: sase-11y.10.1 — Sunset legacy supervision paths, docs, and glossary

[Bead Pages](../README.md) / [sase-11y.10](sase-11y.10.md) / sase-11y.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.md) · **Assignee:** `sase-11y.10.1.land`
**Created:** 2026-09-20 13:56:11 EDT · **Closed:** 2026-09-21 06:37:37 EDT
**Plan:** [202609/service\_host\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/service_host_sunset.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-152][2] | The service-host sunset epic whose plan never listed this sixth direct-start path |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-152/README.md

<!-- sase:links:end -->

## Description

The sase service host is SASE's only supervisor of the scheduler: the service_host beta flag and every Off branch are gone, the ensure watchdog, the TUI direct-start path, the axe-start scope wrapper, the sase-update direct restart, and the Telegram rearm branch are deleted, `sase axe` is a documented alias of `sase scheduler`, the TUI tab id is `services`, and the docs and glossary describe the shipped system.

## Notes

[2026-09-21T07:56:26Z · sase-11y.10.1.land] LANDING PAUSED (sase-11y.10.1.land, 2026-09-21, master 3a08b8681): remaining epic work has been planned as a child epic. The child epic's land agent should resume this landing.

VERIFIED against source and commits. All six phases shipped:
- telegram-rearm: sase-telegram f99521c is on origin/master, and the installed editable checkout on athena already has it (_service_host_owns_receiver no longer reads the flag).
- flag-removal (ef9900990): no service_host / _service_host_enabled reference remains in src or tests. Flag bead sase-12m is closed.
- axe-cli: child epic sase-11y.10.1.3.1 is closed (commits 080693746, d65316234, c833ff3e5, 0508f288f, b87c8e3ee, 103db4bfa). `sase axe ensure` is rejected, and `sase axe start|stop|restart|status` delegate to handle_scheduler_command.
- tab-id (b27b02323): TabName is artifacts/agents/services, and `axe` is in LEGACY_SERVICES_TABS.
- docs (0ea0f5a7b) and glossary (3016e92d2) both landed.
- `sase bead epic-symbols sase-11y.10.1` reports none.

INTEGRATION: reviewed the 34 non-epic commits since ef9900990. 300041d94's duplicate TabName literal already says services. LEGACY_SYSTEMD_UNITS survived d710b0b80's platform split with the sase-axe-ensure units. Nothing else touches the retired surfaces.

REMAINING EPIC WORK, now in the child plan:
(1) chat_install still starts the orchestrator directly (sase-152). This contradicts the goal of "only supervisor". It is also the last writer of desired_state.json.
(2) The axe.health doctor check and the status collector still read desired_state.json. The scheduler CLI no longer writes that file, so a stale `running` marker gives false warnings.
(3) `sase scheduler start|restart` and the `sase axe` aliases accept -A/-H/-q/-z, and `restart` accepts -j. The handler ignores all of them; the options became dead in flag-removal.
(4) AxeCollectedData.axe_status/axe_metrics are always None (.2 follow-up #2). set_service_health(None) has no production caller (.2 #4).
(5) The docs still describe the service_host flag (init/architecture/getting_started; .2 #3, .5 #2), the deleted whole-system `sase axe status`, the heartbeat-verified restart, and the "AXE tab" across about 20 files.

FOLLOW-UP OUTCOMES:
- .1 #1 and .2 #1 (telegram install/release): athena is verified. The sase-telegram release PR #31 (0.4.20, which contains f99521c) is still open. Merging and deploying it to apollo is the owner's call, so it is left undone.
- .1 #2 telegram digest flake: filed as sase-156.
- .2 #2, .2 #3, .2 #4, .5 #2: epic work, moved to the child plan.
- .2 #5: pre-existing failures. The capacity, lazy-tier2 and epic-panel tests now pass. The 26 symvision findings were fixed by 47e281b7a. The remaining symvision failures (bead_touch_glyph, ordered_bead_verb_chips) belong to sase-14j.
- .2 #7 and .4 #2 link-rail pixel-identity flake: filed as sase-155.
- .4 #1 usage_config: still failing. +1 on sase-14u (sase-14v looks like the same report).
- .4 #2 shard drift: still failing. +1 on sase-14r.
- .5 #1 and .6 #1 AxeDesiredState/lifecycle_journal symvision: fixed in 103db4bfa.
- .5 #3: the schema pin and dev-extension tests now pass.
- Child epic follow-ups sase-152/153/154 were filed by its land agent. sase-152 is folded into the child plan; sase-153 and sase-154 stay separate.

[2026-09-21T10:37:37Z · sase-11y.10.1.7.land] LANDING RESUMED AND COMPLETED by sase-11y.10.1.7.land (2026-09-21, master d9ae431dc plus this turn's landing fixes).

RECHECKED: the previous landing note (master 3a08b8681) listed five remaining items: (1) chat_install direct start, (2) the desired_state.json readers, (3) the ignored scheduler start/restart options, (4) the dead TUI state, (5) the stale docs. All five were child epic sase-11y.10.1.7's phases, and all are closed and verified in source (see that bead's close note). sase-152 is closed. Every descendant is closed: phases .1-.6, nested epic .3.1, and child epic .7. The plan 202609/service_host_sunset.md validates (0 warnings). epic-symbols: none for sase-11y.10.1.

GOAL RE-VERIFIED in this workspace's source:
- No service_host flag or start_axe_daemon references remain in src.
- `sase axe ensure` is rejected by argparse.
- The sase-axe-ensure units survive only as LEGACY_SYSTEMD_UNITS cleanup targets.
- `sase axe start|stop|restart|status` alias `sase scheduler` with the service-path option surface.
- The tab id is services.
- Glossary strands sase-scheduler, sase-service, service-proc, and proc exist.

POST-CHILD DRIFT: the only non-epic commit since the child started is 184241fa6 (tilde neighbor keymap), unrelated. The landing fixed a regression from this epic's lineage: d65316234 (sase-11y.10.1.3.1.3) made sase.main.update_types import sase.service.actions at runtime. That pulled service.control/status into TUI startup and broke test_app_import_budget's deferred_modules guard. The import is now TYPE_CHECKING-only; the one-module count overage left is sase-13p's (+1 recorded).

STILL OWNER-GATED from the earlier landing: merging sase-telegram release PR #31 (0.4.20) and deploying it to apollo.

NOTE: athena's installed sase is still 0.17.1 and still accepts `sase axe ensure`. The installed tool picks up this epic's changes only after the next `sase update`.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.land.md) | [sase-11y.10.1](sase-11y.10.1.md) | 0 |
