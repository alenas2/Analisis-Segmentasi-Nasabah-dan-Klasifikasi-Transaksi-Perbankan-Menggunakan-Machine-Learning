## Bank Transaction Analysis: Customer Segmentation and Classification

## Deskripsi Proyek

Proyek ini merupakan implementasi Machine Learning untuk mengelompokkan nasabah berdasarkan karakteristik dan pola transaksi perbankan menggunakan algoritma K-Means Clustering, kemudian membangun model klasifikasi untuk memprediksi kelompok nasabah berdasarkan hasil clustering. Proyek ini menggunakan dataset transaksi perbankan yang terdiri dari 2.512 data transaksi.

## Tujuan Proyek

1. Mengidentifikasi pola dan karakteristik nasabah berdasarkan data transaksi.
2. Mengelompokkan nasabah menggunakan algoritma K-Means Clustering.
3. Menganalisis karakteristik dari setiap cluster.
4. Membangun model klasifikasi untuk memprediksi hasil pengelompokan nasabah.
5. Mengevaluasi performa model menggunakan metrik klasifikasi.

## Dataset

Dataset yang digunakan adalah **Bank Transaction Dataset for Fraud Detection** dengan versi modifikasi yang disediakan oleh ASAH Dicoding melalui Google Drive sebagai referensi wajib pengerjaan.

Dataset mencakup 2.512 sampel transaksi dengan atribut yang berkaitan dengan:
- Identitas dan informasi rekening.
- Nominal dan jenis transaksi.
- Lokasi dan kanal transaksi.
- Usia dan pekerjaan nasabah.
- Durasi transaksi dan aktivitas login.
- Saldo rekening.

**Catatan:** Dataset menggunakan versi Google Drive yang disediakan dalam materi BMLP, bukan mengunduh langsung versi dari Kaggle.

## Metodologi

### 1. Data Preprocessing
- Memeriksa missing values dan data duplikat.
- Menghapus data kosong dan duplikat.
- Menghapus kolom identitas, alamat, dan tanggal yang tidak digunakan dalam pemodelan.
- Melakukan encoding pada fitur kategorikal.
- Melakukan standardisasi fitur numerik.

### 2. Customer Clustering
- Menggunakan Elbow Method dengan metrik Silhouette untuk membantu menentukan jumlah cluster.
- Menerapkan algoritma K-Means Clustering dengan 3 cluster.
- Menganalisis karakteristik masing-masing cluster berdasarkan fitur transaksi dan informasi nasabah.
- Mengekspor hasil clustering untuk digunakan pada tahap klasifikasi.

### 3. Classification
- Menggunakan hasil clustering sebagai target klasifikasi.
- Membagi dataset menjadi data latih dan data uji dengan proporsi 80:20.
- Membangun model Decision Tree dan Random Forest.
- Melakukan hyperparameter tuning pada model Random Forest menggunakan GridSearchCV.
- Mengevaluasi model menggunakan Accuracy, Precision, Recall, dan F1-Score.

## Hasil Model

Berdasarkan hasil pengujian pada data uji sebanyak 389 sampel:

| Model | Accuracy |
|---|---:|
| Decision Tree | 96% |
| Random Forest | 99% |
| Tuned Random Forest | 99% |

Random Forest dan model Random Forest setelah hyperparameter tuning menghasilkan akurasi sebesar 99%, lebih tinggi dibandingkan Decision Tree sebesar 96%.

## Teknologi yang Digunakan

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Yellowbrick
- Joblib
- Jupyter Notebook / Google Colab

## Struktur Proyek

```text
BMLP/
├── data_clustering.csv
├── data_clustering_inverse.csv
├── model_clustering.h5
├── PCA_model_clustering.h5
├── decision_tree_model.h5
├── explore__NAMA ALGORITMA-MU__classification.h5
├── tuning_classification.h5
├── [Clustering]_Submission_Akhir_BMLP.ipynb
└── [Klasifikasi]_Submission_Akhir_BMLP.ipynb
```

## Kesimpulan

Proyek ini menerapkan pendekatan unsupervised learning melalui K-Means Clustering untuk mengelompokkan nasabah berdasarkan karakteristik transaksi, kemudian menggunakan supervised learning untuk mengklasifikasikan hasil pengelompokan tersebut. Berdasarkan evaluasi, model Random Forest memberikan performa klasifikasi terbaik dengan akurasi sebesar 99% pada data uji.
