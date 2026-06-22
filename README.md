# _multica-template

Context pack + template untuk menjalankan **squad agent di [Multica](https://multica.ai)**.
Dua track: **dev** (coding) dan **non-dev** (riset/konten/analisis).

Ini **bukan** template kode (beda dari `_pipeline-template` / `_landing-template`). Isinya konteks
biar Claude jadi guide-mu, plus template instruksi yang tinggal diisi saat case ditentukan.

## Mental model

```
Claude Chat / Cowork   = GUIDE       → bantu mikir, scope, scaffold, nulis instruksi agent
Multica                = WORKSPACE   → tempat agent beneran jalan & nyimpan hasil
```

## Pilih track

| | **dev/** | **non-dev/** |
|---|---|---|
| Untuk | Coding (CRUD, app, fitur) | Riset, konten, analisis, laporan |
| Output | Kode di repo (atau PR) | Dokumen `.md` di `outputs/` |
| Agent | backend / frontend / qa | researcher / writer / analyst |
| Project folder | **Scaffold dulu** + CLAUDE.md | Folder knowledge-base + CLAUDE.md |
| Nyambung ke | `_pipeline-template` (bisa nested) | — |

## Struktur

```
_multica-template/
├── multica-reference.md     ← SHARED: primitive Multica yang akurat (dipakai dua track)
├── dev/
│   ├── GUIDE-CONTEXT.md         ⭐ upload ini buat sesi coding
│   ├── setup-playbook.md
│   ├── agent-templates.md
│   ├── squad-instructions-template.md
│   └── project-template/        (CLAUDE.md + SCAFFOLD-NOTES.md)
└── non-dev/
    ├── GUIDE-CONTEXT.md         ⭐ upload ini buat sesi non-coding
    ├── setup-playbook.md
    ├── agent-templates.md
    ├── squad-instructions-template.md
    └── project-template/        (CLAUDE.md + outputs/)
```

## Cara pakai

1. Buka room Claude baru → **upload `<track>/GUIDE-CONTEXT.md` + `multica-reference.md`**.
2. Cerita case → Claude bantu putuskan: cocok Multica atau cukup chat / Claude Code langsung?
3. Kalau cocok → copy `<track>/project-template/` → isi `CLAUDE.md` → ikuti `setup-playbook.md`.
4. Instruksi agent & squad ambil dari template, ganti `[bracket]`.

## Konvensi bahasa

- Prosa & penjelasan: **Bahasa Indonesia**
- Blok copy-paste ke Multica (instruksi agent, CLAUDE.md): **English** (lebih reliable buat agent)

## Workspace-ku (Multica)

`redhoram` · runtime cuma **Claude (lokal, 1 mesin)** · cloud runtime waitlist · mesin harus nyala saat agent kerja.
