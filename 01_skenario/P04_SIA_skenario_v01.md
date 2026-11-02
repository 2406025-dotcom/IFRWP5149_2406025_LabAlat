# A. Kebutuhan Tugas

| ID | Kebutuhan Tugas |
|---|---|
| SIA-R07 | Mahasiswa dan Dosen yang termasuk dalam Civitas Akademika dapat mengakses serta melihat kalender akademik. |
| SIA-R08 | Dosen dapat memasukkan nilai untuk mata kuliah yang menjadi tanggung jawabnya. |
| SIA-R09 | Mahasiswa dapat melihat Kartu Hasil Studi (KHS) pada semester yang nilai akhirnya sudah dipublikasikan. |
| SIA-R10 | Admin Akademik memiliki kewenangan untuk mengelola data mahasiswa. |
| SIA-R11 | Pengelolaan data mahasiswa terdiri dari tiga fungsi, yaitu menambah, mengubah, dan menghapus data mahasiswa. |
| SIA-R12 | Model sistem harus menunjukkan collaboration yang merealisasikan proses Input Nilai Mata Kuliah dan Lihat KHS. |

## B. Batas Sistem

| No. | Batas Sistem |
|---|---|
| 1 | Sistem yang menjadi objek pembahasan adalah Sistem Informasi Akademik (SIA). |
| 2 | Kalender akademik yang ditampilkan sistem menggunakan agenda resmi yang telah ditetapkan oleh institusi. |
| 3 | Proses input nilai hanya dapat dilakukan oleh Dosen yang mengampu mata kuliah tersebut. |
| 4 | Mahasiswa hanya dapat melihat KHS apabila nilai pada semester yang dipilih sudah dipublikasikan. |
| 5 | Penghapusan data mahasiswa hanya diperbolehkan apabila mahasiswa tidak memiliki data akademik yang masih aktif. |
| 6 | Proses pengajuan KRS tetap menjadi bagian dari diagram kumulatif yang dibuat pada Pertemuan 3. |
| 7 | Pembahasan mengenai pembayaran dan rancangan basis data tidak termasuk dalam ruang lingkup tugas. |

## C. Asumsi

| No. | Asumsi |
|---|---|
| 1 | Setiap pengguna dianggap sudah melakukan login dan memiliki hak akses sesuai dengan perannya. |
| 2 | Data kalender akademik sudah tersedia di dalam sistem dan dapat diakses oleh pengguna yang memiliki wewenang. |
| 3 | Data mata kuliah dan Dosen pengampu telah tersedia sebelum proses input nilai dilakukan. |
| 4 | Nilai yang dimasukkan Dosen belum dianggap sebagai nilai resmi sebelum dipublikasikan sesuai aturan institusi. |
| 5 | KHS yang dapat dilihat Mahasiswa hanya berasal dari semester yang nilai akhirnya sudah dipublikasikan. |
| 6 | Admin Akademik memiliki hak untuk menambah, mengubah, dan menghapus data mahasiswa sesuai batas kewenangan yang berlaku. |

# Langkah 2 — Identifikasi Aktor dan Use Case

## A. Katalog Use Case

| ID | Nama Use Case | Aktor Terkait | Sumber Kebutuhan | Status |
|---|---|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Mahasiswa | SIA-R01 | Tetap |
| SIA-UC02 | Kelola Jadwal Kuliah | Admin Akademik | SIA-R02 | Tetap |
| SIA-UC03 | Ajukan KRS | Mahasiswa | SIA-R03 | Tetap |
| SIA-UC04 | Validasi KRS | Sistem (bagian dari pengajuan) | SIA-R04 | Tetap |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa | SIA-R05 | Tetap |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | SIA-R06 | Tetap |
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | SIA-R07 | Baru |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | SIA-R08 | Baru |
| SIA-UC09 | Lihat KHS | Mahasiswa | SIA-R09 | Baru |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | SIA-R10 | Baru |
| SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |
| SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |
| SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |

## B. Daftar Aktor

| Nama Aktor | Jenis | Keterangan |
|---|---|---|
| Civitas Akademika | Aktor umum | Memiliki hak untuk mengakses dan melihat kalender akademik. |
| Mahasiswa | Aktor khusus | Dapat melihat jadwal kuliah, mengajukan KRS, mengunduh bukti pengajuan, dan melihat KHS. |
| Dosen | Aktor khusus | Dapat memasukkan nilai mata kuliah yang diampu serta melihat kalender akademik. |
| Admin Akademik | Aktor utama | Bertanggung jawab terhadap pengelolaan jadwal kuliah dan data mahasiswa. |
| Dosen Wali | Aktor utama | Bertugas menangani proses keputusan terkait pengajuan KRS mahasiswa. |

## C. Catatan Identifikasi

| No. | Penjelasan |
|---|---|
| 1 | Katalog use case pada Pertemuan 4 merupakan gabungan fungsi dari Pertemuan 2 dan Pertemuan 3 serta beberapa fungsi tambahan. |
| 2 | ID SIA-UC01 sampai SIA-UC06 tetap digunakan karena merupakan fungsi dari pertemuan sebelumnya. |
| 3 | Fungsi baru menggunakan ID SIA-UC07 sampai SIA-UC13. |
| 4 | SIA-UC10 Kelola Data Mahasiswa menjadi use case umum, sedangkan SIA-UC11, SIA-UC12, dan SIA-UC13 menjadi use case khusus. |
| 5 | Hubungan generalization antara use case umum dan khusus akan ditentukan pada langkah berikutnya. |

# Langkah 3 — Menentukan Generalization Aktor

## A. Hierarki Aktor

| Aktor Umum | Aktor Khusus | Fungsi yang Diwarisi | Dasar Pemodelan |
|---|---|---|---|
| Civitas Akademika | Mahasiswa | Lihat Kalender Akademik | Mahasiswa merupakan bagian dari Civitas Akademika sehingga memperoleh hak untuk melihat kalender akademik. |
| Civitas Akademika | Dosen | Lihat Kalender Akademik | Dosen termasuk Civitas Akademika dan dapat menggunakan fungsi melihat kalender akademik. |

## B. Penjelasan Generalization

| No. | Penjelasan |
|---|---|
| 1 | Civitas Akademika dijadikan aktor umum karena fungsi Lihat Kalender Akademik dapat digunakan oleh Mahasiswa dan Dosen. |
| 2 | Mahasiswa dan Dosen berperan sebagai aktor khusus yang memperoleh fungsi dari aktor umum melalui hubungan generalization. |
| 3 | Dengan adanya generalization, use case Lihat Kalender Akademik cukup dikaitkan dengan Civitas Akademika. |
| 4 | Mahasiswa dan Dosen tetap dapat menjalankan fungsi tersebut melalui mekanisme pewarisan sehingga hubungan langsung yang sama tidak perlu dibuat berulang. |

# Langkah 4 — Menentukan Generalization Use Case

## A. Hierarki Use Case

| Use Case Umum | Use Case Khusus | Fungsi yang Diwarisi | Dasar Pemodelan |
|---|---|---|---|
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC11 Tambah Data Mahasiswa | Fungsi pengelolaan data mahasiswa | Menambahkan data merupakan salah satu aktivitas dalam pengelolaan data mahasiswa. |
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC12 Ubah Data Mahasiswa | Fungsi pengelolaan data mahasiswa | Mengubah informasi mahasiswa termasuk kegiatan pengelolaan data. |
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC13 Hapus Data Mahasiswa | Fungsi pengelolaan data mahasiswa | Menghapus data merupakan salah satu aktivitas dalam pengelolaan data mahasiswa. |

## B. Penjelasan Generalization

| No. | Penjelasan |
|---|---|
| 1 | SIA-UC10 Kelola Data Mahasiswa digunakan sebagai use case umum karena mencakup keseluruhan proses pengelolaan data mahasiswa. |
| 2 | SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa merupakan fungsi khusus dari pengelolaan data tersebut. |
| 3 | Ketiga use case khusus memberikan rincian aktivitas yang dapat dilakukan dalam proses pengelolaan data mahasiswa. |
| 4 | Generalization digunakan untuk memperlihatkan hubungan antara fungsi umum dan fungsi khusus serta membuat struktur model lebih terorganisasi. |

## C. Ketentuan Penggambaran

| No. | Ketentuan |
|---|---|
| 1 | SIA-UC10 Kelola Data Mahasiswa berperan sebagai use case umum. |
| 2 | SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa menjadi use case khusus. |
| 3 | Hubungan generalization menggunakan garis utuh dengan segitiga kosong yang diarahkan ke SIA-UC10 Kelola Data Mahasiswa sebagai use case umum. |

# Langkah 5 — Menentukan Collaboration

## A. Daftar Collaboration

| ID Collaboration | Nama Collaboration | Use Case yang Direalisasikan | Aktor Terkait |
|---|---|---|---|
| SIA-CO01 | Input Nilai Mata Kuliah | SIA-UC08 Input Nilai Mata Kuliah | Dosen |
| SIA-CO02 | Lihat KHS | SIA-UC09 Lihat KHS | Mahasiswa |

## B. Penjelasan Collaboration

### 1. SIA-CO01 — Input Nilai Mata Kuliah

| No. | Penjelasan |
|---|---|
| 1 | Collaboration ini menggambarkan proses pelaksanaan use case Input Nilai Mata Kuliah. |
| 2 | Dosen memilih mata kuliah yang diampu kemudian memasukkan nilai mahasiswa. |
| 3 | Setelah nilai dimasukkan, sistem melakukan pemeriksaan terhadap data dan menyimpannya sesuai aturan yang berlaku. |
| 4 | Nilai yang sudah tersimpan belum menjadi nilai resmi apabila belum melalui proses publikasi. |
| 5 | Nilai yang belum dipublikasikan belum dapat digunakan sebagai hasil studi resmi dalam KHS. |

### 2. SIA-CO02 — Lihat KHS

| No. | Penjelasan |
|---|---|
| 1 | Collaboration ini menjelaskan proses pelaksanaan use case Lihat KHS. |
| 2 | Mahasiswa memilih semester yang ingin ditampilkan. |
| 3 | Sistem kemudian memeriksa apakah nilai pada semester tersebut sudah dipublikasikan. |
| 4 | Jika sudah dipublikasikan, sistem mengambil data hasil studi dan menampilkan KHS kepada Mahasiswa. |
| 5 | Jika belum dipublikasikan, sistem memberikan informasi bahwa KHS untuk semester tersebut belum tersedia. |

## C. Hubungan Collaboration dengan Use Case

| Collaboration | Use Case | Hubungan |
|---|---|---|
| SIA-CO01 | SIA-UC08 Input Nilai Mata Kuliah | SIA-CO01 merealisasikan proses Input Nilai Mata Kuliah. |
| SIA-CO02 | SIA-UC09 Lihat KHS | SIA-CO02 merealisasikan proses Lihat KHS. |

| No. | Penjelasan Tambahan |
|---|---|
| 1 | Nama collaboration disesuaikan dengan use case yang direalisasikannya. |
| 2 | Nilai yang dimasukkan oleh Dosen harus melalui proses publikasi terlebih dahulu sebelum dapat ditampilkan kepada Mahasiswa melalui KHS. |

# Langkah 6 — Menyusun Use Case Description

## A. SIA-UC08 — Input Nilai Mata Kuliah

| Elemen | Deskripsi |
|---|---|
| ID Use Case | SIA-UC08 |
| Nama Use Case | Input Nilai Mata Kuliah |
| Aktor Utama | Dosen |
| Tujuan | Memasukkan nilai mahasiswa pada mata kuliah yang diampu oleh Dosen. |
| Prasyarat | Dosen telah login, mempunyai hak akses, dan data mata kuliah serta mahasiswa sudah tersedia. |
| Pemicu | Dosen memilih menu input nilai mata kuliah. |

### Alur Utama

| No. | Proses |
|---|---|
| 1 | Dosen membuka menu Input Nilai Mata Kuliah. |
| 2 | Sistem menampilkan daftar mata kuliah yang diampu oleh Dosen. |
| 3 | Dosen menentukan mata kuliah yang akan diberikan nilai. |
| 4 | Sistem menampilkan daftar Mahasiswa yang mengikuti mata kuliah tersebut. |
| 5 | Dosen memasukkan nilai Mahasiswa. |
| 6 | Dosen menyimpan nilai yang telah diinput. |
| 7 | Sistem melakukan pemeriksaan terhadap kelengkapan dan validitas nilai. |
| 8 | Jika data dinyatakan valid, sistem menyimpan nilai dan menampilkan pemberitahuan bahwa proses berhasil. |

### Alur Alternatif

| Kondisi | Respons Sistem |
|---|---|
| Data nilai belum lengkap atau tidak valid | Sistem menampilkan pesan kesalahan dan meminta Dosen melakukan perbaikan. |
| Proses penyimpanan mengalami kegagalan | Sistem memberikan informasi bahwa nilai belum berhasil disimpan. |

### Pascakondisi

| Kondisi | Hasil |
|---|---|
| Penyimpanan berhasil | Nilai berhasil tersimpan di dalam sistem. |
| Nilai sudah tersimpan | Nilai belum otomatis menjadi nilai resmi atau dipublikasikan. |
| Penyimpanan gagal | Perubahan nilai dianggap belum berhasil disimpan. |

## B. SIA-UC09 — Lihat KHS

| Elemen | Deskripsi |
|---|---|
| ID Use Case | SIA-UC09 |
| Nama Use Case | Lihat KHS |
| Aktor Utama | Mahasiswa |
| Tujuan | Menampilkan Kartu Hasil Studi pada semester yang nilai akhirnya telah dipublikasikan. |
| Prasyarat | Mahasiswa telah login dan memiliki data akademik pada semester yang dipilih. |
| Pemicu | Mahasiswa membuka menu Kartu Hasil Studi (KHS). |

### Alur Utama

| No. | Proses |
|---|---|
| 1 | Mahasiswa membuka menu KHS. |
| 2 | Sistem menampilkan daftar semester yang tersedia. |
| 3 | Mahasiswa memilih semester yang ingin diperiksa. |
| 4 | Sistem mengecek status publikasi nilai pada semester tersebut. |
| 5 | Apabila nilai telah dipublikasikan, sistem mengambil data hasil studi Mahasiswa. |
| 6 | Sistem menampilkan KHS berdasarkan semester yang dipilih. |

### Alur Alternatif

| Kondisi | Respons Sistem |
|---|---|
| Nilai semester belum dipublikasikan | Sistem memberitahukan bahwa KHS untuk semester tersebut belum tersedia. |
| Tidak terdapat data akademik pada semester yang dipilih | Sistem menginformasikan bahwa data KHS belum tersedia. |
| Terjadi masalah saat mengambil data | Sistem memberi informasi bahwa KHS tidak dapat ditampilkan. |

### Pascakondisi

| Kondisi | Hasil |
|---|---|
| Proses berhasil | Mahasiswa dapat melihat KHS dari semester yang dipilih. |
| Nilai belum dipublikasikan | KHS tidak ditampilkan sebagai hasil studi yang tersedia. |
| Proses melihat KHS selesai | Data atau nilai akademik Mahasiswa tidak mengalami perubahan. |

# Langkah 7 — Membuat Diagram

| No. | Tahapan |
|---|---|
| 1 | Buat salinan diagram SIA dari Pertemuan 3 dan jangan mengubah file aslinya. |
| 2 | Tambahkan Civitas Akademika sebagai aktor umum serta Mahasiswa dan Dosen sebagai aktor khusus. |
| 3 | Hubungkan aktor khusus dengan aktor umum menggunakan generalization. |
| 4 | Tambahkan use case layanan hasil studi sesuai kebutuhan yang telah ditentukan. |
| 5 | Tambahkan SIA-UC10 Kelola Data Mahasiswa beserta SIA-UC11, SIA-UC12, dan SIA-UC13 sebagai use case khusus. |
| 6 | Tambahkan hubungan generalization pada use case pengelolaan data mahasiswa. |
| 7 | Tambahkan SIA-CO01 Input Nilai Mata Kuliah dan SIA-CO02 Lihat KHS beserta hubungan realization yang sesuai. |
| 8 | Simpan hasil diagram pada folder `04_model_analisis/P04/SIA/`. |
| 9 | Gunakan nama file `P04_<2406025>_SIA_notasi_usecase_v01.drawio`. |
| 10 | Ekspor diagram ke format PNG menggunakan nama versi yang sama. |
| 11 | Pastikan diagram akhir menggabungkan fungsi jadwal kuliah, pengajuan KRS, dan layanan hasil studi dalam satu model Sistem Informasi Akademik. |

# Langkah 8 — Uji Konsistensi, Review, dan Revisi

## A. Uji Konsistensi

### Situasi A — Mahasiswa Melihat Kalender Akademik Tanpa Asosiasi Langsung

| Bagian | Hasil |
|---|---|
| Situasi | Mahasiswa mencoba menggunakan fungsi Lihat Kalender Akademik tanpa memiliki asosiasi langsung dengan use case tersebut. |
| Hasil Pengujian | Mahasiswa tetap dapat mengakses fungsi tersebut karena merupakan aktor khusus dari Civitas Akademika dan memperoleh fungsi melalui generalization. |
| Kesimpulan | Model konsisten apabila hubungan generalization antara Civitas Akademika dan Mahasiswa telah dibuat dengan benar. |

### Situasi B — Dosen yang Bukan Pengampu Mencoba Memasukkan Nilai

| Bagian | Hasil |
|---|---|
| Situasi | Dosen yang tidak mengampu suatu mata kuliah mencoba melakukan input nilai. |
| Hasil Pengujian | Sistem menolak proses tersebut karena Dosen tidak memiliki hak untuk memasukkan nilai pada mata kuliah yang bukan tanggung jawabnya. |
| Kesimpulan | Model telah sesuai karena hanya Dosen yang mengampu mata kuliah terkait yang diperbolehkan melakukan input nilai. |

### Situasi C — Admin Menghapus Data Mahasiswa yang Masih Memiliki Data Akademik Aktif

| Bagian | Hasil |
|---|---|
| Situasi | Admin Akademik mencoba menghapus data Mahasiswa yang masih memiliki data akademik aktif. |
| Hasil Pengujian | Sistem menolak proses penghapusan dan memberikan informasi mengenai alasan penolakan. |
| Kesimpulan | Model telah sesuai dengan batasan sistem karena data Mahasiswa yang masih memiliki data akademik aktif tidak diperbolehkan untuk dihapus. |

## B. Review dan Revisi

| No. | Temuan | Perbaikan yang Diperlukan | Alasan |
|---|---|---|---|
| 1 | Hubungan generalization antara aktor belum terlihat dengan jelas. | Rapikan hubungan Mahasiswa dan Dosen menuju Civitas Akademika dengan garis utuh dan segitiga kosong yang mengarah ke aktor umum. | Generalization menunjukkan bahwa aktor khusus memperoleh fungsi dari aktor umum. |
| 2 | Dosen memiliki hubungan dengan use case Ajukan KRS. | Hapus asosiasi tersebut apabila Dosen terhubung dengan use case Ajukan KRS. | Pengajuan KRS dilakukan oleh Mahasiswa, bukan Dosen. |
| 3 | ID collaboration pada diagram tidak sesuai dengan katalog. | Samakan ID menjadi SIA-CO01 untuk Input Nilai Mata Kuliah dan SIA-CO02 untuk Lihat KHS. | Konsistensi ID diperlukan agar diagram dan dokumentasi memiliki identitas yang sama. |
| 4 | Notasi collaboration perlu diperiksa kembali. | Sesuaikan simbol dan hubungan collaboration dengan contoh yang terdapat pada modul. | Pemodelan harus mengikuti notasi yang ditetapkan dalam tugas. |
| 5 | Beberapa aktor terlalu dekat atau menyentuh batas sistem. | Posisikan seluruh aktor di luar batas sistem dan rapikan garis asosiasinya. | Aktor merupakan pihak eksternal yang berinteraksi dengan sistem. |

## C. Kesimpulan 

| No. | Kesimpulan |
|---|---|
| 1 | Berdasarkan tiga skenario pengujian, model Sistem Informasi Akademik sudah dapat menggambarkan aturan akses dan pengelolaan data sesuai dengan skenario. |
| 2 | Beberapa bagian diagram masih perlu diperbaiki, terutama generalization aktor, hubungan aktor dengan use case, ID collaboration, dan notasi collaboration. |
| 3 | Setelah seluruh perbaikan selesai, diagram dan deskripsi use case perlu disimpan sebagai versi revisi. |