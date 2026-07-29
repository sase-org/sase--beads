# Bead: sase-av.5 — Artifact-reference highlighting in the prompt input widget

[Bead Pages](../README.md) / [sase-av](README.md) / sase-av.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-av.5` · **Size:** medium
**Created:** 2026-07-29 16:48:11 UTC · **Closed:** 2026-07-29 18:30:28 UTC
**Plan:** [202607/artifact\_refs\_and\_prompt\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_refs_and_prompt_bar.md)

## Description

prompt-highlight: syntax-highlight artifact references in the prompt editor with per-part styles (sigil, kind, separator, payload, fragment) driven by the core scanner and a cached known-kind set, following the xprompt highlighter pattern, with PNG snapshot coverage.

## Notes

[2026-07-29T18:30:28Z · sase-av.5] Implemented core-scanner-driven PromptTextArea artifact-reference highlighting with per-part theme styles, literal-zone filtering, UTF-8 byte-span conversion, cold/unknown neutral treatment, off-thread cached known-kind warming, and a committed PNG golden. Verified focused unit/visual tests, git diff --check, and full COLUMNS=120 just check (all formatting, lint, Symvision, SASE validation, unit tests, and PNG snapshots passed).

[2026-07-29T18:32:15Z · sase-av.5] Verified COLUMNS=120 just check passes, including formatting, Ruff, mypy, Symvision, SASE validation, 23k+ pytest cases, and PNG visual snapshots.

## Dependencies

- **Depends on:** [sase-av.2](sase-av.2.md) ✓
- **Blocks:** [sase-av.6](sase-av.6.md) ◐
