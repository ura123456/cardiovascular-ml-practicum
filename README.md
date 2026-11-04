# Praktikum Machine Learning: Cardiovascular Disease

Proyek praktikum Machine Learning untuk mempelajari dan menerapkan algoritma **Linear Regression** dan **Logistic Regression** menggunakan Python dan Scikit-learn.

Proyek ini mencakup pemahaman data, eksplorasi data (EDA), pembersihan data, preprocessing, pembangunan model, dan evaluasi performa model.

## 1. Tujuan Proyek

Proyek ini bertujuan untuk memahami penerapan dua jenis algoritma Machine Learning:

- **Linear Regression:** memprediksi tekanan darah sistolik (`ap_hi`).
- **Logistic Regression:** mengklasifikasikan target penyakit kardiovaskular (`cardio`) menjadi dua kelas, yaitu 0 dan 1.

Kedua model menggunakan dataset yang sama, tetapi memiliki target dan pemilihan fitur yang berbeda sesuai dengan tujuan masing-masing.

## 2. Dataset

Dataset yang digunakan adalah **Cardiovascular Disease Dataset** dari Kaggle.

**Sumber dataset:** [Cardiovascular Disease Dataset – Kaggle](https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset)

Informasi dataset:
- Jumlah data awal: 70.000 baris
- Jumlah atribut: 13 kolom
- Target klasifikasi: `cardio`
- Nama file: `cardio_train.csv`

Dataset tidak disertakan dalam repository. Untuk menjalankan proyek ini, unduh dataset dari sumber di atas dan letakkan file `cardio_train.csv` di direktori `data/raw/`.

## 3. Struktur Proyek

```text
cardiovascular-ml-practicum/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   ├── 01_data_understanding_eda.ipynb
│   ├── 02_data_cleaning_feature_engineering.ipynb
│   ├── 03_linear_regression.ipynb
│   └── 04_logistic_regression.ipynb
├── .gitignore
├── README.md
└── requirements.txt
```

**Catatan:** Folder `data/raw/` dan `data/processed/` merupakan bagian dari struktur proyek lokal, tetapi tidak disertakan dalam repository GitHub karena diabaikan oleh `.gitignore`. Folder tersebut tetap digunakan untuk menyimpan dataset asli dan data hasil preprocessing di komputer lokal.

Keterangan:
- `data/raw/`: menyimpan dataset asli.
- `data/processed/`: menyimpan dataset yang telah dibersihkan.
- `notebooks/`: menyimpan notebook untuk setiap tahapan praktikum.
- `.gitignore`: menentukan file dan direktori yang tidak perlu diunggah ke repository.
- `requirements.txt`: mencatat library Python yang digunakan dalam proyek.

## 4. Alur Pengerjaan

| Notebook | Deskripsi |
|---|---|
| `01_data_understanding_eda.ipynb` | Memahami struktur, tipe data, distribusi target, statistik deskriptif, dan karakteristik dataset melalui EDA. |
| `02_data_cleaning_feature_engineering.ipynb` | Mengidentifikasi anomali, membersihkan data, memisahkan fitur dan target, membagi data, serta melakukan preprocessing. |
| `03_linear_regression.ipynb` | Membangun dan mengevaluasi model Linear Regression untuk memprediksi tekanan darah sistolik. |
| `04_logistic_regression.ipynb` | Membangun dan mengevaluasi model Logistic Regression untuk klasifikasi penyakit kardiovaskular. |

## 5. Hasil Evaluasi Model

### A. Linear Regression

Model Linear Regression digunakan untuk memprediksi tekanan darah sistolik (`ap_hi`) menggunakan 10 fitur.

Hasil evaluasi pada data testing:

| Metrik | Hasil |
|---|---:|
| MAE | 8,05 |
| MSE | 129,74 |
| RMSE | 11,39 |
| R² | 0,5443 |

Nilai R² sebesar 0,5443 menunjukkan bahwa model dapat menjelaskan sekitar 54,43% variasi nilai tekanan darah sistolik pada data testing.

### B. Logistic Regression

Model Logistic Regression digunakan untuk mengklasifikasikan target `cardio` menggunakan 11 fitur.

Hasil evaluasi pada data testing:

| Metrik | Hasil |
|---|---:|
| Accuracy | 72,18% |
| Precision | 75,12% |
| Recall | 65,44% |
| F1-Score | 69,94% |
| ROC-AUC | 0,7841 |

Evaluasi juga dilakukan menggunakan Confusion Matrix, Classification Report, dan ROC Curve untuk memahami performa model dalam membedakan kedua kelas.

## 6. Teknologi dan Library

Proyek ini menggunakan:
- Python 3.11.9
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## 7. Catatan dan Batasan

- Pembersihan data dilakukan berdasarkan kriteria penyaringan anomali pada atribut tekanan darah, tinggi badan, dan berat badan. Kriteria tersebut merupakan pendekatan untuk menjaga kualitas dataset, bukan batas diagnosis medis universal.
- Preprocessing dipelajari dari data training dan diterapkan pada data testing untuk menghindari kebocoran informasi selama proses tersebut.
- Performa model dipengaruhi oleh karakteristik dataset dan fitur yang digunakan.
- Proyek ini dibuat untuk tujuan pembelajaran Machine Learning dan bukan sebagai alat diagnosis atau pengambilan keputusan medis.