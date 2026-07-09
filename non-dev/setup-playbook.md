# Playbook — Setup Squad Non-Developer di Multica

Langkah dari case kosong sampai agent jalan. Ikuti urut.

## 0. Tentukan & scope case (di chat dulu)

- Apa deliverable-nya? (riset, dokumen, analisis, draft konten…)
- Cocok Multica atau cukup chat? (lihat `GUIDE-CONTEXT.md`)
- Pecah jadi lane: siapa ngerjain apa. Idealnya tiap member punya 1 jenis kerjaan jelas.

## 1. Siapkan folder project (knowledge base)

- Copy `project-template/` → rename, mis. `D:\_Git_\hr-ops`.
- Isi `CLAUDE.md`: nama project, tujuan, peran, konvensi output.
- Biarkan `outputs/` (tempat hasil) dan tambah `data/` kalau ada file sumber.
- `git init` + commit pertama — definition of done di CLAUDE.md minta commit ber-trailer;
  tanpa git init, agent nggak bisa commit.

## 2. Buat Project di Multica

- Sidebar → **Projects** → **New project**.
- Title + description.
- **Repos → Local directory → Choose directory…** → pilih folder project tadi.
- **Create Project**. Pastikan muncul di **Resources**.

## 3. Buat Agents

Untuk tiap agent (mulai dari leader):
- **Agents → New agent**.
- Name (mis. `coordinator`, `researcher`), Description singkat.
- Visibility: **Workspace**. Runtime: **Claude**. Model: pilih yang kuat untuk kualitas.
- **Instructions**: paste dari `agent-templates.md`, sesuaikan ke case.
- (Opsional) attach **Skills**.
- Create. Ulang untuk tiap member.

> Tips: mulai kecil — 1 leader + 2 member. Tambah belakangan kalau perlu.

## 4. Buat Squad

- Sidebar → **Squads → New squad**.
- Name + description, pilih **Leader** (harus agent — mis. `coordinator`).
- Di halaman detail: **tambah members** (agent-agent tadi).
- Isi **Squad Instructions** (routing) — pakai `squad-instructions-template.md`.

## 5. Tulis Issues & assign ke Squad

- **New Issue** per deliverable. Title jelas + description berisi: konteks, langkah, **definition of done**,
  dan lokasi output (`outputs/[nama].md`).
- **Assignee = Squad**. Leader akan baca & delegasi.
- Set Project = project tadi (biar agent jalan di folder yang benar).

## 6. Monitor & ambil hasil

- Lihat **Activity** / **Inbox** untuk progress.
- Hasil agent muncul sebagai **komentar di issue** + file di **`outputs/`**.
- Review, kasih feedback via komentar (mention agent kalau perlu revisi).

## 7. (Opsional) Otomatisasi

- Untuk task berulang (laporan mingguan): **Autopilot** → cron → assign ke squad/agent.

---

### Checklist cepat

- [ ] Folder project + CLAUDE.md + outputs/
- [ ] Project di Multica (local dir bound)
- [ ] Leader agent + member agents
- [ ] Squad (leader + members + instructions)
- [ ] Issues (assign ke squad, set project)
- [ ] Monitor & review hasil
