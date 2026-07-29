# Bead: sase-aq.2 — Python facade and prompt-grammar plumbing

[Bead Pages](../README.md) / [sase-aq](README.md) / sase-aq.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aq.2` · **Size:** small
**Created:** 2026-07-29 13:07:29 UTC · **Closed:** 2026-07-29 13:45:00 UTC
**Plan:** [202607/agent\_name\_key\_markers.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_name_key_markers.md)

## Description

facade: wrap the new Rust entry points in `sase.agent.names`, widen the directive and xprompt argument character classes so braced markers survive parsing, and bump the `sase-core-rs` requirement window.

## Notes

[2026-07-29T13:45:00Z · sase-aq.2] Facade + prompt-grammar plumbing for keyed {@<id>} markers.

Added to src/sase/agent/names/_templates.py: AgentNameTemplateKey and AgentNameKeyMarker frozen dataclasses, agent_name_template_key() and iter_agent_name_key_markers() wrappers over the new bindings, and marker/key fields on AgentNameTemplate populated from the parse payload; agent_name_template_base() now strips the parsed marker instead of a hard-coded '@'. All four names exported from sase.agent.names.

Prompt grammar: rather than adding {} to the flat colon-arg character classes, both _DIRECTIVE_PATTERN and _XPROMPT_PATTERN now admit the shared KEY_MARKER_PATTERN as an indivisible alternative. The flat-class approach regressed test_launch_multi_prompt_text_alt_model_alt_uses_distinct_generated_templates: a loose trailing '}' let %m:#codex} swallow the closing brace of the enclosing %{a | b} fan-out group, yielding agent names like 0.1.cld_opus. Regression test added.

Verified round-trips with the marker intact: %id / %clan / %wait via _DIRECTIVE_PATTERN and extract_prompt_directives, #fork / #resume via _XPROMPT_PATTERN and _RESUME_REF_RE, plus _DIRECTIVE_PREFIX_RE and parse_args (both needed no change, covered by tests as the plan asked).

Validation: keyed markers already route through is_agent_name_template as templates; added _reject_unresolved_key_marker in validate_user_agent_name (the claim-time gate called from _claim_agent_identity) raising an error that names the marker and says the launch pipeline failed to resolve it. Kept private to match the sibling error classes in that file and satisfy symvision.

Tests: 25 new cases across tests/test_agent_name_templates.py, tests/test_xprompt_processor_pattern.py, tests/test_directives_name.py, and new tests/test_agent_name_key_marker_grammar.py. Full suite green: 23498 passed, 7 skipped. All just check lint stages pass (fmt, keep-sorted, ruff, mypy, pyscripts, symvision, toobig).

KNOWN BLOCKER, not resolvable in this phase: pyproject.toml bumped to sase-core-rs>=0.12.8,<0.13.0 (tests/test_sase_core_rs_telemetry_smoke_tool.py updated to match). 0.12.8 is not yet on PyPI -- the grammar phase landed on sase-core master as 8facc89 and release-plz PR #44/45 (chore: release v0.12.8) is still open. So the 'SASE validation' stage of just check fails on --published-minimum. The bump cannot be reverted: parse_agent_name_template now reads payload['marker'], which the 0.12.7 binding does not return, so a released install pinned to 0.12.7 would KeyError. Merging the sase-core release PR unblocks the gate; dev installs already build from the local checkout and work today.

## Dependencies

- **Depends on:** [sase-aq.1](sase-aq.1.md) ✓
- **Blocks:** [sase-aq.3](sase-aq.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-aq.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-aq.2/README.md) | [sase-aq.2](sase-aq.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`79be1d5`](https://github.com/sase-org/sase/commit/79be1d53a316d326790a9421435edf2942481fd9) | feat(agent): expose keyed agent-name markers in Python | [sase-aq.2](sase-aq.2.md) | 2026-07-29 13:45:56 |
