# Bead: sase-i2.1 — Underline glossary matches in the ACE prompt input

[Bead Pages](../README.md) / [sase-i2](README.md) / sase-i2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.w9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.w9/README.md) · **Assignee:** `sase-i2.1` · **Size:** medium
**Created:** 2026-08-09 07:49:47 EDT · **Closed:** 2026-08-09 08:25:47 EDT
**Plan:** [202608/glossary\_term\_underline.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_term_underline.md)

## Description

ace: add the additive underline to the `glossary.term` text-area style, neutralize leaked underlines inside inline-code chips, make the visual glossary matcher fake skip code literals like the Rust matcher, refresh widget assertions, and regenerate dark plus new light PNG goldens with the ACE docs.

## Notes

[2026-08-09T12:25:47Z · sase-i2.1] Implemented ACE glossary underline styling, inline-code underline suppression, visual fake literal skipping, dark/light glossary PNG goldens, and docs. Verified just install, just install-visual, focused glossary/codeblock widget pytest, just fmt, full just test-visual (571 passed, 1 skipped), and just check (full non-visual suite via escalation).

[2026-08-09T12:27:02Z · sase-i2.1] Verified just install; just install-visual; focused ACE widget tests passed; just fmt; just test-visual passed (571 passed, 1 skipped); just check passed with scoped lane escalation to full non-visual tests.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i2.1/README.md) | [sase-i2.1](sase-i2.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c2c8e88`](https://github.com/sase-org/sase/commit/c2c8e883d21188af90675ceae3631a16a64eaae5) | feat(ace): underline glossary terms in prompt | [sase-i2.1](sase-i2.1.md) | 2026-08-09 08:28:23 EDT |
