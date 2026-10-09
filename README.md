# Course 1: Data Mining & Exploratory Data Analysis
Dokumentasi Progres Mingguan Mahasiswa untuk Dosen Pembimbing / Pengampu Mata Kuliah Data Mining.

---

## 📌 Log Riwayat Progres

| Minggu / Modul | Berkas | Fokus Pembahasan | Tanggal Log | Status |
| :--- | :--- | :--- | :--- | :--- |
| **Minggu 1** | `c1-m1.ipynb` | Metodologi CRISP-DM, Taksonomi ML, NumPy & Pandas | 23 September 2026 | ✅ Selesai |
| **Minggu 2** | `c1-m2.ipynb` | Data Retrieval (CSV, JSON, SQL, NoSQL) & Data Cleansing (Missing Values, Outliers) | 9 Oktober 2026 | ✅ Selesai |
| **Minggu 3** | `c1-m3.ipynb` | Exploratory Data Analysis (EDA) & Feature Engineering | - | ⏳ Mendatang |
| **Minggu 4** | `c1-m4.ipynb` | Inferensial Statistik, Distribusi Probabilitas & Uji Hipotesis | - | ⏳ Mendatang |

---

## 📁 Struktur Direktori
```text
course1/
├── data/                # Dataset acuan yang digunakan dalam praktikum
│   ├── classic_rock.db  # Database SQLite (tabel rock_songs) untuk kueri SQL relasional
│   ├── iris_data.csv    # Dataset morfologi bunga Iris untuk CSV reading & visualisasi
│   ├── sample.json      # Dataset semi-terstruktur JSON untuk demonstrasi NoSQL/ekspor
│   ├── unemployment.csv # Dataset tingkat pengangguran bulanan untuk deteksi outlier & IQR
│   └── telco_churn.csv  # Dataset IBM Cognos Analytics Telco Churn untuk studi kasus statistik
├── c1-m1.ipynb          # Progres Minggu 1: Pendahuluan Data Mining & Alur Kerja Machine Learning
├── c1-m2.ipynb          # Progres Minggu 2: Pengambilan Data (Data Retrieval) & Pembersihan Data (Data Cleansing)
├── requirements.txt     # Daftar dependensi pustaka Python
└── README.md            # Ringkasan silabus dan progres per modul
```

---

## 🗓️ Rincian Progres Mingguan

### 1. Minggu 1 (`c1-m1.ipynb`) - Pendahuluan & Alur Kerja Machine Learning (Log: 23 September 2026)
- **Fondasi Konseptual**: Pengertian Data Mining, proses ekstraksi pengetahuan (*Knowledge Discovery in Databases / KDD*), dan tahapan standar industri **CRISP-DM** (*Business Understanding, Data Understanding, Data Preparation, Modeling, Evaluation, Deployment*).
- **Taksonomi Tugas**: *Supervised* vs *Unsupervised Learning*, Klasifikasi, Regresi, Asosiasi, dan Klasterisasi.
- **Hands-on Python**: Setup lingkungan kernel, komputasi vektorisasi array multidimensi dengan **NumPy**, manipulasi tabular dengan **Pandas Series & DataFrame**, penambahan fitur sederhana, serta visualisasi eksplorasi awal.

### 2. Minggu 2 (`c1-m2.ipynb`) - Pengambilan Data & Pembersihan Data (Log: 9 Oktober 2026)
- **Pengambilan Data (*Data Retrieval*)**:
  - **Berkas CSV**: Parameter `pd.read_csv()` (`sep`, `delim_whitespace`, `header`, `names`, dan penanganan nilai kosong khusus via `na_values`).
  - **Berkas JSON**: Karakteristik semi-terstruktur *key-value*, membaca dengan berbagai orientasi (`orient='records'`, `'split'`, dll.), dan ekspor data via `.to_json()`.
  - **Basis Data Relasional SQL**: Membuka koneksi ke SQLite `classic_rock.db`, eksekusi kueri agregasi (`GROUP BY Artist, Release_Year`, `ORDER BY Song_Count DESC`), serta parameter lanjutan `pd.read_sql` (`coerce_float`, `parse_dates`, dan streaming batch dengan generator `chunksize`).
  - **Basis Data NoSQL**: Arsitektur Dokumen (MongoDB), Key-Value, Graph, Wide-Column, serta sintaks manipulasi koleksi data via `pymongo`.
  - **Web & API Publik**: Ekstraksi dataset publik langsung dari endpoint URL internet menggunakan Pandas.
- **Pembersihan Data (*Data Cleansing*)**:
  - Penerapan prinsip *"Garbage-in, Garbage-out"* dan penanganan baris data duplikat (`drop_duplicates()`).
  - **Penanganan Nilai Hilang (*Missing Values*)**: Identifikasi pola kehilangan data (`isna()`, `info()`), perbandingan evaluasi strategi eliminasi (*drop*) vs imputasi (*mean*, *median*, *mode*), serta trade-off bias dan variansi.
- **Deteksi & Penanganan Outlier**:
  - **Deteksi Visual**: Distribusi data melalui Histogram, KDE (*Kernel Density Estimation*), dan Boxplot.
  - **Deteksi Matematis IQR (*Interquartile Range*)**: Kuartil 1 ($Q1$), Median ($Q2$), Kuartil 3 ($Q3$), perhitungan rentang interkuartil ($IQR = Q3 - Q1$), serta batas toleransi Tukey $[Q1 - 1.5 \times IQR, Q3 + 1.5 \times IQR]$ pada data pengangguran.
  - **Deteksi Berbasis Residual Model Regresi**: Pengujian galat model regresi linear melalui *Standardized Residuals*, *Deleted Residuals* (*Leave-One-Out*), dan *Studentized Residuals*.
  - **5 Strategi Penanganan Outlier**: Eliminasi (*Drop/Trimming*), *Winsorizing/Clipping*, Transformasi variabel (Log/Box-Cox), Prediksi/Imputasi model, dan penggunaan model resisten (*Robust Models*).

---

## 💻 Cara Menjalankan Notebook
1. Pastikan dependensi telah terpasang:
   ```bash
   pip install -r requirements.txt
   ```
2. Jalankan server Jupyter Lab dari root direktori proyek:
   ```bash
   jupyter lab
   ```
3. Buka folder `course1/` dan jalankan notebook mingguan:
   - `c1-m1.ipynb`
   - `c1-m2.ipynb`
