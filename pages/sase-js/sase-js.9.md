# Bead: sase-js.9 — Adoption, glossary, and documentation

[Bead Pages](../README.md) / [sase-js](README.md) / sase-js.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.y2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.y2/README.md) · **Assignee:** `sase-js.9` · **Size:** medium
**Created:** 2026-08-11 13:24:06 EDT · **Closed:** 2026-08-12 10:10:12 EDT
**Plan:** [202608/artifact\_ref\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_contract.md)

## Description

adopt: link and install the research plugin, move Bryan's config to `use:` plus overrides, add the `@file` roots for `~/bob`, add the Artifact Reference glossary term, and rewrite the affected documentation end to end.

## Notes

[2026-08-12T14:08:24Z · sase-js.9] PROPOSED FOLLOW-UP: plans sidecar repo-open rebase conflict — `sase repo open plans` in workspace 14 fails applying commit b10820e6 ("Add SDD files for split_patch_handler") with a non-bead conflict in `202608/split_patch_handler.md`, though the plans worktree is clean after the failed attempt.

[2026-08-12T14:08:34Z · sase-js.9] PROPOSED FOLLOW-UP: core dependency floor needs ratcheting — `just check` passes, but its core-floor probe reports `sase-core-rs==0.24.0` is missing artifact-reference capabilities now present in published core releases (notably `artifact_object_relpath`/`artifact_object_prompt_link` from v0.26.0).

[2026-08-12T14:10:12Z · sase-js.9] Verified project config links `sase-research` and sets research sidecar `ref.use: research`; editable plugin is installed and visible in `sase version`/`sase plugin list`; `sase doctor -C config.repos` and `sase doctor -C config.artifact_refs` pass; all `research*` xprompts resolve from `plugin:sase_research`; `research-highlights` file-hook resolves from the user `use:` override with plugin filters; live and chezmoi source config include the `~/bob` `@file` root and old live research swarm files are removed; `sase memory init --no-commit` passes; `just install` and `just check` pass after Markdown formatting.

[2026-08-12T14:11:40Z · sase-js.9] Verified adoption docs/config/plugin migration with sase doctor config.repos, sase doctor config.artifact_refs, plugin xprompt/hook smoke checks, just install, just check, and memory init --no-commit.

## Dependencies

- **Depends on:** [sase-js.6](sase-js.6.md) ✓ · ⧖ 2026-08-11
- **Depends on:** [sase-js.7](sase-js.7.md) ✓ · ⧖ 2026-08-11
- **Depends on:** [sase-js.8](sase-js.8.md) ✓ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-js.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-js.9/README.md) | [sase-js.9](sase-js.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`56d6bd7`](https://github.com/sase-org/sase/commit/56d6bd772dfc16e979f44cdd737251e06eab83b8) | docs: adopt artifact reference provider docs | [sase-js.9](sase-js.9.md) | 2026-08-12 10:14:48 EDT |
