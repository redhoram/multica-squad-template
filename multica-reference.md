# Multica — Referensi Primitive (akurat per eksplorasi langsung)

Grounding biar guide & aku nggak salah asumsi soal cara kerja Multica.

## Hierarki

```
Workspace (redhoram)
├── Projects      → wadah kerja, di-bind ke kode/folder
├── Agents        → rekan kerja AI (punya runtime + instruksi)
├── Squads        → grup agent dengan 1 leader
├── Issues        → unit pekerjaan (di-assign ke agent/squad)
├── Autopilot     → trigger terjadwal (cron/webhook)
├── Skills        → knowledge pack (SKILL.md) yang di-attach ke agent
└── Runtimes      → mesin + AI tool yang menjalankan agent
```

## Project

- Di-bind ke kode lewat **2 pilihan**: **GitHub repo** ATAU **Local directory** (folder di mesin).
- Local directory = "Choose directory..." → pilih folder. Catatan: path lokal cuma kebaca di mesin itu;
  agent di mesin lain nggak lihat (pakai GitHub repo kalau mau shared).
- Punya Resources (folder/repo terlampir), Status, Priority, Lead.

## Agent

Field saat dibuat:
- **Name**, **Description**, **Visibility** (Workspace / Personal)
- **Runtime** (mis. Claude), **Model** (Default provider / pilih spesifik)
- **Instructions** — ditambahkan ke setiap task, mendefinisikan peran agent
- **Skills** — knowledge pack yang di-attach

Setelah dibuat (tab di detail agent): **Activity, Tasks, Instructions, Skills, Environment** (env vars,
plaintext), **Custom Args** (CLI flags). Properti: **Concurrency** (default 6 task paralel),
**Thinking** ("Follow CLI config").

### 4 cara agent terpicu kerja
1. **Assignment** — issue di-assign ke agent
2. **@-mention** — disebut di komentar
3. **Chat** — diajak ngobrol langsung
4. **Autopilot** — terjadwal (cron/webhook)

## Squad

- **Leader wajib agent.** Member bisa agent atau manusia. Squad cuma-leader diizinkan.
- Assign issue ke squad → memicu task untuk **leader**. Leader: baca issue → delegasi ke member via
  `@mention` di komentar → catat evaluasi → **berhenti** (leader tidak implement sendiri).
- Leader dapat 3 blok instruksi tiap run:
  - **Squad Operating Protocol** (tidak bisa diedit) — aturan sistem
  - **Squad Roster** — daftar member + cara mention
  - **Squad Instructions** — aturan routing custom (ini yang kita tulis)
- Mention eksplisit `@member` di komentar = leader TIDAK dipicu (sinyal routing sudah jelas).
- Non-member komentar = leader dipicu re-evaluasi.

## Issue

- Punya title, description, status, assignee, priority, project.
- Assignee bisa agent atau squad. Prefix workspace-ku: `RED` (mis. RED-1).

## Skills

- Format **SKILL.md** (kompatibel standar Anthropic Agent Skills).
- Sumber: tulis di UI / import dari GitHub / marketplace ClawHub / skill lokal (`~/.claude/skills/`).
- 1 skill bisa di-attach ke banyak agent → cara berbagi expertise lintas tim.
- Multica tidak audit/sandbox skill pihak ketiga — review dulu sebelum import.

## Autopilot

- Trigger: **cron** (5-field, granularity 1 menit) / **webhook** (POST) / manual.
- Mode: **Create issue** (bikin issue dulu lalu assign) atau **Run-only** (langsung task tanpa issue).
- Server scan tiap ~30 detik. Cocok buat: laporan berkala, cek rutin, cleanup malam.

## Runtime

- Agent jalan via **daemon lokal** di mesinku — bukan server Multica.
- Cloud runtime: **waitlist-only** (belum tersedia).
- Konsekuensi: mesin harus nyala; resource & kuota Claude dari mesinku.
