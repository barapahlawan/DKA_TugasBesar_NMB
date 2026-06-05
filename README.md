# 🩸 Prediksi Risiko Penyakit Diabetes Menggunakan Logika Fuzzy

Proyek ini berfokus pada pengembangan sistem komputasi cerdas menggunakan *Fuzzy Inference System* (FIS) untuk memprediksi risiko penyakit diabetes. Prediksi dalam sistem ini difokuskan pada dua parameter input medis, yaitu usia dan kadar glukosa darah. Sistem ini diimplementasikan menggunakan dua metode logika fuzzy, yaitu **Mamdani** dan **Sugeno Linear**, untuk kemudian dievaluasi dan dibandingkan performanya.

## 📊 Dataset
* Dataset yang digunakan bersumber dari *Diabetes Dataset* publik yang dibuat oleh Akshay Dattatray Khare di platform Kaggle.
* Data awal terdiri dari 768 baris. 
* Setelah tahap *pre-processing* (menghapus anomali data medis dengan nilai usia atau glukosa 0), dataset bersih yang digunakan berjumlah 763 baris data.
* Variabel Target (Outcome) diklasifikasikan menjadi dua: **Aman** dan **Berisiko**.

## ⚙️ Metodologi Sistem Fuzzy

Sistem ini dikembangkan sepenuhnya menggunakan Python (melibatkan library `pandas`, `numpy`, `matplotlib`, dan `scikit-learn`) dengan membangun fungsi fuzzy dari awal (tanpa library skfuzzy).

### 1. Fuzzifikasi
Variabel input tegas (crisp) diubah menggunakan fungsi keanggotaan berbentuk segitiga (*triangular*) dan trapesium (*trapezoidal*).
* **Usia:** Dibagi menjadi *Muda*, *Paruh Baya*, dan *Tua*.
* **Kadar Glukosa:** Dibagi menjadi *Rendah*, *Sedang*, dan *Tinggi*.

### 2. Inferensi & Basis Aturan (Rule Base)
Sistem menerapkan 9 aturan fuzzy (*fuzzy rules*) untuk mengevaluasi kombinasi kondisi glukosa dan usia. 

### 3. Defuzzifikasi
* **Metode Mamdani:** Menggunakan perhitungan titik pusat penyesuaian (*Center of Gravity*) untuk menentukan kategori. Batas ambang klasifikasi (threshold) ditetapkan pada nilai 50.
* **Metode Sugeno:** Menggunakan rumus rata-rata tertimbang (*Weighted Average*) dari nilai konstan yang ditetapkan pada tiap aturan.

## 📈 Evaluasi & Hasil
Sistem diuji ke seluruh dataset dan menghasilkan metrik evaluasi klasifikasi berikut:
* **Metode Mamdani:** Berhasil mencapai akurasi sebesar **72%** dengan F1-Score **0.71**.
* **Metode Sugeno:** Menunjukkan akurasi yang sedikit lebih tinggi yaitu **73%**, dengan F1-score **0.71**.

Kedua metode menunjukkan kecenderungan performa yang sama, di mana *precision* untuk memprediksi pasien di kelas "Aman" lebih akurat (0.84) dibandingkan kelas "Berisiko" (0.58). 

## 🚀 Cara Menjalankan Proyek
1. *Clone* repositori ini ke dalam mesin lokal Anda.
2. Pastikan Anda telah menginstal seluruh dependensi yang ada pada file `requirements.txt`.
3. Buka dan jalankan blok kode di dalam `src/tubesDKA.ipynb` menggunakan Jupyter Notebook atau layanan Google Colab.

## 👥 Tim Pengembang
Proyek Tugas Besar mata kuliah Dasar Kecerdasan Artifisial ini disusun oleh mahasiswa S-1 Informatika, Fakultas Informatika, Universitas Telkom:
* Nabilah Putri Desky
* Alicia Mazza
* M. Akbar Putra Pahlawan
