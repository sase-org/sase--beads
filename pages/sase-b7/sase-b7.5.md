# Bead: sase-b7.5 — Docs, skill, and configuration reference

[Bead Pages](../README.md) / [sase-b7](README.md) / sase-b7.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b7.5` · **Size:** small
**Created:** 2026-07-30 12:53:42 UTC · **Closed:** 2026-07-30 14:31:58 UTC
**Plan:** [202607/vcs\_backed\_artifact\_capture.md](https://github.com/sase-org/sase--plans/blob/main/202607/vcs_backed_artifact_capture.md)

## Description

docs-and-skill: document VCS-backed artifact files in the `sase_artifact_file` skill source, the artifact docs, and the new configuration block, and regenerate the deployed skill.

## Notes

[2026-07-30T14:31:58Z · sase-b7.5] Documented VCS-backed artifact files: new 'VCS-Backed Artifact Files' section in docs/agent_images.md (decision matrix + reason slugs, the three invariants, the vcs_repo/vcs_sha/vcs_relpath record fields, the ~/.sase/artifacts/vcs-cache/ materialization cache and lookup order, and a 5-step unresolvable-reference diagnosis runbook); new 'artifacts' section + ToC entry in docs/configuration.md for the artifacts.capture block (max_stored_per_agent, max_history_scan, fail-open reads, cap_fired); updated docs/cli.md rows for 'artifact doctor' and 'artifact path'; new 'VCS-Backed Artifacts' + doctor-counts guidance in the sase_artifact_file skill source, with 'create' called out as unaffected; and a scannable 'artifact doctor' description naming the three new counts. Verified: just fmt/lint clean, full suite 24248 passed / 7 skipped, 'sase artifact doctor -h' renders correctly, and 'sase skill init --diff' shows the intended +27-line render for all five providers. 'sase validate' still reports 'init skills --check' pending: per the generated_skills memory the chezmoi deploy is refused from an uncommitted tree, so 'sase skill init --force' must run after this change is committed and merged.

## Dependencies

- **Depends on:** [sase-b7.4](sase-b7.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b7.5/README.md) | [sase-b7.5](sase-b7.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`658e576`](https://github.com/sase-org/sase/commit/658e57696301cdab8119f77ef0ec1cd4fda16037) | docs(artifacts): document VCS-backed artifact files | [sase-b7.5](sase-b7.5.md) | 2026-07-30 14:33:01 |
