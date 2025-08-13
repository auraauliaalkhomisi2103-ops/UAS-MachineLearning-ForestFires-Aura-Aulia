# UAS Machine Learning - Prediksi Luas Kebakaran Hutan

- **Nama:** Aura Aulia
- **NIM:** [NIM Anda]
- **Kelas:** [Kelas Anda]

---

## 1. Tujuan Analisis

Tujuan dari proyek ini adalah untuk membangun sebuah model machine learning yang dapat memprediksi **luas area hutan yang terbakar (`area`)** dalam satuan hektar. Prediksi ini didasarkan pada data spasial (koordinat X-Y), data temporal (bulan dan hari), serta data dari beberapa indeks cuaca dari sistem FWI (Fire Weather Index).

---

## 2. Dataset

- **Nama Dataset:** Forest Fires Dataset
- **Sumber:** UCI Machine Learning Repository
- **Deskripsi:** Dataset ini berisi 517 data kebakaran hutan dari wilayah timur laut Portugal. Terdapat 12 fitur (variabel input) seperti suhu, kelembapan, angin, dan beberapa indeks dari FWI, serta 1 variabel target yaitu `area` (luas area terbakar dalam ha).

---

## 3. Algoritma yang Digunakan

- **Algoritma:** **Random Forest Regressor**
- **Alasan Pemilihan:**
  1.  **Kemampuan Menangani Non-Linearitas:** Hubungan antara cuaca dan luas kebakaran tidak selalu linear. Random Forest sangat baik dalam menangkap pola yang kompleks.
  2.  **Kuat Terhadap Outlier:** Model ini tidak terlalu sensitif terhadap data pencilan.
  3.  **Memberikan Feature Importance:** Random Forest dapat memberikan peringkat fitur mana yang paling berpengaruh dalam membuat prediksi, yang sangat berguna untuk analisis.

---

## 4. Hasil Analisis

Model telah berhasil dilatih untuk memprediksi luas area yang terbakar.

- **Preprocessing:** Kolom `month` dan `day` diubah menjadi format numerik menggunakan One-Hot Encoding. Variabel target `area` ditransformasi menggunakan logaritmik (`log1p`) untuk menangani distribusi data yang sangat miring.
- **Evaluasi Model:** Model dievaluasi menggunakan *Mean Absolute Error (MAE)*. Hasil MAE menunjukkan bahwa rata-rata, prediksi model memiliki selisih sekitar [Isi dengan nilai MAE dari output kodemu] hektar dari nilai sebenarnya.
- **Fitur Paling Penting:** Berdasarkan analisis, fitur yang paling berpengaruh dalam memprediksi luas kebakaran adalah:
  *(Sebutkan 3-4 fitur teratas dari grafik yang dihasilkan kodemu, misalnya: suhu (`temp`), kelembapan (`RH`), dan indeks kekeringan (`DMC`))*

---

## 5. Cara Menjalankan Program

1.  Clone repository ini.
2.  Pastikan library seperti `pandas`, `scikit-learn`, `matplotlib`, dan `seaborn` sudah terpasang.
3.  Buka dan jalankan file `analisis_kebakaran_hutan.ipynb` di lingkungan Jupyter.
