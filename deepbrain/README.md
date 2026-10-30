# DeepBrain — lapisan otak portable PnP milik BINDER

DeepBrain BUKAN repo upstream yang di-clone. Ia dibangun di dalam BINDER
sebagai komponen (versi 0.1 menurut PRD Bab 8.8), dengan kemungkinan spin-off
menjadi proyek terpisah HANYA bila Gerbang Spin-off di PRD Bab 8.8 lolos dan
Patria memberi vonis — spin-off adalah potensi, bukan keputusan.

Desain v1 (PRD Bab 8):

- Sumber kebenaran: folder otak per agen, berversi di git, bisa dibaca manusia.
- Dibaca kedua runtime (Paperclip dan MausBot) lewat MCP dengan agentId yang sama.
- Tulis lesson candidate di akhir run; promosi menjadi memori permanen HANYA setelah review Patria (mingguan).
- Core tidak tahu merek model dan tidak tahu merek runtime. Perbedaan ditampung di Profil Model dan Adapter (Model Adapter, Runtime Adapter, Storage Adapter).
- Mesin recall vendor (Mem0, Hindsight, Graphiti, Cognee, Letta) adalah kandidat Fase 2 sebagai akselerator recall, BUKAN sumber kebenaran v1. Bila diadopsi pun ia mengindeks folder otak, tidak menggantikannya.
- Handoff packet: ringkasan terstruktur di checkpoint. DILARANG masuk packet: secret, kredensial, token API, kunci, password, dan isi task private yang bukan milik agen itu.
- Distiller (agen native DeepBrain) dan Pocket (distilasi + harness skill + protokol + versi dan skor) diatur di PRD Bab 8.9; hanya versi Main satu Pocket yang menjadi output utama recall.

Kode DeepBrain belum ada di repo ini. Ia dibangun setelah Gerbang Fase 0.
