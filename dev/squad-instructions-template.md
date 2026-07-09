# Template — Squad Instructions (routing leader, dev)

Paste ke field **Squad Instructions** di detail squad. English, ganti `[bracket]`.

```
Squad members and their lanes:
- @[backend-dev]   — data model, API routes, server logic, migrations
- @[designer]      — design spec, design system, UI/UX decisions (before frontend codes)
- @[frontend-dev]  — UI, components, pages, styling, client state
- @[qa]            — running the app, testing flows, reviewing diffs, bug reports

Routing rules:
- Schema / API / data / server work          → @[backend-dev]
- Design / layout / visual / UX spec          → @[designer]
- UI / component / page / styling work        → @[frontend-dev]
- "test" / "verify" / "review" / QA           → @[qa]

Full feature (spans lanes): sequence to avoid conflicts and missing dependencies:
  1) @[backend-dev] builds the API/data first
  2) @[designer] writes the design spec (only if the feature has UI)
  3) @[frontend-dev] builds UI against that API, following the design spec
  4) @[qa] verifies the end-to-end flow

Defaults:
- One delegation per task; don't double-assign the same file area in parallel.
- If two members must touch the same files, sequence them, don't run in parallel.
- Every delegated task must end with a passing build (`npm run build`) before it's done.
- Before closing an issue, check the member posted build/test evidence in a comment;
  if it's missing, ask them for it — don't accept "done" without proof.
- If requirements are unclear or out of scope, escalate to the human in an issue comment.
```

## Catatan

- Nama member harus **persis** sama dgn nama agent di workspace.
- Bentrok file = penyebab utama run dev paralel gagal → sequence kalau area kerja overlap.
