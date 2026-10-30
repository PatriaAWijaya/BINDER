# Status BINDER — Gerbang Fase 0

Tanggal mulai: 30 Oktober 2026.
Repo: PatriaAWijaya/BINDER (privat).
PRD acuan: PRD BINDER v1.3, Drive MIMI/BINDER (DRAF).

## Revisi pagu — keputusan Patria 30 Oktober 2026

Pagu harga DITANGGUHKAN. Tiap model punya billing sendiri yang dipantau Patria
tiap bulan, dan pagu baru dipatok setelah Patria mengamati kebutuhan riil di
lapangan. Selama ditangguhkan, ambang 70/90 persen dan hard stop 100 persen PRD
berlaku setelah pagu dipatok; kontrol interim adalah ledger per task + review
mingguan + pantauan billing bulanan Patria. Gate tidak boleh mengklaim hard stop
otomatis atas pagu yang belum ditetapkan.

## Checklist Gerbang Fase 0 (gerbang keseluruhan belum lolos)

- [x] Verifikasi LICENSE Paperclip (MIT) dari repo yang dipakai — terverifikasi 30 Okt 2026, commit clone b3c2172.
- [x] Verifikasi LICENSE OpenMausBot (Apache-2.0) dari repo yang dipakai — terverifikasi 30 Okt 2026, versi 0.1.134, commit clone 0213b74.
- [ ] Verifikasi lisensi dependensi DeepBrain (pola Brain/agentic-stack); bila tidak memungkinkan, bangun ulang polanya tanpa menyalin kode yang lisensinya tidak jelas.
- [ ] Pin versi Paperclip, plugin SDK, MausBot, dan DeepBrain MCP.
- [ ] Verifikasi harga sandbox (Modal/Daytona), Boat bila dipakai, dan langganan CLI.
- [ ] Pagu total pilot — DITANGGUHKAN per keputusan Patria 30 Okt 2026 (bukan dibatalkan); dipatok setelah observasi kebutuhan riil.
- [ ] Uji live jalur Meta lewat OpenCode di dalam Paperclip (dan di MausBot bila dipakai di sana); catat lolos/gagal apa adanya. Bukti yang sudah ada baru panggilan API langsung di hackathon, bukan bukti jalur di dalam Paperclip/MausBot.
- [ ] Vonis Patria: Gerbang Fase 0 lolos atau tidak.

## Clone inspeksi (selesai 30 Oktober 2026)

- `paperclipai/paperclip` — commit b3c2172, LICENSE MIT terverifikasi.
- `milind-soni/OpenMausBot` — commit 0213b74 (v0.1.134), LICENSE Apache-2.0 terverifikasi.

Clone ini hanya untuk inspeksi Gerbang Fase 0, bukan install dan bukan build.

## Dokumen teknis (DRAF v0.1, direvisi pagu 30 Oktober 2026)

TRD, AppFlow, Backend Schematic, dan Rencana Kerja (Tahap 0–13) ada sebagai
Google Doc di Drive MIMI/BINDER, dengan catatan revisi pagu yang sama seperti
di atas. Salinan lokal ada di folder project-binder.

## Yang belum ada di repo ini

- Kode Binder Sync, Binder Gate, dan DeepBrain (dibangun setelah Gerbang Fase 0).
- File LICENSE BINDER (belum diputuskan Patria).
