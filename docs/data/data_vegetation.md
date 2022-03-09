# Vegetasi

Berbagai data satelit menyediakan indeks vegetasi sebagai salah satu produknya, Landsat, MODIS Terra Aqua dan Sentinel adalah beberapa di antaranya.

### Indeks Vegetasi

Indeks vegetasi, biasanya dihasilkan pada interval 8 atau 16 hari dan bulanan dan pada beberapa resolusi spasial, memberikan perbandingan spasial dan temporal yang konsisten dari kehijauan tajuk vegetasi, properti komposit dari luas daun, klorofil dan struktur kanopi. Dua indeks vegetasi diturunkan dari reflektansi yang dikoreksi secara atmosfer pada pita gelombang merah, inframerah-dekat, dan biru; normalized difference vegetation index (NDVI), dan enhanced vegetation index (EVI), yang meminimalkan variasi kanopi-tanah dan meningkatkan sensitivitas terhadap kondisi vegetasi yang rapat. Kedua produk tersebut secara lebih efektif mencirikan kisaran global keadaan dan proses vegetasi.

### MODIS

Produk MOD13A2 Versi 6 memberikan nilai Indeks Vegetasi (VI) pada basis per piksel pada resolusi spasial 1 kilometer (km). Ada dua lapisan vegetasi primer. Yang pertama adalah Normalized Difference Vegetation Index (NDVI), yang dirujuk sebagai indeks kontinuitas dari NDVI yang diturunkan dari National Oceanic and Atmospheric Administration-Advanced Very High Resolution Radiometer (NOAA-AVHRR). Lapisan vegetasi kedua adalah Enhanced Vegetation Index (EVI), yang telah meningkatkan sensitivitas di daerah dengan biomassa tinggi. Algoritme untuk produk ini memilih nilai piksel terbaik yang tersedia dari semua akuisisi dari periode 16 hari. Kriteria yang digunakan adalah awan rendah, sudut pandang rendah dan nilai NDVI/EVI tertinggi.

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menampilkan data indeks vegetasi 16 hari  |
| Variabel  | NDVI  |
| Cakupan Geografis  | Global |
| Resolusi Spasial  | 1 km  |
| Resolusi sementara  | 16-hari  |
| Format  | HDF-EOS  |
| Unit  | n/a, faktor skala 0.0001  |
| Sumber  | https://e4ftl01.cr.usgs.gov/MOLT/MOD13A2.006/  |
| Referensi  | https://lpdaac.usgs.gov/products/mod13a2v006/  |

#### Simbologi

?> Ambang batas dan simbologi untuk NDVI `16-hari` dapat mengikuti kode warna dan gambar di bawah ini.

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
