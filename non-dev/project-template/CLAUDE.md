# [PROJECT NAME] — Project Instructions

> Copy folder ini, rename, lalu ganti SEMUA `[bracket]`. Ini knowledge-base project untuk
> squad agent Multica (non-coding). Bukan aplikasi — outputnya dokumen, bukan fitur.
> Kamu nggak perlu bisa coding: isi bagian yang kamu paham (tujuan, domain, nama agent),
> sisanya biar agent yang mengeksekusi.

## Tujuan

[1-2 kalimat: project ini buat apa, hasil akhirnya apa, buat siapa.]

**Domain:** [HR / Marketing / Finance / Operations / Research / lainnya]

## Output conventions (PENTING)

- Semua deliverable ditulis sebagai **markdown** ke folder `outputs/`.
- Penamaan: `outputs/[topik]-[YYYY-MM].md` (mis. `competitor-scan-2026-07.md`).
- File sumber / input taruh di `data/` (CSV, dokumen, dll).
- Tiap output **self-contained**: ada judul, tanggal, ringkasan di atas, dan sumber di bawah.

## Roles (lanes)

- **[coordinator]** — leader: baca issue, delegasi, tidak mengerjakan sendiri.
- **[researcher]** — [riset & rangkum apa]. (hapus kalau tidak perlu)
- **[content-writer]** — [tulis aset apa]. (hapus kalau tidak perlu)
- **[data-analyst]** — [analisis data apa]. (hapus kalau tidak perlu)
- **[reviewer]** — quality gate sebelum output selesai: cek brief terpenuhi, klaim valid,
  bahasa tepat untuk domain. Wajib kalau output keluar ke luar (email, laporan, dll).

## Conventions

- Bahasa output: **[Indonesia / English]**.
- Selalu **cantumkan sumber**; pisahkan fakta vs opini/inferensi.
- **Jangan mengarang** data atau sumber. Flag ketidakpastian.
- Kalau brief kurang jelas → tanya via komentar issue, jangan asal jalan.
- Reviewer wajib approve sebelum issue ditandai selesai (kecuali draft internal).

## Agent Squad

Project ini dijalankan oleh squad AI agent di Multica. Kasih nama tiap agent — output di repo
jadi kebaca seperti hasil kerja tim beneran.

| Role | Nama agent | Tugas |
|---|---|---|
| `coordinator` | **[nama]** | Lead — baca issue, delegasi, review akhir |
| `researcher` | **[nama]** | Riset & rangkum (hapus kalau tidak dipakai) |
| `content-writer` | **[nama]** | Tulis dokumen, email, aset konten |
| `data-analyst` | **[nama]** | Analisis data, laporan angka |
| `reviewer` | **[nama]** | Quality gate — APPROVED / NEEDS REVISION / ESCALATE |

### Commit convention

Tiap commit agent diakhiri trailer co-author. Tujuannya: jejak **"dibangun bareng squad AI"**
kelihatan di git history — bukti portofolio, walau kamu sendiri nggak nulis outputnya.

```
Co-Authored-By: [Nama] (AI Agent) <[role]@multica.ai>
```

Contoh: `Co-Authored-By: [nama] (AI Agent) <researcher@multica.ai>`

> Author utama commit tetap **kamu** (akun GitHub-mu). Co-author cuma penanda kolaborasi.

## Definition of done

Sebuah issue selesai kalau:
- [ ] Deliverable ada di `outputs/` sesuai penamaan.
- [ ] Ringkasan singkat diposting sebagai komentar issue.
- [ ] Sumber tercantum & klaim bisa diverifikasi.
- [ ] Reviewer sudah posting APPROVED (kalau output keluar ke luar).
- [ ] Commit pakai trailer co-author yang benar.
