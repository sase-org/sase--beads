# Bead: sase-1sb.4 — Shell-quote workflow interpolations, validate git refs, fix agent-guard parity

[Bead Pages](../README.md) / [sase-1sb](README.md) / sase-1sb.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bk.md) · **Assignee:** `sase-1sb.4` · **Size:** medium
**Created:** 2026-11-11 17:38:53 EST · **Closed:** 2026-11-11 21:32:01 EST
**Plan:** [202611/security\_bug\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/security_bug_audit_fixes.md)

## Description

Three bounded hardening fixes, all independently verified:

1. Workflow bash/python step injection (per the epic's `bash_autoquote`
   decision). Sinks: src/sase/macro/workflow_executor_steps_script.py (~line 135)
   and src/sase/main/query_handler/_standalone_steps.py (~line 85) run
   Jinja-rendered templates with `subprocess.run(..., shell=True)`; the Jinja env
   (src/sase/macro/workflow_executor_utils.py) has no shell-quoting filter.
   Interpolated values include macro inputs from prompt text and prior step
   outputs (including model responses). The `word` input type
   (src/sase/macro/models.py ~line 168) only rejects whitespace, so
   `$(touch${IFS}/tmp/pwn)`, `;`, and quotes all pass. Shipped injectable
   examples: src/sase/macros/file.yml (`{{ name }}` inside a bash step path) and
   src/sase/macros/json.yml (`'{{ schema }}'` — a single quote breaks out). For
   `autoquote` (default): auto-apply shlex.quote to every Jinja interpolation
   inside `bash:` steps with an explicit opt-out filter (e.g. `| raw`) for
   intentional raw interpolation; apply equivalent escaping or argument-passing
   for `python:` steps (prefer passing values via argv or env rather than
   splicing into source); update the shipped macros under src/sase/macros/ and
   src/sase/default_macros/ to stay correct under quoting. For `tighten_only`:
   instead restrict `word` to a charset allowlist `[A-Za-z0-9._-]+` and audit
   shipped templates. In BOTH cases tighten `word` validation.

2. Git argument injection in VCS plugins:
   src/sase/vcs_provider/plugins/_git_core_ops.py `vcs_checkout` (~line 29)
   passes `revision` positionally to `git checkout`, and
   src/sase/vcs_provider/plugins/bare_git.py `vcs_mail` (~line 33) to `git push
   -u origin <revision>`. `revision` derives from Patch NAME / branch-map values
   in agent-writable `.sase` files (src/sase/vcs_provider/plugins/
   _git_revision_ops.py), so values like `--receive-pack=...` (push; executes a
   local command for filesystem remotes) or `-B`/`--pathspec-from-file=`
   (checkout) smuggle flags. Fix: validate candidate revisions where they are
   read (reject names starting with `-` and names failing `git check-ref-format
   --branch` or an equivalent charset check), and prefer flag-safe invocation
   forms where git's syntax allows.

3. Agent-guard detection parity: tools/_sase_install_env.py `AGENT_ENV_VARS`
   (~line 22) lists only `SASE_AGENT` and `SASE_MONITOR_ID`, but the canonical
   detector `agent_marker_present` (src/sase/agent/identity.py ~lines 34-48) also
   recognizes `SASE_AGENT_NAME` and discovered agent metadata. A process carrying
   only `SASE_AGENT_NAME` bypasses the "Global Install Is Human-Only" refusal in
   `agent_guard`. Fix: add `SASE_AGENT_NAME` to `AGENT_ENV_VARS` (keep the module
   stdlib-only; do not import sase) and add/extend the parity test the module's
   comments promise so the two sets cannot silently drift again. Read the memory
   note sase/memory/tools.md before changing anything under tools/.

Tests: injection attempts through macro args and workflow context must execute
nothing (assert via marker files/mocked subprocess); hostile revision names must
be refused before any git invocation; agent_guard must refuse under each marker
env var.

## Notes

[2026-11-12T02:32:01Z · sase-1sb.4--1] Fixed 3 real regressions from the hardening change plus 1 load-flake, verified green. (1) Agent-type regex rejected @tribe names (#fork:@epic): split validation so AGENT allows optional leading @ via _AGENT_RE while WORD stays strict [A-Za-z0-9._-]+; @ is shell-safe so autoquoting still verbatim. (2) test_python_step_with_jinja_context used the pre-hardening inside-string idiom that repr-quoting intentionally breaks (shipped macros already migrated to tojson-outside-string, e.g. mentor.yml): migrated the test template to print("result=" + {{ input_value | tojson }} + "_processed"), assertion unchanged (hello_processed) — expectation change justified by the autoquote contract, not a weakening. (3) test_git_mail_bare_remote_push_only expected the pre-hardening push argv: updated to the flag-safe form with --end-of-options (verified real git 2.47.3 accepts and pushes it), matching the phase's own test_mail_pins_revision_after_end_of_options. (4) test_wait_spec_display_and_result_are_canonical timed out in pilot.pause() under full-suite load (64s) with no code-path overlap to this phase's 16 files; passes consistently in isolation (25/25 modal file green in 8s). Verified: 31 focused + 88 broader (executor script, jinja/standalone, git ops, guards) + 30 fork/query + 25 modal all pass; ruff check, ruff format --check, mypy clean on touched files; epic-symbols clean.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.4.md) | [sase-1sb.4](sase-1sb.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`22e1ef1`](https://github.com/sase-org/sase/commit/22e1ef1249059503a29749c548564dbf01da0825) | fix(sase-1sb.4): repair shell-arg-hardening regressions found by check | [sase-1sb.4](sase-1sb.4.md) | 2026-11-11 21:33:39 EST |
