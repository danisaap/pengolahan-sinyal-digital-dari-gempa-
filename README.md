# Analisis Sinyal Gempa & Risiko Bencana

Projek analisis data gempa bumi tahun 2020 menggunakan pemrosesan sinyal digital, klasifikasi risiko, dan visualisasi interaktif. Dibangun dengan Python (Jupyter Notebook).

## Dataset

**`gempa_2020.csv`** — 4.049 kejadian gempa di kawasan Indonesia, Filipina, Papua Nugini, dan sekitarnya (Cincin Api Pasifik).

Kolom: Year, Month, Day, Time, Lat, Lon, Depth (km), Mag, Region, Timestamp

## Alur Pengerjaan

1. **Cleaning Data** — Cek NaN, konversi tipe data, format kolom `Time` dan `Region`
2. **Feature Engineering** — Standarisasi nama region, ekstraksi waktu
3. **Visualisasi Sinyal** — Plot time-series magnitude
4. **Filtering Sinyal** — Low-pass, High-pass, Band-pass (Butterworth), Wavelet Denoising, Wiener Filter
5. **Klasifikasi** — Kategori kedalaman (Dangkal/Menengah/Dalam) dan magnitudo (Minor/Moderat/Kuat/Besar/Hebat)
6. **Analisis STFT** — Spektrogram frekuensi sinyal terhadap waktu
7. **Wilayah Gempa** — 10 region terbanyak
8. **Kerusakan & Peringatan** — Skor risiko = (Mag × Depth) / (jam+1), level risiko (Rendah/Sedang/Tinggi/Sangat Tinggi), sistem peringatan (AMAN/INFO/WARNING/ALERT)
9. **Peta Interaktif** — Folium map dengan marker gempa (warna = kategori kerusakan, ukuran = magnitudo)
10. **Query Interface** — Cari data gempa berdasarkan bulan/tanggal

## File Output

| File | Deskripsi |
|---|---|
| `dataset_cleaning.csv` | Data bersih |
| `dataset_sinyal.csv` | Data + sinyal sintetis |
| `dataset_sinyal_filter.csv` | Data + sinyal hasil Wiener filter |
| `dataset_kategori_mag.csv` | Data + kategori kedalaman & magnitudo |
| `dataset_peringatan.csv` | Data + skor risiko & peringatan |
| `dataset_final.csv` | Dataset final (17 kolom) |
| `earthquake_map.html` | Peta interaktif gempa (Folium) |

## Teknologi

- Python (pandas, numpy, scikit-learn)
- Visualisasi (matplotlib, seaborn)
- Pemrosesan sinyal (PyWavelets, scipy.signal)
- Peta interaktif (Folium)
- Jupyter Notebook
