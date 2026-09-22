# Tren Pekerja Migran Indonesia (2022–2024)

Proyek **Data Wrangling** yang menganalisis tren dan faktor pendorong penduduk Indonesia dalam memilih bekerja di luar negeri, menggunakan data ketenagakerjaan dari **BPS** (Badan Pusat Statistik) dan **BP2MI/BPN2TKI** (Badan Pelindungan Pekerja Migran Indonesia) periode 2022–2024.

## Latar Belakang

Migrasi tenaga kerja dari Indonesia terus meningkat, didorong oleh keterbatasan lapangan kerja formal, rendahnya upah minimum di beberapa daerah, serta semakin terbukanya akses informasi global (tercermin dari tagar viral *"#KaburAjaDulu"*). Proyek ini mengumpulkan, membersihkan, mengintegrasikan, dan menganalisis data resmi pemerintah untuk memahami pola serta faktor di balik tren tersebut.

## Tujuan

- Mengetahui faktor-faktor utama yang mendorong penduduk Indonesia bekerja di luar negeri
- Melacak perubahan tren Pekerja Migran Indonesia (PMI) pasca pandemi
- Menganalisis pengaruh wilayah, jenis kelamin, dan upah minimum terhadap keputusan migrasi kerja

## Sumber Data

| Sumber | Data | Format |
|---|---|---|
| BPS (Badan Pusat Statistik) | Pencari kerja terdaftar, lowongan kerja terdaftar, dan penempatan/pemenuhan tenaga kerja per provinsi & jenis kelamin (2022–2024) | .xlsx |
| BP2MI/KP2MI | Data penempatan & pelindungan Pekerja Migran Indonesia, 2024 | .pdf |
| Kementerian Ketenagakerjaan (Kemnaker) | Upah Minimum Provinsi (UMP), 2022–2024 | .xlsx, .jpg |

## Alur Proses (Pipeline)

1. **Data Collecting** — Diambil dari portal resmi BPS dan BP2MI, termasuk ekstraksi tabel dari PDF (`camelot`) dan input manual dari gambar ke Excel.
2. **Data Cleaning** — Mengisi nilai kosong (median untuk data ketenagakerjaan, 0 untuk provinsi hasil pemekaran Papua tahun 2023), menyamakan penamaan provinsi antar dataset, konversi tipe data.
3. **Data Integration** — Menggabungkan seluruh dataset bersih (pencari kerja, lowongan, penempatan, upah minimum) tahun 2022–2024 menjadi satu dataset terpadu.
4. **Exploratory Data Analysis (EDA)** — Statistik deskriptif (mean, median, modus, std dev) serta pemeriksaan outlier/distribusi.
5. **Visualisasi Data** — Histogram, boxplot, scatter plot, heatmap korelasi, bar chart/grouped bar, pie chart.
6. **Data Publishing** — Dataset final dipublikasikan ke repositori ini.

## Struktur Repositori

├── code/
│ └── data_wrangling.ipynb # Notebook: collecting, cleaning, integration
├── eda/
│ └── eda_visualization.ipynb # Notebook: exploratory data analysis & visualisasi
├── data/
│ ├── raw_data/ # Data mentah dari BPS, BP2MI, Kemnaker
│ └── processed_data/ # Dataset hasil cleaning & integrasi
│ └── final_data/ # Dataset final
└── README.md

## Insight Utama

- Jumlah pencari kerja jauh melebihi lowongan kerja domestik yang tersedia setiap tahun dari 2022–2024.
- Penempatan kerja ke luar negeri secara konsisten lebih tinggi dibanding penempatan domestik sepanjang 2022–2024.
- Pekerja migran didominasi asal Jawa Timur (laki-laki) serta Jawa Barat/Jawa Timur (perempuan).
- Upah Minimum Provinsi menunjukkan tren kenaikan dari 2022 ke 2024, namun korelasinya lemah dengan jumlah pencari kerja.

## Tools & Library

`Python`, `pandas`, `camelot-py` (ekstraksi tabel PDF), `matplotlib`/`seaborn` (visualisasi), `Jupyter Notebook`, `Microsoft Excel`

## Kontributor

| Nama | NIM | Kontribusi |
|---|---|---|
| Moh. Rasya Al Khalifi | 24031554132 | Scraping, coding, BAB II & III, daftar pustaka |
| Muhammad Khoirul Ilham | 24031554193 | Scraping, coding, BAB I & III, kesimpulan |

**Dosen Pengampu:** Ike Fitriyaningsih, M.Si

## 📄 Lisensi

Proyek ini dibuat untuk keperluan akademik (tugas mata kuliah). Data bersumber dari lembaga resmi pemerintah Indonesia (BPS, BP2MI, Kemnaker) yang bersifat publik.
