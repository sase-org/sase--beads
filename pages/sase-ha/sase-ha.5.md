# Bead: sase-ha.5 — Model advisories and the Contributor data-sharing guard

[Bead Pages](../README.md) / [sase-ha](README.md) / sase-ha.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ve](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ve/README.md) · **Assignee:** `sase-ha.5` · **Size:** medium
**Created:** 2026-08-07 20:46:01 EDT · **Closed:** 2026-08-07 22:03:22 EDT
**Plan:** [202608/muse\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/muse_provider.md)

## Description

advisory: add a provider-neutral model-advisory hook, surface it in the model picker, `%model` completion, and model labels, and add a doctor check that reports when a resolved default routes SASE traffic to an advisory-flagged model.

## Notes

[2026-08-08T02:03:22Z · sase-ha.5] Implemented the provider-neutral llm_model_advisories hook (normalized in _registry_metadata, malformed entries dropped not raised), exposed it via registry.model_advisory_map()/model_advisory_for(), flagged muse-spark-1.2-contributor as warn in the Muse provider, and surfaced advisories at three render sites (model picker rows + option text, %model completion detail/LSP payload, resolved model label marker) plus a new sase doctor -C llm.model_advisory check that WARNs (never fails) on alias views and default-provider tier mappings routing to a flagged model. Verified: new tests in tests/llm_provider/test_model_advisories.py and tests/doctor/test_checks_providers_advisory.py, updated tests/doctor/test_checks_providers.py and tests/test_xprompt_model_completion.py, doctor check silent for shipped defaults, and a full 'just check' run green (all lint gates + scoped test lane, exit 0).

## Dependencies

- **Depends on:** [sase-ha.2](sase-ha.2.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-ha.7](sase-ha.7.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ha.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.5/README.md) | [sase-ha.5](sase-ha.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b9ac35d`](https://github.com/sase-org/sase/commit/b9ac35d9e2e36a1f148670213b089295b69b297b) | feat(llm-provider): add model advisories and a data-sharing guard | [sase-ha.5](sase-ha.5.md) | 2026-08-07 22:04:04 EDT |
