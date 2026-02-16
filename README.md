# 📊 Student Academic Performance Classification

**Data Science Project - Tugas Akhir SUBA**

Repository ini berisi proyek klasifikasi untuk memprediksi perubahan performa akademik siswa berdasarkan faktor sosial, kesehatan mental, dan kebiasaan belajar. Proyek ini mencakup seluruh *pipeline* data science, mulai dari pembersihan data yang kotor hingga optimasi model menggunakan *Hyperparameter Tuning*.

---

## 🔍 Latar Belakang & Ruang Lingkup

Prestasi belajar siswa dipengaruhi oleh banyak faktor di luar kemampuan intelektual, seperti tingkat stres dan penggunaan teknologi. Proyek ini bertujuan untuk:

* Menganalisis faktor-faktor yang memengaruhi performa akademik.
* Membangun model klasifikasi untuk memprediksi apakah performa siswa akan **Declined**, **Improved**, atau **Same**.
* Memberikan wawasan berbasis data bagi pendidik untuk mendukung kualitas pembelajaran.

**Dataset Source:** [UCI Machine Learning Repository - Student Performance](https://archive.ics.uci.edu/dataset/320/student+performance)

---

## 🛠️ Alur Kerja (Workflow)

1. **Data Extraction & Cleaning**:
* Menangani data kotor (contoh: mengubah string 'twenty' menjadi numerik `20`).
* Konversi tipe data dan penanganan nilai kosong (*Missing Values*) menggunakan Median (Numerik) dan kategori 'Unknown'/'Other' (Kategorik).


2. **Exploratory Data Analysis (EDA)**:
* Analisis Univariate (Distribusi & Frekuensi).
* Deteksi Outlier menggunakan Boxplot dan penanganan dengan teknik **Winsorizing**.
* Analisis Multivariate menggunakan Heatmap Korelasi.


3. **Preprocessing**:
* *Feature Selection* (Menghapus kolom non-informatif seperti 'Name').
* *Feature Encoding* menggunakan **Ordinal Encoder**.
* *Handling Imbalanced Data* menggunakan **SMOTE** (Synthetic Minority Over-sampling Technique).


4. **Modeling & Evaluation**:
* Pembangunan Pipeline dengan `RobustScaler`.
* *Hyperparameter Tuning* menggunakan `GridSearchCV`.
* Evaluasi menggunakan *Confusion Matrix*, *F1-Score*, dan *Cross-Validation*.



---

## 🤖 Algoritma & Performa

Proyek ini berfokus pada penggunaan:

* **Decision Tree Classifier** (Optimized)
* **SMOTE** (untuk penyeimbangan kelas)
* **RobustScaler** (untuk standarisasi fitur yang tahan terhadap outlier)

**Metode Evaluasi:**

* **Accuracy & F1-Macro Score**
* **Stratified K-Fold Cross-Validation** (5 Splits)
* **Confusion Matrix** (Visualisasi Prediksi vs Aktual)

---

## 🧰 Tools & Library

* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Visualization:** Plotly Express (Interactive), Matplotlib, Seaborn
* **Machine Learning:** Scikit-learn
* **Imbalance Handling:** Imbalanced-learn (SMOTE)

---

### 📂 Struktur Data (Dataset Features)

Berikut adalah kolom-kolom yang digunakan dalam pengembangan model setelah tahap pembersihan:

* **Gender**: Jenis kelamin responden (Dukategorikan menjadi: Male, Female, Other).
* **Age**: Usia responden dalam tahun (Data numerik).
* **Education Level**: Tingkat pendidikan yang sedang ditempuh.
* **Screen Time (hrs/day)**: Durasi penggunaan layar per hari dalam jam.
* **Sleep Duration (hrs)**: Rata-rata durasi tidur per hari dalam jam.
* **Physical Activity (hrs/week)**: Total durasi aktivitas fisik per minggu dalam jam.
* **Stress Level**: Tingkat stres responden.
* **Anxious Before Exams**: Indikator kecemasan sebelum ujian (Yes/No).
* **Academic Performance Change (Target)**: Label klasifikasi yang terdiri dari tiga kelas:
* `0`: Declined
* `1`: Improved
* `2`: Same



---

### 🤖 Algoritma & Pipeline

Berdasarkan kode yang dijalankan, model dibangun menggunakan *Machine Learning Pipeline* yang terdiri dari:

1. **RobustScaler**: Untuk standarisasi fitur agar lebih tangguh terhadap *outlier* yang terdeteksi pada EDA.
2. **SMOTE (Synthetic Minority Over-sampling Technique)**: Digunakan untuk menangani *imbalance target* pada kolom *Academic Performance Change*.
3. **Decision Tree Classifier**: Algoritma utama yang dioptimalkan melalui *Hyperparameter Tuning* dengan `GridSearchCV`.

---

## 📈 Hasil Evaluasi

Model akhir menggunakan parameter terbaik hasil tuning (misal: `criterion='entropy'`, `max_depth=30`) yang menghasilkan performa yang lebih stabil dalam memprediksi kelas minoritas setelah dilakukan resampling dengan SMOTE.

---

**Author:** Owen Luciano
*Project ini dibuat sebagai project akhir dengan Komunitas GSB-Gerakan Suka Baca.*

---
