## Review dan Revisi

Setelah dilakukan pemeriksaan terhadap diagram dan pengujian konsistensi, masih terdapat beberapa bagian yang perlu disesuaikan agar model Sistem Informasi Akademik dapat memenuhi ketentuan tugas.

| No. | Temuan | Perbaikan yang Diperlukan | Alasan |
|---|---|---|---|
| 1 | Hubungan *generalization* antara aktor belum tergambar secara jelas. | Rapikan hubungan Mahasiswa dan Dosen dengan Civitas Akademika menggunakan garis utuh serta segitiga kosong yang diarahkan kepada aktor umum. | *Generalization* menunjukkan bahwa aktor khusus memperoleh atau mewarisi fungsi dari aktor umum. |
| 2 | Terdapat hubungan antara Dosen dan use case Ajukan KRS. | Hapus asosiasi tersebut jika Dosen memang terhubung dengan use case Ajukan KRS. | Proses pengajuan KRS merupakan tanggung jawab Mahasiswa, bukan Dosen. |
| 3 | ID *collaboration* pada diagram belum sesuai dengan katalog. | Samakan ID *collaboration* menjadi SIA-CO01 untuk Input Nilai Mata Kuliah dan SIA-CO02 untuk Lihat KHS. | Keseragaman ID diperlukan agar diagram dan dokumentasi tidak memiliki perbedaan. |
| 4 | Penggunaan notasi *collaboration* masih perlu diperiksa. | Sesuaikan bentuk simbol dan hubungan *collaboration* dengan contoh yang diberikan dalam modul. | Notasi yang digunakan harus mengikuti aturan pemodelan yang ditetapkan dalam tugas. |
| 5 | Beberapa aktor berada terlalu dekat dengan batas sistem atau menyentuhnya. | Pindahkan aktor ke luar batas sistem dan rapikan kembali garis asosiasinya. | Aktor merupakan pihak eksternal yang berinteraksi dengan sistem. |

## Kesimpulan

Hasil pengujian terhadap tiga kondisi menunjukkan bahwa model Sistem Informasi Akademik sudah mampu menggambarkan aturan akses dan pengelolaan data sesuai dengan skenario yang telah ditentukan. Namun, masih terdapat beberapa bagian diagram yang perlu disempurnakan, terutama pada hubungan *generalization* aktor, asosiasi antara aktor dan use case, kesesuaian ID *collaboration*, serta penggunaan notasi *collaboration*. Setelah seluruh perbaikan selesai dilakukan, diagram dan deskripsi use case dapat disimpan sebagai versi revisi agar hasil pemodelan menjadi lebih rapi, jelas, dan konsisten.