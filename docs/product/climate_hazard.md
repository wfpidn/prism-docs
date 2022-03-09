# Bahaya terkait iklim

Pemetaan tingkat bahaya alam (misalnya, menilai daerah dengan risiko tinggi) atau bencana adalah langkah pertama dalam manajemen risiko bencana dan tanggap darurat. Selanjutnya, pemetaan keterpaparan memungkinkan estimasi dampak bahaya atau bencana, misalnya mengenai jumlah penduduk atau infrastruktur yang terkena dampak.

Bagian ini menjelaskan secara rinci metodologi dan operasi analisis yang diperlukan untuk memenuhi persyaratan pengguna WFP di tingkat negara atau regional. Hal ini didasarkan pada pencarian ekstensif dari jurnal terkait untuk perhitungan dampak selama bencana dan ketersediaan data gratis global di internet.

## Curah hujan (rasio) anomali

Tujuan dari anomali curah hujan adalah untuk mengevaluasi kualitas curah hujan bulanan di negara tersebut. Hal ini dicapai melalui analisis anomali, yaitu perbandingan terhadap referensi. Referensi klasik adalah rata-rata jangka panjang.

Anomali curah hujan dibangkitkan berdasarkan data dekad. Model akan menghitung akumulasi curah hujan dan indeks iklim lainnya dari curah hujan berdasarkan data selama dekad terbaru yang telah dikumpulkan dari perkiraan pentad. Setiap bulan memiliki tiga dekad, sehingga dua dekad pertama memiliki 10 hari (yaitu, 1-10, 11-20), dan yang ketiga terdiri dari sisa hari dalam sebulan (21-28 atau 21-29 atau 21- 30 atau 21-31 Oleh karena itu, panjang dekad ketiga setiap bulan tidak konsisten dan bervariasi dari 8-11 hari, tergantung pada panjang bulan.

Anomali dihitung berdasarkan persentase rata-rata

Anomali (%) = $100$ * $\dfrac{x_i}{x_j}$

dimana $x_i$ curah hujan saat ini dan $x_j$ adalah curah hujan rata-rata jangka panjang.

Anomali curah hujan yang berasal dari data CHIRPS

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menampilkan data anomali curah hujan dekad dan bulanan  |
| Variabel  | Anomali curah hujan  |
| Cakupan Geografis  | Global 50N-50S, 180W-180E |
| Resolusi Spasial  | 0.05 derajat ~ 5.6 km di equator  |
| Resolusi sementara  | dekad, 1 bulan, 3 bulan, 6 bulan, 9 bulan, dan 12 bulan, bergulir oleh dekad.  |
| Format  | GeoTIFF  |
| Unit  | Persen (%)  |

#### Simbologi

?> Ambang batas dan simbologi untuk anomali curah hujan dapat mengikuti kode warna dan gambar di bawah ini.

| Class  | Hex  | RGB  |
|---|---|---|
| 40% ke bawah  | `#a16622` ![#a16622](https://via.placeholder.com/15/a16622/000000?text=+) | rgb(161, 102, 34)  |
| 40 to 60%  | `#db9835` ![#db9835](https://via.placeholder.com/15/db9835/000000?text=+)  | rgb(219, 152, 53)  |
| 60 to 80%  | `#eec883` ![#eec883](https://via.placeholder.com/15/eec883/000000?text=+)  | rgb(238, 200, 131)  |
| 80 to 90%  | `#fcebb6` ![#fcebb6](https://via.placeholder.com/15/fcebb6/000000?text=+)  | rgb(252, 235, 182)  |
| 90 to 110%  | `#ffffff` ![#ffffff](https://via.placeholder.com/15/ffffff/000000?text=+)  | rgb(255, 255, 255)  |
| 110 to 120%  | `#caf8f9` ![#caf8f9](https://via.placeholder.com/15/caf8f9/000000?text=+)  | rgb(202, 248, 249)  |
| 120 to 140%  | `#91e0ee` ![#91e0ee](https://via.placeholder.com/15/91e0ee/000000?text=+)  | rgb(145, 224, 238)  |
| 140 to 180%  | `#50b7da` ![#50b7da](https://via.placeholder.com/15/50b7da/000000?text=+)  | rgb(80, 183, 218)  |
| 180% ke atas  | `#3d78cf` ![#3d78cf](https://via.placeholder.com/15/3d78cf/000000?text=+)  | rgb(61, 120, 207)  |




## Indeks Presipitasi Standar

Standardized Precipitation Index (SPI) adalah indeks normalisasi yang mewakili kemungkinan terjadinya jumlah curah hujan yang diamati jika dibandingkan dengan klimatologi curah hujan dalam periode jangka panjang. Catatan jangka panjang ini dicocokkan dengan distribusi probabilitas, yang kemudian diubah menjadi distribusi normal sehingga rata-rata SPI untuk lokasi dan periode yang diinginkan adalah nol.

Nilai SPI negatif merupakan defisit curah hujan dan kurang dari median curah hujan (Kering), dimulai ketika nilai SPI sama atau di bawah -1.0. Sedangkan nilai SPI positif menunjukkan kelebihan curah hujan dan lebih besar dari curah hujan median (Basah), dimulai ketika nilai SPI sama atau di atas 1,0, dan berakhir ketika nilainya menjadi negatif.

### Bagaimana ini bekerja
- Curah hujan dinormalisasi menggunakan fungsi distribusi probabilitas sehingga nilai SPI benar-benar dilihat sebagai simpangan baku dari median.
- Distribusi yang dinormalisasi memungkinkan estimasi periode kering dan basah.
- Nilai akumulasi dapat digunakan untuk menganalisis tingkat keparahan kekeringan (magnitudo).
- Diperlukan setidaknya 30 tahun data curah hujan bulanan terus menerus tetapi catatan jangka panjang akan lebih disukai.
- Interval skala waktu SPI yang lebih pendek dari 1 bulan dan lebih dari 24 bulan mungkin tidak dapat diandalkan.
- Ini secara spasial invarian dalam interpretasinya.
- Sifatnya yang berbasis probabilitas (probabilitas presipitasi yang diamati diubah menjadi indeks) membuatnya sangat cocok untuk manajemen risiko dan pemicu pengambilan keputusan.

Python packages [climate-indices](https://pypi.org/project/climate-indices/) dikembangkan oleh [U.S. Drought Portal](https://www.drought.gov/drought/python-climate-indices) digunakan untuk mengkalkulasi index.

SPI berasal dari data CHIRPS

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menampilkan SPI-1, SPI-2, SPI-3, SPI-6, SPI-9, SPI-12 and SPI-24  |
| Variabel  | SPI  |
| Cakupan Geografis  | Global 50N-50S, 180W-180E |
| Resolusi Spasial  | 0.05 degree ~ 5.6 km at equator  |
| Resolusi sementara  | 1-bulan, 3-bulan, 6-bulan, 9-bulan, 12-bulan and 24-bulan, bergulir oleh dekad.  |
| Format  | GeoTIFF  |
| Unit  | n/a  |

#### Simbologi

?> Ambang batas dan simbologi untuk SPI dapat mengikuti kode warna dan gambar di bawah ini.

| Class  | Threshold  | Hex  | RGB  |
|---|---|---|---|
| Exceptionally Dry  | -2.00 and below  | `#760005` ![#760005](https://via.placeholder.com/15/760005/000000?text=+)  | rgb(118, 0, 5)  |
| Extremely Dry  | -2.00 to -1.50  | `#ec0013` ![#ec0013](https://via.placeholder.com/15/ec0013/000000?text=+)  | rgb(236, 0, 19)  |
| Severely Dry  | -1.50 to -1.20  | `#ffa938` ![#ffa938](https://via.placeholder.com/15/ffa938/000000?text=+)  | rgb(255, 169, 56)  |
| Moderately Dry  | -1.20 to -0.70  | `#fdd28a` ![#fdd28a](https://via.placeholder.com/15/fdd28a/000000?text=+)  | rgb(253, 210, 138)  |
| Abnormally Dry  | -0.70 to -0.50  | `#fefe53` ![#fefe53](https://via.placeholder.com/15/fefe53/000000?text=+)  | rgb(254, 254, 83)  |
| Near Normal  | -0.50 to +0.50  | `#ffffff` ![#ffffff](https://via.placeholder.com/15/ffffff/000000?text=+)  | rgb(255, 255, 255)  |
| Abnormally Moist  | +0.50 to +0.70  | `#a2fd6e` ![#a2fd6e](https://via.placeholder.com/15/a2fd6e/000000?text=+)  | rgb(162, 253, 110)  |
| Moderately Moist  | +0.70 to +1.20  | `#00b44a` ![#00b44a](https://via.placeholder.com/15/00b44a/000000?text=+)  | rgb(0, 180, 74)  |
| Very Moist  | +1.20 to +1.50  | `#008180` ![#008180](https://via.placeholder.com/15/008180/000000?text=+)  | rgb(0, 129, 128)  |
| Extremely Moist  | +1.50 to +2.00  | `#2a23eb` ![#2a23eb](https://via.placeholder.com/15/2a23eb/000000?text=+)  | rgb(42, 35, 235)  |
| Exceptionally Moist  | +2.00 and above  | `#a21fec` ![#a21fec](https://via.placeholder.com/15/a21fec/000000?text=+)  | rgb(162, 31, 236)  |




## LST (selisih) anomali

Tujuannya adalah untuk mengevaluasi deviasi bulanan suhu di seluruh negeri. Hal ini dicapai melalui analisis Anomali, (yaitu perbandingan terhadap referensi).

Anomali dihitung berdasarkan selisih rata-rata.

LST anomali (°C) = $LST - LSTavg$

dimana:
- $LST$ adalah nilai LST saat ini
- $LSTavg$ adalah nilai rata-rata jangka panjang dari LST.

LST dan Rata-rata jangka panjang LST berasal dari data MODIS

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menampilkan data anomali LST 8 hari  |
| Variabel  | anomali LST |
| Cakupan Geografis  | Global  |
| Resolusi Spasial  | 1 km di equator  |
| Resolusi sementara  | 8-hari.  |
| Format  | GeoTIFF  |
| Unit  | Derajat Celcius (°C)  |

#### Simbologi

?> Ambang batas dan simbologi untuk anomali perbedaan suhu permukaan tanah `8 hari` dalam derajat celcius (°C) dapat mengikuti kode warna dan gambar di bawah ini.

| Class  | Hex  | RGB  |
|---|---|---|
| -10 ke bawah  | `#b2182b` ![#b2182b](https://via.placeholder.com/15/b2182b/000000?text=+) | rgb(178, 24, 43)  |
| -10 to -5  | `#d6604d` ![#d6604d](https://via.placeholder.com/15/d6604d/000000?text=+)  | rgb(214, 96, 77)  |
| -5 to -2  | `#f4a582` ![#f4a582](https://via.placeholder.com/15/f4a582/000000?text=+)  | rgb(244, 165, 130)  |
| -2 to -1  | `#fddbc7` ![#fddbc7](https://via.placeholder.com/15/fddbc7/000000?text=+)  | rgb(253, 219, 199)  |
| -1 to +1  | `#f7f7f7` ![#f7f7f7](https://via.placeholder.com/15/f7f7f7/000000?text=+)  | rgb(247, 247, 247)  |
| +1 to +2  | `#d1e5f0` ![#d1e5f0](https://via.placeholder.com/15/d1e5f0/000000?text=+)  | rgb(209, 229, 240)  |
| +2 to +5  | `#92c5de` ![#92c5de](https://via.placeholder.com/15/92c5de/000000?text=+)  | rgb(146, 197, 222)  |
| +5 to +10  | `#4393c3` ![#4393c3](https://via.placeholder.com/15/4393c3/000000?text=+)  | rgb(67, 147, 195)  |
| +10 ke atas  | `#2166ac` ![#2166ac](https://via.placeholder.com/15/2166ac/000000?text=+)  | rgb(33, 102, 172)  |




## Indeks Kondisi Suhu

Indeks Kondisi Suhu (VCI) membandingkan LST saat ini dengan kisaran nilai yang diamati pada periode yang sama di tahun-tahun sebelumnya. TCI dinyatakan dalam % dan memberikan gambaran di mana nilai yang diamati terletak di antara nilai-nilai ekstrim (minimum dan maksimum) pada tahun-tahun sebelumnya. TCI digunakan untuk menentukan stres pada vegetasi yang disebabkan oleh suhu dan kebasahan yang berlebihan. Kondisi diperkirakan relatif terhadap suhu maksimum dan minimum dan dimodifikasi untuk mencerminkan respon vegetasi yang berbeda terhadap suhu.

TCI dihitung menggunakan persamaan,

$TCI$ = $100$ * $\dfrac{LSTmax - LST}{LSTmax - LSTmin}$

dimana:
- $LST$ adalah nilai saat ini dari LST
- $LSTmin$ adalah nilai minimum jangka panjang dari LST.
- $LSTmax$ adalah nilai maksimum jangka panjang dari LST.

LST max and min berasal dari data MODIS

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | proxy untuk perhitungan Indeks Kesehatan Vegetasi |
| Variabel  | TCI  |
| Cakupan Geografis  | Global  |
| Resolusi Spasial  | 1 km di equator  |
| Resolusi sementara  | 16-hari.  |
| Format  | GeoTIFF  |
| Unit  | Persen (%)  |




## Anomali NDVI

Tujuannya adalah untuk mengevaluasi penyimpangan bulanan vegetasi di seluruh negeri. Hal ini dicapai melalui analisis Anomali, (yaitu perbandingan terhadap referensi).

Anomali dihitung berdasarkan persentase rata-rata

Anomali (%) = $100$ * $\dfrac{x_i}{x_j}$

dimana $x_i$ adalah NDVI saat ini dan $x_j$ adalah rata-rata jangka panjang dari NDVI.

Rata-rata jangka panjang NDVI dan NDVI berasal dari data MODIS

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menampilkan data anomali NDVI 16 hari  |
| Variabel  | Anomali NDVI  |
| Cakupan Geografis  | Global  |
| Resolusi Spasial  | 1 km di equator  |
| Resolusi sementara  | 16-hari.  |
| Format  | GeoTIFF  |
| Unit  | Persen (%)  |

#### Simbologi

?> Ambang batas dan simbologi untuk anomali NDVI dapat mengikuti kode warna dan gambar di bawah ini.

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




## Indeks Kondisi Vegetasi

Vegetation Condition Index (VCI) membandingkan NDVI saat ini dengan kisaran nilai yang diamati pada periode yang sama di tahun-tahun sebelumnya. VCI dinyatakan dalam % dan memberikan gambaran di mana nilai yang diamati terletak di antara nilai-nilai ekstrim (minimum dan maksimum) pada tahun-tahun sebelumnya. Nilai yang lebih rendah dan lebih tinggi menunjukkan kondisi vegetasi yang buruk dan baik. VCI berhubungan dengan kondisi kelembaban vegetasi

Anomali dihitung berdasarkan persentase rata-rata

$VCI$ = $100$ * $\dfrac{NDVI - NDVImin}{NDVImax - NDVImin}$

dimana:
- $NDVI$ adalah nilai saat ini dari NDVI
- $NDVImin$ adalah nilai minimum jangka panjang dari NDVI
- $NDVImax$ adalah nilai maksimum jangka panjang NDVI.

Maks dan min jangka panjang NDVI berasal dari data MODIS

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | proxy untuk perhitungan Indeks Kesehatan Vegetasi  |
| Variabel  | VCI  |
| Cakupan Geografis  | Global  |
| Resolusi Spasial  | 1 km di equator  |
| Resolusi sementara  | 16-hari.  |
| Format  | GeoTIFF  |
| Unit  | Persen (%)  |


## Indeks Kesehatan Vegetasi

Vegetation Health Index (VHI) didasarkan pada kombinasi (i) Vegetation Condition Index (VCI): berhubungan dengan kondisi kelembaban vegetasi; dan (ii) Indeks Kondisi Suhu (VCI): berhubungan dengan kondisi termal vegetasi.

VCI dibangun menggunakan NDVI dan suhu permukaan tanah (LST) untuk TCI. VHI cukup efektif untuk digunakan sebagai data proxy untuk memantau kesehatan vegetasi, kekeringan, kelembaban, kondisi termal, dll.

Setelah menghitung nilai VCI dan TCI, indeks akhir untuk kekeringan pertanian adalah

$VHI$ = $0.5 * (TCI + VCI)$

#### Tentang data

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Menampilkan data VHI 16 hari  |
| Variabel  | VHI  |
| Cakupan Geografis  | Global  |
| Resolusi Spasial  | 1 km di equator  |
| Resolusi sementara  | 16-hari.  |
| Format  | GeoTIFF  |
| Unit  | n/a  |

#### Simbologi

?> Ambang batas dan simbologi untuk VHI dapat mengikuti kode warna dan gambar di bawah ini.

| Class  | Threshold  | Hex  | RGB  |
|---|---|---|---|
| No Drought  | 40 and above  | `#b2b2b2` ![#b2b2b2](https://via.placeholder.com/15/b2b2b2/000000?text=+) | rgb(178, 178, 178)  |
| Mild Drought  | 30 to 40  | `#ffe5d9` ![#ffe5d9](https://via.placeholder.com/15/ffe5d9/000000?text=+)  | rgb(255, 229, 217)  |
| Moderate Drought  | 20 to 30  | `#fcaf92` ![#fcaf92](https://via.placeholder.com/15/fcaf92/000000?text=+)  | rgb(252, 175, 146)  |
| Severe Drought  | 10 to 20  | `#fa6948` ![#fa6948](https://via.placeholder.com/15/fa6948/000000?text=+)  | rgb(250, 105, 72)  |
| Extreme Drought  | 10 and below  | `#cc181e` ![#cc181e](https://via.placeholder.com/15/cc181e/000000?text=+)  | rgb(204, 24, 30)  |
