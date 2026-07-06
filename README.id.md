<p align="center">
  <img src="https://img.shields.io/badge/Built%20for-Multica%20AI%20Squad-D97757" alt="Built for Multica AI Squad">
  <img src="https://img.shields.io/badge/Tracks-Dev%20%2B%20Non--Dev-informational" alt="Dev + Non-Dev Tracks">
  <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT License">
</p>

<p align="center">
  <a href="README.md">English</a> | <a href="README.id.md">Bahasa Indonesia</a>
</p>

---

# multica-squad-template

Context pack + template untuk menjalankan **squad AI agent di [Multica](https://multica.ai)**.
Dua track: **dev** (coding) dan **non-dev** (riset / konten / analisis).

Ini **bukan** template kode (beda dari [`_pipeline-template`](https://github.com/redhoram/claude-pipeline-template) / [`_landing-template`](https://github.com/redhoram/claude-landing-template)). Isinya
file konteks biar Claude bisa jadi guide-mu, plus template instruksi agent yang tinggal diisi.

### Mental model

```
Claude Chat / Cowork   = GUIDE       → bantu mikir, scope, scaffold, nulis instruksi agent
Multica                = WORKSPACE   → tempat agent beneran jalan & nyimpan hasil
```

### Pilih track

| | **dev/** | **non-dev/** |
|---|---|---|
| Untuk | Coding (CRUD, app, fitur) | Riset, konten, analisis, laporan |
| Output | Kode di repo (atau PR) | Dokumen `.md` di `outputs/` |
| Agent | PM · Designer · Backend · Frontend · QA | Coordinator · Researcher · Writer · Analyst · Reviewer |
| Project folder | **Scaffold dulu** + CLAUDE.md | Folder knowledge-base + CLAUDE.md |
| Nyambung ke | `_pipeline-template` (bisa nested) | — |

### Struktur

```
multica-squad-template/
├── multica-reference.md         ← SHARED: primitive Multica yang akurat (dipakai dua track)
├── dev/
│   ├── GUIDE-CONTEXT.md             ⭐ upload ini buat sesi coding
│   ├── setup-playbook.md
│   ├── agent-templates.md           (PM · Designer · Backend · Frontend · QA)
│   ├── squad-instructions-template.md
│   └── project-template/            (CLAUDE.md + SCAFFOLD-NOTES.md)
└── non-dev/
    ├── GUIDE-CONTEXT.md             ⭐ upload ini buat sesi non-coding
    ├── setup-playbook.md
    ├── agent-templates.md           (Coordinator · Researcher · Writer · Analyst · Reviewer)
    ├── squad-instructions-template.md
    └── project-template/            (CLAUDE.md + outputs/)
```

### Cara pakai

1. Buka sesi Claude baru → **upload `<track>/GUIDE-CONTEXT.md` + `multica-reference.md`**.
2. Cerita case → Claude bantu putuskan: cocok Multica atau cukup chat / Claude Code langsung?
3. Kalau cocok → copy `<track>/project-template/` → isi `CLAUDE.md` → ikuti `setup-playbook.md`.
4. Instruksi agent & squad ambil dari template, ganti `[bracket]`.

### Keputusan desain penting

- **Beri nama orang ke tiap agent** (mis. Jaya, Citra) — git history kebaca seperti tim beneran.
- **Co-author trailer** di tiap commit — jejak "dibangun bareng squad AI" kelihatan di GitHub.
- **Reviewer/QA sebagai quality gate** — output belum selesai sampai lolos review.
- **Prosa Indonesia, instruksi agent English** — agent lebih reliable merespons prompt English.

### Cocok dipakai bersama

- [`_pipeline-template`](https://github.com/redhoram/claude-pipeline-template) — pipeline 5-tahap untuk fitur kompleks (bisa nested di dalam agent Multica)
- [`_landing-template`](https://github.com/redhoram/claude-landing-template) — visual loop untuk landing page & app sederhana

### Kredit

**Author**
- Redho Ramadhani — [linkedin.com/in/redhoramadhanihamid](https://id.linkedin.com/in/redhoramadhanihamid) · [github.com/redhoram](https://github.com/redhoram)

Dibangun dengan [Claude Code](https://claude.com/claude-code) untuk dipakai bersama [Multica](https://multica.ai).
