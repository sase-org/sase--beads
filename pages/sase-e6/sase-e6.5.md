# Bead: sase-e6.5 — Prompt archive stores both prompt renderings

[Bead Pages](../README.md) / [sase-e6](README.md) / sase-e6.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rs](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rs/README.md) · **Assignee:** `sase-e6.5` · **Size:** medium
**Created:** 2026-08-02 13:22:53 UTC · **Closed:** 2026-08-02 15:52:06 UTC
**Plan:** [202608/stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/stored_prompt_duality.md)

## Description

archive: linkify xprompt references in the published prompt body, append the rendered prompt as a collapsed verbatim section, and extend prompt archive validation and the sidecar README template to cover both.

## Notes

[2026-08-02T15:52:06Z · sase-e6.5] Verified prompt archive publication rewrites artifact links before xprompt links, appends the selected rendered prompt in a deterministic collapsed dynamic fence, tolerates missing rendered artifacts, validates sentinel/fence/HTTPS invariants with a legacy informational count, and updates the sidecar README; focused archive/CLI tests passed (23), git diff --check passed, and full just check passed.

[2026-08-02T15:52:41Z · sase-e6.5] Verified prompt archive publication rewrites artifact links before xprompt links, appends the selected rendered prompt in a deterministic collapsed dynamic fence, tolerates missing rendered artifacts, validates sentinel/fence/HTTPS invariants with a legacy informational count, and updates the sidecar README; focused archive/CLI tests passed (23), git diff --check passed, and full just check passed.

## Dependencies

- **Depends on:** [sase-e6.3](sase-e6.3.md) ✓
- **Blocks:** [sase-e6.6](sase-e6.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e6.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e6.5/README.md) | [sase-e6.5](sase-e6.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`f578c0a`](https://github.com/sase-org/sase/commit/f578c0aa4e1cdd699ce9fb715ce59fcea89cb93e) | feat(prompt-archive): store rendered prompts and link xprompts | [sase-e6.5](sase-e6.5.md) | 2026-08-02 15:54:16 |
