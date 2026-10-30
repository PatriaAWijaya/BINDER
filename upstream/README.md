# Upstream — referensi saja, bukan vendoring

Repo ini TIDAK menyalin kode Paperclip atau OpenMausBot.

| Komponen | Repo upstream | Lisensi menurut PRD | Status verifikasi |
|---|---|---|---|
| Paperclip (backbone) | `paperclipai/paperclip` | MIT | Belum terverifikasi dari clone — menunggu Gerbang Fase 0 |
| OpenMausBot (slice desktop/VM) | `milind-soni/OpenMausBot` | Apache-2.0 | Belum terverifikasi dari clone — menunggu Gerbang Fase 0 |

Aturan:

- Clone inspeksi upstream disimpan terpisah di mesin kerja, bukan di repo ini.
- Versi yang dipakai (commit/tag) akan di-pin di sini SETELAH verifikasi Gerbang Fase 0 selesai.
- Jangan mengimpor perilaku upstream ke kode Binder sebelum LICENSE di repo yang dipakai diverifikasi.
- Atribusi upstream wajib dicantumkan bila ada kode atau perilaku upstream yang dipakai, sesuai lisensinya masing-masing.
