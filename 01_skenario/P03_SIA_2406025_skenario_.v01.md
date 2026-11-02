# Spesifikasi Kebutuhan Sistem & Analisis Use Case Pengajuan KRS

---

## 1. Analisis Skenario & Kebutuhan Sistem

### Deskripsi Skenario
Proses diawali saat mahasiswa mengakses menu KRS untuk memilih mata kuliah. Setiap berkas yang dikirim akan secara otomatis diproses oleh sistem melalui tahapan verifikasi guna mengecek kelengkapan data, prasyarat mata kuliah, serta potensi bentrokan jadwal. 

Apabila pengecekan dinyatakan memenuhi syarat, berkas akan tersimpan dengan status **Menunggu Persetujuan Dosen Pembimbing Akademik**. Pada layar konfirmasi, mahasiswa diberi opsi tambahan untuk mengunduh lembar bukti pengajuan. Selanjutnya, Dosen Pembimbing Akademik meninjau berkas tersebut untuk memberikan persetujuan atau penolakan beserta catatan evaluasi.

---

### Katalogs Kebutuhan Tugas (Requirements Catalog)

| ID | Deskripsi Kebutuhan |
| :--- | :--- |
| **SIA-R01** | Mahasiswa dapat melihat jadwal perkuliahan. |
| **SIA-R02** | Staf Admin Akademik dapat mengelola jadwal perkuliahan. |
| **SIA-R03** | Mahasiswa dapat mengajukan rencana studi (KRS). |
| **SIA-R04** | Sistem mengeksekusi verifikasi kelayakan KRS saat proses pengajuan. |
| **SIA-R05** | Mahasiswa dapat mengunduh bukti KRS setelah menyelesaikan pengajuan. |
| **SIA-R06** | Dosen Pembimbing Akademik dapat menyetujui atau menolak draf KRS. |

---

### Batasan & Asumsi Sistem
* **Autentikasi:** Akses hanya diberikan kepada pengguna yang telah berhasil masuk (*authenticated*).
* **Ketersediaan Data:** Seluruh referensi data (jadwal, ketersediaan kelas, dan prasyarat) dianggap sudah siap di dalam database.
* **Kegagalan Validasi:** Kegagalan verifikasi otomatis akan menggagalkan penyimpanan berkas KRS.
* **Sifat Bukti Pengajuan:** Pencetakan/pengunduhan bukti pengajuan bersifat opsional dan tidak memengaruhi keabsahan pengajuan.
* **Status Persetujuan:** Tersimpannya draft KRS tidak menjamin persetujuan otomatis dari Dosen Pembimbing Akademik.
* **Batas Cakupan:** Alur modul pembayaran, input nilai, dan arsitektur database berada di luar cakupan skenario ini.

---

## 2. Pihak & Interaksi Pengguna (Aktor)

| Pihak | Peran & Interaksi dalam Skenario | Status / Kategori |
| :--- | :--- | :--- |
| **Mahasiswa** | Membuka portal, menentukan daftar mata kuliah, mengirim berkas, serta melihat konfirmasi dan mengunduh bukti. | Aktor Utama |
| **Dosen Pembimbing Akademik** | Meninjau pengajuan yang telah lolos verifikasi, lalu menetapkan keputusan (setuju/tolak). | Aktor Utama |
| **Sistem (Pemeriksa KRS)** | Berjalan otomatis pada latar belakang sistem tanpa butuh interaksi manusia. | Fungsi Internal (*Include*) |
| **Admin Akademik** | Tidak terlibat langsung dalam tahapan operasional pengajuan KRS ini. | Tidak Dilibatkan |

---

## 3. Katalog Fungsi & Pemetaan Relasi

| ID | Nama Fungsi | Aktor Terkait | Sumber Referensi |
| :--- | :--- | :--- | :--- |
| **SIA-R01** | Lihat Jadwal Kuliah | Mahasiswa | SIA-R01 |
| **SIA-R03** | Pengajuan KRS | Mahasiswa | SIA-R03 |
| **SIA-R04** | Validasi Otomatis KRS | Tidak ada (Dipanggil oleh SIA-R03 via *Include*) | SIA-R04 |
| **SIA-R05** | Unduh Bukti Pengajuan | Mahasiswa (*Extend* dari SIA-R03) | SIA-R05 |
| **SIA-R06** | Persetujuan Dosen Wali | Dosen Pembimbing Akademik | SIA-R06 |

> **Catatan:** Fungsi **SIA-R02** (*Pengelolaan Jadwal oleh Admin*) ditiadakan dari skenario ini karena Admin Akademik tidak memiliki keterkaitan langsung dengan alur pengisian KRS oleh mahasiswa.

---

## 4. Penjelasan Relasi Use Case

### A. Analisis Relasi Include (SIA-R03 $\rightarrow$ SIA-R04)

* **Aspek Relasi:** *Pengajuan KRS* (SIA-R03) memanggil *Validasi KRS* (SIA-R04).
* **Rasionalisasi:** Tahapan pengecekan pasti dieksekusi setiap kali mahasiswa mengirimkan KRS tanpa kondisi khusus. Tanpa kelulusan tahapan ini, berkas tidak akan tersimpan. 
* **Tujuan Pemisahan:** Membuat struktur alur utama tetap ringkas serta memungkinkan logika validasi dipanggil kembali jika terjadi revisi di masa mendatang.
* **Arah Relasi:** Panah mengarah dari SIA-R03 menuju SIA-R04 sebagai *sub-routine* yang wajib dipanggil.

### B. Analisis Relasi Extend (SIA-R05 $\rightarrow$ SIA-R03)

* **Aspek Relasi:** *Lihat/Unduh Bukti* (SIA-R05) memperluas *Pengajuan KRS* (SIA-R03).
* **Rasionalisasi:** Pengajuan KRS tetap dianggap selesai dan sah meskipun mahasiswa tidak membuka atau mengunduh bukti. Tindakan ini murni atas kehendak pengguna pada titik ekstensi (*extension point*) di layar konfirmasi akhir. Oleh sebab itu, relasi yang tepat adalah *Extend* (opsional), bukan *Include* (wajib).
* **Arah Relasi:** Panah bertuliskan `<<extend>>` mengarah dari SIA-R05 ke SIA-R03.

---

## 5. Detail Spesifikasi Use Case

### A. SIA-R03 — Pengajuan KRS

* **Tujuan:** Merekam draf rencana studi mahasiswa ke dalam database.
* **Aktor Utama:** Mahasiswa
* **Aktor Pendukung:** Dosen Pembimbing Akademik
* **Prasyarat:** Mahasiswa telah *login*, periode KRS aktif, dan data mata kuliah tersedia.
* **Pascakondisi Berhasil:** Berkas tersimpan dengan status *Menunggu Persetujuan*.
* **Pascakondisi Gagal:** Tidak ada pengajuan KRS baru yang tersimpan di sistem.
* **Include:** SIA-R04 (Validasi KRS)
* **Extension Point:** Bukti pengajuan tersedia pada langkah 6.
* **Extend:** SIA-R05 jika [mahasiswa memilih lihat/unduh bukti pengajuan].

#### Alur Langkah (Main Flow):
| Langkah | Tindakan Mahasiswa | Respons Sistem |
| :---: | :--- | :--- |
| **1** | Membuka formulir pengajuan KRS | Menampilkan daftar mata kuliah dan jadwal yang ditawarkan |
| **2** | Memilih mata kuliah yang diinginkan | Merekam pilihan dan menghitung kalkulasi total SKS |
| **3** | Mengirimkan berkas pengajuan | Memeriksa kelengkapan input data |
| **4** | — | Memicu eksekusi **SIA-R04 (Validasi KRS)** |
| **5** | — | Jika valid, menyimpan berkas KRS dan meneruskannya ke Dosen Pembimbing |
| **6** | Melihat konfirmasi pengajuan | Menampilkan status pengajuan (*mencapai Extension Point*) |
| **7** | Mengakhiri proses pengajuan | Menutup sesi formulir pengajuan |

---

### B. SIA-R04 — Validasi Otomatis KRS

* **Tujuan:** Memastikan susunan mata kuliah tidak melanggar aturan akademik.
* **Aktor Utama:** Tidak ada (Sistem/Internal)
* **Pemicu:** Dipanggil otomatis oleh SIA-R03 pada langkah ke-4.
* **Prasyarat:** Data pengajuan KRS telah diterima oleh sistem.
* **Pascakondisi Berhasil:** Pengajuan dinyatakan valid.
* **Pascakondisi Gagal:** Pengajuan dinyatakan tidak valid disertai pesan kesalahan.
* **Included By:** SIA-R03

#### Alur Langkah:
| Langkah | Tindakan Aktor | Respons Sistem |
| :---: | :--- | :--- |
| **1** | — | Mengecek batas maksimal SKS berdasarkan IPS semester sebelumnya |
| **2** | — | Memeriksa potensi bentrokan jam antar jadwal kuliah yang dipilih |
| **3** | — | Memeriksa kelengkapan mata kuliah prasyarat |
| **4** | — | Mengembalikan status hasil verifikasi ke fungsi SIA-R03 |

---

### C. SIA-R05 — Lihat Bukti Pengajuan KRS

* **Tujuan:** Menyajikan ringkasan dan bukti fisik pengajuan rencana studi.
* **Aktor Utama:** Mahasiswa
* **Pemicu:** Mahasiswa memilih opsi "Lihat Bukti" pada *extension point* SIA-R03.
* **Prasyarat:** Pengajuan KRS telah berhasil tersimpan.
* **Pascakondisi Berhasil:** Lembar bukti pengajuan KRS ditampilkan.
* **Pascakondisi Gagal:** Bukti pengajuan tidak ditampilkan.
* **Extend:** Memperluas SIA-R03 pada titik ekstensi *"Bukti pengajuan tersedia"*.

#### Alur Langkah:
| Langkah | Tindakan Mahasiswa | Respons Sistem |
| :---: | :--- | :--- |
| **1** | Memilih perintah untuk melihat bukti | Mengambil rincian data KRS yang tersimpan |
| **2** | — | Menampilkan bukti (daftar mata kuliah, total SKS, status, dan timestamp) |
| **3** | Menutup tampilan bukti | Kembali ke alur utama SIA-R03 |

---

### D. SIA-R06 — Konfirmasi Pengajuan KRS

* **Tujuan:** Menetapkan keputusan persetujuan atas draf KRS mahasiswa bimbingan.
* **Aktor Utama:** Dosen Pembimbing Akademik
* **Prasyarat:** Dosen terautentikasi dan terdapat pengajuan KRS berstatus *Menunggu Persetujuan*.
* **Pascakondisi Berhasil:** Status berkas diperbarui menjadi *Disetujui* atau *Ditolak*.
* **Pascakondisi Gagal:** Status berkas tetap *Menunggu Persetujuan*.

#### Alur Langkah:
| Langkah | Tindakan Dosen Wali | Respons Sistem |
| :---: | :--- | :--- |
| **1** | Membuka daftar pengajuan KRS mahasiswa bimbingan | Menyajikan daftar mahasiswa yang mengajukan KRS |
| **2** | Memilih salah satu berkas pengajuan | Menampilkan rincian rencana studi yang dipilih |
| **3** | Menyetujui atau menolak (disertai catatan) | Menyimpan keputusan dan memperbarui status berkas |
| **4** | — | Menampilkan notifikasi konfirmasi sukses |