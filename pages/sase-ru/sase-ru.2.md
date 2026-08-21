# Bead: sase-ru.2 — Prove update-time completion refresh across supported shells

[Bead Pages](../README.md) / [sase-ru](README.md) / sase-ru.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09i.md) · **Assignee:** `sase-ru.2` · **Size:** medium
**Created:** 2026-08-21 10:44:26 EDT · **Closed:** 2026-08-21 11:20:04 EDT
**Plan:** [202608/open\_feature\_flag\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/open_feature_flag_closeout.md)

## Description

completion_soak: gather reproducible unmanaged-install evidence for completion_refresh_on_update across bash, fish, and zsh without changing the flag definition.

## Notes

[2026-08-21T15:17:51Z · sase-ru.2] Soak passed: unmanaged bash/fish/zsh completion refresh across 3 successful sase update cycles in disposable dirs (real emitters + zcompile), plus stale replacement, idempotence, mixed absent shells, per-shell failure isolation, and chezmoi skip. Flag definition unchanged. Evidence on sase-qg and file:explicit:247001ef31ee220528ea9398.

[2026-08-21T15:18:41Z · sase-ru.2] PROPOSED FOLLOW-UP: just check feature-flag lint is red on out-of-scope sase-rc — tools/check_feature_flags rule 8: live flag bead sase-rc has no registry definition for key artifact_links (explicitly owned elsewhere; this phase did not touch it).

[2026-08-21T15:19:06Z · sase-ru.2] PROPOSED FOLLOW-UP: Unrelated _lint-symvision private-import failures — _ProcProducerSite, commit_finalizer auto-commit helpers, and finalizers/declaration loaders fail as private imports by non-test files; not caused by completion soak.

[2026-08-21T15:19:30Z · sase-ru.2] PROPOSED FOLLOW-UP: Unrelated toobig violation in src/sase/finalizers/declaration.py — 1038 lines exceeds the 1000-line limit; likely pluggable_finalizers work, not this phase.

[2026-08-21T15:20:04Z · sase-ru.2] Verified unmanaged bash/fish/zsh completion refresh on the production sase update path across 3 successful cycles in disposable directories (real emitters + zcompile): stale scripts replaced, stamps restamped to 0.16.0, zsh .zwc fresh, cycles idempotent, mixed absent shells untouched, per-shell failures nonfatal and isolated, chezmoi-managed files skipped. Flag definition unchanged. Evidence on sase-qg and file:explicit:247001ef31ee220528ea9398. Soak tests 6/6 passed; just test-scoped 1818 passed. Unrelated just check red (sase-rc flags, symvision, toobig) recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-ru.7](sase-ru.7.md) ◐ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ru.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ru.2/README.md) | [sase-ru.2](sase-ru.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f425005`](https://github.com/sase-org/sase/commit/f425005a0f95b1ced138ae5018ed8a60e99e2c6d) | test(completion): soak unmanaged refresh across bash, fish, and zsh | [sase-ru.2](sase-ru.2.md) | 2026-08-21 11:26:21 EDT |
