## Langkah 3 — Tabel Skenario Use Case

1. SIA-UC07 – Lihat Kalender Akademik
   **Tabel Skenario Use Case SIA-UC07 Lihat Kalender Akademik**

| Elemen        | Keterangan                                                                                                          |
| ------------- | ------------------------------------------------------------------------------------------------------------------- |
| Nama use case | SIA-UC07 Lihat Kalender Akademik                                                                                    |
| Aktor         | Civitas Akademika (berlaku untuk Mahasiswa dan Dosen)                                                               |
| Tujuan        | Civitas Akademika dapat melihat informasi kalender akademik.                                                        |
| Deskripsi     | Civitas Akademika membuka menu kalender akademik untuk melihat informasi kegiatan dan jadwal akademik yang berlaku. |

| Kegiatan                                                                                        | Respon sistem                                                                                                                                     |
| ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                                             |                                                                                                                                                   |
| 1. Civitas Akademika memilih menu Lihat Kalender Akademik.                                      | 2. Sistem menampilkan halaman kalender akademik.                                                                                                  |
| 3. Civitas Akademika memilih kalender akademik yang ingin dilihat.                              | 4. Sistem mengambil dan menampilkan informasi kalender akademik yang dipilih.                                                                     |
| 5. Civitas Akademika melihat informasi kalender akademik.                                       | 6. Sistem menampilkan informasi kalender akademik secara lengkap.                                                                                 |
| **Skenario Alternative**                                                                        |                                                                                                                                                   |
| 7. Civitas Akademika memilih kalender yang informasinya belum tersedia (cabang dari langkah 4). | 8. Sistem menampilkan pemberitahuan bahwa informasi kalender akademik belum tersedia.                                                             |
| **Skenario Akhir**                                                                              | Use case selesai jika informasi kalender akademik berhasil ditampilkan; jika informasi belum tersedia, sistem menampilkan pemberitahuan tersebut. |

**Keterangan tabel:** Skenario ditulis satu kali atas nama Civitas Akademika dan berlaku untuk Mahasiswa serta Dosen melalui generalization aktor. Mahasiswa dan Dosen tidak dibuatkan tabel skenario terpisah.

2. SIA-UC08 – Input Nilai Mata Kuliah
   **Tabel Skenario Use Case SIA-UC08 Input Nilai Mata Kuliah**

| Elemen        | Keterangan                                                                                                                 |
| ------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Nama use case | SIA-UC08 Input Nilai Mata Kuliah                                                                                           |
| Aktor         | Dosen                                                                                                                      |
| Tujuan        | Nilai mahasiswa pada mata kuliah yang diampu dapat dimasukkan dan disimpan oleh dosen.                                     |
| Deskripsi     | Dosen memilih mata kuliah yang diampu, memasukkan nilai mahasiswa, kemudian sistem memeriksa dan menyimpan nilai tersebut. |
| Prasyarat     | Dosen merupakan pengampu mata kuliah yang dipilih.                                                                         |

| Kegiatan                                                                                              | Respon sistem                                                                                                                                                                                                                  |
| ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Skenario Normal**                                                                                   |                                                                                                                                                                                                                                |
| 1. Dosen memilih menu Input Nilai Mata Kuliah.                                                        | 2. Sistem menampilkan daftar mata kuliah yang diampu oleh dosen.                                                                                                                                                               |
| 3. Dosen memilih mata kuliah yang akan diinput nilainya.                                              | 4. Sistem menampilkan daftar mahasiswa pada mata kuliah tersebut beserta kolom nilai.                                                                                                                                          |
| 5. Dosen memasukkan nilai mahasiswa.                                                                  | 6. Sistem memeriksa kelengkapan dan rentang nilai yang dimasukkan.                                                                                                                                                             |
| 7. Dosen menyimpan nilai yang telah dimasukkan.                                                       | 8. Sistem menyimpan nilai mahasiswa dan menampilkan konfirmasi penyimpanan.                                                                                                                                                    |
| **Skenario Alternative**                                                                              |                                                                                                                                                                                                                                |
| 9. Dosen memilih mata kuliah yang bukan merupakan mata kuliah yang diampunya (cabang dari langkah 4). | 10. Sistem menolak akses dan menampilkan pemberitahuan bahwa dosen tidak memiliki hak untuk menginput nilai pada mata kuliah tersebut.                                                                                         |
| 11. Dosen memasukkan nilai di luar rentang nilai yang sah (cabang dari langkah 6).                    | 12. Sistem menolak nilai tersebut dan meminta dosen memperbaiki nilai yang dimasukkan.                                                                                                                                         |
| 13. Dosen belum melengkapi nilai mahasiswa (cabang dari langkah 6).                                   | 14. Sistem menampilkan pemberitahuan bahwa masih terdapat nilai yang belum diisi.                                                                                                                                              |
| **Skenario Akhir**                                                                                    | Use case selesai jika nilai mahasiswa berhasil disimpan; jika dosen bukan pengampu mata kuliah, nilai berada di luar rentang yang sah, atau nilai belum lengkap, sistem menolak atau meminta perbaikan sebelum nilai disimpan. |

**Keterangan tabel:** Use case ini direalisasikan oleh collaboration SIA-CO01 Input Nilai Mata Kuliah. Collaboration tersebut tidak memiliki langkah kegiatan tersendiri pada tabel skenario.

3. SIA-UC09 – Lihat KHS
   **Tabel Skenario Use Case SIA-UC09 Lihat KHS**

| Elemen        | Keterangan                                                                                                                                |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Nama use case | SIA-UC09 Lihat KHS                                                                                                                        |
| Aktor         | Mahasiswa                                                                                                                                 |
| Tujuan        | Mahasiswa dapat melihat Kartu Hasil Studi (KHS) berdasarkan semester yang dipilih.                                                        |
| Deskripsi     | Mahasiswa memilih semester yang ingin dilihat, kemudian sistem menampilkan KHS apabila nilai pada semester tersebut sudah dipublikasikan. |

| Kegiatan                                                                                  | Respon sistem                                                                                                                                                                                 |
| ----------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                                       |                                                                                                                                                                                               |
| 1. Mahasiswa memilih menu Lihat KHS.                                                      | 2. Sistem menampilkan daftar semester yang tersedia.                                                                                                                                          |
| 3. Mahasiswa memilih semester yang ingin dilihat.                                         | 4. Sistem memeriksa ketersediaan publikasi nilai pada semester tersebut.                                                                                                                      |
| 5. Mahasiswa meminta untuk melihat KHS semester yang dipilih.                             | 6. Sistem menampilkan KHS yang berisi daftar mata kuliah dan nilai yang telah dipublikasikan.                                                                                                 |
| **Skenario Alternative**                                                                  |                                                                                                                                                                                               |
| 7. Mahasiswa memilih semester yang nilainya belum dipublikasikan (cabang dari langkah 4). | 8. Sistem menampilkan pemberitahuan bahwa KHS pada semester tersebut belum tersedia karena nilai belum dipublikasikan.                                                                        |
| **Skenario Akhir**                                                                        | Use case selesai jika KHS berhasil ditampilkan untuk semester yang nilainya telah dipublikasikan; jika nilai belum dipublikasikan, sistem menampilkan pemberitahuan bahwa KHS belum tersedia. |

**Keterangan tabel:** Use case ini direalisasikan oleh collaboration SIA-CO02 Lihat KHS. Collaboration tersebut tidak memiliki langkah kegiatan tersendiri pada tabel skenario. Sistem hanya menampilkan nilai yang sudah dipublikasikan.

4. SIA-UC10 – Kelola Data Mahasiswa
   **Tabel Skenario Use Case SIA-UC10 Kelola Data Mahasiswa**

| Elemen        | Keterangan                                                                                                                                      |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Nama use case | SIA-UC10 Kelola Data Mahasiswa                                                                                                                  |
| Aktor         | Admin Akademik                                                                                                                                  |
| Tujuan        | Admin Akademik dapat mengelola data mahasiswa melalui fungsi tambah, ubah, dan hapus data mahasiswa.                                            |
| Deskripsi     | Admin Akademik membuka fungsi pengelolaan data mahasiswa, melihat daftar data mahasiswa, kemudian memilih tindakan pengelolaan yang diperlukan. |

| Kegiatan                                                                                                                                                    | Respon sistem                                                                                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                                                                                                         |                                                                                                                                                                                                 |
| 1. Admin Akademik memilih menu Kelola Data Mahasiswa.                                                                                                       | 2. Sistem menampilkan halaman pengelolaan dan daftar data mahasiswa.                                                                                                                            |
| 3. Admin Akademik memilih tindakan pengelolaan data mahasiswa yang akan dilakukan.                                                                          | 4. Sistem mengarahkan proses ke use case khusus sesuai tindakan yang dipilih.                                                                                                                   |
| 5. Admin Akademik menjalankan salah satu fungsi pengelolaan data mahasiswa.                                                                                 | 6. Sistem memproses tindakan sesuai skenario use case khusus yang dipilih.                                                                                                                      |
| 7. Admin Akademik melihat hasil pengelolaan data mahasiswa.                                                                                                 | 8. Sistem menampilkan hasil pengelolaan data mahasiswa.                                                                                                                                         |
| **Skenario Alternative**                                                                                                                                    |                                                                                                                                                                                                 |
| 9. Admin Akademik memilih tindakan pengelolaan yang tidak dapat dilanjutkan karena data atau proses yang diperlukan tidak tersedia (cabang dari langkah 4). | 10. Sistem menampilkan pemberitahuan bahwa tindakan pengelolaan tidak dapat dilanjutkan.                                                                                                        |
| **Skenario Akhir**                                                                                                                                          | Use case selesai jika salah satu fungsi pengelolaan data mahasiswa berhasil diproses; jika tindakan tidak dapat dilanjutkan, sistem menampilkan pemberitahuan dan data mahasiswa tidak berubah. |

**Keterangan tabel:** SIA-UC10 merupakan use case umum (generalization) untuk SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa. Langkah khusus dari ketiga use case tersebut dijelaskan pada tabel masing-masing, sedangkan langkah pengelolaan yang bersifat umum dirujuk dari tabel ini.

5. SIA-UC11 – Tambah Data Mahasiswa
   **Tabel Skenario Use Case SIA-UC11 Tambah Data Mahasiswa**

| Elemen        | Keterangan                                                                                                                                    |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Nama use case | SIA-UC11 Tambah Data Mahasiswa                                                                                                                |
| Aktor         | Admin Akademik                                                                                                                                |
| Tujuan        | Data mahasiswa baru berhasil ditambahkan ke dalam sistem.                                                                                     |
| Deskripsi     | Admin Akademik menjalankan fungsi tambah data mahasiswa dengan mengisi informasi mahasiswa baru. Langkah pengelolaan umum mengikuti SIA-UC10. |

| Kegiatan                                                                                                    | Respon sistem                                                                                                                                                     |
| ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                                                         |                                                                                                                                                                   |
| 1. Admin Akademik menjalankan fungsi Tambah Data Mahasiswa sesuai SIA-UC10 (lihat Tabel skenario SIA-UC10). | 2. Sistem menampilkan formulir penambahan data mahasiswa.                                                                                                         |
| 3. Admin Akademik mengisi data mahasiswa baru pada formulir yang tersedia.                                  | 4. Sistem memeriksa kelengkapan data mahasiswa yang dimasukkan.                                                                                                   |
| 5. Admin Akademik menyimpan data mahasiswa baru.                                                            | 6. Sistem menyimpan data mahasiswa baru dan menampilkan konfirmasi bahwa data berhasil ditambahkan.                                                               |
| **Skenario Alternative**                                                                                    |                                                                                                                                                                   |
| 7. Admin Akademik mengisi data mahasiswa yang belum lengkap (cabang dari langkah 4).                        | 8. Sistem menampilkan pemberitahuan bahwa data belum lengkap dan meminta Admin Akademik melengkapi data.                                                          |
| **Skenario Akhir**                                                                                          | Use case selesai jika data mahasiswa baru berhasil disimpan; jika data belum lengkap, sistem tidak menyimpan data dan meminta Admin Akademik melengkapi formulir. |

**Keterangan tabel:** SIA-UC11 merupakan use case khusus (generalization) dari SIA-UC10 Kelola Data Mahasiswa. Langkah pengelolaan umum mengikuti SIA-UC10, sedangkan tabel ini hanya menjelaskan perilaku khusus berupa penambahan data mahasiswa baru.

6. SIA-UC12 – Ubah Data Mahasiswa
   **Tabel Skenario Use Case SIA-UC12 Ubah Data Mahasiswa**

| Elemen        | Keterangan                                                                                                                                                                          |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nama use case | SIA-UC12 Ubah Data Mahasiswa                                                                                                                                                        |
| Aktor         | Admin Akademik                                                                                                                                                                      |
| Tujuan        | Data mahasiswa yang dipilih berhasil diperbarui.                                                                                                                                    |
| Deskripsi     | Admin Akademik menjalankan fungsi ubah data mahasiswa dengan memilih data yang akan diperbarui dan mengubah informasi yang diperlukan. Langkah pengelolaan umum mengikuti SIA-UC10. |

| Kegiatan                                                                                                  | Respon sistem                                                                                                                                                      |
| --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Skenario Normal**                                                                                       |                                                                                                                                                                    |
| 1. Admin Akademik menjalankan fungsi Ubah Data Mahasiswa sesuai SIA-UC10 (lihat Tabel skenario SIA-UC10). | 2. Sistem menampilkan daftar data mahasiswa yang dapat diubah.                                                                                                     |
| 3. Admin Akademik memilih data mahasiswa yang akan diperbarui.                                            | 4. Sistem menampilkan formulir berisi data mahasiswa yang dipilih.                                                                                                 |
| 5. Admin Akademik mengubah informasi mahasiswa yang diperlukan.                                           | 6. Sistem memeriksa kelengkapan data yang telah diperbarui.                                                                                                        |
| 7. Admin Akademik menyimpan perubahan data mahasiswa.                                                     | 8. Sistem memperbarui data mahasiswa dan menampilkan konfirmasi bahwa perubahan berhasil disimpan.                                                                 |
| **Skenario Alternative**                                                                                  |                                                                                                                                                                    |
| 9. Admin Akademik memilih data mahasiswa yang tidak ditemukan (cabang dari langkah 4).                    | 10. Sistem menampilkan pemberitahuan bahwa data mahasiswa tidak ditemukan dan proses perubahan tidak dapat dilanjutkan.                                            |
| 11. Admin Akademik mengisi perubahan data yang belum lengkap (cabang dari langkah 6).                     | 12. Sistem menampilkan pemberitahuan bahwa data belum lengkap dan meminta Admin Akademik melengkapi data.                                                          |
| **Skenario Akhir**                                                                                        | Use case selesai jika perubahan data mahasiswa berhasil disimpan; jika data tidak ditemukan atau perubahan belum lengkap, sistem tidak memperbarui data mahasiswa. |

**Keterangan tabel:** SIA-UC12 merupakan use case khusus (generalization) dari SIA-UC10 Kelola Data Mahasiswa. Langkah pengelolaan umum mengikuti SIA-UC10, sedangkan tabel ini hanya menjelaskan perilaku khusus berupa perubahan data mahasiswa.

7. SIA-UC13 – Hapus Data Mahasiswa
   **Tabel Skenario Use Case SIA-UC13 Hapus Data Mahasiswa**

| Elemen        | Keterangan                                                                                                                                                                                                                                        |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nama use case | SIA-UC13 Hapus Data Mahasiswa                                                                                                                                                                                                                     |
| Aktor         | Admin Akademik                                                                                                                                                                                                                                    |
| Tujuan        | Data mahasiswa yang memenuhi syarat berhasil dihapus dari sistem.                                                                                                                                                                                 |
| Deskripsi     | Admin Akademik menjalankan fungsi hapus data mahasiswa dengan memilih data yang akan dihapus. Sistem memeriksa apakah mahasiswa tersebut memiliki data akademik aktif sebelum melakukan penghapusan. Langkah pengelolaan umum mengikuti SIA-UC10. |

| Kegiatan                                                                                                   | Respon sistem                                                                                                                                                                                                                                       |
| ---------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                                                        |                                                                                                                                                                                                                                                     |
| 1. Admin Akademik menjalankan fungsi Hapus Data Mahasiswa sesuai SIA-UC10 (lihat Tabel skenario SIA-UC10). | 2. Sistem menampilkan daftar data mahasiswa yang dapat dipilih.                                                                                                                                                                                     |
| 3. Admin Akademik memilih data mahasiswa yang akan dihapus.                                                | 4. Sistem memeriksa data akademik aktif yang dimiliki mahasiswa tersebut.                                                                                                                                                                           |
| 5. Admin Akademik mengonfirmasi penghapusan data mahasiswa.                                                | 6. Sistem menghapus data mahasiswa dan menampilkan konfirmasi bahwa data berhasil dihapus.                                                                                                                                                          |
| **Skenario Alternative**                                                                                   |                                                                                                                                                                                                                                                     |
| 7. Mahasiswa yang dipilih masih memiliki data akademik aktif (cabang dari langkah 4).                      | 8. Sistem menolak penghapusan dan menampilkan pemberitahuan bahwa data mahasiswa masih memiliki data akademik aktif.                                                                                                                                |
| 9. Admin Akademik memilih data mahasiswa yang tidak ditemukan (cabang dari langkah 4).                     | 10. Sistem menampilkan pemberitahuan bahwa data mahasiswa tidak ditemukan dan proses penghapusan tidak dapat dilanjutkan.                                                                                                                           |
| **Skenario Akhir**                                                                                         | Use case selesai jika data mahasiswa berhasil dihapus dan mahasiswa tidak memiliki data akademik aktif; jika mahasiswa masih memiliki data akademik aktif atau data tidak ditemukan, sistem menolak penghapusan dan data mahasiswa tetap tersimpan. |

**Keterangan tabel:** SIA-UC13 merupakan use case khusus (generalization) dari SIA-UC10 Kelola Data Mahasiswa. Langkah pengelolaan umum mengikuti SIA-UC10, sedangkan tabel ini hanya menjelaskan perilaku khusus berupa penghapusan data mahasiswa. Penghapusan hanya diperbolehkan apabila mahasiswa tidak memiliki data akademik aktif.

### Langkah 4. Penerapan Generalization Aktor pada UC07

Pada Use Case UC07 (Lihat Kalender Akademik), aktor yang digunakan adalah **Civitas Akademika** sebagai aktor umum (_general actor_). Aktor Mahasiswa dan Dosen merupakan aktor khusus (_specific actor_) yang mewarisi hak akses dari Civitas Akademika melalui hubungan _generalization_.

Oleh karena itu, skenario UC07 cukup ditulis satu kali menggunakan aktor Civitas Akademika. Skenario tersebut berlaku untuk Mahasiswa maupun Dosen, sehingga tidak perlu dibuat tabel skenario secara terpisah untuk masing-masing aktor.

**Keterangan:** Generalization aktor diterapkan agar perilaku yang sama dapat digunakan oleh aktor Mahasiswa dan Dosen tanpa harus menuliskan skenario secara berulang.

### Langkah 5. Penerapan Generalization Use Case pada UC10–UC13

Pada tahap ini, diterapkan hubungan _generalization_ antara UC10 (Kelola Data Mahasiswa) sebagai _general use case_ dengan UC11 (Tambah Data Mahasiswa), UC12 (Ubah Data Mahasiswa), dan UC13 (Hapus Data Mahasiswa) sebagai _specific use case_.

UC10 digunakan untuk menjelaskan alur umum dalam pengelolaan data mahasiswa yang menjadi dasar bagi ketiga use case khusus tersebut. Sementara itu, UC11, UC12, dan UC13 masing-masing menjelaskan proses khusus sesuai dengan fungsi yang dilakukan, yaitu menambahkan, mengubah, dan menghapus data mahasiswa.

Dengan penerapan generalization ini, langkah-langkah yang bersifat umum cukup dijelaskan pada UC10. Adapun setiap use case khusus hanya menjelaskan langkah-langkah yang membedakannya dari UC10 serta memberikan rujukan terhadap skenario umum tersebut. Dengan demikian, tidak terjadi pengulangan penulisan langkah yang sama pada setiap tabel skenario.

### Langkah 6. Penerapan Keterangan Collaboration pada UC08 dan UC09

Pada tahap ini, keterangan _collaboration_ diterapkan pada skenario UC08 (Input Nilai Mata Kuliah) dan UC09 (Lihat KHS) sesuai dengan hubungan yang terdapat pada diagram P04.

Pada UC08, dicantumkan keterangan bahwa proses Input Nilai Mata Kuliah direalisasikan melalui **SIA-CO01**. Sementara itu, pada UC09 dicantumkan keterangan bahwa proses Lihat KHS direalisasikan melalui **SIA-CO02**.

Hubungan _collaboration_ tersebut hanya dicantumkan sebagai keterangan pada masing-masing tabel skenario dan tidak dituliskan sebagai aktivitas tersendiri dalam alur normal maupun alternatif. Dengan demikian, penulisan skenario tetap berfokus pada interaksi antara aktor dan sistem.

<Langkah 7 dilanjutkan pada folder 06_laporan>
