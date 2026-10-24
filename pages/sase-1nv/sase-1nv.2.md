# Bead: sase-1nv.2 — Apollo GitHub pushes authenticate as bbugyi200

[Bead Pages](../README.md) / [sase-1nv](README.md) / sase-1nv.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13m](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13m.md) · **Assignee:** `sase-1nv.2` · **Size:** small
**Created:** 2026-10-24 07:01:33 EDT
**Plan:** [202610/unblock\_sase\_1nf.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_sase_1nf.md)

## Description

ssh-identity: change the chezmoi-managed tailnet SSH config, get it applied on athena and apollo through a gate, verify the GitHub identity, and close sase-1ni.

## Notes

[2026-10-24T11:12:47Z · sase-1nv.2] Pre-apply identity baseline (Athena 2026-10-24): ssh -G github.com => user git, hostname ssh.github.com, identitiesonly yes, identityfile ~/.ssh/id_sase_service, forwardagent no. Apollo (forwarded agent): identitiesonly no, greets bobs-org/bob. Apollo hostname chezmoi.hostname=apollo, has ~/.ssh/id_rsa, no id_sase_service.

[2026-10-24T11:32:04Z · sase-1nv.2] Implementation complete in chezmoi: Apollo-only github.com template selects User git, id_rsa and IdentitiesOnly yes; include-hook hash follows renamed template. Four bashunit regression tests (20 assertions) pass; the Apollo test fails on HEAD before the fix. Full chezmoi just check passed via sase tool run -- just check, ToolRun b5cae73a3aa533bb7d390d3797057b61 (66.979s). No phase epic symbols. Live forwarded zsh -lc baseline greets bobs-org/bob; explicit candidate identity greets bbugyi200, SASE agents push dry-run exits 0 (up-to-date), bob-cli exits 1 (non-fast-forward, authenticated). Apollo repo lookups require -p gh_sase-org__sase / gh_bobs-org__bob-cli and -w 0. Preparing a durable non-turn approval gate so the host finalizer can first commit source; its reviewed command performs both chezmoi updates, default-config identity/push verification, epic-symbol check, and closes only this phase. Per the current user instruction, sase-1ni remains for the land agent. No memory changes or publication retries.

## Dependencies

- **Blocks:** [sase-1nv.5](sase-1nv.5.md) ◐ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.2/README.md) | [sase-1nv.2](sase-1nv.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@1da17c9`](https://github.com/bbugyi200/dotfiles/commit/1da17c915d8e1113f12f49801c4f10e86b5c9589) | fix(ssh): pin Apollo GitHub authentication to its local identity | [sase-1nv.2](sase-1nv.2.md) | 2026-10-24 07:33:13 EDT |
