# Scaffold notes (dev project)

Beda dari non-dev: project dev **di-scaffold dulu**, bukan folder kosong. Urutan:

1. **Scaffold stack** di folder baru, mis.:
   ```bash
   npx create-next-app@latest [nama] --ts --tailwind --app --no-src-dir --use-npm --yes
   ```
   (atau Vite / stack lain sesuai project)

2. **Drop `CLAUDE.md`** (template di folder ini) ke root repo → isi semua `[bracket]`.

3. **Tambah skeleton minimum** biar agent fokus fitur, bukan setup:
   - `lib/types.ts` (model data), `lib/db.ts` (helper store) — secukupnya, jangan implement penuh.
   - Placeholder page/route biar app jalan.

4. **Verify**: `npm run build` harus lulus.

5. **`git init` + commit pertama.**

6. Baru bind folder ini ke **Project Multica** (Local directory / GitHub repo) dan lanjut ke
   `../setup-playbook.md`.

> Ingat: yang menyatukan agent itu **CLAUDE.md**, bukan skeleton-nya. Skeleton cuma biar
> `npm install` & keputusan stack nggak makan token tiap agent.
