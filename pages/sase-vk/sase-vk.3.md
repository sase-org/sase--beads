# Bead: sase-vk.3 — Documentation, memory notes, and regenerated artifacts

[Bead Pages](../README.md) / [sase-vk](README.md) / sase-vk.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0g6.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0g6.w0.md) · **Assignee:** `sase-vk.3` · **Size:** medium
**Created:** 2026-08-29 11:29:35 EDT · **Closed:** 2026-08-30 06:51:27 EDT
**Plan:** [202608/memory\_webs\_agents\_section.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_webs_agents_section.md)

## Description

docs: rewrite the tier vocabulary in docs/, the generated sase.md and README memory templates, the affected glossary strands, and a new decision record, then regenerate and commit every generated artifact here and in the chezmoi linked repo.

## Notes

[2026-08-30T10:30:16Z · sase-vk.3] PROPOSED FOLLOW-UP: actstat and bob-cli (other enabled SASE projects) have their own generated AGENTS.md/CLAUDE.md that still use the old Tier 1/Tier 2 memory vocabulary and will stay drifted until `sase memory init` runs in each of them. Not this repo and not a linked repo, so out of scope here per the epic plan.

[2026-08-30T10:30:38Z · sase-vk.3] PROPOSED FOLLOW-UP: src/sase/memory/assets/memory-directory-map.png (and its committed copies) is now stale relative to its updated src/sase/memory/assets/memory-directory-map.prompt.md wording (Tier 1/Tier 2 region labels became "core memory lane"/"reference memory lane"). Regenerating the PNG was explicitly out of scope for this phase; needs a follow-up to regenerate and re-propagate the asset.

[2026-08-30T10:31:00Z · sase-vk.3] PROPOSED FOLLOW-UP: discovered flaky test tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation — failed once under `just check`'s parallel test-scoped run, passed cleanly when rerun in isolation. Unrelated to this docs/memory-vocabulary phase (I did not touch TUI agents-panel fold code).

[2026-08-30T10:31:26Z · sase-vk.3] PROPOSED FOLLOW-UP: `sase memory init`'s home-root target resolution (use_chezmoi: true + repos.linked.chezmoi.path) writes directly to and auto-commits in the live ~/.local/share/chezmoi on the host, bypassing the private per-workspace clone that `sase repo open chezmoi` returns for an ephemeral sase_<N> workspace. This phase's home-doc regeneration therefore landed in the real host chezmoi checkout (commit f429de9b there, matching prior "chore: initialize sase memory" commits) rather than through the /sase_repo-isolated checkout. I also hand-edited the stale chezmoi/sase/memory/README.md Tier-vocabulary lines directly in that live checkout (left uncommitted, since a phase-worker agent should not commit to the user's personal dotfiles repo unprompted) rather than in the /sase_repo clone, to keep it consistent with where sase memory init actually wrote. Worth a bug bead: sase memory init should probably honor an opened workspace-private linked-repo clone for the chezmoi home target instead of reaching directly for the configured live path.

[2026-08-30T10:51:27Z · sase-vk.3--1] just check-full passed clean (only known test-cost advisories, no new failures); no --epic-symbol entries pointed at this phase

## Dependencies

- **Depends on:** [sase-vk.2](sase-vk.2.md) ✓ · ⧖ 2026-08-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vk.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-vk.3.md) | [sase-vk.3](sase-vk.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0860fcb`](https://github.com/sase-org/sase/commit/0860fcb200f35e3ec99cdd50cc9f54ad82ea857b) | docs(memory): rewrite Tier-1/Tier-2 memory vocabulary across docs and templates | [sase-vk.3](sase-vk.3.md) | 2026-08-30 06:52:22 EDT |
