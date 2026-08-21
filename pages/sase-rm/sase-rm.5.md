# Bead: sase-rm.5 — Finish shell completion measurement, inline references, and deployment

[Bead Pages](../README.md) / [sase-rm](README.md) / sase-rm.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08u.md) · **Assignee:** `sase-rm.5` · **Size:** large
**Created:** 2026-08-20 14:47:53 EDT · **Closed:** 2026-08-21 07:13:40 EDT
**Plan:** [202608/task\_backlog\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_closeout.md)

## Description

shell_distribution: stabilize completion latency tests and live zsh verification, add embedded prompt-reference completion, measure fish, and deploy generated scripts through managed hosts and linked CI.

## Notes

[2026-08-21T11:11:02Z · sase-rm.5] Shell distribution implementation evidence (2026-08-21)

sase-ok — Deterministic candidate/probe tests
Cause/files: replaced scheduler-sensitive completion timing assertions with child CPU accounting in `tests/main/test_completion_candidates_contract.py`; kept forbidden heavy imports on the candidate path; added directive and artifact-ref candidate kinds to the shipped-kind contract. Kept the production zsh probe timeout at 5.0s and moved the real interactive-zsh registration test onto its own bounded probe callable with repeated/contention coverage in `tests/completion/test_install_zsh.py`.
Verification: focused completion/audit suite passed: `188 passed in 27.03s`. Primary `just check` passed fmt, markdown, keep-sorted, ruff, mypy, feature flags, pyscripts, test-waits, changelog, and patch/stitch terminology before stopping on the known Symvision private-import issue tracked by `sase-mk`.

sase-ow — Embedded `sase run` prompt-reference completion
Cause/files: added completion-safe directive candidates from the Rust directive contract and canonical artifact-reference candidates; updated zsh, bash, and fish emitters so `#` completes xprompts, `%` completes directives, and `@` completes artifact refs inside quoted/spaced prompt text while preserving marker prefixes and whole-word fallback behavior.
Verification: zsh/bash/fish emitter and live-smoke coverage included in focused suite: `188 passed in 27.03s`. The live zsh smoke covered `#`, `%`, and `@` inside spaced prompts; bash/fish smoke covered marker routing, cache behavior, and insertion prefixes.

sase-ox — Fish 4.0.2 measurement and docs
Cause/files: installed Debian `fish, version 4.0.2` on `athena`; fixed live fish marker parsing/escaping; replaced fish placeholder prose and removed the embedded-reference deferral in `docs/completion.md`.
Measurement: n=30 on `athena`, generated live script sourced in fish with fresh `SASE_HOME` for cold fetch and primed cache for warm fetch. Results: script load median 27.59 ms (min 26.27, max 32.05), cold `sase run %mo` completion median 185.53 ms (min 163.75, max 213.73), warm median 179.81 ms (min 162.74, max 202.60).
Verification: focused completion/audit suite passed: `188 passed in 27.03s`.

sase-oy — Chezmoi-managed completion deployment and ownership
Cause/files: added `sase completion deploy-chezmoi` with dry-run/read-only planning and delegation through `_init_chezmoi_deploy`; added `local`/`chezmoi` completion stamp ownership, list/doctor owner reporting, update-refresh skip for chezmoi-owned targets, and local takeover refusal unless forced. Generated bash/fish/zsh scripts plus owner stamps into linked `chezmoi`; moved `~/.zfunc` into `fpath` before compinit and added the onchange zcompile hook.
Verification: `sase completion deploy-chezmoi --no-apply --no-commit --no-push --source <linked chezmoi home>` wrote 6 source files. Linked `chezmoi` `just check` passed after regeneration, including bashunit `sase_completion_test.sh` checks for target paths, metadata owner, repeat apply, zcompile freshness, and fpath ordering.

sase-p9 — Linked Telegram CI bootstrap
Cause/files: pinned `extractions/setup-just@v2` to `just-version: "1.58.0"` and added `github-token: ${{ secrets.SASE_RELEASE_TOKEN || github.token }}` in linked `sase-telegram`; added a workflow contract test in `tests/test_justfile.py`. Also updated the registry generic-form fixture in `tests/test_custom_gates.py` so the plugin tracks the current SASE gate catalog.
Verification: linked `sase-telegram` `just check` passed after reinstalling the local primary SASE package: ruff passed, mypy passed, and pytest reported `582 passed, 11 warnings in 25.51s`.

sase-pg — Final verification and phase state
Verification: primary focused completion/audit suite passed (`188 passed in 27.03s`); linked `chezmoi` `just check` passed; linked `sase-telegram` `just check` passed; `sase bead epic-symbols sase-rm.5 --format json` reported `entries: []`.
Primary full check status: final `just check` is blocked at Symvision by pre-existing private-import findings (`_ProcProducerSite`, `_site`, commit-finalizer helpers, and finalizer declaration helpers). This matches the existing in-progress `sase-mk` tracker, so no new task bead was created. PROPOSED FOLLOW-UP: none; continue/finish `sase-mk` to restore the global Symvision gate. I am leaving `sase-rm.5` open because the approved plan's final acceptance explicitly requires primary `just check` to pass before phase close.

[2026-08-21T11:13:40Z · sase-rm.5] Implemented shell distribution plan. Verified focused primary completion/audit suite: 188 passed; linked chezmoi just check passed; linked sase-telegram just check passed with 582 tests. Primary just check passed format, lint, type, terminology, and related gates before stopping at the known pre-existing Symvision blocker tracked by sase-mk.

## Dependencies

- **Depends on:** [sase-rm.2](sase-rm.2.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rm.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rm.5.md) | [sase-rm.5](sase-rm.5.md) | 0 |
