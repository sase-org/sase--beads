# Bead: sase-gu.1 — Accept both shapes in the schema, parser, and doctor

[Bead Pages](../README.md) / [sase-gu](README.md) / sase-gu.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.um](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.um/README.md) · **Assignee:** `sase-gu.1` · **Size:** medium
**Created:** 2026-08-07 09:34:24 EDT · **Closed:** 2026-08-07 09:54:52 EDT
**Plan:** [202608/split\_sidecar\_config.md](https://github.com/sase-org/sase--plans/blob/main/202608/split_sidecar_config.md)

## Description

dual_read: teach the JSON schema, the sidecar config parser, the memory-generation validator, and the CI bootstrap tool to read the new builtin/custom mapping while still accepting the legacy list, and add a doctor check that reports the migration and mis-bucketed roles.

## Notes

[2026-08-07T13:53:37Z · sase-gu.1] PROPOSED FOLLOW-UP: `sase validate` fails on a clean master tree — `init memory --check` wants to update ~/.local/share/chezmoi/home/sase/memory/README.md (+2 −2); pre-existing and unrelated to epic sase-gu.

[2026-08-07T13:54:06Z · sase-gu.1] PROPOSED FOLLOW-UP: flaky test — tests/test_install_coverage_contexts_tool.py::test_installing_prunes_the_cache_to_the_keep_limit fails intermittently under the parallel `just test-scoped` lane but passes in isolation; likely shared coverage-context cache state across xdist workers.

[2026-08-07T13:54:52Z · sase-gu.1] dual_read complete. Schema: added sidecarRepoEntry (sidecarRepo minus name) and made repos.sidecar a oneOf of the new {builtin,custom} role-keyed object (propertyNames enforces reserved/non-reserved bucketing) and the deprecated list; default is now {} and default_config.yml ships sidecar: {builtin: {}, custom: {}}. Parser: new _sidecar_config_entries in _linked_repo_config.py reads both shapes, emitting builtin roles in canonical plans/beads/agents order then custom roles in configured order, custom winning a role declared in both; the {role,slug} token merge is retained for the legacy list. Raw readers updated: init_memory/config.py _sidecar_repos_raw now yields (label, role, entry) triples so mapping errors read repos.sidecar.custom['research'] while the list form keeps repos.sidecar[0] ('research'); tools/ci_bootstrap_sidecars plan_sidecars accepts both shapes. New doctor check config.repos (src/sase/doctor/checks_config_repos.py, registered in checks_config.py) reports the legacy list with each entry's target bucket, mis-bucketed/duplicated roles, leftover name: keys, non-mapping buckets/entries, and enabled lazy custom entries with no description. Re-grepped src/ and tools/ for REPOS_SIDECAR_CONFIG_KEY / repos.sidecar: the only remaining raw reader is _repo_init_config.explicit_sidecar_config_update, which migrate_configs owns. Tests added for both shapes across schema, parser ordering/layer-merge, doctor (one case per problem class), memory generation, and the CI tool; test_config_schema_rejects_invalid_sidecar_controls updated for the oneOf error shape. Verified: just install, just lint (ruff/mypy/symvision/toobig all clean), just test-scoped (26760 passed; one unrelated flake noted), sase doctor -C config.repos, and sase repo list showing unchanged sidecar rows. Two PROPOSED FOLLOW-UP notes recorded for the pre-existing sase validate memory-README failure and the flaky coverage-context test.

[2026-08-07T13:55:49Z · sase-gu.1] Dual-read sidecar config: schema oneOf (role-keyed builtin/custom map + deprecated legacy array), parser _sidecar_config_entries, init_memory and ci_bootstrap_sidecars raw readers, new config.repos doctor check. Verified with just install, just lint (ruff/mypy/symvision/toobig clean), just test-scoped (26760 passed), sase doctor -C config.repos, and sase repo list.

## Dependencies

- **Blocks:** [sase-gu.2](sase-gu.2.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gu.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gu.1/README.md) | [sase-gu.1](sase-gu.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`50bed7f`](https://github.com/sase-org/sase/commit/50bed7f99c48d78515bbc48f74c83924380982f5) | feat(config): accept role-keyed sidecar repo config alongside the legacy list | [sase-gu.1](sase-gu.1.md) | 2026-08-07 09:56:38 EDT |
