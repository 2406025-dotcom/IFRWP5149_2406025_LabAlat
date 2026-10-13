# Evaluasi & Perbaikan Notasi Use Case — P03 Sistem Informasi Akademik (KRS)

## Ringkasan Perbaikan Notasi

Dokumen ini berisi poin-poin evaluasi dan perbaikan notasi untuk penyesuaian spesifikasi kebutuhan serta pemodelan _use case_ pada modul Sistem Informasi Akademik (KRS).

---

### 1. Penyesuaian Format ID Use Case pada Dokumen Deskripsi

- **Permasalahan:** Terjadi ketidakselarasan penamaan antara referensi kebutuhan dan katalog fungsi pada berkas `03_latihan_tools/P03/SIA/P03_2406014_SIA_deskripsi_v01.md`. Kebutuhan menggunakan format `SIA-R01` hingga `SIA-R06`, sedangkan _use case_ menggunakan penomoran `SIA-UC01`, `SIA-UC03`, `SIA-UC04`, `SIA-UC05`, dan `SIA-UC06`.
- **Alasan & Solusi:** Perbedaan penamaan ini menimbulkan inkonsistensi antara tabel kebutuhan dan katalog fungsi. Seluruh identifikasi _use case_ disetarakan menjadi format `SIA-R` agar sejalan dan konsisten dengan matriks kebutuhan sistem.

---

### 2. Koreksi Sumber Kebutuhan pada Fungsi Utama Ajukan KRS

- **Permasalahan:** Bagian spesifikasi fungsi `SIA-R03` (sebelumnya `SIA-UC03`) mencantumkan dua sumber kebutuhan sekaligus, yaitu `SIA-R03` dan `SIA-R04`.
- **Alasan & Solusi:** Sesuai dengan prinsip pemisahan tanggung jawab (_separation of concerns_), `SIA-R03` adalah _use case_ utama (_Ajukan KRS_), sedangkan `SIA-R04` (_Validasi KRS_) merupakan fungsi _include_ yang dipanggil oleh `SIA-R03`. Oleh karena itu, sumber kebutuhan untuk _Ajukan KRS_ cukup mencantumkan `SIA-R03`, karena proses verifikasi sudah menjadi bagian internal (_include_) dari alur pengajuan.

---

### 3. Klarifikasi Penomoran ID yang Melompat

- **Permasalahan:** Urutan _use case_ tidak berurutan, melompat dari `SIA-UC01` langsung ke `SIA-UC03` tanpa adanya `SIA-UC02`, padahal kode `SIA-R02` (_Admin akademik dapat mengelola jadwal kuliah_) ada di daftar kebutuhan.
- **Alasan & Solusi:** Ketidakhadiran `SIA-UC02` dalam alur pengajuan KRS dapat membingungkan pembaca. Seharusnya diberikan penjelasan eksplisit bahwa `SIA-R02` tidak direalisasikan sebagai _use case_ dalam diagram skenario ini karena Admin Akademik tidak berinteraksi langsung dalam alur pengisian KRS oleh mahasiswa.

---

### 4. Penyelarasan Kode ID Antar-Dokumen Penunjang

- **Permasalahan:** Penggunaan variabel penamaan belum seragam di seluruh dokumen proyek.
- **Alasan & Solusi:** Dengan digunakannya format `SIA-R` sebagai acuan akhir untuk seluruh identifikasi (kebutuhan dan _use case_), maka berkas deskripsi pada folder `03_latihan_tools` dan `04_model_analisi` harus diperbarui agar selaras dengan dokumen acuan utama pada `01_skenario/P03_SIA_skenario_v01.md`.
