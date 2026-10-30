# Binder Sync — jembatan Paperclip ↔ MausBot

Binder Sync adalah satu-satunya jembatan resmi antara Paperclip dan MausBot
(PRD Bab 6.3). Kode lapisan ini belum ada di repo ini; ia dibangun setelah
Gerbang Fase 0.

Kontrak yang sudah ditetapkan PRD (bukan kode yang sudah jalan):

- Kunci kanonik: `paperclip_task_id`. Job MausBot, VM, dan artifact selalu merujuk ke task_id ini. Tanpa task_id, job ditolak.
- Hanya CEO (Mimi) yang boleh membuat job MausBot dari task yang sudah disetujui scope-nya. Bot tidak boleh membuat task Paperclip sendiri.
- Status MausBot: queued → running → need_approval → done / failed, dipetakan ke status Paperclip, bukan menggantikannya.
- Setiap job desktop wajib mengembalikan minimal satu artifact: file, screenshot bukti, log ringkas, dan diff bila ada perubahan file. Tanpa artifact, task tidak bisa masuk In Review.
- Aksi eksternal HANYA jalan bila task membawa `approved_action_id` dari Paperclip. Binder Gate menolak aksi tanpa ID itu.
- Biaya (waktu VM, token model, biaya tools) dicatat ke task_id yang sama.
- VM dibuat untuk job, dihentikan setelah job selesai/gagal. Snapshot hanya bila task secara eksplisit membutuhkannya, dan snapshot tanpa idleTimeout dan pagu dilarang.
- VM timeout → job failed, checkpoint terakhir disimpan, task kembali ke Todo dengan catatan gagal. Tidak ada retry otomatis tanpa batas; retry butuh persetujuan CEO dan dicatat.
