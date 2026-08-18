# Bead: sase-p3.3 — Required plugin prefix for every \`use:\` field

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.3` · **Size:** medium
**Created:** 2026-08-17 18:50:04 EDT · **Closed:** 2026-08-17 21:15:38 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

use-prefix: require `<plugin>@<id>` on artifact-ref and file-hook `use:` values, migrate every in-tree and chezmoi-managed config, and report legacy bare values as hard errors.

## Notes

[2026-08-18T00:34:49Z · sase-p3.3] Implemented required <plugin>@<id> parser, wired it into sidecar refs and file hooks, added config.file_hooks doctor ERROR that fails sase validate, migrated in-tree configs/docs/schema/scaffolder, and updated the Artifact Reference glossary. Chezmoi file_hooks use: prefix is already on origin/master (3c1d88df) and deployed. Installed sase-research-artifacts editable --no-deps in this workspace venv so the live hook resolves. just check lint+validate passed; scoped tests escalated (root-conftest + src-data-asset) and will be verified via just check-full.

[2026-08-18T00:35:16Z · sase-p3.3] PROPOSED FOLLOW-UP: Plugin-less ephemeral workspaces fail sase validate after this phase because the chezmoi-managed file_hooks use: is now a hard ERROR — sase-p3.4 plugins.required will still fail validate; consider documenting the local uv pip install --no-deps -e of sase-research-artifacts or a later workspace-dev exception.

[2026-08-18T01:15:38Z · sase-p3.3--3] Required <plugin>@<id> parser, sidecar/file-hook wiring with provenance match and unambiguous replacement messages, schema pattern, in-tree + chezmoi migrations, glossary, and config.file_hooks doctor ERROR that fails sase validate. Chezmoi prefix is on origin/master (3c1d88df) and deployed; sase-research-artifacts installed editable --no-deps in this workspace venv. Verified: epic-symbols clean; .venv sase doctor -C config.file_hooks OK; .venv sase validate OK including doctor config.file_hooks; just check lint/validate/committed-plans green; just check-full pytest 32621 passed / 12 skipped / 0 failed. check-full exited 1 only on tools/check_test_cost_budgets (collection_cpu, peak RSS, ACE/Textual/parser/subprocess causes), the standing master-red gate already tracked on sase-j0 — not caused by this phase.

[2026-08-18T01:17:51Z · sase-p3.3--3] Required <plugin>@<id> parser, sidecar/file-hook wiring with provenance match and unambiguous replacement messages, schema pattern, in-tree + chezmoi migrations, glossary, and config.file_hooks doctor ERROR that fails sase validate. Chezmoi prefix is on origin/master (3c1d88df) and deployed; sase-research-artifacts installed editable --no-deps in this workspace venv. Verified: epic-symbols clean; .venv sase doctor -C config.file_hooks OK; .venv sase validate OK including doctor config.file_hooks; just check lint/validate/committed-plans green; just check-full pytest 32621 passed / 12 skipped / 0 failed. check-full exited 1 only on tools/check_test_cost_budgets (collection_cpu, peak RSS, ACE/Textual/parser/subprocess causes), the standing master-red gate already tracked on sase-j0 — not caused by this phase.

## Dependencies

- **Blocks:** [sase-p3.4](sase-p3.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p3.3.md) | [sase-p3.3](sase-p3.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`54da09b`](https://github.com/sase-org/sase/commit/54da09ba5c0aeca06d27ff6b7c8bbfd75c7925ba) | feat(config)!: require plugin prefix on every use: field | [sase-p3.3](sase-p3.3.md) | 2026-08-17 21:18:39 EDT |
