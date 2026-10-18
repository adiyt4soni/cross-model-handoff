# Cross-model handoff

Writes a self-contained handoff packet so Codex, ChatGPT, Gemini or a fresh Claude session can take over a task with none of this conversation's context.

**Type:** Claude Code skill · **Area:** General skills

## What it does

- Fixed packet structure: the ask, the deadline, the standing rules copied exactly, current state, files to read in order, facts that are easy to get wrong, do-nots, gotchas, how the work will be checked, and the report format.
- Variants for a blind second opinion (the receiver derives its own answer first), an end-of-session Claude-to-Claude handoff, and a single paste-in prompt for a chat product.
- Final check: could a newcomer start without asking a question? Every path exists, every date matches its source, no credentials.

## Guardrails

- Personal facts go in only when the task needs them; the user is told what personal data the packet holds.
- Unverified claims are marked OPEN and the receiver is told to re-check them, not inherit them.

## When it triggers

> Write a self-contained handoff packet so another tool (Codex, ChatGPT, Gemini) or a fresh Claude session can pick up a task with no access to this conversation. The packet carries the goal, the standing rules, the current state, the exact files to read, the facts that are easy to get wrong, what not to do, and how the work will be checked. Use when the user says "hand this to Codex", "make a prompt for ChatGPT", "write a handoff", "blind check this with another model", or a session is ending with work in progress.

## What's in this repo

- `SKILL.md`: the skill itself, the file Claude or Codex reads.
- Written to be generic: where the skill relies on the user's own files, it names them by role, not by content.

## Install

```bash
mkdir -p ~/.claude/skills/cross-model-handoff
curl -fsSL https://raw.githubusercontent.com/adiyt4soni/cross-model-handoff/main/SKILL.md -o ~/.claude/skills/cross-model-handoff/SKILL.md
```
