# Status BINDER — Gerbang Fase 0

Tanggal mulai: 30 Oktober 2026.
Repo: PatriaAWijaya/BINDER (privat).
PRD acuan: PRD BINDER v1.3, Drive MIMI/BINDER (DRAF).

## Checklist Gerbang Fase 0 (semua belum lolos)

- [ ] Verifikasi LICENSE Paperclip (MIT) dari repo yang dipakai.
- [ ] Verifikasi LICENSE OpenMausBot (Apache-2.0) dari repo yang dipakai.
- [ ] Verifikasi lisensi dependensi DeepBrain (pola Brain/agentic-stack); bila tidak memungkinkan, bangun ulang polanya tanpa menyalin kode yang lisensinya tidak jelas.
- [ ] Pin versi Paperclip, plugin SDK, MausBot, dan DeepBrain MCP.
- [ ] Verifikasi harga sandbox (Modal/Daytona), Boat bila dipakai, dan langganan CLI.
- [ ] Patria menetapkan pagu total pilot.
- [ ] Uji live jalur Meta lewat OpenCode di dalam Paperclip (dan di MausBot bila dipakai di sana); catat lolos/gagal apa adanya.
- [ ] Vonis Patria: Gerbang Fase 0 lolos atau tidak.

## Clone inspeksi (berjalan, belum selesai saat commit awal ini)

- `paperclipai/paperclip`
- `milind-soni/OpenMausBot`

Clone ini hanya untuk inspeksi Gerbang Fase 0, bukan install dan bukan build.
Hasil verifikasi lisensi/versi akan dicatat di `upstream/README.md` setelah
clone selesai, dan commit awal ini TIDAK mengklaim verifikasi itu sudah lolos.

## Yang belum ada di repo ini

- Kode Binder Sync, Binder Gate, dan DeepBrain (dibangun setelah Gerbang Fase 0).
- TRD, AppFlow, Backend Schematic, dan Rencana Kerja (disusun sebagai draf terpisah, menyusul).
- File LICENSE BINDER (belum diputuskan Patria).
