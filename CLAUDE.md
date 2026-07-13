# LLM Wiki — Schema & Operating Manual

This vault is an **LLM-maintained knowledge base**. A human curates sources and asks
questions; the LLM (you) reads sources, extracts knowledge, and maintains an interlinked
wiki of markdown files. The wiki is a *compounding artifact* — knowledge is compiled once
and kept current, not re-derived on every query.

**Read this file at the start of every session before touching the wiki.** For the full
research method behind these conventions, read [`METHODOLOGY.md`](METHODOLOGY.md).

---

## The three layers

1. **`raw/`** — Immutable source documents (articles, papers, notes, images, data).
   The source of truth. **You read these; you NEVER modify them.**
2. **`wiki/`** — LLM-generated markdown pages. You own this layer entirely: create pages,
   update them on new sources, maintain cross-references, keep everything consistent.
3. **This schema (`CLAUDE.md`)** — How the wiki is structured and the workflows to follow.
   Co-evolve it with the human as conventions improve.

Control files at the root: **`index.md`** (catalog), **`log.md`** (timeline), and
**`questions.md`** (the open-questions ledger — the live research backlog).

---

## Wiki structure

`wiki/` is divided into four domain areas. Each area uses the **same page conventions**
below — only the *kinds* of pages differ.

| Area | Purpose | Typical page types |
|------|---------|--------------------|
| `wiki/research/` | Deep-dive on a topic over time | source summaries, concepts, entities, **synthesis** (evolving thesis) |
| `wiki/personal/` | Goals, health, psychology, self-improvement | journal entries, themes, a self-overview |
| `wiki/book/`     | Reading companion | chapters, characters, themes, locations, timeline |
| `wiki/general/`  | Flexible / mixed knowledge | sources, concepts, entities |

Keep it flat within each area. Don't create deeper subfolders unless a domain genuinely
outgrows one level — prefer more pages over more folders.

---

## Page conventions

Every wiki page is a markdown file with YAML frontmatter:

```markdown
---
title: <Page Title>
type: source | concept | entity | synthesis | solution | fragment | journal | chapter | character | theme | overview
area: research | personal | book | general
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: [<links to raw/ files this page draws on>]
tags: [<freeform>]
summary: <one-line description — helps scanning without opening the page>
# Optional research-integrity fields (see METHODOLOGY.md):
credibility: high | medium | low   # on source pages — how much to trust it
review-by: YYYY-MM-DD              # when this page's claims should be re-checked
---

# <Page Title>

<body — use [[wikilinks]] liberally to connect related pages>
```

- **Filenames**: kebab-case, descriptive. e.g. `transformer-architecture.md`, `chapter-03.md`.
- **Links**: use Obsidian `[[wikilinks]]`. Link freely — a `[[link]]` to a page that doesn't
  exist yet is fine; it marks a page worth creating.
- **Citations**: when a claim comes from a source, link the raw file: `(see [[raw/article.md]])`.
  For web sources, use a dated inline markdown link: `([Author, 2026](https://…))`.
- **Confidence tags**: mark non-obvious claims with their support level inline:
  `[C:high]` (multiple independent sources or direct primary evidence), `[C:med]` (single
  credible source), `[C:low]` (single weak/biased source, or inference). Load-bearing claims
  should reach `[C:high]` before a synthesis leans on them — see *Triangulation* in
  [`METHODOLOGY.md`](METHODOLOGY.md).
- **Contradictions**: when a new source contradicts an existing claim, don't silently
  overwrite — note both and flag it: `> ⚠️ Contradiction: source A says X, source B says Y.`
  Then log it in `questions.md` so it doesn't get lost.
- **Solutions & fragments**: two lightweight page types for compounding knowledge fast:
  - `type: solution` — A proven fix, workaround, or procedure. Short and actionable.
  - `type: fragment` — A distilled rule or observation worth preserving across sessions.

---

## Operations

### Ingest (add a source)
1. Read the source in `raw/`. If it references images, read the text first, then view images.
2. **Evaluate the source** (CRAAP — see [`METHODOLOGY.md`](METHODOLOGY.md)) and set a
   `credibility:` rating. Note any bias or conflict of interest up front.
3. Briefly discuss key takeaways with the human.
4. Write/update a **source summary** page in the relevant `wiki/<area>/`, tagging claims
   with confidence markers.
5. Update or create **entity / concept** pages the source touches (a single source may touch
   many pages). Maintain cross-references both ways.
6. For research: revise the **synthesis** page if the new source shifts the thesis. If it
   contradicts an existing claim, flag it and add to `questions.md`.
7. Update **`index.md`**, append an entry to **`log.md`**, and prune/add to **`questions.md`**.

### Query (ask a question)
1. Read `index.md` first to find relevant pages, then drill in.
2. Synthesize an answer **with citations** to wiki pages and raw sources. State confidence.
3. If the answer is valuable, **file it back** as a new wiki page (a comparison, analysis,
   or discovered connection) so explorations compound. Then update `index.md` + `log.md`.

### Research (investigate a topic)
Follow the **research loop** in [`METHODOLOGY.md`](METHODOLOGY.md): Frame → Discover →
Triangulate → Synthesize → File back → Review.
1. Frame the question and record it in `questions.md`.
2. Use WebSearch / WebFetch to explore beyond `raw/`. Prefer primary sources; corroborate
   load-bearing claims across ≥2 independent sources.
3. Synthesize findings and discuss key points with the human.
4. File back as wiki pages — source summaries, concepts, entities, comparisons — with dated
   inline links for web content (web content isn't saved to `raw/`).
5. Update `index.md` + `log.md`; resolve or refine the entry in `questions.md`.

### Lint (health-check)
Periodically scan for: contradictions between pages, **stale claims past their `review-by`
date**, orphan pages (no inbound links), concepts mentioned but lacking a page, missing
cross-references, low-credibility claims a synthesis over-relies on, and data gaps a web
search could fill. Report findings and suggested next questions; fix what's safe to fix.
Log the pass and refresh `questions.md`.

---

## index.md, log.md & questions.md

- **`index.md`** is content-oriented: a catalog of every page, grouped by area, each with a
  link and one-line summary. Update on every ingest/file-back.
- **`log.md`** is chronological and append-only. Each entry starts with a consistent prefix
  so it's greppable: `## [YYYY-MM-DD] ingest | <title>` (or `query` / `research` / `lint`).
- **`questions.md`** is the live research backlog: open questions, unresolved contradictions,
  and pages worth creating. Add to it as you work; clear items as they're answered. This is
  what keeps the vault *driving forward* between sessions.

---

## Working style

- The human curates sources, directs analysis, and asks questions. **You do the bookkeeping**:
  summarizing, cross-referencing, filing, consistency. Touch as many pages as a change needs.
- Default to ingesting one source at a time and staying collaborative unless told to batch.
- When unsure how to file something, propose a placement and proceed — don't stall.
- **Cite everything and mark your confidence.** An uncited claim is a liability; an
  unmarked guess is worse. Prefer "I don't know yet — logged to `questions.md`" over
  a confident fabrication.
- **Persist immediately.** Any mid-session decision, convention change, or discovered pattern
  that should survive the session must be written to a wiki page or `CLAUDE.md` right away —
  don't wait until the end.

---

## Model routing (guidance, not rules)

Match the model to the operation for cost-efficiency:
- **Opus / Fable** — synthesis, analysis, research, complex queries, contradiction resolution.
- **Sonnet** — standard ingests, entity pages, comparisons.
- **Haiku** — lint passes, index/log/questions updates, tag cleanup.

The human can override anytime with `/model`. This is guidance, not enforcement.
