# Research Methodology

How this vault turns sources into trustworthy, compounding knowledge. `CLAUDE.md` is the
*what* (structure and conventions); this is the *how* (the research method behind them).
Read it once to understand the discipline; refer back when a step gets fuzzy.

The whole point: **a claim in this wiki should be more trustworthy than the same claim
pulled fresh from a search engine** — because it has been evaluated, cited, cross-checked,
and dated. That trust is the compounding asset. These methods protect it.

---

## The research loop

Every investigation follows the same six-step cycle. It's deliberately repeatable so the
vault behaves the same whether it's you or a cohort-mate driving it.

```
   ┌────────────────────────────────────────────────────────────┐
   │  1. FRAME  →  2. DISCOVER  →  3. TRIANGULATE  →             │
   │       4. SYNTHESIZE  →  5. FILE BACK  →  6. REVIEW  ─────────┘
```

**1. Frame.** Write the actual question down in `questions.md` before searching. A sharp
question ("Does Agent Zero's memory survive a container rebuild?") beats a vague topic
("Agent Zero memory"). Framing first stops scope creep and gives the file-back a home.

**2. Discover.** Gather sources. Prefer **primary** (the paper, the docs, the person who
built it) over **secondary** (someone summarizing it). Cast wide enough to find
*disagreement*, not just confirmation — one corroborating blog post is not evidence.

**3. Triangulate.** Corroborate load-bearing claims across **≥2 independent sources**.
"Independent" means they don't share an author, a sponsor, or a common upstream source.
Two outlets reprinting the same press release count as *one* source. If sources disagree,
that's a finding — capture it (see *Contradictions*).

**4. Synthesize.** Turn corroborated claims into wiki prose. Say what's known, how well
it's known (confidence), and what's still open. Update the evolving `synthesis` page if the
new evidence shifts the thesis — don't just append; re-weigh.

**5. File back.** Write the pages: source summaries, concept/entity updates, comparisons.
Cite every claim. Cross-link both directions. Then update `index.md`, `log.md`, and
`questions.md`. **An investigation that isn't filed back didn't happen** — it evaporates
when the session ends.

**6. Review.** Set a `review-by:` date on anything time-sensitive (benchmarks, prices,
"latest version"). The lint pass re-checks these so the vault ages gracefully instead of
quietly going stale.

---

## Evaluating a source (CRAAP)

Before trusting a source, run it through five quick lenses and set its `credibility:` field.

| Lens | Ask | Red flag |
|------|-----|----------|
| **C**urrency | How old is it? Is the topic fast-moving? | Undated, or old claims about a moving target |
| **R**elevance | Does it actually address the question? | Tangential, cherry-picked |
| **A**uthority | Who made it? What's their standing? | Anonymous, no expertise, no track record |
| **A**ccuracy | Is it evidenced? Reproducible? Cited? | No sources, unfalsifiable, "trust me" |
| **P**urpose | Why does it exist? Who profits? | Selling something, affiliate links, agenda |

Then rate:
- **`credibility: high`** — primary source, named expert/institution, evidenced, no conflict
  of interest. (Peer-reviewed papers, official docs, first-party data.)
- **`credibility: medium`** — credible secondary source, some evidence, minor agenda.
  (Reputable journalism, a knowledgeable practitioner's writeup.)
- **`credibility: low`** — anonymous, unevidenced, or conflicted. (Promotional content,
  affiliate videos, single anecdote.) *Still worth ingesting — just label it, and never let
  a synthesis lean on it alone.*

> **Always disclose conflicts of interest at the top of a source page.** If a video is an
> affiliate pitch, the summary's first line says so. The reader should never discover the
> bias after they've believed the claim.

---

## Confidence tagging

Attach a confidence marker to any non-obvious claim, inline, right where it's made:

- **`[C:high]`** — corroborated across independent sources, or direct primary evidence.
- **`[C:med]`** — a single credible source; plausible but not cross-checked.
- **`[C:low]`** — a single weak/biased source, or your own inference. Treat as a hypothesis.

Rules of thumb:
- A `synthesis` page's central thesis should rest on `[C:high]` claims. If it can't, say so —
  "thinly sourced; see `questions.md`."
- Numbers, dates, versions, and benchmark figures decay fastest. Tag them and give them a
  `review-by`.
- Upgrading a claim's confidence (low → high) as new sources arrive is real work worth doing.
  It's how the vault gets *more* reliable over time, not just larger.

---

## Handling contradictions

New sources will disagree with old ones. That's signal, not noise. Never silently overwrite.

1. **Keep both.** On the affected page, flag it:
   `> ⚠️ Contradiction: [[source-a]] says X [C:med]; [[source-b]] says Y [C:high].`
2. **Log it.** Add a line to `questions.md` so it stays visible until resolved.
3. **Resolve when you can.** A newer, higher-credibility source usually wins — but *record
   why*, and keep the superseded claim with a note ("superseded 2026-07 by [[source-b]]")
   rather than deleting it. The history is part of the knowledge.

---

## Primary vs. secondary sources

- **Primary** — the original artifact: the paper, the codebase, the API docs, the raw
  interview, the dataset. Highest evidentiary weight.
- **Secondary** — commentary on a primary source: a summary video, a blog recap, a news
  article. Useful for orientation and framing, weak as sole evidence.
- **Tertiary** — summaries of summaries (many listicles, most "top 10" content). Use only
  to find the primary source underneath, never to cite.

When a secondary source makes a factual claim, chase it to the primary if the claim is
load-bearing. "According to a YouTube video" is where research starts, not where it ends.

---

## Keeping the vault fresh

Knowledge rots. The vault fights entropy in three ways:

1. **`review-by` dates** on time-sensitive pages, surfaced by the lint pass.
2. **`questions.md`** as a living backlog — open questions and unresolved contradictions
   stay visible instead of being forgotten.
3. **Periodic lint** — a scheduled sweep for stale claims, orphan pages, missing links, and
   over-reliance on `[C:low]` sources. Cheap to run (route it to Haiku), high-value.

A vault that's only ever added to becomes a landfill. A vault that's reviewed becomes a
reference. The difference is these three habits.

---

## The one-paragraph version

Frame the question in `questions.md`. Gather sources, preferring primary ones. Rate each
source's credibility (CRAAP) and disclose any bias. Corroborate load-bearing claims across
two independent sources; tag every claim with its confidence. Keep contradictions visible
instead of overwriting them. File everything back with citations and cross-links, and set
review dates on anything that will age. Then update the index, the log, and the open
questions — so the next session, or the next person, picks up exactly where you left off.
