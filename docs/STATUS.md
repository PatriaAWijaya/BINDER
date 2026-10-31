# Status BINDER — Gerbang Fase 0

Tanggal mulai: 30 Oktober 2026.
Repo: PatriaAWijaya/BINDER (PUBLIK sejak 30 Oktober 2026).
PRD acuan: PRD BINDER v1.4, Drive MIMI/BINDER (DISETUJUI — vonis 0A Patria 30 Oktober 2026).

## Revisi arsitektur v1.4 — keputusan Patria 30 Oktober 2026

BINDER adalah satu aplikasi baru yang merekonstruksi ulang kelebihan
Paperclip dan MausBot menjadi satu sistem, BUKAN integrasi dua runtime.
DeepBrain adalah bagian utama BINDER yang bersifat PnP: terpasang secara
default di BINDER dan bisa dijalankan terpisah bila dibutuhkan, lewat
MCP/CLI dan file git yang sama, tanpa mengubah Core.
Sync dan Gate menjadi modul internal di dalam aplikasi baru (lihat
`internal-sync/README.md`).
Jalur kode DIPUTUSKAN di Gerbang Fase 0 (30 Oktober 2026): fork dulu lalu
modifikasi; UI dan semua fungsi awal dipertahankan, modifikasi hanya bila
Patria memerintahkan.

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

## Checklist Gerbang Fase 0 — LOLOS DENGAN CATATAN (vonis Patria 31 Oktober 2026)

Catatan vonis yang tetap berlaku (bukan syarat yang membatalkan lolosnya gerbang,
melainkan pekerjaan/keputusan yang dibawa ke depan):
- Pagu total pilot tetap DITANGGUHKAN; hard stop otomatis belum bisa jalan penuh
  tanpa angka pagu; kontrol interim = ledger per task + review mingguan +
  pantauan billing bulanan Patria.
- Harga langganan CLI belum terverifikasi karena model CEO belum diputuskan
  (Meta via OpenCode vs Claude langsung).
- Pin versi + lisensi wajib diverifikasi dulu bila ada dependensi DeepBrain
  yang diimpor; selama ini DeepBrain dibangun sebagai file + MCP sendiri.
- Uji live Meta di dalam aplikasi baru masih menunggu build pertama yang bisa jalan.
- Keputusan yang masih menunggu vonis Patria: provider sandbox (Modal vs Daytona),
  model CEO, default VM pilot (Local VM Docker/Podman vs Boat), Pocket pertama,
  model ekstraksi Distiller, bobot skor Pocket, nama perusahaan final + proyek
  pilot pertama, anggaran token, dan detail kadens Leads.
- Modifikasi kode fork tetap hanya atas perintah spesifik Patria; lolosnya gerbang
  BUKAN perintah modifikasi.

- [x] Verifikasi LICENSE Paperclip (MIT) dari repo yang dipakai — terverifikasi 30 Okt 2026, commit clone b3c2172 (kini pola acuan Inti Perusahaan).
- [x] Verifikasi LICENSE OpenMausBot (Apache-2.0) dari repo yang dipakai — terverifikasi 30 Okt 2026, versi 0.1.134, commit clone 0213b74 (kini pola acuan Mesin Desktop).
- [ ] Verifikasi lisensi dependensi DeepBrain (pola Brain/agentic-stack); bila tidak memungkinkan, bangun ulang polanya tanpa menyalin kode yang lisensinya tidak jelas.
- [x] Keputusan jalur kode — DIPUTUSKAN 30 Okt 2026: fork dulu lalu modifikasi. UI dan semua fungsi awal dipertahankan; modifikasi hanya bila Patria memerintahkan. Dimulai dari Paperclip sebagai rancangan organisasi utama Binder. Fork lokal: `~/workspace/binder-fork/paperclip` (commit b3c2172, bersih, tanpa modifikasi); fork remote: PatriaAWijaya/BINDER-paperclip (lihat butir fork remote di bawah).
- [ ] Pin versi DeepBrain MCP dan dependensi yang dipakai; pin upstream hanya bila jalur fork diputuskan.
- [ ] Verifikasi harga sandbox (Modal/Daytona), Boat bila dipakai, dan langganan CLI.
- [ ] Pagu total pilot — DITANGGUHKAN per keputusan Patria 30 Okt 2026 (bukan dibatalkan); dipatok setelah observasi kebutuhan riil.
- [ ] Uji live jalur Meta lewat OpenCode di dalam aplikasi BINDER baru; catat lolos/gagal apa adanya. Bukti yang sudah ada baru panggilan API langsung di hackathon, bukan bukti jalur di dalam aplikasi baru.
- [x] Fork remote — DIBUAT 30 Okt 2026: PatriaAWijaya/BINDER-paperclip (https://github.com/PatriaAWijaya/BINDER-paperclip), fork dari paperclipai/paperclip, branch default master, HEAD master = b3c2172 (tree identik dengan baseline lokal; HEAD upstream saat fork dibuat sudah maju ke 81ebe47 dan sengaja di-reset ke baseline). Sifat: PUBLIK (fork dari repo publik). UI dan fungsi awal belum diubah.
- [x] Vonis Patria: PRD v1.4 disetujui (0A, 30 Okt 2026) dan Gerbang Fase 0 LOLOS DENGAN CATATAN (31 Okt 2026).

## Clone inspeksi (selesai 30 Oktober 2026)

- `paperclipai/paperclip` — commit b3c2172, LICENSE MIT terverifikasi.
- `milind-soni/OpenMausBot` — commit 0213b74 (v0.1.134), LICENSE Apache-2.0 terverifikasi.

Clone ini hanya untuk inspeksi Gerbang Fase 0, bukan install dan bukan build.

## Dokumen teknis (v0.3, revisi arsitektur 30 Oktober 2026)

TRD, AppFlow, Backend Schematic, Rencana Kerja, dan Rencana Pengerjaan Detail
ada sebagai Google Doc di Drive MIMI/BINDER, selaras dengan PRD v1.4.
Salinan lokal ada di folder project-binder.

## Aturan visibilitas DeepBrain (keputusan Patria 30 Okt 2026)

README desain DeepBrain boleh tetap di repo publik ini. Kode dan repo
DeepBrain nanti bersifat privat.

## Yang belum ada di repo ini

- Kode aplikasi BINDER baru, Sync & Gate Internal, dan DeepBrain (dibangun setelah Gerbang Fase 0).
- File LICENSE BINDER (belum diputuskan Patria).

## Progres per fase/modul — diperbarui 30 Oktober 2026

Legenda: [x] selesai, [~] sebagian, [ ] belum.

### Fase 0 — Persetujuan dan Verifikasi
- [x] 0A Persetujuan PRD — PRD v1.4 DISETUJUI Patria 30 Okt 2026 ~16:51 WIB ("0A oke"). Status DRAF dicabut.
- [x] 0B Gerbang Fase 0 — LOLOS DENGAN CATATAN (vonis Patria 31 Okt 2026). Lisensi Paperclip MIT (b3c2172) dan OpenMausBot Apache-2.0 (0.1.134) terverifikasi; jalur kode DIPUTUSKAN (fork); pagu DITANGGUHKAN; fork remote dibuat; harga sandbox/Boat terverifikasi 30 Okt 2026 (lihat bawah). Catatan yang dibawa ke depan: lihat daftar catatan vonis di atas (pagu, harga CLI, pin DeepBrain bila impor, uji live Meta in-app, dan keputusan provider/model/VM/Pocket yang masih menunggu vonis).

### Fase 1 — Fondasi dan Modul Inti
- [~] 1A Repo dan dokumen — repo PatriaAWijaya/BINDER PUBLIK; PRD v1.4 DISETUJUI + 5 dokumen teknis v0.3 di Drive MIMI/BINDER dan terbaca-balik; repo fork PatriaAWijaya/BINDER-paperclip PUBLIK. Sisa 1A: verifikasi baseline fork (test/build) dan pencatatan hasil finalnya.
- [ ] 1B Modul Inti Perusahaan + CEO — belum dibangun. Persiapan saja: fork lokal dari b3c2172, `pnpm install` lolos.
- [x] 1C DeepBrain Core + MCP/CLI — SELESAI + ter-push (lokal 85ea872 ↔ remote 85ecbfa, tree identik; verifikasi independen: tsc 0 error, test 29/29). Desain PRD Bab 8; KEPUTUSAN 31 Okt 2026 (Patria): dibangun dari scratch v1 file-first, BUKAN dari repo dasar; Mem0 hanya kandidat akselerator recall Fase 2. Repo privat PatriaAWijaya/DeepBrain (terverifikasi private). Aturan: desain boleh publik, kode/repo PRIVAT. Kanonikalisasi nama 31 Okt 2026 (perintah Patria): semua penulisan deebrain/deeBrain/DEEBRAIN diubah jadi deepbrain/DEEPBRAIN (bin tunggal "deepbrain", env DEEPBRAIN_ROOT + DEEPBRAIN_REQUIRE_AUTH); push rename menunggu tree 1H stabil.
- [ ] 1D Sync & Gate Internal — desain/kontrak selesai; kode dan uji bypass BELUM.
- [ ] 1E Mesin Desktop + VM — desain selesai; kode dan task desktop pilot BELUM.
- [ ] 1F Routing model + QC + checkpoint swap — desain selesai; uji packet/QC BELUM.
- [ ] 1G Roster spesialis (6 agen) — desain selesai; hire dan task kecil per agen BELUM.
- [ ] 1H Distiller + Pocket pilot — AMANDEMEN DESAIN 31 Okt 2026 ~08:45 WIB (vonis Patria: "Setuju, ubah Distiller jadi hook + validator"): Distiller BUKAN lagi agen mandiri yang membaca ulang artifact + konteks; Distiller = (1) HOOK distilasi propose-only di lifecycle task, jalan di checkpoint setelah task lolos QC, memakai konteks yang sudah dimuat agen itu (tanpa panggilan model re-reading); (2) VALIDATOR keluarga model berbeda + review Patria sebelum candidate naik ke Main (maker tidak boleh mengesahkan sendiri). Pengaman: hook terbatas + agnostik-model (input hanya artifact Done + ringkasan run, lewat redaksi secret), best-effort (gagal distilasi tidak menggagalkan task), gerbang anti-banjir (hanya task Done + filter dedup/novelty vs Main), token distilasi per task dicatat di ledger (1J). Siklus Pocket Raw → Candidate → Main → Superseded → Archived + recall Main-only TETAP. Build 1H sedang berjalan per desain amandemen ini.
- [ ] 1I Leads Generator rutin — desain selesai; Proposal Pack dan keputusan per kandidat BELUM.
- [ ] 1J Ledger, audit, observabilitas — desain selesai; ledger terekonsiliasi BELUM.

### Fase 2 — Pilot terintegrasi
- [ ] 2A Operasi 2 minggu ledger nyata — BELUM.
- [ ] 2B Vonis Fase 1 — BELUM.

### Fase 3 — Go-live
- [ ] 3A Stabilisasi 2–4 minggu — BELUM.
- [ ] 3B Checklist go-live + pernyataan live — BELUM (live = beroperasi harian untuk Patria saja, bukan rilis publik).
- [ ] 3C Runbook, cadangan, prosedur berhenti — BELUM (belum diuji).

### Pasca-live — Fase 2 (per item, hanya dengan vonis)
- [ ] Vendor recall tambahan, spin-off DeepBrain, agen/konektor tambahan, tinjau ulang pagu — BELUM, dan tidak dimulai sebelum live stabil.

### Verifikasi baseline fork (di luar modul, dicatat jujur)
- [x] `pnpm install --frozen-lockfile` lolos (VM 6m28s; MacBook 24m10s).
- [x] Typecheck PENUH lolos di MacBook (30 paket termasuk server; Rust hanya peringatan) — menutup kegagalan VM exit 137 yang terbukti lingkungan, bukan kode.
- [~] Test (`pnpm test:run`): test3 selesai 9 gagal dari 28.652, semua terdiagnosis (7 timeout flaky lolos di rerun terarah; 2 test git akarnya config sistem Apple MacBook `init.defaultbranch=main`, terbukti karena rerun workspace-runtime dengan override env saja = 179/179 lolos). Test4 full run dengan override sedang berjalan sebagai konfirmasi satu angka bersih.
- [ ] Build (`pnpm build`) baseline — antre setelah test4 lolos.
- [x] Modifikasi pertama fork: app icon Patria dipasang (lokal 2ab8810 ↔ remote 9a66d6a); tidak ada perubahan kode/fungsi.

### 0B — Verifikasi harga (30 Okt 2026, dari halaman resmi vendor, bukan ringkasan pihak ketiga kecuali Modal)

Perbandingan mesin yang sama, hitung dari tarif publik (bukan penawaran):
- Boat (docs.boat.dev/pricing, dibaca 30 Okt 2026): small 2 vCPU/4 GB = $0,018/jam; default 4 vCPU/8 GB = $0,036/jam; large 8/16 = $0,072/jam; xlarge 16/32 = $0,200/jam. Paket $20/bln = 555 jam default; sandbox berhenti = tidak kena biaya mesin; egress tidak ditagih; snapshot otomatis 14 hari. Contoh: 1 default 8 jam/hari x 22 hari = $6,34, tertutup paket $20.
- Daytona (daytona.io/pricing, dibaca 30 Okt 2026): $0,0504/vCPU/jam + $0,0162/GiB/jam + storage $0,000108/GiB/jam setelah 5 GiB gratis; $200 kredit compute gratis; tagih per detik. Mesin 2/4 = $0,1656/jam; 4/8 = $0,3312/jam.
- Modal (modal.com/pricing, dibaca 30 Okt 2026): Starter $0 + kredit $30/bln; Team $250/bln + kredit $100/bln; sandbox ditagih non-preemptible 3x. Angka $/core/detik tidak tampil di halaman resmi yang dibaca, jadi angka sandbox di sini memakai tarif yang konsisten di dua sumber independen + tabel perbandingan Boat: mesin 2/4 = $0,380/jam; 4/8 = $0,760/jam.

Catatan yang tetap berlaku untuk 0B:
- Pagu total pilot DITANGGUHKAN (keputusan Patria 30 Okt 13:11 WIB) — jadi 0B tidak menunggu angka pagu, dan hard stop otomatis belum bisa jalan penuh tanpa angka itu.
- Langganan CLI belum bisa diverifikasi angkanya karena model CEO belum diputuskan (Meta via OpenCode vs Claude langsung) — tiap jalur punya langganan berbeda.
- Pola DeepBrain Brain/agentic-stack adalah pola acuan, bukan dependensi yang diimpor: DeepBrain dibangun sebagai file + MCP sendiri, sehingga tidak ada kode berlisensi tidak jelas yang disalin. Bila nanti ada dependensi yang diimpor, pin versi + lisensinya wajib diverifikasi dulu.
- Uji live Meta di dalam aplikasi baru BELUM bisa dilakukan — butuh build pertama yang bisa jalan dari fork (baseline penuh fork sendiri masih tertahan di VM).
- Gerbang LOLOS DENGAN CATATAN per vonis Patria 31 Okt 2026 (lihat daftar catatan di atas). Lolosnya gerbang BUKAN perintah modifikasi kode — modifikasi fork tetap hanya atas perintah spesifik Patria.
