# [PROJECT NAME] — Project Instructions

> Drop file ini ke ROOT repo yang sudah di-scaffold (mis. hasil `create-next-app`).
> Ganti SEMUA `[bracket]`. Ini yang menyatukan semua agent squad — isi dengan jelas.

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
- **[frontend-dev]** — [screens/komponen apa]. Panggil endpoint dari backend-dev (jangan karang endpoint).
- **[qa]** — jalankan app, test flow [apa], verify acceptance criteria, lapor bug.

## Conventions

- Code & komentar: English. Komunikasi dgn user: [Indonesia / English].
- TypeScript strict, no `any`. Komponen kecil & fokus.
- **Verify wajib**: `npm run build` harus lulus sebelum nandai selesai. Tunjukkan buktinya di komentar.
- Jangan commit `.env*` atau secret. [Runtime data yang di-gitignore: ...]
- Agent paralel: jangan sentuh file yang sama bersamaan — sequence kalau overlap.

## Definition of done

- [ ] Fitur sesuai acceptance criteria di issue.
- [ ] `npm run build` lulus (bukti di komentar).
- [ ] Diff bersih, konvensi diikuti, nggak ada console error.
