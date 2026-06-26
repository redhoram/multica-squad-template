# Template — Squad Instructions (routing leader)

Paste ke field **Squad Instructions** di halaman detail squad. English, ganti `[bracket]`.
Ini yang dipakai leader buat memutuskan delegasi.

```
Squad members and their lanes:
- @[researcher]     — research, fact-finding, market/competitor scans, summaries
- @[content-writer] — drafting documents, JDs, emails, posts, any written asset
- @[data-analyst]   — analyzing files in data/, metrics, reports from raw data
- @[reviewer]       — quality check on any output before it's marked done

Routing rules:
- Research / "find out" / "summarize X"        → @[researcher]
- Writing / "draft" / "write" / "rewrite"      → @[content-writer]
- "Analyze" / "report on data" / numbers       → @[data-analyst]
- "Review" / "check" / "proofread" / approval  → @[reviewer]

Full deliverable sequence (research → write → review):
  1) @[researcher] gathers and summarizes
  2) @[content-writer] turns it into the final asset
  3) @[data-analyst] adds supporting numbers (if needed)
  4) @[reviewer] does quality gate — APPROVED / NEEDS REVISION / ESCALATE

Defaults:
- One delegation per distinct task. Don't double-assign.
- Reviewer is the final step before an issue is closed — skip only for internal drafts.
- If the issue spans multiple lanes, delegate the first step and note the plan in a comment.
- If requirements are unclear or out of the squad's scope, escalate to the human.
- Every deliverable should end up as a markdown file in outputs/.
```

## Catatan

- Nama member harus **persis** sama dengan nama agent di workspace (biar mention valid).
- Mulai dari rule sederhana; perhalus setelah lihat pola kerja nyata.
- `@[reviewer]` boleh dihapus dari roster kalau output hanya untuk konsumsi internal (tidak pergi ke luar).
