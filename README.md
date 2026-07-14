# BAEWORXS // LLM Wiki — Cohort Vault

> *A BAEWORXS build by **Bae** — forked for the crew. Feed it › Cite it › Compound it.*

**💬 Join the crew:** [discord.gg/4dWXPudfjm](https://discord.gg/4dWXPudfjm)

A starter kit for an **LLM-maintained knowledge base**. You curate sources and ask
questions; your LLM (Claude Code, or any agent that reads this repo) reads the sources,
extracts knowledge, and maintains an interlinked wiki of markdown files. The wiki is a
*compounding artifact* — knowledge is compiled once and kept current, not re-derived on
every query.

This is a **fresh, empty vault** built for a cohort to copy and run independently. It ships
with the structure, the operating manual, a refreshed research methodology, and one seed
page per area so the conventions are obvious.

---

## Quick start

1. **Copy this whole `vault-template/` folder** to wherever you keep your work, and rename it
   (e.g. `my-vault/`). Optionally `git init` inside it so your friends can each fork their own.
2. **Open it in Claude Code** (or point your agent at the folder). The agent reads `CLAUDE.md`
   at the start of every session — that's the contract that makes the whole thing work.
3. **Drop a source** into `raw/` — an article, a paper, a transcript, notes, an image.
4. **Ask the agent to ingest it:** *"Ingest the file I just added to raw/."* It will summarize
   the source, rate its credibility, and file it into `wiki/` with cited, confidence-tagged
   claims — updating `index.md`, `log.md`, and `questions.md` as it goes.
5. **Ask questions.** *"What do my sources say about X?"* Good answers get filed back as new
   pages, so your explorations compound instead of evaporating.
6. **Delete the 🌱 seed pages** once you have real content in an area.

---

## What's in here

| Path | What it is |
|------|-----------|
| `CLAUDE.md` | The operating manual. The agent reads this every session. Structure + conventions. |
| `METHODOLOGY.md` | The research method: the loop, source evaluation, confidence tagging, contradictions. |
| `CONTRIBUTING.md` | Hard-won lessons from running a vault. Read before you get 50 pages deep. |
| `index.md` | Catalog of every page, grouped by area. Kept current on every change. |
| `log.md` | Append-only timeline of everything the agent has done. |
| `questions.md` | The live research backlog — open questions and unresolved contradictions. |
| `raw/` | Your immutable source documents. The agent reads these; it never edits them. |
| `wiki/research/` | Deep-dives on a topic: sources, concepts, entities, an evolving synthesis. |
| `wiki/personal/` | Goals, health, journal entries, a self-overview. |
| `wiki/book/` | Reading companion: chapters, characters, themes, locations. |
| `wiki/general/` | Flexible / mixed knowledge. |

---

## The three layers (the core idea)

1. **`raw/` — sources.** Immutable source of truth. Read-only for the agent.
2. **`wiki/` — knowledge.** LLM-generated, interlinked markdown. The agent owns this entirely.
3. **`CLAUDE.md` — the rules.** How the wiki is structured and maintained. Co-evolve it as
   your conventions improve.

Sources go in, knowledge comes out, and the rules keep it consistent. That separation is
what lets the wiki stay trustworthy as it grows.

---

## What's new in this refresh

This template updates the original vault with sharper **research methods** (full detail in
`METHODOLOGY.md`):

- **A named research loop** — Frame → Discover → Triangulate → Synthesize → File back →
  Review — so anyone in the cohort runs research the same way.
- **Source credibility ratings** (`credibility: high|medium|low`) via a CRAAP checklist, with
  mandatory conflict-of-interest disclosure at the top of every source page.
- **Confidence tags on claims** (`[C:high]` / `[C:med]` / `[C:low]`) so readers know what's
  solid and what's a hypothesis.
- **Triangulation rule** — load-bearing claims need ≥2 *independent* sources before a
  synthesis can lean on them.
- **`questions.md`** — a live research backlog that keeps the vault driving forward between
  sessions instead of stalling.
- **Freshness discipline** — `review-by:` dates + a lint pass so time-sensitive claims don't
  quietly rot.

---

## Working with your agent — the operations

- **Ingest** — add a source: *"Ingest `raw/<file>`."*
- **Query** — ask a question: *"What connects X and Y across my sources?"*
- **Research** — go beyond `raw/`: *"Research <topic> on the web and file it back."*
- **Lint** — health-check: *"Do a lint pass — find stale claims, orphans, and contradictions."*

Full definitions of each are in `CLAUDE.md`.

---

## A few house rules that make this work

- **One source at a time**, discussed with you, unless you say to batch.
- **Everything gets cited and confidence-tagged.** "I don't know yet" (logged to
  `questions.md`) beats a confident guess.
- **Contradictions are kept, not overwritten.** Disagreement between sources is a finding.
- **Persist immediately.** Any decision or convention that should outlive the session gets
  written down the moment it's made.

Have fun. The vault gets more valuable every time you feed it — that's the whole point.
