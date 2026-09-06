# Bead: sase-x7.3.1.1 — Canonicalize authoritative SASE producers

[Bead Pages](../README.md) / [sase-x7.3.1](sase-x7.3.1.md) / sase-x7.3.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-x7.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.3.md) · **Assignee:** `sase-x7.3.1.1` · **Size:** medium
**Created:** 2026-09-06 09:14:53 EDT · **Closed:** 2026-09-06 09:53:00 EDT
**Plan:** [202609/canonical\_producers.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_producers.md)

## Description

host-producers: land canonical host workflows, automation, skill and memory sources, completion discovery filtering, and portable ownership stamps.

## Notes

[2026-09-06T13:52:30Z · sase-x7.3.1.1] HOST-PRODUCERS CENSUS (changed/deferred/no-op)
CHANGED: commit.yml+pr.yml emit meta_patch from patch_name (fallback changespec_name/name); sase_bug, doctor project.patch_refs next_steps, bead create --bug-id error, config mentor-match dest/help; retired src/sase/xprompts/skills/sase_changespecs.md; sase_patches teaches only sase patch; memory authoring short|long -> core|reference (xprompts.md, glossary core/reference, generated_skills.md) via sase memory init -C; completion discovery omits changespec/task/vcs/artifact-file aliases, --changespec/--cl, ACE tab changespecs/patches via src/sase/completion/compat.py marks at parser registrations; chezmoi stamps store ~/... targets (tested with a /Users home).
DEFERRED (later sase-x7 owners): runtime parsers/facades and TUI tab/keymap aliases (remove-facades); nvim (editor-producers); plugin callers (plugin-producers); chezmoi model aliases + skill/completion deploy (chezmoi-authority); Mac ~/sase/memory/sase_beads.md (fleet-deploy); COMMITS:/short|long readers (shared-format-bridge); telegram pending-action (telegram-bridge).
NO-OP: apollo overlay (census F4); propose.yml (no patch-name emission); historical bead codec; unrelated .gp/GAI paths; docs/change_spec.md compatibility-reader prose.
CHEZMOI-AUTHORITY PREVIEWS from this tree (do not deploy unlanded): `sase skill init -n -C` would delete provider sase_changespecs SKILL.md copies (claude, grok, codex, gemini/agy, muse, opencode, qwen) and overwrite sase_patches; `sase completion deploy-chezmoi` would write portable ~/ stamp targets and omit ledgered compatibility aliases from bash/fish/zsh specs. Regenerate from the host-landed revision of this phase.

[2026-09-06T13:53:00Z · sase-x7.3.1.1] Verified host-producers on the tree above b688aeddc68b: commit.yml and pr.yml consume patch_name and emit meta_patch (rendered with sase xprompt show; focused report-step tests pass); sase_bug, doctor project.patch_refs, mentor-match, and bead --bug-id errors use sase patch/--patch; sase_changespecs skill source removed and sase_patches teaches only canonical commands; sase skill init -n -C preview would prune provider sase_changespecs copies (not deployed); memory authoring is core|reference with short|long retained as readers; completion bash/fish/zsh specs keep patch/proc/stitch/artifact/--patch/artifacts and omit changespec/task/vcs/artifact-file/--changespec/--cl/changespecs tab while sase changespec current still parses; chezmoi stamps store ~/... and match a non-Linux home; epic-symbols none; just check passed (escalated full suite).

## Dependencies

- **Blocks:** [sase-x7.3.1.2](sase-x7.3.1.2.md) ✓ · ⧖ 2026-09-06
- **Blocks:** [sase-x7.3.1.3](sase-x7.3.1.3.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.3.1.1/README.md) | [sase-x7.3.1.1](sase-x7.3.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`caa7917`](https://github.com/sase-org/sase/commit/caa7917ac966141b5cd6757e89ca245710e95950) | feat(cli): canonicalize host producers for the fleet cutover | [sase-x7.3.1.1](sase-x7.3.1.1.md) | 2026-09-06 09:54:28 EDT |
