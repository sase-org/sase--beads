# Bead: sase-su.5 — End-to-end drill and reference documentation

[Bead Pages](../README.md) / [sase-su](README.md) / sase-su.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ce](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ce.md) · **Assignee:** `sase-su.5` · **Size:** small
**Created:** 2026-08-24 10:29:15 EDT · **Closed:** 2026-08-24 15:26:13 EDT
**Plan:** [202608/provider\_drain.md](https://github.com/sase-org/sase--plans/blob/main/202608/provider_drain.md)

## Description

soak: prove the whole loop through the fakey provider end to end and document draining in the LLM provider reference.

## Notes

[2026-08-24T19:26:13Z · sase-su.5--3] Verified: docs/ace.md and docs/llms.md updated with drain documentation; tests/fakey/test_provider_drain_e2e.py added and both tests pass (flag-on relaunch, flag-off no-op). just check-full stopped at pre-existing 'SASE validation / init memory --check' gate (chezmoi memory drift, confirmed present on clean git-stashed tree, unrelated to this phase). Full just test run: 3 failed / 36741 passed / 13 skipped -- all 3 failures pre-existing on clean stashed tree and unrelated to this phase's docs-only + new-test changes: test_default_config_matches_public_schema (finalizers.instances.commit.refusal schema drift) and two tests/completion/test_snapshot.py CLI-completion-drift failures (confirmed via git stash -u, since this phase touches no CLI/argparse code). No --epic-symbol entries for this bead.

## Dependencies

- **Depends on:** [sase-su.3](sase-su.3.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-su.4](sase-su.4.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-su.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-su.5.md) | [sase-su.5](sase-su.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ad9ed74`](https://github.com/sase-org/sase/commit/ad9ed74aff241bc7101a8014210b5acb2e8cefde) | docs(ace,llms): document provider drain end-to-end and add fakey e2e drain tests | [sase-su.5](sase-su.5.md) | 2026-08-24 15:27:05 EDT |
