# Generating JTBD by working backwards

No provided JTBD? Generate one. Product artifacts *encode* the JTBD — positioning,
pricing tiers, feature names, onboarding copy, and competitor comparisons all
reveal who the product is for and what job they hire it for. An LLM is genuinely
good at recovering that by **working backwards** from the artifacts to the job.
Treat the result as a strong, fast hypothesis — not ground truth (see Caveats).

## 1. Gather the sources

Read what the product says about itself, in rough order of signal:

- **Hero / landing page** — the promise and the target ("for marketing agencies")
- **Pricing + "who it's for"** — segments, by plan; who pays and why
- **Onboarding / empty states** — the first job the product pushes you toward
- **Docs / changelog** — what they ship reveals what users need
- **Competitor / "alternatives" pages** — what users would fire to switch
- **App copy + nav** — the surfaces where jobs get done

For a thorough pass, drive this with a `Workflow`: one agent per source →
synthesize the findings into personas. For a quick pass, read the top 2–3 inline.

## 2. Work backwards to the job — per persona

For each distinct user the artifacts imply, answer:

- **Who** are they? (role, company type, context, pressure)
- **What progress** are they trying to make? (functional + emotional + social)
- **What do they use today**, and what would they fire to adopt this?
- **What triggers the switch?** (the struggling moment)
- **What does "done" look like?** (their success criteria)
- **What's holding them back?** (habit, anxiety, switching cost)

Write each job as a statement:

> When **[situation]**, I want to **[motivation]**, so I can **[outcome]**.

## 3. Output

Produce 2–4 personas in the schema in `jtbd-workflow.md`, each tagged
**confidence: hypothesis** — they're LLM-generated until corroborated.

## 4. Raise confidence (validate)

Cross-check the hypotheses against real signal where it exists — user reviews,
support tickets, sales-call notes, product analytics, or the user's own
knowledge. Promote a persona to **validated** when corroborated; drop or merge
ones nothing supports. Always **confirm with the user before testing**.

## Caveats — why "hypothesis", not "truth"

- Artifacts reflect how the company *wants* to be seen — you inherit its
  positioning bias and blind spots.
- LLM-generated JTBD misses segments the artifacts don't mention (e.g. the power
  user the marketing page ignores).
- It's a head start that makes the *first* test possible, not a substitute for
  talking to real users. Confirm-before-test is the guard.
