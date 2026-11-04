# Bead: sase-1r5.1 — Retry transient GitHub SSH publickey denials on git network operations

[Bead Pages](../README.md) / [sase-1r5](README.md) / sase-1r5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1r5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.md) · **Assignee:** `sase-1r5.1.land`
**Created:** 2026-11-04 06:54:52 EST · **Closed:** 2026-11-04 10:28:33 EST
**Plan:** [202611/github\_publickey\_retry.md](https://github.com/sase-org/sase--plans/blob/main/202611/github_publickey_retry.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/github_publickey_retry.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1r7][2] | Epic that added the shared CredentialRetry policy this task extends |

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/github_publickey_retry.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1r7/README.md

<!-- sase:links:end -->

## Description

A GitHub-side burst of `Permission denied (publickey)` rejections of valid SSH keys no longer aborts agent launches or background git jobs. Launch-blocking and background git network operations retry such denials within a bounded, deadline-aware budget. Genuine credential failures still surface promptly as permanent authentication errors that keep the original stderr: deploy-key refusals, a host with no local SSH credential at all, and a denial that outlasts the budget.

## Notes

[2026-11-04T15:28:33Z · sase-1r5.1.land] Land verification (sase-1r5.1.land):
STEP 1 VERIFY: All 5 phases closed. Read every child note and the epic commits:
sase-core 55532e2d (on sase-core master, matches sase-core-revision.txt), plus sase
d008039511, 31174e283c, 82742081f9, and 8b0e640242.
- core-verdict: retryability/mod.rs is a facade over classify.rs and tests.rs. git and
  git_clone publickey denials give credential_unconfirmed (retryable=false, reason
  category authentication). gh publickey stays permanent. The DEPLOY_KEY_MARKER check
  runs before publickey (decision deploy_key_marker=yes).
- credential-retry-policy: wire constant, local_ssh_credential_state, and
  git_credential_retry.py. LAUNCH budget is 5/10/20/30/45 (decision
  launch_budget=two_minutes) and BACKGROUND is (10,). Includes the env kill switch,
  10-minute per-host exhaustion memo, absent-credential fast fail, deadline check, and
  failure_suffix.
- sdd-clone-adopt: credential retries are separate from transient attempts, sleep
  outside remote_clone_admission, and fail non-transient with original stderr plus
  suffix. Telemetry fields added; SSH-shim tests cover it.
- network-git-and-lease-adopt: run_sdd_network_git_with_retries and the lease fetch use
  the shared tracker; the bespoke 10s confirmation is deleted. launch_condition_workspace
  passes the launch budget. is_credential_failure, the ssh-agent hint, and mirror
  auth_error are intact.
- docs: service-host.md, sdd-storage.md, and environment-variables.md updated; the
  sase-167 note is present.
Other lease callers (task/epic/prompt-proc launch) keep the background budget, which
matches pre-epic behavior; task and epic launches hold a global submit lock while
acquiring the lease. Every test that runs a real tracker resets the process-global memo.
Landing cleanup: the _git_network.py and _lease_git.py adopters now compare against
RETRYABILITY_VERDICT_CREDENTIAL_UNCONFIRMED instead of the string literal.
STEP 2 INTEGRATE: The only non-epic commits since the epic began, a3deb1020f and
761362a1f8, are release-watch test splits that don't touch retryability. Nothing to
integrate.
VERIFICATION: 102 focused tests pass (tracker, ssh credential state, core parity, clone
shim, lease prepare/acquire, network git, external mirror, condition workspace).
`sase tool run check` passed (run f124f37f1c8aaf42489f17bfaf428899). No epic-symbols
remain.
FOLLOW-UPS:
- sase-1r5.1.4 Muse watchdog flake: filed as new flake task sase-1r6. Not a duplicate of
  sase-16i or sase-1k0.
- sase-1r5.1.5 #1-#4 (sidecar_git push_sidecar, axe runner_workspace_sidecar,
  _git_commit_dispatch finalizer pushes, bead sync worker): folded into one feature task,
  sase-1r7, because all four share the same remediation (adopt CredentialRetry at
  network git sites that never consult the classifier). The bead sync worker is marked
  lowest priority, since the next tick recovers it.
No proposals declined.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r5.1.land/README.md) | [sase-1r5.1](sase-1r5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`75226f2`](https://github.com/sase-org/sase/commit/75226f2435623f480915cc5a0c9bf5dcba97cf8e) | refactor(retryability): match credential\_unconfirmed via the wire constant | [sase-1r5.1](sase-1r5.1.md) | 2026-11-04 10:31:14 EST |
