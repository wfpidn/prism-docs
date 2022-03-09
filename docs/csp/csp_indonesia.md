# Produk spesifik Indonesia

Pemetaan tingkat bahaya alam (misalnya, menilai daerah dengan risiko tinggi) atau bencana adalah langkah pertama dalam manajemen risiko bencana dan tanggap darurat. Selanjutnya, pemetaan keterpaparan memungkinkan estimasi dampak bahaya atau bencana, misalnya mengenai jumlah penduduk atau infrastruktur yang terkena dampak.

Bagian ini menjelaskan secara rinci metodologi dan operasi analisis yang diperlukan untuk memenuhi persyaratan pengguna WFP di tingkat negara atau regional. Hal ini didasarkan pada pencarian ekstensif dari jurnal terkait untuk perhitungan dampak selama bencana dan ketersediaan data gratis global di internet.

## Hari Kering Berturut-turut

Jumlah hari kering berturut-turut (CDD) adalah jumlah hari berturut-turut terbesar dengan jumlah curah hujan harian kurang dari 1 mm (atau tergantung pada kriteria hari hujan negara), dalam waktu tertentu. Biasanya proses menghitung jumlah hari dalam 90 hari terakhir untuk mengukur tingkat kekeringan.

### Bagaimana ini bekerja

Hitung jumlah hari hujan berdasarkan ambang batas dan hitung jumlah hari terakhir sejak hari hujan atau rangkaian hari terakhir berturut-turut yang memenuhi kriteria ambang dijumlahkan.

Kriteria ambang batas: 1, 2.5, 5, 10 dan 20 milimeter curah hujan

```
IF previousCDD == null THEN previousCDD == 0
ELSEIF todayRAIN > 1 AND previousCDD == 0 THEN previousCDD + 1
```

CDD berasal dari data IMERG

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menampilkan CDD harian  |
| Variabel  | CDD  |
| Cakupan Geografis  | Indonesia 7N-12S, 94E-142E |
| Resolusi Spasial  | 0.1 derajat ~ 11.1 km di equator  |
| Resolusi sementara  | Harian  |
| Format  | GeoTIFF  |
| Unit  | Jumlah hari  |

#### Simbologi

?> Ambang batas dan simbologi untuk CDD dapat mengikuti kode warna dan gambar di bawah ini.

| Class  | Threshold  | Hex  | RGB  |
|---|---|---|---|
| No Drought  | 0  | `#cccccc` ![#cccccc](https://via.placeholder.com/15/cccccc/000000?text=+)  | rgb(204, 204, 204)  |
| Very Short  | 1 - 5  | `#ffe5d9` ![#ffe5d9](https://via.placeholder.com/15/ffe5d9/000000?text=+)  | rgb(255, 229, 217)  |
| Short  | 6 - 10  | `#fcbba2` ![#fcbba2](https://via.placeholder.com/15/fcbba2/000000?text=+)  | rgb(252, 187, 162)  |
| Moderate  | 11 - 20  | `#fc9272` ![#fc9272](https://via.placeholder.com/15/fc9272/000000?text=+)  | rgb(252, 146, 114)  |
| Long  | 21 - 30  | `#fa6948` ![#fa6948](https://via.placeholder.com/15/fa6948/000000?text=+)  | rgb(250, 105, 72)  |
| Very Long  | 31 - 60  | `#de2c26` ![#de2c26](https://via.placeholder.com/15/de2c26/000000?text=+)  | rgb(222, 44, 38)  |
| Extreme Drought  | +60  | `#a60f14` ![#a60f14](https://via.placeholder.com/15/a60f14/000000?text=+)  | rgb(166, 15, 20)  |


## Hari Basah Berturut-turut

Jumlah hari hujan berturut-turut (CWD) serupa dengan CDD di atas, jumlah hari berturut-turut terbesar dengan jumlah curah hujan harian lebih dari 1 mm (atau tergantung pada kriteria hari hujan negara), dalam waktu tertentu. Biasanya proses menghitung jumlah hari dalam 90 hari terakhir untuk mengukur tingkat kebasahan.

### Bagaimana ini bekerja

Hitung jumlah hari hujan berdasarkan ambang batas dan hitung jumlah hari terakhir sejak hari kering atau rangkaian hari terakhir berturut-turut yang memenuhi kriteria ambang dijumlahkan.

Kriteria ambang batas: 1, 2.5, 5, 10 dan 20 milimeter curah hujan

```
IF previousCWD == null THEN previousCWD == 0
ELSEIF todayRAIN < 1 AND previousCWD == 0 THEN previousCWD + 1
```

CWD berasal dari data IMERG

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menamilkan CWD harian |
| Variabel  | CWD  |
| Cakupan Geografis  | Indonesia 7N-12S, 94E-142E |
| Resolusi Spasial  | 0.1 derajat ~ 11.1 km di equator  |
| Resolusi sementara  | Harian  |
| Format  | GeoTIFF  |
| Unit  | Jumlah hari  |

#### Simbologi

?> Ambang batas dan simbologi untuk CWD dapat mengikuti kode warna dan gambar di bawah ini.

| Class  | Threshold  | Hex  | RGB  |
|---|---|---|---|
| No Rainfall  | 0  | `#cccccc` ![#cccccc](https://via.placeholder.com/15/cccccc/000000?text=+)  | rgb(204, 204, 204)  |
| Very Short  | 1 - 5  | `#ffffcc` ![#ffffcc](https://via.placeholder.com/15/ffffcc/000000?text=+)  | rgb(255, 255, 204)  |
| Short  | 6 - 10  | `#c6e8b3` ![#c6e8b3](https://via.placeholder.com/15/c6e8b3/000000?text=+)  | rgb(198, 232, 179)  |
| Moderate  | 11 - 20  | `#7eccba` ![#7eccba](https://via.placeholder.com/15/7eccba/000000?text=+)  | rgb(126, 204, 186)  |
| Long  | 21 - 30  | `#41b7c4` ![#41b7c4](https://via.placeholder.com/15/41b7c4/000000?text=+)  | rgb(65, 183, 196)  |
| Very Long  | 31 - 60  | `#2c80b8` ![#2c80b8](https://via.placeholder.com/15/2c80b8/000000?text=+)  | rgb(44, 128, 184)  |
| Extreme Wet  | +60  | `#253494` ![#253494](https://via.placeholder.com/15/253494/000000?text=+)  | rgb(37, 52, 148)  |


## Anomali EVI

Tujuannya adalah untuk mengevaluasi penyimpangan bulanan vegetasi di seluruh negeri. Hal ini dicapai melalui analisis Anomali, (yaitu perbandingan terhadap referensi). Enhanced Vegetation Index (EVI) digunakan sebagai ganti Normalized Difference Vegetation Index (NDVI) karena lebih sensitif terhadap perubahan di area yang memiliki biomassa tinggi, mengurangi pengaruh kondisi atmosfer pada nilai indeks vegetasi, dan mengoreksi sinyal latar belakang kanopi .

Anomali dihitung berdasarkan persentase rata-rata

Anomali (%) = $100$ * $\dfrac{x_i}{x_j}$

dimana $x_i$ adalah EVI saat ini dan $x_j$ adalah rata-rata jangka panjang dari EVI.

Anomali EVI berasal dari data MODIS MOD13Q1

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menampilkan data anomali EVI 16 hari  |
| Variabel  | Anomali EVI  |
| Cakupan Geografis  | Indonesia 7N-12S, 94E-142E  |
| Resolusi Spasial  | 250m di equator  |
| Resolusi sementara  | 16-hari.  |
| Format  | GeoTIFF  |
| Unit  | Persen (%)  |

#### Simbologi

?> Ambang batas dan simbologi untuk anomali EVI `16-hari` dapat mengikuti kode warna dan gambar di bawah ini.

| Class  | Hex  | RGB  |
|---|---|---|
| 50% ke bawah  | `#6a2b0e` ![#6a2b0e](https://via.placeholder.com/15/6a2b0e/000000?text=+) | rgb(106, 43, 14)  |
| 50 to 70%  | `#e06c2c` ![#e06c2c](https://via.placeholder.com/15/e06c2c/000000?text=+)  | rgb(224, 108, 44)  |
| 70 to 80%  | `#ebb049` ![#ebb049](https://via.placeholder.com/15/ebb049/000000?text=+)  | rgb(235, 176, 73)  |
| 80 to 90%  | `#e5db9e` ![#e5db9e](https://via.placeholder.com/15/e5db9e/000000?text=+)  | rgb(229, 219, 158)  |
| 90 to 110%  | `#ffffff` ![#ffffff](https://via.placeholder.com/15/ffffff/000000?text=+)  | rgb(255, 255, 255)  |
| 110 to 120%  | `#d6fb57` ![#d6fb57](https://via.placeholder.com/15/d6fb57/000000?text=+)  | rgb(214, 251, 87)  |
| 120 to 130%  | `#6fec48` ![#6fec48](https://via.placeholder.com/15/6fec48/000000?text=+)  | rgb(111, 236, 72)  |
| 130 to 150%  | `#3f8b48` ![#3f8b48](https://via.placeholder.com/15/3f8b48/000000?text=+)  | rgb(63, 139, 39)  |
| 150% ke atas  | `#1e4b10` ![#1e4b10](https://via.placeholder.com/15/1e4b10/000000?text=+)  | rgb(30, 75, 16)  |



## Analisis dampak

Selama satu dekade terakhir, lebih dari 16.600 bencana alam terjadi di Indonesia, dengan rata-rata 1700 bencana setiap tahunnya. Peristiwa cuaca hidrometeorologi menyebabkan 95 persen dari bencana ini, dengan banjir, tanah longsor dan angin kencang yang paling sering terjadi.

Sistem pangan Indonesia sering terganggu oleh bencana alam. Selain menyebabkan biaya manusia, lingkungan dan ekonomi yang tinggi, peristiwa cuaca ekstrem ini dapat menekan ketahanan pangan dan gizi, melalui efek buruk pada ketersediaan dan akses pangan, dan pada situasi gizi. Cuaca ekstrem dan bencana alam menghancurkan aset, tanah, tanaman, ternak, dan stok makanan. Mereka sering membuat pasar dan persediaan tidak terjangkau atau tidak terjangkau.

Namun, terlepas dari pentingnya menilai dampak kerusakan dan kerugian setelah peristiwa tersebut, memperkirakan dampak tepat waktu dan menantang.
Dengan mengotomatiskan akuisisi dan pemrosesan data, platform VAMPIRE memberikan perkiraan langsung tentang:
- Daerah prioritas yang kemungkinan terkena banjir atau kekeringan;
- Jumlah orang yang kemungkinan besar terkena dampak banjir dan kekeringan, dan
- Tanaman yang kemungkinan terkena banjir dan kekeringan (dalam hektar).

Perkiraan kekeringan tersedia dalam waktu hampir nyata (1 hari yang lalu dari hari ini); sedangkan perkiraan dampak banjir diberikan 3 hari ke depan.

Estimasi dampak yang disajikan dalam sistem menggunakan analisis spasial yang dilakukan dengan overlay (1) perkiraan area geografis yang terkena musim kemarau (kekeringan) atau basah (banjir), dengan (2) jumlah orang di area yang terkena dampak atau area tanaman di zona yang terkena dampak.

### Musim kemarau

#### Populasi

Dampak terhadap penduduk menunjukkan jumlah penduduk yang tinggal di suatu wilayah yang terkena kekeringan ekstrem dalam 90 hari terakhir. Indikator tersebut menutupi kepadatan penduduk dengan paparan kekeringan ekstrem yang ditentukan oleh jumlah hari sejak curah hujan terakhir (untuk kekeringan ekstrem, lebih dari 60 hari berturut-turut tanpa hujan).

Data paparan kekeringan diperoleh dari hari-hari sejak indikator hujan terakhir dari kumpulan data Integrated Multi-satelitE Retrievals for GPM (IMERG). Kepadatan populasi berasal dari dataset Facebook.

#### Tanaman-tanaman

Lapisan tanaman yang terkena dampak mengacu pada area tanaman (dalam hektar) yang telah terkena kekeringan ekstrim dalam 16 hari terakhir. Indikator ini menggabungkan keterpaparan suatu area terhadap kekeringan ekstrem (didefinisikan sebagai nilai VHI kurang dari 10) dan masker tanaman di area yang terpapar. Daerah yang teridentifikasi berada pada risiko dampak kekeringan pada tanaman.

Data untuk paparan kekeringan berasal dari Vegetation Health Index dari dataset MODIS. Luas tanaman menggunakan topeng tanaman MODIS.

### Musim hujan

#### Populasi

Dampak terhadap penduduk menunjukkan jumlah penduduk yang tinggal di suatu wilayah yang diperkirakan akan terkena curah hujan ekstrim yang dapat memicu banjir dalam 1 sampai 5 hari ke depan. Indikator tersebut menutupi kepadatan penduduk dengan curah hujan ekstrim yang memicu prakiraan banjir untuk semua kategori waspada untuk menghitung jumlah orang yang terkena dampak banjir.

Data untuk prakiraan curah hujan ekstrim berasal dari NOAA Global Forecast System dan NASA GPM IMERG. Kepadatan populasi berasal dari dataset Facebook.

#### Tanaman-tanaman

Lapisan tersebut mengacu pada luas tanaman (dalam hektar) yang diperkirakan akan terkena curah hujan ekstrim yang dapat memicu banjir dalam 1 hingga 5 hari ke depan. Indikator tersebut menutupi kepadatan penduduk dengan curah hujan ekstrem yang memicu prakiraan banjir untuk semua kategori peringatan dengan crop mask untuk area dengan peringatan yang terdeteksi dalam 1 hingga 5 hari ke depan.

Data curah hujan ekstrim berasal dari NOAA Global Forecast System dan NASA GPM IMERG. Luas tanaman menggunakan topeng tanaman MODIS.

