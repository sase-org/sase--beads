# Bead: sase-1nv.2 — Apollo GitHub pushes authenticate as bbugyi200

[Bead Pages](../README.md) / [sase-1nv](README.md) / sase-1nv.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13m](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13m.md) · **Assignee:** `sase-1nv.2` · **Size:** small
**Created:** 2026-10-24 07:01:33 EDT · **Closed:** 2026-10-24 07:34:15 EDT
**Plan:** [202610/unblock\_sase\_1nf.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_sase_1nf.md)

## Description

ssh-identity: change the chezmoi-managed tailnet SSH config, get it applied on athena and apollo through a gate, verify the GitHub identity, and close sase-1ni.

## Notes

[2026-10-24T11:12:47Z · sase-1nv.2] Pre-apply identity baseline (Athena 2026-10-24): ssh -G github.com => user git, hostname ssh.github.com, identitiesonly yes, identityfile ~/.ssh/id_sase_service, forwardagent no. Apollo (forwarded agent): identitiesonly no, greets bobs-org/bob. Apollo hostname chezmoi.hostname=apollo, has ~/.ssh/id_rsa, no id_sase_service.

[2026-10-24T11:32:04Z · sase-1nv.2] Implementation complete in chezmoi: Apollo-only github.com template selects User git, id_rsa and IdentitiesOnly yes; include-hook hash follows renamed template. Four bashunit regression tests (20 assertions) pass; the Apollo test fails on HEAD before the fix. Full chezmoi just check passed via sase tool run -- just check, ToolRun b5cae73a3aa533bb7d390d3797057b61 (66.979s). No phase epic symbols. Live forwarded zsh -lc baseline greets bobs-org/bob; explicit candidate identity greets bbugyi200, SASE agents push dry-run exits 0 (up-to-date), bob-cli exits 1 (non-fast-forward, authenticated). Apollo repo lookups require -p gh_sase-org__sase / gh_bobs-org__bob-cli and -w 0. Preparing a durable non-turn approval gate so the host finalizer can first commit source; its reviewed command performs both chezmoi updates, default-config identity/push verification, epic-symbol check, and closes only this phase. Per the current user instruction, sase-1ni remains for the land agent. No memory changes or publication retries.

[2026-10-24T11:34:15Z · bryanbugyi34@gmail.com] Verified 2026-10-24T11:34:12.901745+00:00 after approved chezmoi update -a --force on Athena and Apollo. Athena ssh -G github.com is byte-identical before/after, still selects id_sase_service, and still greets bbugyi200. Apollo under default forwarded SSH (zsh -lc) selects only id_rsa with IdentitiesOnly yes and greets bbugyi200. Both agents-clone push dry-runs passed authentication: [{"project": "gh_sase-org__sase", "exit_code": 0, "output": "Everything up-to-date"}, {"project": "gh_bobs-org__bob-cli", "exit_code": 1, "output": "To github.com:bobs-org/bob-cli--agents.git\n ! [rejected]            HEAD -> main (non-fast-forward)\nerror: failed to push some refs to 'github.com:bobs-org/bob-cli--agents.git'\nhint: Updates were rejected because the tip of your current branch is behind\nhint: its remote counterpart. If you want to integrate the remote changes,\nhint: use 'git pull' before pushing again.\nhint: See the 'Note about fast-forwards' in 'git push --help' for details."}]. Epic-symbol entries empty. Chezmoi just check passed in ToolRun b5cae73a3aa533bb7d390d3797057b61; four regression tests passed and old-config Apollo regression failed. No publication retries. Only this phase is closed; sase-1ni closure evidence is available to the epic land agent.

## Dependencies

- **Blocks:** [sase-1nv.5](sase-1nv.5.md) ◐ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.2/README.md) | [sase-1nv.2](sase-1nv.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nv.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.2/README.md

<!-- sase:referenced-by:end -->
