# Baseline

Sistem penanggulangan bencana yang efektif memerlukan pengumpulan data dasar yang komprehensif, akurat, tepat waktu, dan dapat diakses. Tanpa karakteristik tersebut, sistem penanggulangan bencana yang efektif, ekonomis, dan berorientasi pada tugas tidak dapat dicapai. Bagian ini berfokus pada pengumpulan data dasar dan perhitungan dampak untuk bencana tertentu, yang dapat didefinisikan sebagai ruang lingkup dan sifat dari keseluruhan sumber informasi yang diperlukan untuk mempersiapkan dan menanggapi berbagai bencana. Yang dibutuhkan saat ini adalah pemahaman yang jelas tentang karakteristik sumber daya informasi saat ini, kemampuan fungsionalnya, dan penggunaannya untuk manajemen bencana.

## Populasi

Pemetaan populasi global berkembang pesat dalam beberapa tahun terakhir. Mereka tersedia pada skala spasial rinci. Analisis didasarkan pada satelit atau lapisan data geospasial lainnya. Data kependudukan diperlukan untuk analisis dampak pertumbuhan penduduk, pemantauan perubahan penduduk, dan perencanaan intervensi.

### Pemindaian

Basis Data Pemindaian Populasi Global dikembangkan di Departemen Energi [Laboratorium Nasional Oak Ridge](https://landscan.ornl.gov). Data tersebut mewakili database distribusi populasi global resolusi terbaik yang tersedia. LandScan dikenal sebagai aplikasi yang sangat praktis dalam urusan kemanusiaan karena menyediakan model distribusi penduduk yang paling dapat diandalkan.

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | Kepadatan populasi yang divisualisasikan di dasbor  |
| Variabel  | Total populasi  |
| Cakupan Geografis | Global  |
| Resolusi Spasial | Cell berukuran 30 arc-second, or 0.008333333 derajat desimal, mewakili sekitar 1 km2 di dekat khatulistiwa  |
| Resolusi sementara  | Tahunan  |
| Format  | Format grid ESRI dan format raster biner ESRI  |
| Unit  | Nilai cell adalah jumlah populasi bilangan bulat yang mewakili rata-rata atau ambien dari distribusi populasi  |
| Sumber  | https://landscan.ornl.gov/landscan-datasets  |
| Referensi  | https://landscan.ornl.gov/documentation  |

#### Simbologi

?> Ambang batas dan simbologi pemindaian kepadatan penduduk dapat mengikuti kode warna dan gambar di bawah ini.

| Class  | Hex  | RGB  |
|---|---|---|
| Tidak ada populiasi  | `#c2c3c6` ![#c2c3c6](https://via.placeholder.com/15/c2c3c6/000000?text=+) | rgb(194, 195, 198)  |
| 1 to 5  | `#fbf6c2` ![#fbf6c2](https://via.placeholder.com/15/fbf6c2/000000?text=+)  | rgb(251, 246, 194)  |
| 6 - 25  | `#f6ef8d` ![#f6ef8d](https://via.placeholder.com/15/f6ef8d/000000?text=+)  | rgb(246, 239, 141)  |
| 26 - 50  | `#f4e957` ![#f4e957](https://via.placeholder.com/15/f4e957/000000?text=+)  | rgb(244, 233, 87)  |
| 51 - 100  | `#eda343` ![#eda343](https://via.placeholder.com/15/eda343/000000?text=+)  | rgb(237, 163, 67)  |
| 101 - 500  | `#e26d38` ![#e26d38](https://via.placeholder.com/15/e26d38/000000?text=+)  | rgb(226, 109, 56)  |
| 501 - 2,500  | `#da3832` ![#da3832](https://via.placeholder.com/15/da3832/000000?text=+)  | rgb(218, 56, 50)  |
| 2,501 - 5,000  | `#b93634` ![#b93634](https://via.placeholder.com/15/b93634/000000?text=+)  | rgb(185, 54, 52)  |
| 5,001 - 130,000  | `#561b1b` ![#561b1b](https://via.placeholder.com/15/561b1b/000000?text=+)  | rgb(86, 27, 27)  |



### Facebook

Untuk membuat peta populasi resolusi tinggi, Facebook menggunakan teknik pembelajaran mesin untuk mengidentifikasi bangunan dari citra satelit yang tersedia secara komersial. Kemudian bekerja dengan mitra di Universitas Columbia untuk melapisi perkiraan populasi umum berdasarkan data sensus yang tersedia untuk umum dan statistik populasi lainnya. Peta yang dihasilkan adalah alat yang paling rinci dan dapat ditindaklanjuti yang tersedia untuk organisasi bantuan dan penelitian.

| Karakteristik  | Deskripsi  |
|---|---|
| Fungsi  | proxy untuk analisis dampak  |
| Variabel  | Jumlah penduduk, Pria, Wanita, Balita, Remaja 15-24, Wanita usia subur 15-49, Lansia 60+  |
| Cakupan Geografis  | Global  |
| Resolusi Spasial  | 30 meter/pixel  |
| Resolusi sementara  | t/a (Estimasi tahun 2019)  |
| Format  | GeoTIFF  |
| Unit  | Jumlah populasi pada resolusi 30m  |
| Sumber  | https://data.humdata.org/organization/facebook  |
| Referensi  | https://dataforgood.fb.com/docs/high-resolution-population-density-maps-demographic-estimates-documentation/  |


## Lahan pertanian

Peta tutupan lahan mewakili informasi spasial pada berbagai jenis (classes) tutupan fisik permukaan bumi, mis. hutan, padang rumput, lahan pertanian, danau, lahan basah. Lahan pertanian mencakup area yang digunakan untuk produksi tanaman yang disesuaikan untuk panen. Dua subkategori lahan pertanian diakui: dibudidayakan dan non-digarap. Lahan pertanian yang dibudidayakan terdiri dari lahan untuk tanaman baris atau tanaman jarak dekat dan juga lahan tanaman budidaya lainnya, misalnya, lahan jerami atau lahan penggembalaan yang bergiliran dengan tanaman baris atau tanaman jarak dekat. Lahan pertanian non-budidaya meliputi lahan jerami permanen dan lahan pertanian hortikultura.

### GFSAD30

[GFSAD30](https://geography.wr.usgs.gov/science/croplands/index.html) adalah proyek yang didanai NASA untuk menyediakan data lahan pertanian global beresolusi tinggi dan penggunaan airnya yang berkontribusi terhadap ketahanan pangan global di abad kedua puluh satu. Produk GFSAD30 diturunkan melalui data penginderaan jauh multi-sensor (misalnya, Landsat, MODIS, AVHRR), data sekunder, dan data plot lapangan dan bertujuan untuk mendokumentasikan dinamika lahan pertanian dari tahun 1990 hingga 2017.

| Karakterisik | Deskripsi |
|---|---|
| Fungsi | proxy untuk analisis dampak  |
| Variabel  | Luas tanaman  |
| Cakupan Geografis  | Global  |
| Resolusi Spasial  | 30 meter/pixel  |
| Resolusi sementara | t/a (Estimasi tahun 2015)  |
| Format  | GeoTIFF  |
| Unit  | t/a  |
| Sumber  | [Southeast and Northeast Asia](https://lpdaac.usgs.gov/products/gfsad30seacev001/)  |
| Referensi  | https://lpdaac.usgs.gov/documents/168/GFSAD30SEACE_User_Guide_V1.pdf  |


### MODIS

Dataset luasan lahan pertanian global MODIS menggunakan 250m data MODIS (MODerate Resolution Imaging Spectroradiometer) untuk memetakan luas lahan pertanian produksi global. Satu set metrik MODIS multi-tahun yang menggabungkan empat pita tanah MODIS, NDVI (Normalized Difference Vegetation Index) dan data termal digunakan untuk menggambarkan fenologi lahan pertanian selama periode 2000-2008.

Dengan resolusi spasial 250m, produk luas lahan tanaman global mewakili peta lahan pertanian global skala terbaik yang diturunkan menggunakan input sinoptik, dan karena dimasukkannya data MODIS 9 tahun, peta ini dirancang untuk relatif tidak sensitif terhadap variabilitas antar-tahunan di menggambarkan area produksi lahan pertanian inti.

| Karakterisik  | Probabilitas Lahan Pertanian  | Lahan Pertanian/Non-Pertanian Terpisah  |
|---|---|---|
| Fungsi  | proxy untuk analisis dampak  | proxy untuk analisis dampak  |
| Variabel  | Luas tanaman  | Luas tanaman  |
| Cakupan Geografis  | Global  | Global  |
| Resolusi Spasial  | 250 meter/pixel  | 250 meter/pixel  |
| Resolusi sementara  | t/a (Estimasi tahun 2010)  | t/a (Estimasi tahun 2010)  |
| Format  | GeoTIFF  | GeoTIFF  |
| Unit  | Nilai dari 1 sampai 100 adalah probabilitas bahwa piksel adalah lahan pertanian produksi. Nilai 0 adalah air dan nilai 255 adalah data.  | Nilai 1 berarti lahan pertanian, 0 berarti bukan lahan pertanian. Nilai 254 berarti air dan 255 bukan data.  |
| Sumber  | http://glad.geog.umd.edu/dataset/gce/250mprob  | http://glad.geog.umd.edu/dataset/gce/modis-global-crop-extent-discrete-croplandnot-cropland-data  |
| Referensi  | http://glad.geog.umd.edu/dataset/gce/global-cropland-extent  | http://glad.geog.umd.edu/dataset/gce/global-cropland-extent  |
