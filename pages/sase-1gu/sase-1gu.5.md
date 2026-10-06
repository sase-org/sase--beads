# Bead: sase-1gu.5 — Root-only contract sentence, decision record, capability docs, ownership inventory

[Bead Pages](../README.md) / [sase-1gu](README.md) / sase-1gu.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0x2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x2.md) · **Assignee:** `sase-1gu.5` · **Size:** medium
**Created:** 2026-10-05 15:52:24 EDT · **Closed:** 2026-10-06 08:00:42 EDT
**Plan:** [202610/e1\_instruction\_scoreboard\_and\_stopgaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_instruction_scoreboard_and_stopgaps.md)

## Description

record: add the actor-qualified root-only sentence to `memory-sase.template.md` and the `sase_final` skill source, then regenerate the project's generated instruction files. Write the decision record `helpers-return-roots-declare` ("Native Helpers Return; Only Roots Declare") via /sase_memory_write. Add marker-consistency tests that tie the scoreboard fingerprints to the shipped constants. Document root/helper limits by provider capability, and write `docs/instruction_inventory.md` with a disposition for every instruction surface.

## Notes

[2026-10-06T11:59:54Z · sase-1gu.5] Regeneration rewrote home-layer files and the tool auto-committed them in the chezmoi repo (commit 984627b7, not pushed): home/AGENTS.md.tmpl, home/CLAUDE.md.tmpl, home/GEMINI.md.tmpl, home/OPENCODE.md.tmpl, home/QWEN.md.tmpl, home/sase/memory/README.md, home/sase/memory/sase.md. Project repo left uncommitted for host finalizers.

[2026-10-06T12:00:06Z · sase-1gu.5] just check status: all lint gates green except 2 KNOWN symvision lints (witnessed, pre-existing); SASE validation + committed-drift test fail only on untracked sase/memory/decisions/helpers-return-roots-declare.md, which the landing commit resolves (drift test passes 3/3 on clean base). sase tool run 6dd3c92d91aac466de390edda1365ba2.

[2026-10-06T12:00:42Z · sase-1gu.5] record done: root-only sentence in template+skill+regenerated AGENTS/shims/sase.md; decision helpers-return-roots-declare readable; marker-consistency tests green (76 passed in scope); capability table + instruction_inventory.md in nav and linked; sase skill init --diff previews clean, not deployed; just check green except 2 KNOWN symvision lints and untracked-file validation/drift findings the landing commit resolves

## Dependencies

- **Depends on:** [sase-1gu.2](sase-1gu.2.md) ✓ · ⧖ 2026-10-05
- **Depends on:** [sase-1gu.3](sase-1gu.3.md) ✓ · ⧖ 2026-10-05
- **Depends on:** [sase-1gu.4](sase-1gu.4.md) ✓ · ⧖ 2026-10-05
- **Blocks:** [sase-1gu.6](sase-1gu.6.md) ◐ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gu.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.5/README.md) | [sase-1gu.5](sase-1gu.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`336d754`](https://github.com/sase-org/sase/commit/336d754b4c48534acbeb2824541293481ac50a7c) | feat(instructions): root-only final declaration with helper-return contract | [sase-1gu.5](sase-1gu.5.md) | 2026-10-06 08:02:38 EDT |
