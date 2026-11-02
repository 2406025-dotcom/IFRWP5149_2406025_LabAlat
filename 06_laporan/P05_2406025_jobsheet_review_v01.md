### Langkah 7. Pemeriksaan Ketujuh Tabel Skenario

Pada tahap terakhir, dilakukan pemeriksaan terhadap tujuh tabel skenario, mulai dari UC07 sampai UC13, menggunakan checklist yang terdapat pada Jobsheet Praktikum Pertemuan 5. Pemeriksaan ini bertujuan untuk memastikan bahwa setiap tabel skenario telah memenuhi ketentuan penulisan dan sesuai dengan diagram kumulatif SIA Pertemuan 4.

Aspek yang diperiksa meliputi kelengkapan field tabel, urutan dan penomoran langkah, kesesuaian antara kolom kegiatan dengan respon sistem, kejelasan data yang dimasukkan dan ditampilkan, serta penerapan hubungan _generalization_ dan _collaboration_.

Selain itu, dilakukan penelusuran terhadap setiap tabel untuk memastikan bahwa nama use case, ID, aktor, dan hubungan yang digunakan telah sesuai dengan diagram P04. Diagram SIA Pertemuan 4 tetap dipertahankan dan tidak dilakukan perubahan karena hanya digunakan sebagai acuan dalam penyusunan dokumen skenario.

#### A. Checklist Pemeriksaan

| No. | Aspek Pemeriksaan                                                                                                                                                            | Status |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ |
| 1   | Seluruh field tabel telah terisi, meliputi nama use case, aktor, tujuan, deskripsi, kolom kegiatan, respon sistem, skenario normal, skenario alternatif, dan skenario akhir. | ✓      |
| 2   | Langkah ditulis berurutan dengan satu aksi pada setiap langkah.                                                                                                              | ✓      |
| 3   | Penomoran berlanjut dari skenario normal ke skenario alternatif.                                                                                                             | ✓      |
| 4   | Kolom kegiatan hanya berisi aksi aktor dan kolom respon sistem hanya berisi tanggapan sistem.                                                                                | ✓      |
| 5   | Data yang dimasukkan dan ditampilkan disebutkan secara jelas.                                                                                                                | ✓      |
| 6   | Relasi _include_ dan _extend_ ditulis sesuai ketentuan pada use case terkait.                                                                                                | ✓      |
| 7   | _Generalization_ aktor diterapkan pada UC07 dengan menggunakan aktor Civitas Akademika.                                                                                      | ✓      |
| 8   | _Generalization_ use case diterapkan pada UC10–UC13.                                                                                                                         | ✓      |
| 9   | _Collaboration_ dicantumkan pada keterangan UC08 dan UC09, bukan sebagai langkah kegiatan.                                                                                   | ✓      |
| 10  | Setiap tabel memiliki skenario alternatif dan skenario akhir.                                                                                                                | ✓      |
| 11  | Nama, ID, dan aktor disesuaikan dengan diagram SIA P04.                                                                                                                      | ✓      |
| 12  | Diagram P04 tidak diubah dan dokumen skenario disiapkan untuk disimpan pada folder yang ditentukan.                                                                          | ✓      |

#### B. Catatan Penelusuran Setiap Tabel

| Tabel yang Diperiksa           | Relasi yang Ditelusuri                                               | Hasil Pencocokan terhadap Diagram P04                                                          |
| ------------------------------ | -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| UC07 – Lihat Kalender Akademik | _Generalization_ aktor Civitas Akademika dengan Mahasiswa dan Dosen. | Skenario menggunakan aktor Civitas Akademika dan berlaku untuk Mahasiswa serta Dosen.          |
| UC08 – Input Nilai Mata Kuliah | _Collaboration_ SIA-CO01.                                            | Keterangan SIA-CO01 dicantumkan pada tabel UC08 dan tidak dibuat sebagai langkah kegiatan.     |
| UC09 – Lihat KHS               | _Collaboration_ SIA-CO02.                                            | Keterangan SIA-CO02 dicantumkan pada tabel UC09 dan tidak dibuat sebagai langkah kegiatan.     |
| UC10 – Kelola Data Mahasiswa   | _Generalization_ use case sebagai use case umum.                     | UC10 menjadi skenario umum yang digunakan sebagai acuan bagi UC11, UC12, dan UC13.             |
| UC11 – Tambah Data Mahasiswa   | _Generalization_ terhadap UC10.                                      | UC11 menjelaskan proses khusus penambahan data mahasiswa dan merujuk pada skenario umum UC10.  |
| UC12 – Ubah Data Mahasiswa     | _Generalization_ terhadap UC10.                                      | UC12 menjelaskan proses khusus perubahan data mahasiswa dan merujuk pada skenario umum UC10.   |
| UC13 – Hapus Data Mahasiswa    | _Generalization_ terhadap UC10.                                      | UC13 menjelaskan proses khusus penghapusan data mahasiswa dan merujuk pada skenario umum UC10. |

#### C. Hasil Pemeriksaan

Berdasarkan hasil pemeriksaan, tujuh tabel skenario UC07 sampai UC13 telah disusun dengan memperhatikan struktur tabel, alur interaksi antara aktor dan sistem, serta hubungan antar-use case sesuai dengan ketentuan Jobsheet Praktikum Pertemuan 5.

Penerapan _generalization_ aktor pada UC07 dilakukan dengan menggunakan Civitas Akademika sebagai aktor umum. Sementara itu, penerapan _generalization_ use case dilakukan dengan menjadikan UC10 sebagai skenario umum bagi UC11, UC12, dan UC13. Keterangan _collaboration_ juga telah dicantumkan pada UC08 dan UC09 sesuai dengan hubungan yang terdapat pada diagram P04.

Dengan demikian, penyusunan tujuh tabel skenario SIA Pertemuan 5 telah diselesaikan berdasarkan hasil praktik dan pemeriksaan terhadap ketentuan jobsheet. Diagram SIA Pertemuan 4 tetap digunakan sebagai acuan tanpa dilakukan perubahan.
