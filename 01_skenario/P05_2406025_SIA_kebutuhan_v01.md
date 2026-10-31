## Langkah 1 — Meneruskan Pengerjaan Sebelumnya

Buka kembali diagram SIA Pertemuan 4 pada folder 04_model_analisis/P04/SIA hanya sebagai acuan. Jangan mengubah isi diagram.

## Langkah 2 — Identifikasi Kebutuhan dan Katalog Use Case

### A. Generalization Aktor

| Aktor Umum        | Aktor Khusus |
| ----------------- | ------------ |
| Civitas Akademika | Mahasiswa    |
| Civitas Akademika | Dosen        |

Mahasiswa dan Dosen merupakan aktor khusus yang mewarisi fungsi dari Civitas Akademika, yaitu melihat kalender akademik.

### B. Generalization Use Case

| Use Case Umum                  | Use Case Khusus                |
| ------------------------------ | ------------------------------ |
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC11 Tambah Data Mahasiswa |
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC12 Ubah Data Mahasiswa   |
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC13 Hapus Data Mahasiswa  |

SIA-UC10 Kelola Data Mahasiswa merupakan use case umum yang memiliki tiga use case khusus, yaitu tambah, ubah, dan hapus data mahasiswa.

### C. Keterangan

Kebutuhan SIA-R07 sampai SIA-R12 dan katalog use case SIA-UC07 sampai SIA-UC13 digunakan sebagai tambahan dari kebutuhan dan katalog pertemuan sebelumnya. Seluruh ID yang sudah digunakan tetap dipertahankan agar model Sistem Informasi Akademik bersifat kumulatif.
