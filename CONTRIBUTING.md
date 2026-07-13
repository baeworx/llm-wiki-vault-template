# Contributing — Lessons from Running a Vault

Notes from actually operating an LLM-maintained wiki, so your cohort doesn't relearn them the
hard way. `CLAUDE.md` tells the agent the rules; this tells *you* how to get the most out of it.

---

## The habits that make or break a vault

**Feed it one good source at a time.** The temptation is to dump ten articles and say "ingest
all of these." Resist it. Sources ingested in a batch get shallow summaries and weak
cross-links. One source, discussed, filed well, beats ten filed fast.

**Frame the question before you research.** Vague topics produce vague pages. "What's the
memory model?" beats "tell me about the framework." Write the question in `questions.md`
first — it gives the answer a place to land.

**Cite everything, always.** An uncited claim is worse than no claim: it *looks* trustworthy
without being it. If the agent states something load-bearing without a citation, push back
and ask where it came from. This is the single most important discipline.

**Keep contradictions visible.** When a new source disagrees with an old one, the lazy move
is to overwrite. Don't. Two sources disagreeing is a *finding* — flag both, log it in
`questions.md`, resolve it later with evidence. The disagreement is often the most valuable
thing in the vault.

**Run lint before the vault gets big.** At 15 pages you don't need it. At 50, orphan pages
and stale claims pile up invisibly. Schedule a lint pass every ~10 ingests. It's cheap
(route it to Haiku) and it's what keeps the vault a reference instead of a landfill.

**Delete the seed pages.** They're scaffolding. Once an area has real content, the 🌱 seeds
just add noise and clutter the index. Kill them.

---

## Anti-patterns we've hit

- **The landfill.** Only ever adding, never reviewing. The vault grows, trust shrinks. Cure:
  `review-by` dates + regular lint.
- **The echo chamber.** Corroborating a claim with three sources that all trace to one press
  release. That's *one* source. Independence is what makes triangulation mean something.
- **Silent staleness.** "Latest version," "current price," "as of now" with no date. In six
  months it's wrong and nobody knows. Tag time-sensitive claims and give them a review date.
- **Confidence laundering.** A `[C:low]` guess gets cited by a concept page, which gets cited
  by a synthesis, and three hops later it reads as fact. Watch confidence propagation — a
  conclusion is only as strong as its weakest load-bearing input.
- **Orphan sprawl.** Pages nobody links to. If a page has no inbound links, either wire it in
  or question whether it should exist.

---

## Evolving the schema

`CLAUDE.md` is meant to change. When your cohort discovers a better convention, update it —
but do it deliberately:

1. Propose the change and why (a sentence in `log.md` or a PR description).
2. Keep it **backward compatible** where you can — new optional fields, not renamed required
   ones. A schema change that invalidates 40 existing pages isn't worth it.
3. If you all share one repo, agree on schema changes together so vaults don't diverge.

The original vault added `solution`/`fragment` page types and model-routing guidance this
way. This template added credibility ratings, confidence tags, and `questions.md`. Yours will
add the next thing. Just write down *why*, so future-you understands the decision.

---

## Sharing across the cohort

A few models, from lightest to heaviest coordination:

- **Fork-and-go** (default). Everyone copies the template once and runs their own vault.
  Zero coordination, zero merge conflicts. Best for personal knowledge bases.
- **Shared repo, separate areas.** One git repo; each person owns an area or a topic folder.
  Works if you're researching a shared subject together. Agree on schema up front.
- **Shared repo, shared everything.** Highest value, highest friction — you get one compounding
  knowledge base, but you need discipline around `index.md`/`log.md` merge conflicts and
  schema alignment. Only worth it for a tight, motivated group.

Whichever you pick: **the log and the index are the coordination surface.** Keep them honest
and everyone can see what everyone else has done.

---

## When in doubt

Ask the agent to explain its reasoning and show its citations. The whole point of this system
is that knowledge is *inspectable* — every claim traces back to a source you can check. If you
can't follow the trail from a wiki claim to a raw source, that's a bug in the vault, not a
feature of the agent. Fix it.
