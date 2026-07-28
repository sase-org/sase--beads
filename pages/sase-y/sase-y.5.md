# Bead: sase-y.5 — Phase 5 — Regeneration, Provider Deployment Check, and Docs Hygiene

[Bead Pages](../README.md) / [sase-y](README.md) / sase-y.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-y.5`
**Created:** 2026-04-27 18:28:00 UTC
**Plan:** [202604/changespec\_skill\_1.md](https://github.com/sase-org/sase--plans/blob/main/202604/changespec_skill_1.md)

## Description

Regenerate skills with sase init-skills --force, apply generated files with chezmoi apply if required, confirm generated skill exists for normal providers that receive skill: true, run just install and just check, and inspect any generated chezmoi diff separately from the SASE repo diff before committing.

## Dependencies

- **Depends on:** [sase-y.4](sase-y.4.md) ✓
