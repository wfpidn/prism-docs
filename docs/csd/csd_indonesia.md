# Data Spesifik Indonesia

## Curah hujan

Indonesia menggunakan data GPM IMERG untuk memberikan informasi hampir real-time tentang curah hujan ekstrem setiap hari dan NOAA GEFS untuk prakiraan curah hujan harian yang dapat memicu banjir.

### GPM IMERG

GPM adalah generasi berikutnya dari Misi Pengukuran Curah Hujan Tropis (TRMM - https://pmm.nasa.gov/TRMM). Seperti TRMM, misi GPM bertujuan untuk memberikan perkiraan curah hujan yang dikalibrasi secara seragam pada skala kuasi-global dengan menggabungkan pengukuran dari konstelasi satelit microwave dan IR. Semua set data GPM termasuk pengukuran yang diperoleh dari setiap platform (Level 2) tersedia di situs PMM (https://pmm.nasa.gov/data-access). Di antara banyak produk GPM, Multi-satellitE Retrievals for GPM (IMERG) paling menarik bagi pengguna karena memberikan perkiraan curah hujan 'terbaik' dengan menggabungkan data yang diperoleh dari semua platform microwave dan inframerah (IR) yang tersedia dari konstelasi satelit GPM.

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menampilkan data curah hujan 6 jam dan harian  |
| Variabel  | Jumlah curah hujan  |
| Cakupan Geografis  | Global 60N-60S, 180W-180E |
| Resolusi Spasial  | 0.1 derajat ~ 11.1 km di equator  |
| Resolusi sementara  | 30 menit dan setiap hari  |
| Format  | NetCDF  |
| Unit  | Total mm untuk langkah waktu tertentu, mm/jam, mm/hari, dll.  |
| Sumber  | 30 menit https://disc.gsfc.nasa.gov/datasets/GPM_3IMERGHH_06/summary and Daily: https://disc.gsfc.nasa.gov/datasets/GPM_3IMERGDF_06/summary  |
| Referensi  | https://pmm.gsfc.nasa.gov/GPM  |

### NOAA GEFS

Global Ensemble Forecast System (GEFS), sebelumnya dikenal sebagai GFS Global ENSemble (GENS), adalah model prakiraan cuaca yang terdiri dari 21 prakiraan terpisah, atau anggota ansambel. National Centers for Environmental Prediction ([NCEP](https://www.ncep.noaa.gov)) dari NOAA memulai GEFS untuk mengatasi sifat ketidakpastian dalam pengamatan cuaca, yang digunakan untuk menginisialisasi model prakiraan cuaca. GEFS mencoba untuk mengukur jumlah ketidakpastian dalam prakiraan dengan menghasilkan kumpulan prakiraan ganda, masing-masing sangat berbeda, atau terganggu, dari pengamatan asli.

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menampilkan prakiraan curah hujan 6 jam dan harian  |
| Variabel  | Prakiraan curah hujan total  |
| Cakupan Geografis  | Global |
| Resolusi Spasial  | 0.25 derajat ~ 27.5 km di equator  |
| Resolusi sementara  | Setiap 6 jam, hingga 16 hari ke depan  |
| Format  | GRIB2  |
| Unit  | Total mm/6-jam.  |
| Sumber  | https://nomads.ncep.noaa.gov/cgi-bin/filter_gefs_atmos_0p25s.pl  |
| Referensi  | https://www.ncdc.noaa.gov/data-access/model-data/model-datasets/global-ensemble-forecast-system-gefs  |

## Indeks Vegetasi

Indeks vegetasi, biasanya diproduksi pada interval 8 atau 16 hari dan bulanan dan pada beberapa resolusi spasial, memberikan perbandingan spasial dan temporal yang konsisten dari kehijauan tajuk vegetasi, properti komposit dari luas daun, klorofil dan struktur kanopi. Dua indeks vegetasi diturunkan dari reflektansi yang dikoreksi secara atmosfer pada pita gelombang merah, inframerah-dekat, dan biru; Normalized Difference Vegetation Index (NDVI), dan Enhanced Vegetation Index (EVI), yang meminimalkan variasi tanah tajuk dan meningkatkan sensitivitas terhadap kondisi vegetasi yang rapat. Kedua produk tersebut secara lebih efektif mencirikan kisaran global keadaan dan proses vegetasi.

### MODIS

Produk MOD13Q1 Versi 6 memberikan nilai Indeks Vegetasi (VI) pada basis per piksel pada resolusi spasial 250 meter. Ada dua lapisan vegetasi primer. Yang pertama adalah Normalized Difference Vegetation Index (NDVI), yang dirujuk sebagai indeks kontinuitas dari NDVI yang diturunkan dari National Oceanic and Atmospheric Administration-Advanced Very High Resolution Radiometer (NOAA-AVHRR). Lapisan vegetasi kedua adalah Enhanced Vegetation Index (EVI), yang telah meningkatkan sensitivitas di daerah dengan biomassa tinggi. Algoritme untuk produk ini memilih nilai piksel terbaik yang tersedia dari semua akuisisi dari periode 16 hari. Kriteria yang digunakan adalah awan rendah, sudut pandang rendah dan nilai NDVI/EVI tertinggi.

Enhanced Vegetation Index (EVI) digunakan sebagai ganti Normalized Difference Vegetation Index (NDVI) karena lebih sensitif terhadap perubahan di area yang memiliki biomassa tinggi, mengurangi pengaruh kondisi atmosfer pada nilai indeks vegetasi, dan mengoreksi sinyal latar belakang kanopi.

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menampilkan data indeks vegetasi 16 hari  |
| Variabel  | EVI  |
| Cakupan Geografis  | Global |
| Resolusi Spasial  | 250 meter  |
| Resolusi sementara  | 16-hari  |
| Format  | HDF-EOS  |
| Unit  | n/a, Faktor skala 0.0001  |
| Sumber  | https://e4ftl01.cr.usgs.gov/MOLT/MOD13Q1.006/  |
| Referensi  | https://lpdaac.usgs.gov/products/mod13q1v006/  |

#### Simbologi

?> Ambang batas dan simbologi untuk EVI `16-hari` dapat mengikuti kode warna dan gambar di bawah ini.

| Class  | Hex  | RGB  |
|---|---|---|
| 0 ke bawah  | `#002596` ![#002596](https://via.placeholder.com/15/002596/000000?text=+) | rgb(0, 37, 150)  |
| 0 to 0.05  | `#752a27` ![#752a27](https://via.placeholder.com/15/752a27/000000?text=+)  | rgb(117, 42, 39)  |
| 0.06 to 0.10  | `#b4672a` ![#b4672a](https://via.placeholder.com/15/b4672a/000000?text=+)  | rgb(180, 103, 42)  |
| 0.11 to 0.15  | `#f3a63b` ![#f3a63b](https://via.placeholder.com/15/f3a63b/000000?text=+)  | rgb(243, 166, 59)  |
| 0.16 to 0.25  | `#f6c042` ![#f6c042](https://via.placeholder.com/15/f6c042/000000?text=+)  | rgb(246, 192, 66)  |
| 0.26 to 0.35  | `#fffd54` ![#fffd54](https://via.placeholder.com/15/fffd54/000000?text=+)  | rgb(255, 253, 84)  |
| 0.34 to 0.42  | `#bdfb50` ![#bdfb50](https://via.placeholder.com/15/bdfb50/000000?text=+)  | rgb(189, 251, 80)  |
| 0.43 to 0.50  | `#8af94d` ![#8af94d](https://via.placeholder.com/15/8af94d/000000?text=+)  | rgb(138, 249, 77)  |
| 0.51 to 0.58  | `#64d640` ![#64d640](https://via.placeholder.com/15/64d640/000000?text=+)  | rgb(100, 214, 64)  |
| 0.59 to 0.66  | `#4ba52f` ![#4ba52f](https://via.placeholder.com/15/4ba52f/000000?text=+)  | rgb(75, 165, 47)  |
| 0.67 to 0.74  | `#33741f` ![#33741f](https://via.placeholder.com/15/33741f/000000?text=+)  | rgb(51, 116, 31)  |
| 0.75 to 1  | `#1f4d11` ![#1f4d11](https://via.placeholder.com/15/1f4d11/000000?text=+)  | rgb(31, 77, 17)  |
