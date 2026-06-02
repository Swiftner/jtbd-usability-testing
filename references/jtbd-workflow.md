# JTBD workflow (startup)

Personas are **not** bundled — this skill works on any product, so build the
JTBD for THIS product at the start of every run, then derive tasks from it.
Garbage personas → useless test; spend real effort here.

## Get the JTBD — best source first

1. **Use what the user has.** Ask first: "Do you have personas, an ICP, or a
   JTBD doc I should use?" If they point to a file, deck, or research, use it.
2. **Generate it by working backwards.** If not, generate the JTBD from what the
   product says about itself (landing page, pricing, onboarding, docs,
   competitors). An LLM is good at this — see `generating-jtbd.md` for the
   working-backwards method. Produces 2–4 **hypothesis** personas.
3. **Ask, briefly.** If artifacts are thin, ask 2–3 questions: Who is this for
   (roles)? What are they trying to accomplish (the job)? What do they use today
   instead?

If you generated the personas yourself, **confirm them with the user before
testing** — a wrong persona invalidates the whole run. If the user can't
confirm, proceed with personas tagged **hypothesis** and weight their findings
lower in the report.

## Persona schema (keep each compact)

- **name + one-line job** — e.g. "Sales Manager — see my team's blind spots without setup"
- **context** — their situation, constraints, pressure
- **mindset** — what they care about; what they won't tolerate
- **top jobs** — the concrete jobs they hire the product for
- **surfaces** — where in the product they do these jobs
- **confidence** — validated | hypothesis (weight hypothesis personas lower in the report)

## From persona to tasks

Pick the persona(s) the run targets. Derive **3–6 concrete tasks** from persona
jobs + the run focus + **what actually changed**. Tasks are goals the persona
would really attempt ("find the one thing to fix before my next call"), not UI
steps. Stay in character: take the path this persona would take, with their
priorities and impatience.
