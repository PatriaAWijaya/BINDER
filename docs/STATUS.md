# Status BINDER — Gerbang Fase 0

Tanggal mulai: 30 Oktober 2026.
Repo: PatriaAWijaya/BINDER (privat).
PRD acuan: PRD BINDER v1.4, Drive MIMI/BINDER (DRAF — revisi arsitektur satu aplikasi).

## Revisi arsitektur v1.4 — keputusan Patria 30 Oktober 2026

BINDER adalah satu aplikasi baru yang merekonstruksi ulang kelebihan
Paperclip dan MausBot menjadi satu sistem, BUKAN integrasi dua runtime.
DeepBrain adalah bagian utama BINDER yang bersifat PnP: terpasang secara
default di BINDER dan bisa dijalankan terpisah bila dibutuhkan, lewat
MCP/CLI dan file git yang sama, tanpa mengubah Core.
Sync dan Gate menjadi modul internal di dalam aplikasi baru (lihat
`internal-sync/README.md`).
Jalur kode (fork kode MIT/Apache lalu modifikasi vs bangun ulang bersih
terinspirasi pola) BELUM diputuskan dan diputuskan di Gerbang Fase 0
sebelum build.

## Repo BINDER menjadi PUBLIK — keputusan Patria 30 Oktober 2026

PatriaAWijaya/BINDER diubah dari privat menjadi publik. Dokumen teknis
di Drive sudah naik ke v0.3 dan selaras dengan keputusan terbaru: fork,
BINDER publik, dan DeepBrain (desain boleh publik, kode/repo privat).

## Revisi pagu — keputusan Patria 30 Oktober 2026

Pagu harga DITANGGUHKAN. Tiap model punya billing sendiri yang dipantau Patria
tiap bulan, dan pagu baru dipatok setelah Patria mengamati kebutuhan riil di
lapangan. Selama ditangguhkan, ambang 70/90 persen dan hard stop 100 persen PRD
berlaku setelah pagu dipatok; kontrol interim adalah ledger per task + review
mingguan + pantauan billing bulanan Patria. Gate tidak boleh mengklaim hard stop
otomatis atas pagu yang belum ditetapkan.

## Checklist Gerbang Fase 0 (gerbang keseluruhan belum lolos)

- [x] Verifikasi LICENSE Paperclip (MIT) dari repo yang dipakai — terverifikasi 30 Okt 2026, commit clone b3c2172 (kini pola acuan Inti Perusahaan).
- [x] Verifikasi LICENSE OpenMausBot (Apache-2.0) dari repo yang dipakai — terverifikasi 30 Okt 2026, versi 0.1.134, commit clone 0213b74 (kini pola acuan Mesin Desktop).
- [ ] Verifikasi lisensi dependensi DeepBrain (pola Brain/agentic-stack); bila tidak memungkinkan, bangun ulang polanya tanpa menyalin kode yang lisensinya tidak jelas.
- [x] Keputusan jalur kode — DIPUTUSKAN 30 Okt 2026: fork dulu lalu modifikasi. UI dan semua fungsi awal dipertahankan; modifikasi hanya bila Patria memerintahkan. Dimulai dari Paperclip sebagai rancangan organisasi utama Binder. Fork lokal: `~/workspace/binder-fork/paperclip` (commit b3c2172, bersih, tanpa modifikasi); destinasi fork remote belum diputuskan.
- [ ] Pin versi DeepBrain MCP dan dependensi yang dipakai; pin upstream hanya bila jalur fork diputuskan.
- [ ] Verifikasi harga sandbox (Modal/Daytona), Boat bila dipakai, dan langganan CLI.
- [ ] Pagu total pilot — DITANGGUHKAN per keputusan Patria 30 Okt 2026 (bukan dibatalkan); dipatok setelah observasi kebutuhan riil.
- [ ] Uji live jalur Meta lewat OpenCode di dalam aplikasi BINDER baru; catat lolos/gagal apa adanya. Bukti yang sudah ada baru panggilan API langsung di hackathon, bukan bukti jalur di dalam aplikasi baru.
- [x] Fork remote — DIBUAT 30 Okt 2026: PatriaAWijaya/BINDER-paperclip (https://github.com/PatriaAWijaya/BINDER-paperclip), fork dari paperclipai/paperclip, branch default master, HEAD master = b3c2172 (tree identik dengan baseline lokal; HEAD upstream saat fork dibuat sudah maju ke 81ebe47 dan sengaja di-reset ke baseline). Sifat: PUBLIK (fork dari repo publik). UI dan fungsi awal belum diubah.
- [ ] Vonis Patria: PRD v1.4 disetujui dan Gerbang Fase 0 lolos atau tidak.

## Clone inspeksi (selesai 30 Oktober 2026)

- `paperclipai/paperclip` — commit b3c2172, LICENSE MIT terverifikasi.
- `milind-soni/OpenMausBot` — commit 0213b74 (v0.1.134), LICENSE Apache-2.0 terverifikasi.

Clone ini hanya untuk inspeksi Gerbang Fase 0, bukan install dan bukan build.

## Dokumen teknis (DRAF v0.2, revisi arsitektur 30 Oktober 2026)

TRD, AppFlow, Backend Schematic, Rencana Kerja, dan Rencana Pengerjaan Detail
ada sebagai Google Doc di Drive MIMI/BINDER, selaras dengan PRD v1.4.
Salinan lokal ada di folder project-binder.

## Aturan visibilitas DeepBrain (keputusan Patria 30 Okt 2026)

README desain DeepBrain boleh tetap di repo publik ini. Kode dan repo
DeepBrain nanti bersifat privat.

## Yang belum ada di repo ini

- Kode aplikasi BINDER baru, Sync & Gate Internal, dan DeepBrain (dibangun setelah Gerbang Fase 0).
- File LICENSE BINDER (belum diputuskan Patria).
