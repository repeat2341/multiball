---
name: multiball
description: Boot or run the MULTIBALL setup (parallel Claude Code sessions in isolated slots with full environments, a hub that verifies hand-backs, a self-checking knowledge base). Use when the user says multiball, asks to set up parallel agent slots, or asks to boot from MULTIBALL.ai.md.
---

# MULTIBALL

1. Find `MULTIBALL.ai.md`: the repo root first, else the plugin's copy at `${CLAUDE_PLUGIN_ROOT}/MULTIBALL.ai.md`. If it is not in the
   repo, copy it there so the next session finds it.
2. Read it whole. Then do what its first section says: run the terminal check, and stop with its message unless the
   session is in WezTerm or the user asked for the flat setup.
3. Run § 16 Boot in order. Ask the user only the step 1 interview questions, all at once. Every step ends with its
   check. Record each answer and permission, quoted and dated, in the repo's `CLAUDE.md`.
4. When the setup already exists (a `CLAUDE.md` with a MULTIBALL section, a slot CLI, a hub), work as its hub: plan,
   launch slots, verify hand-backs against the AC, fold durable facts, and fix the harness from each Harness section.
5. When a launch puts two or more slots in play: MULTIBALL! MULTIBALL!! MUL-TI-BALL!!!
