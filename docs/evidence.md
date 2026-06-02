# Evidence base — does agent/persona usability testing actually work?

A fact-checked literature scan behind this skill's design. **Verdict:
pursue-with-caveats** — valuable as a fast, human-in-the-loop first-pass
hypothesis generator; *not* a replacement for testing with real users, and *not*
ground truth on its own. (Method: 23 sources, 111 extracted claims, 25
adversarially verified — 3 independent votes each; only claims that survived are
cited below. Compiled 2026-06; this is a fast-moving area of mostly 2025–2026
preprints.)

## What supports the approach

- **The mechanism exists and works.** *UXAgent* generates LLM personas that
  autonomously drive a real Chrome-rendered UI and emit action/reasoning traces +
  video for analysis. ([arXiv:2502.12561](https://arxiv.org/abs/2502.12561),
  [2504.09407](https://arxiv.org/html/2504.09407v2))
- **Feasible and useful as a low-cost pre-pass** — and every author frames it as
  a *complement, never a replacement* for human participants.
  ([2507.02306](https://arxiv.org/html/2507.02306v1),
  [2506.16345](https://arxiv.org/html/2506.16345v1), UXAgent)

## What undermines / bounds it

- **High false positives:** ~24–31% of LLM-found "issues" are hallucinated
  non-issues; human triage is mandatory.
  ([2506.16345](https://arxiv.org/html/2506.16345v1),
  [2507.02306](https://arxiv.org/html/2507.02306v1))
- **Low overlap with humans:** GPT-4o matched only **21.2%** of issues human
  experts found. ([2506.16345](https://arxiv.org/html/2506.16345v1))
- **Sim2real gap:** LLM-simulated users create an "easy mode" that inflates
  success above the real-human baseline; results swing up to **9 points** by
  simulator-LLM choice; LLM judges inflate quality ratings.
  ([2603.11245](https://arxiv.org/pdf/2603.11245) — first full τ-bench run with
  451 real humans; [2601.17087](https://arxiv.org/abs/2601.17087))
- **Demographic bias:** worse fidelity for AAVE and Indian-English speakers,
  compounding with age; gender stereotyping in personas.
  ([2601.17087](https://arxiv.org/abs/2601.17087),
  [2504.09407](https://arxiv.org/html/2504.09407v2))
- **Flow-level blindness:** LLMs caught ~43–50% of cross-screen issues vs
  ~83–86% for humans. ([2507.02306](https://arxiv.org/html/2507.02306v1))
- **The decisive gap:** *no study* has validated agent-found issues against real
  end-users on the same product. Until then: hypothesis generator, not verdict.

> Note: four optimistic pro-AI claims were *refuted* in verification — including
> the often-quoted "GPT-4 found 73–77% of issues, beating humans." The honest
> balance is more skeptical than vendor marketing.

## Industry & critiques

- **Synthetic Users** ([syntheticusers.com](https://www.syntheticusers.com/)) —
  flagship commercial "AI users"; tool roundup at
  [thegood.com](https://thegood.com/insights/ai-research-tools/).
- **Nielsen Norman Group** — skeptical
  ([article](https://www.nngroup.com/articles/synthetic-users/),
  [video](https://www.nngroup.com/videos/ai-generated-users/)).
- **ACM *interactions*** — ["The Synthetic Persona Fallacy"](https://interactions.acm.org/blog/view/the-synthetic-persona-fallacy-how-ai-generated-research-undermines-ux-research),
  ["Challenges of Synthetic Users"](https://interactions.acm.org/archive/view/january-february-2026/the-challenges-of-synthetic-users-in-ux-research);
  MeasuringU [review](https://measuringu.com/review-of-experiments-with-synthetic-users/).

Most of the market sells synthetic *interview* users (ask an AI persona
questions). This skill does the rarer, better-evidenced thing: agents that
**drive the running UI**.

## How this skill responds to the evidence

| Research says you must… | This skill… |
|---|---|
| Keep a human in the loop; not a replacement | Frames output as first-pass; AI-PM report is *for the human to work from* |
| Validate against real signal | `generating-jtbd.md`: validate personas vs reviews/tickets/analytics; tag `hypothesis` until corroborated |
| Confirm before trusting | `jtbd-workflow.md`: confirm personas before testing |
| Triage false positives | `confidence` field per finding + mandatory AI-PM triage step in `report-format.md` |
| Cover cross-screen flows | `jtbd-workflow.md`: favor end-to-end flows over single screens |
| Guard against persona bias | `generating-jtbd.md`: demographic-stereotyping check |

**Open question this skill could help answer:** measure agent-found issues
against real end-users on the same product — the validation nobody has published
yet.
