# Bone-Fracture-Xray-Classification
Klasifikasi patah tulang pada citra X-ray menggunakan ekstraksi fitur GLCM, LBP, dan Feature Fusion dengan model SVM, ANN, dan BNN.


# Bone Fracture X-ray Classification

## Deskripsi Proyek

Proyek ini membahas klasifikasi patah tulang berdasarkan citra X-ray menggunakan pendekatan pengolahan citra digital dan machine learning. Penelitian membandingkan tiga metode ekstraksi fitur, yaitu Gray Level Co-occurrence Matrix (GLCM), Local Binary Pattern (LBP), dan Feature Fusion, dengan tiga model klasifikasi: Support Vector Machine (SVM), Artificial Neural Network (ANN), dan Bayesian Neural Network (BNN).

Tujuan utamanya adalah mengetahui kombinasi metode ekstraksi fitur dan model klasifikasi yang memberikan performa terbaik dalam mengelompokkan citra X-ray ke dalam enam kategori patah tulang.

## Tujuan

- Menerapkan preprocessing citra X-ray sebelum ekstraksi fitur.
- Mengekstraksi karakteristik tekstur citra menggunakan GLCM dan LBP.
- Menggabungkan fitur GLCM dan LBP melalui metode Feature Fusion.
- Membandingkan performa model SVM, ANN, dan BNN.
- Mengevaluasi hasil klasifikasi menggunakan accuracy, precision, recall, F1-score, dan confusion matrix.

## Dataset

Dataset yang digunakan adalah **Bone Fracture Detection** dari Kaggle.

Sumber dataset: [Bone Fracture Detection - Kaggle](https://www.kaggle.com/datasets/pkdarabi/bone-fracture-detection-computer-vision-project)

Dataset awal terdiri atas 4.148 citra. Setelah proses data cleaning, diperoleh 2.060 citra yang digunakan dalam penelitian.

Enam kategori yang digunakan:

- Elbow Positive
- Finger Positive
- Forearm Fracture
- Humerus Fracture
- Shoulder Fracture
- Wrist Positive

Data dibagi menjadi training, validation, dan testing sesuai struktur dataset yang digunakan dalam penelitian.

## Metodologi

### 1. Data Cleaning

Pembersihan data dilakukan dengan memeriksa pasangan citra dan file label, menghapus citra dengan label kosong, serta memeriksa duplikasi data. Citra tanpa label yang valid tidak digunakan dalam proses klasifikasi.

### 2. Preprocessing Citra

Tahapan preprocessing meliputi:

- Resize citra menjadi 224 × 224 piksel.
- Konversi citra ke grayscale.
- Peningkatan kontras menggunakan Contrast Limited Adaptive Histogram Equalization (CLAHE).
- Pengurangan noise menggunakan median blur.
- Penghalusan citra menggunakan Gaussian blur.

### 3. Ekstraksi Fitur

Penelitian membandingkan tiga pendekatan ekstraksi fitur:

- **GLCM:** mengambil karakteristik tekstur berdasarkan hubungan intensitas antar-piksel, meliputi contrast, dissimilarity, homogeneity, energy, correlation, dan Angular Second Moment (ASM).
- **LBP:** merepresentasikan pola tekstur lokal melalui perbandingan intensitas piksel.
- **Feature Fusion:** menggabungkan fitur GLCM dan LBP menggunakan concatenation untuk memperoleh representasi tekstur yang lebih lengkap.

Fitur GLCM menghasilkan 72 fitur, LBP menghasilkan 18 fitur, sedangkan Feature Fusion menghasilkan 90 fitur untuk setiap citra.

### 4. Normalisasi Fitur

Fitur dinormalisasi menggunakan StandardScaler sebelum digunakan dalam pemodelan. Parameter normalisasi dipelajari dari data training, kemudian diterapkan pada data validation dan testing.

### 5. Klasifikasi

Tiga algoritma yang dibandingkan:

- Support Vector Machine (SVM).
- Artificial Neural Network (ANN).
- Bayesian Neural Network (BNN).

Pengujian dilakukan menggunakan sembilan kombinasi, yaitu masing-masing dari tiga metode ekstraksi fitur dengan ketiga model klasifikasi.

### 6. Evaluasi Model

Performa model dievaluasi menggunakan:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix

Hasil pengujian kemudian dibandingkan untuk menentukan kombinasi metode yang memberikan performa terbaik.

## Hasil Utama

Berdasarkan laporan proyek, kombinasi Feature Fusion dan ANN memperoleh hasil terbaik.

| Metrik | Hasil |
|---|---:|
| Accuracy | 72,29% |
| Precision | 75,80% |
| Recall | 72,29% |
| F1-score | 71,72% |

Hasil tersebut menunjukkan bahwa penggabungan fitur GLCM dan LBP dapat memberikan representasi tekstur yang lebih lengkap pada penelitian ini. Namun, performa model masih memiliki ruang untuk ditingkatkan.

## Konteks Akademik

Proyek mata kuliah Pengolahan Citra Digital (PCD)  
Program Studi Sains Data  
Universitas Negeri Surabaya

## Catatan

Dataset citra X-ray tidak harus disertakan langsung dalam repository karena ukuran file dapat cukup besar dan penggunaannya perlu mengikuti ketentuan lisensi sumber dataset. Tautan dataset disediakan agar pengguna dapat mengunduhnya secara mandiri.

Proyek ini merupakan penelitian akademik untuk klasifikasi citra. Hasil prediksi model tidak dimaksudkan sebagai pengganti pemeriksaan atau diagnosis oleh tenaga medis.
