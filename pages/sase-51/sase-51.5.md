# Bead: sase-51.5 — Phase 5: Maintained Local Configuration Sweep

[Bead Pages](../README.md) / [sase-51](README.md) / sase-51.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-51.5`
**Created:** 2026-06-20 17:53:57 UTC · **Closed:** 2026-06-20 20:47:22 UTC
**Plan:** [202606/linked\_repos\_rename\_codex.md](https://github.com/sase-org/sase--plans/blob/main/202606/linked_repos_rename_codex.md)

## Notes

COMMIT: 83cdf590d

[2026-07-27T21:36:34Z · sase-a1.land] [2026-06-20T20:43:22Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 5 complete — maintained local config sweep (sibling_repos -> linked_repos).

Migrated (in scope):
- ~/.local/share/chezmoi/home/dot_config/sase/sase.yml (chezmoi SOURCE): key renamed; entry preserved exactly (name: chezmoi, workspace.strategy: none).
- ~/.config/sase/sase.yml (generated): regenerated via 'chezmoi apply', not edited directly.

Verified: rg '^sibling_repos:|sibling_repos:' over both maintained config sources is clean; 'sase config show' resolves linked_repos with the chezmoi entry and emits NO deprecation warning.

Intentionally deferred / left for later:
- bob-cli sase.yml -> Phase 6 (sase-51.6).
- Numbered workspace clones (sase_0/sase_11..14, zorg_100): ephemeral/stale worktrees, deliberately not swept per design.
- Chezmoi SOURCE change applied but NOT committed (Phase 5 scope = update+apply; commit workflow reserved for Phase 6).
- Unrelated 'sibling' usages left intact: TUI start_sibling_mode keymap; *_sibling_commit_stop_hook bash tools; zorg/sase.yml has no sibling_repos key.

[2026-07-27T21:36:37Z · sase-a1.land] [2026-06-20T20:48:22Z · bryanbugyi34@gmail.com] (restored 2026-07-27) COMMIT: 75284a1cd

## Dependencies

- **Depends on:** [sase-51.4](sase-51.4.md) ✓
- **Blocks:** [sase-51.6](sase-51.6.md) ✓
