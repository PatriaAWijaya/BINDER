# BINDER

Perusahaan solo Patria A. Wijaya yang diikat menjadi satu sistem kerja.

- **Paperclip** sebagai backbone: company, goal, task, approval, budget hard stop, audit.
- **MausBot (OpenMausBot)** hanya untuk slice desktop/VM: aplikasi GUI, live screen, interaksi visual yang tidak bisa dikerjakan sandbox headless.
- **DeepBrain** sebagai lapisan ingatan portable PnP di luar kedua runtime: file git per agen + MCP + adapter model/runtime, supaya ganti model, ganti agen, atau ganti runtime tidak mereset otak.

BINDER adalah perekat di antara ketiganya, bukan produk keempat yang menggantikannya.

## Status

**DRAF. Gerbang Fase 0 BELUM lolos. Belum install, belum build, belum ada aksi eksternal.**

Dokumen kanon: PRD BINDER v1.3 di Drive MIMI/BINDER (DRAF, 30 Oktober 2026).
Keputusan yang masih menunggu Patria tercantum di Bab 14 PRD itu, antara lain:
nama company final dan proyek pilot, provider sandbox (Modal atau Daytona),
model utama CEO (Meta lewat OpenCode atau Claude langsung), default VM pilot,
pagu total pilot, dan total budget token ($110/bln usulan v1.3 atau tetap $100
dengan realokasi).

Langkah berikutnya menurut PRD bukan langsung install, melainkan Gerbang Fase 0:
verifikasi lisensi, pin versi, verifikasi harga, dan uji live jalur Meta.
Tanpa vonis Patria di gerbang itu, tidak lanjut ke install.

## Prinsip yang tidak bisa ditawar (PRD Bab 3)

- Patria adalah satu-satunya manusia, Board, dan approver akhir. Tidak ada self-approval oleh agen.
- Tidak ada auto-post, tidak ada auto-kirim outreach, tidak ada order trading live.
- QC harus beda keluarga model dari pembuat. Skor minimal 75, nol pelanggaran keras, maksimal 2 putaran revisi, lalu eskalasi ke Patria.
- Budget hard stop di 100 persen, peringatan 70 persen dan 90 persen.
- Secret tidak pernah masuk handoff packet, memori bersama, log, atau artifact.
- Lisensi AGPL/GPL adalah hard stop untuk bundling; engine AGPL hanya lewat proses eksternal/API.

## Struktur repo ini

- `upstream/` — catatan referensi upstream, BUKAN vendoring kode upstream.
- `binder-sync/` — lapisan integrasi Paperclip ↔ MausBot (akan dibangun setelah Gerbang Fase 0).
- `deepbrain/` — lapisan otak portable PnP milik BINDER sendiri (file-first + MCP).
- `docs/` — status gerbang dan dokumen teknis (TRD, AppFlow, Backend Schematic, Rencana Kerja menyusul sebagai draf terpisah).

## Upstream yang dirujuk

- Paperclip — `paperclipai/paperclip` — lisensi MIT menurut PRD; verifikasi ulang di Gerbang Fase 0.
- OpenMausBot — `milind-soni/OpenMausBot` — lisensi Apache-2.0 menurut PRD; verifikasi ulang di Gerbang Fase 0.

Kode upstream TIDAK disalin ke repo ini. Clone inspeksi upstream disimpan terpisah
di mesin kerja untuk verifikasi Gerbang Fase 0, dan versi yang dipakai akan di-pin
di `upstream/README.md` setelah verifikasi selesai. Lisensi BINDER sendiri belum
diputuskan Patria dan karena itu repo ini belum memuat file LICENSE.
