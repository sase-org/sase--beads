# Bead: sase-1nf.3 — bob-cli tests stop leaking read-only vault fixtures

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.3` · **Size:** small
**Created:** 2026-10-20 13:36:14 EDT · **Closed:** 2026-10-20 13:51:42 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

bobcli-vault: in the bob-cli repo, restore write permission after the read-only completion test locks its fixture vault, and make the test TempDir removal repair owner write permission inside its own tree.

## Notes

[2026-10-20T17:51:42Z · sase-1nf.3] bob-cli lock_tree now returns a TreeLock whose Drop restores 0755/0644; TempDir drop repairs owner u+wx on real directories (symlink_metadata + O_NOFOLLOW fchmod) and retries remove_dir_all once. Verified: tempdir_drop_removes_write_locked_tree, tempdir_drop_does_not_chmod_symlink_target, locked_vault_fixture_is_removed_after_guard_and_tempdir_drop, completion_is_read_only; sase tool run -- just check 5de423b2a11095b00b842ce070fa7dcb exited 0; epic-symbols clean.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.3/README.md) | [sase-1nf.3](sase-1nf.3.md) | 0 |
