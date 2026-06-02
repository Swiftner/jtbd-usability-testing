# Report format — AI product manager synthesis

**The run always ends here.** After all personas have run, switch into an **AI
product manager**: evaluate the raw persona feedback, decide what's real, and
produce the prioritized, evidence-backed **report the human works from** — the
deliverable of every run (UI or not).

## Synthesize

1. Pool every persona's findings.
2. **Triage false positives.** The personas are LLMs, so a share of findings
   will be non-issues (research puts this around a quarter). Drop or down-rank
   anything tagged `needs-human-check` or that you can't tie to evidence; present
   confirmed issues as findings and clearly flag the rest as *to verify*, never
   as fact.
3. **Dedupe:** merge findings that are the same underlying issue across personas
   (note which personas hit it — cross-persona issues rank higher).
4. **Prioritize** by **severity × JTBD impact**: a `critical` that blocks a core
   job outranks a `moderate` annoyance. Weight hypothesis (unvalidated) personas
   lower than validated ones.

## Report structure

Write a dated markdown report (e.g. `reports/YYYY-MM-DD-<focus>.md`). Screenshots
live in `evidence/` at the repo root, so links from the report use `../evidence/`:

```
# Usability run — <focus> — <date>
the work validated (PR/diff/branch) · URL tested (or "no UI — evaluated via workflow") · personas run · build/commit if known

## Summary
N critical · N serious · N moderate. One-paragraph headline.

## Recommendations (prioritized)
For each: **issue** → **evidence** (persona, task, screenshot/GIF) →
**recommended fix** → **which persona/job it blocks**.

## Per-persona appendix
Each persona: tasks attempted, completed/partial/no, notable quotes.

## Evidence index
Links to `../evidence/<persona>-<taskN>.png` screenshots (and any session GIF)
referenced in findings, organized by persona + task.
```

Keep recommendations actionable and specific (a fix a designer/engineer could
pick up), and tie each to the job it unblocks — usability in service of the
JTBD, not generic nitpicks.
