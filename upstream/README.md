# Upstream — referensi saja, bukan vendoring

Repo ini TIDAK menyalin kode Paperclip atau OpenMausBot. Sejak revisi arsitektur v1.4, kedua repo ini adalah POLA ACUAN untuk rekonstruksi satu aplikasi BINDER baru, bukan runtime yang di-install. Jalur kode (fork lalu modifikasi vs bangun ulang bersih terinspirasi pola) BELUM diputuskan dan diputuskan di Gerbang Fase 0.

| Komponen | Repo upstream | Lisensi menurut PRD | Status verifikasi |
|---|---|---|---|
| Paperclip (pola acuan Inti Perusahaan) | `paperclipai/paperclip` | MIT | Terverifikasi 30 Okt 2026 dari clone — commit b3c2172 |
| OpenMausBot (pola acuan Mesin Desktop) | `milind-soni/OpenMausBot` | Apache-2.0 | Terverifikasi 30 Okt 2026 dari clone — v0.1.134, commit 0213b74 |

Aturan:

- Clone inspeksi upstream disimpan terpisah di mesin kerja, bukan di repo ini.
- Versi yang dipakai (commit/tag) akan di-pin di sini SETELAH verifikasi Gerbang Fase 0 selesai.
- Jangan mengimpor perilaku upstream ke kode Binder sebelum LICENSE di repo yang dipakai diverifikasi.
- Atribusi upstream wajib dicantumkan bila ada kode atau perilaku upstream yang dipakai, sesuai lisensinya masing-masing.
