# Bead: sase-f1.4 — Prove the acceptance criterion end to end

[Bead Pages](../README.md) / [sase-f1](README.md) / sase-f1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sw.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sw.f1/README.md) · **Assignee:** `sase-f1.4` · **Size:** small
**Created:** 2026-08-03 14:47:09 EDT · **Closed:** 2026-08-03 16:42:42 EDT
**Plan:** [202608/zero\_friction\_model\_alias\_defaults.md](https://github.com/sase-org/sase--plans/blob/main/202608/zero_friction_model_alias_defaults.md)

## Description

verify: perturb every target and description in the shipped defaults YAML, prove the full check and visual suite pass with zero edits outside that file, confirm just fmt heals the generated docs block idempotently, exercise the hardened loader's negative paths, then restore and report.

## Notes

[2026-08-03T19:49:23Z · sase-f1.4] PROPOSED FOLLOW-UP: Fix unrelated Symvision unused-public-symbol lint failure — just _lint-symvision fails on a clean alias-defaults tree for load_xprompt_source_records in src/sase/xprompt_links.py and render_prompt_sections in src/sase/history/chat_prompt_sections.py.

[2026-08-03T21:37:54Z · sase-f1.land] Acceptance verification completed on integrated tree. Perturbation changed targets: coder=codex/gpt-4.1-mini, medium_phase_worker=codex/o3@medium, smartest=claude/sonnet@xhigh, cheap=claude/haiku@medium | codex/gpt-4.1-mini@medium, cheaper=claude/haiku@low | codex/gpt-4o-mini@low, cheapest=claude/haiku@low | codex/gpt-4.1; every alias description was changed to the synthetic Perturbed acceptance description for alias text and fallback references were unchanged. Untouched baseline: just install completed; the two config-center visual nodes passed; the seven listed non-visual baseline nodes passed. Clean full just check first exposed an unrelated Symvision private-import failure from the bead sync split at HEAD 15e4213cc, which I recorded on active epic sase-ej and fixed by making cross-module sync APIs public while preserving sync.py compatibility aliases; just _lint-symvision then passed. Full baseline just check after that cleanup had one run fail only the known lock-timeout node and notification custom-gate tracked-executor node; both passed immediately in isolation, the lock-timeout duplicate remains owned by in-progress task sase-e2 with the existing sw alias-default evidence, and the new custom-gate full-suite flake was filed as ready task sase-f5. A rerun of full just check passed. With the perturbation still present, full just check passed, then just test-visual passed 407 with 1 skipped. just fmt rewrote only the generated model-alias defaults block in docs/llms.md for the perturbation, and a second just fmt was idempotent. Loader negative paths were exercised through .venv/bin/sase doctor -C config.model_aliases -v: unknown fallback epic_lander -> @missing_alias, two-alias fallback cycle large_phase_worker -> smart -> large_phase_worker, and malformed selector cheap=claude/haiku@medium |; each failure named model_alias_defaults.yml and the offending alias or chain. Restored model_alias_defaults.yml and docs/llms.md to committed content with a file-scoped reverse patch; final just fmt was idempotent and final just check passed. Follow-up disposition: config-center visual proposals no longer reproduce on the integrated tree, so no new corroboration was added to sase-bl; the pytest-clean watched-temp proposal did not recur in acceptance or final checks and is declined as non-reproducible; f1.4 Symvision proposed symbols load_xprompt_source_records and render_prompt_sections are absent from current src/tests/Justfile due the related sase-f2 work, so no standalone task is needed.

## Dependencies

- **Depends on:** [sase-f1.1](sase-f1.1.md) ✓
- **Depends on:** [sase-f1.2](sase-f1.2.md) ✓
- **Depends on:** [sase-f1.3](sase-f1.3.md) ✓
