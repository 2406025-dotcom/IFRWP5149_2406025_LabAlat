# Kebutuhan Sistem Informasi Akademik

## 1. Kebutuhan Fungsional

| ID      | Kebutuhan                                                                  |
| ------- | -------------------------------------------------------------------------- |
| SIA-R03 | Mahasiswa dapat mengajukan KRS.                                            |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian dari pengajuan.                      |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan. |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS.                 |

## 2. Kebutuhan dari Pertemuan Sebelumnya

| ID      | Kebutuhan                                     |
| ------- | --------------------------------------------- |
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah.        |
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah. |

## 3. Batas dan Asumsi

1. Pengguna telah terautentikasi.
2. Data mata kuliah, prasyarat, dan jadwal tersedia.
3. Validasi yang gagal menyebabkan pengajuan belum berhasil tersimpan.
4. Unduh bukti bukan syarat keberhasilan pengajuan.
5. KRS yang tersimpan belum berarti disetujui dosen wali.
6. Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

## 4. Alur Utama

1. Mahasiswa memilih mata kuliah.
2. Sistem memvalidasi kelengkapan, prasyarat, dan benturan jadwal.
3. Jika validasi berhasil, sistem menyimpan pengajuan KRS dengan status menunggu persetujuan dosen wali.
4. Sistem menampilkan konfirmasi penyimpanan.
5. Mahasiswa memilih apakah akan mengunduh bukti pengajuan.
6. Dosen wali dapat menyetujui atau menolak KRS dan memberikan catatan keputusan.

## Langkah 2 — Identifikasi Aktor dan Use Case

### A. Daftar Aktor

| No. | Nama Aktor | Deskripsi                                                                    |
| --- | ---------- | ---------------------------------------------------------------------------- |
| 1   | Mahasiswa  | Mengajukan KRS dan memilih untuk mengunduh bukti pengajuan.                  |
| 2   | Dosen Wali | Memproses persetujuan atau penolakan KRS serta memberikan catatan keputusan. |

### B. Katalog Use Case

| ID    | Nama Fungsi           | Aktor Terkait                                   | Sumber Kebutuhan |
| ----- | --------------------- | ----------------------------------------------- | ---------------- |
| UC-01 | Ajukan KRS            | Mahasiswa                                       | SIA-R03          |
| UC-02 | Validasi KRS          | Sistem, sebagai bagian dari pengajuan Mahasiswa | SIA-R04          |
| UC-03 | Unduh Bukti Pengajuan | Mahasiswa                                       | SIA-R05          |
| UC-04 | Proses Keputusan KRS  | Dosen Wali                                      | SIA-R06          |

### C. Batas Identifikasi

Identifikasi aktor dan use case difokuskan pada proses pengajuan KRS, validasi pengajuan, pengunduhan bukti, serta pemrosesan keputusan oleh dosen wali. Kebutuhan SIA-R01 dan SIA-R02 tetap dipertahankan dengan ID aslinya sebagai kebutuhan dari Pertemuan 2, tetapi tidak dimasukkan sebagai fungsi utama pada katalog ini.

## Langkah 3 — Menentukan Include

### Relasi Include

- **Sumber:** UC-01 — Ajukan KRS
- **Tujuan:** UC-02 — Validasi KRS
- **Perilaku yang disertakan:** Memeriksa kelengkapan pengajuan, prasyarat mata kuliah, dan benturan jadwal.

### Alasan Relasi

Relasi `<<include>>` digunakan karena validasi merupakan proses wajib yang harus dilakukan setiap kali mahasiswa mengajukan KRS. Jika validasi gagal, pengajuan belum berhasil tersimpan.

## Langkah 4 — Menentukan Extend

### Relasi Extend

- **Sumber:** UC-03 — Unduh Bukti Pengajuan
- **Tujuan:** UC-01 — Ajukan KRS
- **Kondisi:** Pengajuan KRS berhasil disimpan, konfirmasi penyimpanan ditampilkan, dan mahasiswa memilih untuk mengunduh bukti.
- **Perilaku tambahan:** Sistem menyediakan bukti pengajuan untuk diunduh oleh mahasiswa.

### Alasan Relasi

Relasi `<<extend>>` digunakan karena pengunduhan bukti bukan proses wajib dalam pengajuan KRS. Mahasiswa dapat memilih untuk mengunduh bukti atau tidak. Jika mahasiswa tidak memilih unduh bukti, pengajuan yang berhasil disimpan tetap dianggap berhasil.
sampai langkah 4