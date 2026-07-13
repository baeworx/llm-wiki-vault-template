# Log

Append-only timeline of wiki activity. Each entry is prefixed for easy grep:
`grep "^## \[" log.md | tail -5` shows the last 5 events.

Prefixes: `init` · `ingest` · `query` · `research` · `lint` · `conversation`.

## [2026-07-13] init | Vault scaffolded from cohort template
Created the LLM Wiki structure: `CLAUDE.md` (schema), `METHODOLOGY.md` (research method),
`index.md`, `log.md`, `questions.md`, `raw/`, and `wiki/` with four areas (research,
personal, book, general). Added one seed page per area to demonstrate conventions. Ready
for the first source — drop a document in `raw/` and ask to ingest it.
