# Sync & Gate Internal — modul di dalam aplikasi BINDER (PRD v1.4)

Sejak revisi arsitektur v1.4, Sync dan Gate BUKAN lagi jembatan antara
Paperclip dan MausBot. Keduanya adalah modul internal di dalam satu aplikasi
BINDER baru yang merekonstruksi kelebihan Paperclip (Inti Perusahaan) dan
MausBot (Mesin Desktop).

Kode modul ini belum ada di repo ini; ia dibangun setelah Gerbang Fase 0.

Kontrak yang sudah ditetapkan PRD (bukan kode yang sudah jalan):

- Kunci kanonik: `binder_task_id`. Job desktop, VM, dan artifact selalu
  merujuk ke task_id ini. Tanpa task_id, job ditolak.
- Hanya CEO (Mimi) yang boleh membuat job desktop dari task yang sudah
  disetujui scope-nya. Bot tidak boleh membuat task BINDER sendiri.
- Status job desktop: queued → running → need_approval → done / failed,
  dipetakan ke status task BINDER, bukan menggantikannya.
- Setiap job desktop wajib mengembalikan minimal satu artifact: file,
  screenshot bukti, log ringkas, dan diff bila ada perubahan file. Tanpa
  artifact, task tidak bisa masuk In Review.
- Aksi eksternal HANYA jalan bila task membawa `approved_action_id` dari
  BINDER. Gate Internal menolak aksi tanpa ID itu.
- Biaya (waktu VM, token model, biaya tools) dicatat ke task_id yang sama.
- VM dibuat untuk job, dihentikan setelah job selesai/gagal. Snapshot hanya
  bila task secara eksplisit membutuhkannya, dan snapshot tanpa idleTimeout
  dan pagu dilarang (pagu VM dipatok bersama pagu total setelah observasi;
  selama pagu ditangguhkan, biaya wajib tercatat).
- VM timeout → job failed, checkpoint terakhir disimpan, task kembali ke
  Todo dengan catatan gagal. Tidak ada retry otomatis tanpa batas; retry
  butuh persetujuan CEO dan dicatat.
