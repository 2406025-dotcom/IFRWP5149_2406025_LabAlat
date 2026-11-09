ID artefak : P06-JOBSHEET-REVIEW
Judul : Laporan Review Jobsheet Pemodelan Activity Diagram
Pertemuan : 6
Sumber skenario : Artefak analisis LAB dan SIA Pertemuan 6
Jenis/status : Laporan review jobsheet
Kakas : draw.io; Markdown
Pembuat : 2406025
Versi dan tanggal : v01 / 09-11-2026
Asumsi/pertanyaan : Review dibatasi pada artefak P06 yang tersedia di repositori; jobsheet resmi P06 tidak ditemukan dalam berkas yang diperiksa.
Pemeriksaan : Diagram sumber dan ekspor gambar LAB serta diagram aktivitas SIA telah ditelusuri; temuan perlu ditindaklanjuti.
Riwayat revisi : v01 - Penyusunan laporan berdasarkan artefak P06 yang tersedia.

# Laporan Review Jobsheet Pertemuan 6

## A. Tujuan

Laporan ini mendokumentasikan pemeriksaan artefak Pertemuan 6 yang tersedia di repositori. Pemeriksaan mencakup alur aktivitas, aktor atau swimlane, keputusan, dan konsistensi isi yang dapat ditelusuri dari diagram. Karena jobsheet resmi P06 tidak ditemukan, laporan ini merupakan review terhadap artefak yang tersedia dan bukan verifikasi terhadap seluruh instruksi jobsheet.

## B. Artefak yang Ditinjau

| Kelompok | Artefak |
|---|---|
| LAB | Diagram aktivitas pengajuan peminjaman, keputusan peminjaman, lihat ketersediaan, cetak bukti, kelola data peralatan, laporan peminjaman, dan pengembalian peralatan. |
| LAB | Diagram sumber skenario P06 yang memuat tujuh halaman. |
| SIA | Diagram aktivitas P06 dengan tujuh halaman: SIA-UC07 sampai SIA-UC13. |

Diagram sumber dan ekspor gambar untuk aktivitas LAB berada di `04_model_analisis/P06/LAB/`. Diagram aktivitas SIA berada di `04_model_analisis/P06/SIA/`.

## C. Ringkasan Hasil Penelusuran

### 1. Sistem Internal Laboratorium (LAB)

Diagram LAB mencakup proses pengajuan peminjaman dan pemeriksaan ketersediaan, keputusan petugas, pencetakan bukti, pengelolaan data peralatan, penyajian laporan, serta pengembalian dan pemeriksaan kondisi peralatan. Alur pengelolaan peralatan telah menunjukkan cabang tambah, ubah, dan hapus, termasuk pemeriksaan syarat penghapusan.

### 2. Sistem Informasi Akademik (SIA)

Diagram aktivitas SIA mencakup tujuh use case:

| ID | Use case |
|---|---|
| SIA-UC07 | Lihat Kalender Akademik |
| SIA-UC08 | Input Nilai Mata Kuliah |
| SIA-UC09 | Lihat KHS |
| SIA-UC10 | Kelola Data Mahasiswa |
| SIA-UC11 | Tambah Data Mahasiswa |
| SIA-UC12 | Ubah Data Mahasiswa |
| SIA-UC13 | Hapus Data Mahasiswa |

Secara umum, diagram menampilkan aktor, respons sistem, serta keputusan atau kondisi pada alur yang relevan, seperti ketersediaan kalender, validasi nilai, publikasi nilai, dan kelayakan penghapusan data mahasiswa.

## D. Checklist Pemeriksaan

| No. | Aspek pemeriksaan | Hasil |
|---|---|---|
| 1 | Cakupan artefak LAB yang tersedia ditelusuri berdasarkan tujuh diagram aktivitas dan diagram sumber skenario. | ✓ |
| 2 | Diagram aktivitas SIA memuat halaman SIA-UC07 sampai SIA-UC13. | ✓ |
| 3 | Aktor atau swimlane dan respons sistem dapat dikenali pada diagram yang diperiksa. | ✓ |
| 4 | Cabang kondisi dan hasil alternatif ditampilkan pada alur yang memerlukannya. | ✓ |
| 5 | Konsistensi aktor pada aktivitas laporan LAB terhadap skenario sebelumnya. | Perlu verifikasi |
| 6 | Label swimlane dan aktivitas pada diagram pengembalian LAB. | Perlu perbaikan |
| 7 | Pembedaan kondisi pada alur Lihat KHS SIA-UC09. | Perlu verifikasi |

## E. Temuan dan Rekomendasi

| No. | Temuan | Rekomendasi |
|---|---|---|
| 1 | Diagram aktivitas LAB untuk laporan peminjaman menampilkan swimlane **Mahasiswa**, sedangkan skenario LAB sebelumnya menyebut laporan peminjaman untuk **Kepala Laboratorium**. | Pastikan aktor yang berwenang melihat laporan. Jika sesuai skenario, ubah swimlane menjadi Kepala Laboratorium dan sesuaikan alur terkait. |
| 2 | Pada diagram pengembalian LAB, judul swimlane tengah tidak terbaca pada ekspor gambar. Alur juga memuat aktivitas **Memproses Keputusan peminjaman** setelah pemeriksaan kondisi pengembalian. | Perjelas judul swimlane dan pastikan label aktivitas tersebut memang sesuai proses pengembalian; ganti dengan aktivitas pengembalian yang tepat jika merupakan sisa dari diagram lain. |
| 3 | Pada SIA-UC09, diagram memuat kondisi publikasi nilai dan juga pesan bahwa data hasil studi belum tersedia. Hubungan antara kedua kondisi tersebut belum cukup jelas untuk membedakan nilai yang belum dipublikasikan dari data hasil studi yang tidak tersedia. | Tegaskan kondisi dan hasil untuk masing-masing cabang agar pengguna memahami kapan KHS belum dapat diakses dan kapan data semester memang belum tersedia. |

## F. Kesimpulan

Artefak P06 yang tersedia telah mencakup rangkaian aktivitas LAB dan tujuh use case aktivitas SIA. Penelusuran menunjukkan beberapa bagian yang perlu diperiksa sebelum hasil dianggap final, terutama aktor pada laporan peminjaman LAB, label dan aktivitas pada diagram pengembalian, serta pembedaan kondisi pada SIA-UC09.

Setelah perbaikan atau konfirmasi dilakukan, diagram terkait sebaiknya ditinjau kembali dan laporan ini diperbarui agar status pemeriksaan mencerminkan versi artefak terbaru.
