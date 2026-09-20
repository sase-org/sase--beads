# Bead: sase-11y.10.1.1 — Retire the Telegram receiver rearm branch

[Bead Pages](../README.md) / [sase-11y.10.1](sase-11y.10.1.md) / sase-11y.10.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.md) · **Assignee:** `sase-11y.10.1.1` · **Size:** small
**Created:** 2026-09-20 13:56:12 EDT · **Closed:** 2026-09-20 14:19:05 EDT
**Plan:** [202609/service\_host\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset.md)

## Description

telegram-rearm: in the sase-telegram repo, stop `ensure_receiver_running` from consulting the `service_host` flag so removing that flag from sase cannot silently re-arm a second getUpdates consumer, and delete the rearm branch's flag-off tests.

## Notes

[2026-09-20T18:18:01Z · sase-11y.10.1.1] PROPOSED FOLLOW-UP: sase-telegram needs a release bump/install before sase-11y.10.1.2 (flag-removal) removes FeatureFlag.service_host — the installed plugin must contain this receiver.py change or athena runs two getUpdates consumers.

[2026-09-20T18:18:33Z · sase-11y.10.1.1] PROPOSED FOLLOW-UP: sase-telegram tests/test_receiver_runtime.py generation-digest tests (test_host_plugin_and_native_changes_each_new_generation / test_executable_replacement_changes_generation) flake on unchanged tree — equal digests after replacing files, likely mtime granularity.

[2026-09-20T18:19:05Z · sase-11y.10.1.1] In sase-telegram: _service_host_owns_receiver() no longer reads FeatureFlag.service_host (keeps the load_service_config check + except fallback); removed override_flags(service_host=True) from tests/test_receiver.py; added autouse conftest fixture stubbing load_service_config so tests don't depend on host service config (this also fixed 15 pre-existing host-dependent failures). Verified ruff, ruff format, mypy clean; pytest 654 passed, 1 unrelated flaky test_receiver_runtime digest test (fails on unchanged tree too). Not committed/released; see follow-up notes.

## Dependencies

- **Blocks:** [sase-11y.10.1.2](sase-11y.10.1.2.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.1/README.md) | [sase-11y.10.1.1](sase-11y.10.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-telegram | [`sase-telegram@f99521c`](https://github.com/sase-org/sase-telegram/commit/f99521c8e285bf16133db2ca67cbed0ad2dd52c6) | fix(receiver): stop consulting the service\_host flag in the rearm check | [sase-11y.10.1.1](sase-11y.10.1.1.md) | 2026-09-20 14:20:19 EDT |
