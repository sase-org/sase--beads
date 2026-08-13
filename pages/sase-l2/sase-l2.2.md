# Bead: sase-l2.2 — Rewire SASE to the renamed linked repository and plugin

[Bead Pages](../README.md) / [sase-l2](README.md) / sase-l2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zt](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zt.md) · **Assignee:** `sase-l2.2` · **Size:** small
**Created:** 2026-08-13 14:12:14 EDT · **Closed:** 2026-08-13 14:50:44 EDT
**Plan:** [202608/research\_artifacts\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202608/research_artifacts_rename.md)

## Description

host-wiring: update SASE's linked-repository configuration, provider provenance fixtures, artifact-reference documentation, and generated memory outputs to use the new identity without the obsolete sidecar-name warning.

## Notes

[2026-08-13T18:48:58Z · sase-l2.2] PROPOSED FOLLOW-UP: Bump the declared sase-core-rs floor — just check reports core-floor-probe stale_actionable because 0.26.6 lacks apply_snippet_session_event, which first appears in released v0.26.10.

[2026-08-13T18:50:09Z · sase-l2.2] PROPOSED FOLLOW-UP: Make `sase repo list` honor workspace-local uncommitted repo config for pre-land verification — it says it defaults to the current checkout, but inventory rows are built from the registered primary checkout, so this phase still showed the old linked row until the config lands there.

[2026-08-13T18:50:44Z · sase-l2.2] Verified just install; sase memory init --no-commit and --check; just check; exact stale identity and obsolete warning rg audits; workspace-local repo config resolves only sase-research-artifacts plus the research sidecar; and sase repo open resolves the renamed checkout with origin git@github.com:sase-org/sase-research-artifacts.git. Recorded proposed follow-ups for the unrelated core floor advisory and repo-list pre-land inventory behavior.

[2026-08-13T18:52:19Z · sase-l2.2] Verified just install, sase memory init --no-commit, sase memory init --check, just check, stale identifier audits, and linked repo resolution for sase-research-artifacts.

## Dependencies

- **Depends on:** [sase-l2.1](sase-l2.1.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l2.3](sase-l2.3.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l2.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l2.2/README.md) | [sase-l2.2](sase-l2.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`04cd969`](https://github.com/sase-org/sase/commit/04cd969719ab3c2237a122efe1289b8016270109) | chore: rename research artifact plugin wiring | [sase-l2.2](sase-l2.2.md) | 2026-08-13 14:53:19 EDT |
