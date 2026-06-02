# jtbd-usability-testing

A self-contained [Claude Code](https://claude.com/claude-code) skill that runs
**persona-driven usability testing on any product — before you ship.**

**On-system ≠ usable.** Your tests passing, pages rendering, and APIs returning
200s prove the system *works*. They don't prove a real person with a real job
can actually *get that job done*. Real usability testing closes that gap — but it
means recruiting users, scheduling sessions, and watching, so most teams skip it
and ship on vibes.

This skill makes a first pass cheap. It **establishes your product's
Jobs-To-Be-Done, derives personas, then has the agent *be* those users against
your running product** — trying their real jobs, on the actual screens — and
reports where the job breaks down, prioritized by impact, with screenshots.

It is *not* a replacement for testing with real humans. It's the pass you can run
on every change to catch "a real person would be lost here" while it's still
cheap to fix.

## How it works

1. **JTBD workflow (startup)** — establish who the users are and what jobs they
   hire the product for (from your JTBD doc, or derived from the product itself).
2. **Persona sessions** — adopt each persona and attempt 3–6 of its real jobs
   against the running, logged-in app, staying in character.
3. **Synthesis** — a PM-style report: prioritized, evidence-backed
   recommendations, each tied to the job it unblocks.

No UI to test (an API / backend / CLI change)? It evaluates the change as the
persona it most affects instead of forcing a browser session.

## Principles

- **Test the job, not the system** — a task passes when the goal was accomplished.
- **Be the user, don't tour the UI** — take the path they'd take.
- **Ground it in what changed** — rank friction by the job it blocks.

## Install

```bash
git clone https://github.com/Swiftner/jtbd-usability-testing
ln -s "$PWD/jtbd-usability-testing" ~/.claude/skills/jtbd-usability-testing
```

## Use

Give Claude a running, logged-in URL and a focus:

> "usability-test https://app.example.com/onboarding as our users — focus on first-run."

The skill never logs in and never takes irreversible actions.
