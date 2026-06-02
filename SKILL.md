---
name: jtbd-usability-testing
description: Persona-driven usability testing for any product. Starts by establishing the product's Jobs-To-Be-Done and deriving personas, then adopts each persona and attempts its real jobs against the running app — driving the live UI in the browser, or for non-UI changes (API, backend, CLI) evaluating the change as the persona it most affects — then synthesizes prioritized, evidence-backed recommendations. Use when validating whether a built change actually serves its users (not just technically works) before shipping — e.g. "usability-test this screen as our users", "would a [role] get through onboarding", "does this API change still work for the integrator".
---

# JTBD usability testing

**On-system ≠ usable.** Passing tests, rendered pages, and 200s prove the system
*works* — not that a real person with a real job can get that job done. This
skill closes that gap: establish who the users are and what jobs they hire the
product for, then *be* those users against the running product and report where
the job breaks down — before shipping.

Three principles it runs on:

1. **Test the job, not the system** — a task passes when the persona accomplished
   their goal, not when the code technically worked.
2. **Be the user, don't tour the UI** — adopt the persona's context and
   impatience; take the path they'd take; derive tasks from their jobs.
3. **Ground it in what changed** — test what actually shipped; rank friction by
   the job it blocks (severity × JTBD impact), with evidence.

## Startup process (do this first, every run)

A usability test is only as good as the JTBD behind it, so the run **starts** by
establishing that — never jump straight to driving the app.

1. **Run the JTBD workflow** — establish the product's personas and their jobs
   per `references/jtbd-workflow.md`. No JTBD provided? Generate one by working
   backwards from the product (`references/generating-jtbd.md`). This is the
   gate: no personas, no test.
2. **Confirm the target** — get a running, **already-authenticated** URL (you
   never log in), plus the **focus** and **what changed** (the work being
   validated). For changes with no UI, see below — no URL needed.
3. **Select personas** — pick which derived persona(s) this run targets
   (default: all).

## Run procedure

1. **Preflight (once)** — open a tab and load the URL per
   `references/running-a-session.md`; stop at any login wall.
2. **Per-persona sessions** — for each selected persona, in turn: derive 3–6
   tasks from its jobs + the focus + **what actually changed**, then drive the
   app and record findings per `references/running-a-session.md`. One persona at
   a time (sequential — no parallel browser sessions).
3. **Synthesize** — when all personas are done, produce the report per
   `references/report-format.md`.

## When there's no UI to drive

Some work isn't browser-testable — an API change, a backend job, a CLI, a schema
migration. Don't force a browser session and don't be rigid. Evaluate the change
as the persona it affects most: walk that persona's job through the new behavior
(contract, request/response, output, error path) and judge whether it still
serves the job. The persona usually meets the change *through* something else (a
frontend, an integration, a downstream job), so trace the consumer — e.g. grep
the consuming code for a renamed/removed field — or you can only flag the *risk*
of a break, not confirm it. Drive it inline for a small change, or fan out with a
`Workflow`. Feed results into the same finding schema and report
(`references/running-a-session.md`, `references/report-format.md`).

## Load references on demand

Read only what the current phase needs — `jtbd-workflow.md` (and
`generating-jtbd.md` if generating personas) at startup, `running-a-session.md`
while driving, `report-format.md` at synthesis. Don't preload everything.

## Safety

Never log in or handle credentials (login wall → stop and ask). Never take
irreversible actions (send/purchase/delete/submit/publish) without explicit user
approval. If stuck on a page/element after 2–3 tries, record it as a finding and
move on. Full rules in `references/running-a-session.md`.
