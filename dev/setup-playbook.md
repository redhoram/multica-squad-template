# Playbook — Setup Squad Developer di Multica

Dari fitur/project sampai agent ngoding. Ikuti urut. Beda utama dari non-dev: **scaffold dulu**.

## 0. Validasi (di chat)

- Perlu Multica, atau cukup Claude Code / `_pipeline-template` `/ship`? (lihat `GUIDE-CONTEXT.md`)
- Kalau perlu Multica: pecah jadi lane — backend / frontend / qa.

## 1. Scaffold skeleton + CLAUDE.md  ⬅️ langkah kunci

- Scaffold stack (mis. `npx create-next-app`, atau Vite). Pastikan `npm run build` lulus.
- Drop `project-template/CLAUDE.md` → isi: stack, model data, konvensi, **lane per agent**, definition of done.
- Tambah skeleton minimum (types, helper db) biar agent fokus fitur — **bukan** implement penuh.
- `git init` + commit pertama.
- Verifikasi jalan (dev server / build) sebelum lanjut.

## 2. Buat Project di Multica

- **Projects → New project** → title + description.
- **Repos**:
  - **Local directory** → pilih folder repo (simpel, 1 mesin), ATAU
  - **GitHub repos** → paste URL (kalau mau PR / multi-mesin / review).
- **Create Project**. Cek muncul di **Resources**.

## 3. Buat Agents

Per agent (mulai leader):
- **Agents → New agent** → Name (`pm-lead`, `backend-dev`, …), Description.
- Visibility **Workspace**, Runtime **Claude**, **Model: pilih yang kuat buat coding**.
- **Instructions**: paste dari `agent-templates.md`, sesuaikan stack. Tegaskan **verify sebelum selesai**.
- Create. Ulang.

> Mulai kecil: leader + 2 (backend, frontend). Tambah qa kalau perlu.

## 4. Buat Squad

- **Squads → New squad** → name, **Leader = agent** (`pm-lead`).
- Tambah members. Isi **Squad Instructions** (routing) dari `squad-instructions-template.md`.

## 5. Tulis Issues & assign

- **New Issue** per fitur. Description: konteks, langkah, **acceptance criteria**, file yang disentuh.
- **Assignee = Squad**, set **Project**.
- Untuk fitur penuh: urutkan (backend dulu → frontend → qa) biar nggak bentrok / asumsi kosong.

## 6. Monitor, review, verify

- Pantau **Activity/Inbox**. Hasil = komentar issue + perubahan di repo (atau PR kalau GitHub).
- **Jangan percaya "selesai" tanpa bukti** — minta agent tunjukkan build/test lulus.
- Review diff. Feedback via komentar (mention agent buat revisi).

## 7. (Opsional) Otomatisasi

- Autopilot buat task berulang: nightly build, dependency/security check, dll.

---

### Checklist

- [ ] Skeleton scaffolded + CLAUDE.md + build lulus + git init
- [ ] Project di Multica (repo/local dir bound)
- [ ] Leader + member agents (model coding kuat, instruksi "verify")
- [ ] Squad + routing instructions
- [ ] Issues (acceptance criteria, assign ke squad, sequence)
- [ ] Review diff + verify build sebelum terima
