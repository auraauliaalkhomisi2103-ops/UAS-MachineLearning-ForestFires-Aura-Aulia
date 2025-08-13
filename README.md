# UAS Machine Learning - Prediksi Luas Kebakaran Hutan

- **Nama:** Aura Aulia Alkhomisi
- **NIM:** 227006516044
- **Kelas:** Machine Leaning

---

## 1. Tujuan Analisis

Tujuan dari proyek ini adalah untuk membangun sebuah model *machine learning* yang dapat memprediksi **luas area hutan yang terbakar (`area`)** dalam satuan hektar. Prediksi ini didasarkan pada data spasial (koordinat X-Y), data temporal (bulan dan hari), serta beberapa variabel cuaca dari sistem *Fire Weather Index* (FWI) Kanada.

---

## 2. Dataset

- **Nama Dataset:** Forest Fires Dataset
- **Sumber:** UCI Machine Learning Repository
- **Deskripsi:** Dataset ini berisi 517 catatan kebakaran hutan dari wilayah timur laut Portugal. Terdapat 12 fitur (variabel input) seperti suhu, kelembapan relatif, kecepatan angin, dan beberapa indeks dari FWI. Variabel target yang ingin diprediksi adalah `area`, yaitu total luas area hutan yang terbakar dalam satuan hektar (ha).

---

## 3. Algoritma dan Alasan Pemilihan

- **Algoritma:** **Random Forest Regressor**
- **Alasan Pemilihan:**
  1.  **Kemampuan Menangani Hubungan Kompleks:** Hubungan antara kondisi cuaca dan luas kebakaran hutan tidak bersifat sederhana atau linear. Random Forest sangat baik dalam menangkap pola-pola yang rumit tanpa memerlukan asumsi yang kaku tentang distribusi data.
  2.  **Kuat Terhadap *Outlier*:** Dataset ini kemungkinan memiliki beberapa nilai ekstrem (kebakaran yang sangat luas). Random Forest tidak terlalu sensitif terhadap nilai-nilai pencilan ini dibandingkan model regresi linear.
  3.  **Memberikan *Feature Importance*:** Salah satu keunggulan utama Random Forest adalah kemampuannya untuk memberikan peringkat fitur mana yang paling berpengaruh dalam membuat prediksi. Ini sangat berguna untuk memahami faktor-faktor pendorong utama kebakaran hutan.

---

## 4. Hasil Analisis dan Kesimpulan

Model telah berhasil dilatih untuk memprediksi luas area yang terbakar dan dievaluasi menggunakan data uji.

- **Preprocessing Data:** Kolom kategorikal seperti `month` dan `day` diubah menjadi format numerik menggunakan *One-Hot Encoding*. Variabel target `area`, yang distribusinya sangat miring (banyak nilai nol), ditransformasi menggunakan logaritma natural (`np.log1p`) untuk menormalkan distribusinya dan membantu model belajar lebih efektif.

- **Evaluasi Model:** Kinerja model dievaluasi menggunakan metrik *Mean Absolute Error (MAE)*.
  - **MAE yang Diperoleh: 19.88 hektar**
  - **Interpretasi:** Hasil ini berarti bahwa, secara rata-rata, prediksi yang dibuat oleh model memiliki selisih atau kesalahan sekitar **19.88 hektar** dari luas area kebakaran yang sebenarnya.

- **Fitur Paling Penting:** Berdasarkan analisis *feature importance* dari model Random Forest, faktor-faktor yang paling berpengaruh dalam memprediksi luas kebakaran hutan adalah **suhu (`temp`), kelembapan relatif (`RH`), dan indeks kekeringan dari *Duff Moisture Code* (`DMC`)**. Hal ini menunjukkan bahwa kondisi cuaca harian memegang peranan paling krusial.

- **Kesimpulan:** Model Random Forest terbukti mampu mempelajari pola dari data kebakaran hutan untuk melakukan prediksi. Meskipun terdapat selisih prediksi (MAE), model ini berhasil mengidentifikasi variabel-variabel meteorologis kunci sebagai faktor pendorong utama.

---

## 5. Cara Menjalankan Program

Program ini dikerjakan menggunakan Google Colab yang terhubung dengan repository GitHub.

1.  Buka file `analisis_kebakaran_hutan.ipynb` yang ada di repository ini.
2.  Pilih opsi "Open in Colab" untuk membuka notebook di lingkungan Google Colab.
3.  Pastikan untuk mengganti `username` di dalam kode dengan username GitHub yang benar agar program dapat memuat dataset.
4.  Jalankan semua sel kode secara berurutan dari atas ke bawah.
