# Bead: sase-ax.4 — Skill template and documentation

[Bead Pages](../README.md) / [sase-ax](README.md) / sase-ax.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ax.4` · **Size:** small
**Created:** 2026-07-29 21:06:47 UTC · **Closed:** 2026-07-29 23:21:57 UTC
**Plan:** [202607/artifact\_read\_cli.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_read_cli.md)

## Description

artifact-skill-docs: extend the sase_artifact_file skill template from create-only to create-and-read and update the CLI, configuration, agent-images, ace, and axe docs to the new command group and record fields.

## Notes

[2026-07-29T23:21:57Z · sase-ax.4] Extended src/sase/xprompts/skills/sase_artifact_file.md from create-only to create-and-read (new frontmatter description; create with the corrected -l/--label and the new ref: output line; list/show/path/open/doctor sections with agent-oriented examples; noted that only create is agent-gated and that sase artifact-file is a compatibility alias). Updated docs/cli.md (sase artifact group rows replacing the single artifact-file create row), docs/configuration.md (renamed the section to sase artifact with a full subcommand/option table, list filter semantics, reference kinds, bare-id sugar, and the path/open/doctor exit-code contract), docs/agent_images.md (canonical spelling, alias mention, ref: output, and the sha256/size_bytes/mime_type fields plus doctor -f/-v and the schema 1..2 reader / preserving writer), and the stale spellings in docs/ace.md, docs/axe.md, docs/notifications.md, plus the bundled-skill row in docs/xprompt.md. Fixed the skill-source phrase test to the new command surface. Verified every documented claim against the landed CLI by smoke test: list (-l/-s 14d/-s 3w/-j), rejected -s bogus, list -p nope exits 2, path on a plans: ref prints the resolved absolute path, path on commit:sase@30e2ed37e exits 2 with a show hint, doctor reports the enrichment gap and exits 0/1 on health. just fmt-md-check, fmt-py-check, lint-keep-sorted, ruff, mypy, pyscripts, changelog, symvision, toobig all pass; full just test is 23911 passed with only a per-run-varying ACE PNG contention flake that passes in isolation (just test-visual: 382 passed). Also repaired a pre-existing phase-3 regression: tests/test_artifact_refs.py still called artifact_refs._resolve_artifact_ref, which sase-ax.3 renamed to the public resolve_artifact_ref (2 deterministic failures on clean HEAD, now green). Did not deploy the regenerated skill (per plan, sase skill init --force happens after landing, not from a phase workspace). Not fixed and pre-existing on clean HEAD: just validate fails on the plans sidecar for 202607/at_reference_completion_menu.md missing its prompt link pair, which belongs to an unrelated epic.

## Dependencies

- **Depends on:** [sase-ax.3](sase-ax.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ax.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ax.4/README.md) | [sase-ax.4](sase-ax.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`c40aa7f`](https://github.com/sase-org/sase/commit/c40aa7f9f5b755223e54469ee31693edc24d46f7) | docs: document the sase artifact read commands | [sase-ax.4](sase-ax.4.md) | 2026-07-29 23:22:55 |
