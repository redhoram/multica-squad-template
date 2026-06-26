# [PROJECT NAME] — Project Instructions

> Drop file ini ke ROOT repo yang sudah di-scaffold (mis. hasil `create-next-app`).
> Ganti SEMUA `[bracket]`. Ini yang menyatukan semua agent squad — isi dengan jelas.
> Kamu nggak perlu bisa coding: isi bagian yang kamu paham (tujuan, brand, nama agent),
> sisanya (stack, data model) biar agent yang bantu lengkapi saat issue pertama.

[1-2 kalimat: project ini apa, untuk siapa, tujuannya.]

## Stack

- Framework: [e.g. Next.js 16 (App Router)] — ⚠️ kalau versi baru, ingatkan agent baca docs resmi dulu.
- UI: [e.g. React 19 + Tailwind v4]
- Data: [e.g. JSON file store / Prisma + SQLite / Supabase]
- [hapus/tambah baris sesuai kebutuhan]

## Data model

[Definisikan entitas inti + tipe. Taruh di `lib/types.ts` dan rujuk dari sini.]

## What to build (squad lanes)

- **[backend-dev]** — [API routes / data layer apa]. Pakai helper di `lib/`.
- **[designer]** — [design spec untuk layar/komponen apa]: layout, token warna, state interaksi. Tulis spec SEBELUM frontend coding. (Hapus lane ini kalau project tanpa UI.)
- **[frontend-dev]** — [screens/komponen apa]. Ikuti design spec dari designer. Panggil endpoint dari backend-dev (jangan karang endpoint).
- **[qa]** — jalankan app, test flow [apa], verify acceptance criteria, lapor bug.

## Brand & Design

> Isi kalau project punya UI. Designer ([nama]) yang menyusun & menjaga bagian ini.
> Kalau brand belum ada, minta designer propose dulu sebelum frontend mulai.

**Palette:**
- Primary: [hex] (hover [hex])
- [tambah warna netral / aksen sesuai brand]

**Typography:**
- [Font heading] — judul, angka, badge
- [Font body] — teks, label, input, tombol

**Theme:** [light only / dark only / day-night toggle]
[Kalau day-night toggle: simpan preferensi di `localStorage`, dan set
`document.documentElement.style.colorScheme` saat ganti tema — biar elemen form
native (input, select) ikut warna tema.]

## Conventions

- Code & komentar: English. Komunikasi dgn user: [Indonesia / English].
- TypeScript strict, no `any`. Komponen kecil & fokus.
- **Verify wajib**: `npm run build` harus lulus sebelum nandai selesai. Tunjukkan buktinya di komentar.
- Jangan commit `.env*` atau secret. [Runtime data yang di-gitignore: ...]
- Agent paralel: jangan sentuh file yang sama bersamaan — sequence kalau overlap.

## Agent Squad

Project ini dibangun oleh squad AI agent di Multica. Tiap agent punya lane jelas (lihat *What to build*).
Kasih nama tiap agent — bikin git history kebaca seperti tim beneran.

| Role | Nama agent | Tugas |
|---|---|---|
| `pm-lead` | **[nama]** | Spec, delegasi, review akhir (SHIP / NEEDS WORK / BLOCK) |
| `designer` | **[nama]** | Design spec & design system sebelum frontend (hapus kalau tanpa UI) |
| `backend-dev` | **[nama]** | API, data layer, validasi |
| `frontend-dev` | **[nama]** | UI, komponen, halaman |
| `qa` | **[nama]** | Testing end-to-end, laporan bug |

### Commit convention

Tiap commit agent diakhiri trailer co-author. Tujuannya: jejak **"dibangun bareng squad AI"**
kelihatan di git history — bukti portofolio, walau kamu sendiri nggak nulis kodenya.

```
Co-Authored-By: [Nama] (AI Agent) <[role]@multica.ai>
```

Contoh (agent backend): `Co-Authored-By: [nama] (AI Agent) <backend-dev@multica.ai>`

> Author utama commit tetap **kamu** (akun GitHub-mu). Co-author cuma penanda kolaborasi —
> agent tampil sebagai kontributor, kepemilikan repo tetap di tangan kamu.

## Definition of done

- [ ] Fitur sesuai acceptance criteria di issue.
- [ ] `npm run build` lulus (bukti di komentar).
- [ ] Diff bersih, konvensi diikuti, nggak ada console error.
- [ ] (UI) Sesuai design spec & brand palette di atas.
- [ ] Commit pakai trailer co-author yang benar.
