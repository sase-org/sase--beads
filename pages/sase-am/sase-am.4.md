# Bead: sase-am.4 — Derive the CI sidecar environment from configuration

[Bead Pages](../README.md) / [sase-am](README.md) / sase-am.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-am.4` · **Size:** small
**Created:** 2026-07-28 22:06:02 UTC · **Closed:** 2026-07-28 23:23:09 UTC
**Plan:** [202607/ci\_flakiness\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/ci_flakiness_redesign.md)

## Description

config-driven-sidecars: replace the hand-written sidecar checkouts and sdd-store heredoc with a tools/ci_bootstrap_sidecars script generated from sase/sase.yml, with unit tests locking the store shape.

## Notes

[2026-07-28T23:23:09Z · sase-am.4] Added tools/ci_bootstrap_sidecars, which derives the CI sidecar environment from sase/sase.yml: it clones each configured store-representable sidecar (plans, research, beads) to sase/repos/<role> with bounded retries and writes .sase/sdd-store.json from the same config. The hidden 'agents' sidecar and any non-store roles are skipped with a logged reason; disabled entries are honored; clone failures raise an actionable message naming the repo, and the token never lands in the clone's remote or in error text. ci.yml's lint job now has one 'Bootstrap SDD sidecars' step (after setup-sase, so PyYAML is available) replacing three hand-written checkout steps and the sdd-store heredoc; the plans checkout still lands at sase/repos/plans for just validate-committed-plans. Verified: 16 new unit tests in tests/test_ci_bootstrap_sidecars_tool.py lock config parsing, repo-slug derivation, skip/disable rules, the exact store payload, the retry+token-scrubbing clone path, and dry-run behavior, including a test that feeds the generated record to sase.sdd.store.normalize_sdd_store_record. That check caught a real latent bug: the old heredoc wrote schema_version 2 with a beads sidecar, which sase rejects as a foreign record ('beads sidecars require schema_version >= 3'); the script now emits 3 when beads is present and 2 otherwise. Updated tests/test_justfile_lint.py::test_ci_lint_job_derives_sdd_sidecars_from_config to assert the heredoc and hand-written checkouts are gone. Ran the script end-to-end against real GitHub into a temp workspace: all three sidecars cloned, origin rewritten to the token-free URL, store written. just fmt-py-check/ruff/mypy/pyscripts/symvision/toobig all pass; full just test passes apart from pre-existing visual/TUI snapshot flakes that pass in isolation. just validate still fails on pre-existing 'init skills --check' chezmoi drift, which reproduces on a clean tree and is unrelated to this phase.

## Dependencies

- **Depends on:** [sase-am.3](sase-am.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-am.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-am.4/README.md) | [sase-am.4](sase-am.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`b5efaf7`](https://github.com/sase-org/sase/commit/b5efaf7e7929d41e94c53fc01d1e2e143cc011f9) | ci: derive sidecar checkouts from sase.yml | [sase-am.4](sase-am.4.md) | 2026-07-28 23:24:57 |
