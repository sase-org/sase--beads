# Bead: sase-1sb.1 — Stop $(cmd) execution in agent-authored prompt text

[Bead Pages](../README.md) / [sase-1sb](README.md) / sase-1sb.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bk.md) · **Assignee:** `sase-1sb.1` · **Size:** medium
**Created:** 2026-11-11 17:38:52 EST · **Closed:** 2026-11-12 01:01:15 EST
**Plan:** [202611/security\_bug\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/security_bug_audit_fixes.md)

## Description

`preprocess_prompt_late` (src/sase/llm_provider/preprocessing.py:205) runs
`process_command_substitution` (sink: src/sase/file_references.py:393,
`_execute_cmd_cached`, `subprocess.run(cmd, shell=True)`) on every prompt after
protecting only disabled regions and fenced blocks. Monitor follow-up prompts
already defend against this: src/sase/monitor/followup_prompt.py:337 wraps
untrusted command output in `wrap_disabled_region`. But two agent-authored prompt
paths get no such protection, so LLM-written text is executed host-side as shell,
outside every permission gate:

1. Handoff successor prompts: persisted verbatim by
   src/sase/agent/_staged_handoff_successor.py (~lines 65-88), launched without
   approval via src/sase/axe/run_agent_successor_delivery.py (~lines 383-439),
   then macro-expanded and late-preprocessed. Any unfenced `$(...)` the previous
   agent wrote executes in the host process. Agent-authored `sase run` launch
   prompts flow the same way.
2. Workflow-interpolated LLM output: `preprocess_prompt_early` Jinja-renders
   workflow context into prompt steps (preprocessing.py ~lines 100-110, via
   src/sase/macro/workflow_executor_steps_prompt_prepare.py), and context includes
   raw prior agent responses (`context[step.name] = {"_raw": response_text}` in
   src/sase/main/query_handler/_standalone_steps.py ~line 192). `$(...)` inside a
   model response then executes during the late phase.

First re-verify both traces (line numbers may have drifted). Then implement per
the epic's `agent_cmdsub` decision. For `provenance` (default): add an explicit
prompt-authorship parameter threaded from the launch entry points into
`preprocess_prompt_late`, and skip `process_command_substitution` (and any other
host-side execution steps, but NOT macro/artifact expansion) when the prompt text
is agent-authored. Agent-authored entry points to cover: staged-handoff successor
delivery, agent-initiated `sase run`/LaunchApproval launches, and any other path
where the prompt author is an agent rather than a human. Human-typed TUI/CLI
prompts keep current behavior. Independently of the decision, wrap workflow
context values that carry model output (`_raw`, `_response`) in
`wrap_disabled_region` the way monitor output already is, so Jinja interpolation
cannot smuggle `$(...)` back into an executable region. For `wrap`: instead wrap
the entire agent-authored prompt body in a disabled region at persist/launch time.

Tests: regression tests proving (a) a handoff/launch prompt containing `$(touch
/tmp/pwn)` does not execute and the literal text survives, (b) a workflow agent
step whose response contains `$(...)` does not execute it when a later prompt step
interpolates `{{ step._raw }}`, (c) human-authored prompts still perform command
substitution, (d) macros still expand in handoff prompts under the `provenance`
choice. Place tests near existing preprocessing tests (tests/ mirrors src/
layout).

## Notes

[2026-11-12T06:01:15Z · sase-1sb.1] Implemented authorship provenance gating for prompt command substitution; preserved model output through Jinja and directive extraction; macro and artifact expansion remain active. Verified with passing sase tool run check: 2,058 scoped test files passed, with all lint and validation stages green.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.1/README.md) | [sase-1sb.1](sase-1sb.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d0dc942`](https://github.com/sase-org/sase/commit/d0dc942c16b2da6cb3ddb6a38abee394ef1d10a3) | fix(prompts): prevent command substitution in agent text | [sase-1sb.1](sase-1sb.1.md) | 2026-11-12 01:03:32 EST |
