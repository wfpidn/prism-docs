# Backend

Ini berisi kode yang mengunduh dan mengekstrak data dari berbagai sumber mentah, melakukan perhitungan, dan menghasilkan produk data. Ini juga berisi pengaturan untuk [Geoserver](http://geoserver.org/) yang menyajikan produk data ke front-end.


## Pengembangan
---

### Persyaratan

Untuk membuatnya lebih mudah untuk dikembangkan secara lokal, kami memutuskan untuk menggunakan Docker dan Make.
Satu-satunya persyaratan adalah docker dan docker-compose.
Jika mereka tidak diinstal pada mesin Anda, Anda dapat mengikuti langkah-langkah ini untuk memulai:
https://docs.docker.com/compose/install/

### Environment

Anda perlu menyiapkan file `.env` dengan informasi yang diperlukan. Anda dapat menggunakan `.env.sample` sebagai contoh.

### File Data

Untuk menghindari pemeriksaan file besar ke repositori, kami menghapus file data yang dihasilkan, data SQL, dan Boundary/"shapefiles" yang digunakan untuk memfilter data menurut negara. Untuk membuat produk data atau memulai Geoserver, Anda mungkin perlu mengunduh file tambahan. Anda dapat mengunduh arsip yang berisi file-file ini dari tautan berikut. Salin file arsip ini ke direktori `prisma/backend` utama, lalu ekstrak untuk mendapatkan file yang relevan:

```
cd prism/backend
# Download the archive that you would like.
curl -O https://wfp-prism.s3-us-west-1.amazonaws.com/prism_sql_20191010.tar.gz
tar -xzvf prism_sql_20191010.tar.gz
```

Berikut ini tautan ke beberapa file impor:

- **Indonesia Shape Files:** https://wfp-prism.s3-us-west-1.amazonaws.com/prism_shapefiles_20191010.tar.gz
  Shapefile ini diperlukan untuk membuat produk data untuk Indonesia.
- **Sample SQL data:** https://wfp-prism.s3-us-west-1.amazonaws.com/prism_sql_20191010.tar.gz
  Ini berisi dump SQL dari produk data yang dibuat untuk Indonesia.
- **Mock Geoserver data:** https://wfp-prism.s3-us-west-1.amazonaws.com/prism_geoserver_mock_data_20191010.tar.gz
  Ini berisi contoh produk data untuk memungkinkan Geoserver menyajikan respons "tiruan", atau contoh setiap kali produk data.

Jika Anda ingin membuat arsip Anda sendiri dengan file besar (ingat, kami tidak ingin memeriksa file besar ke dalam repo) yang akan berguna untuk tim Anda, Anda dapat dengan mudah membuat arsip Anda sendiri. Cara termudah untuk melakukannya adalah dengan membuat kueri `find` yang cocok dengan file yang ingin Anda bagikan, lalu membuat arsip menggunakan `tar`. Misalnya, jika Anda ingin membuat arsip semua file `.tif` di `geoserver_data`:

```
find geoserver_data -name *.tif -exec tar -czvf my_archive.tar.gz {} \;
```

Ini menghasilkan `my_archive.tar.gz`. `find` mendukung berbagai macam pemilih, termasuk regex.
### Menjalankan Produk
Skrip task runner mencoba membuat tugas mudah dijalankan. Secara otomatis memulai Docker containers
dan kemudian menjalankan tugas di dalam containers. Script ini membutuhkan docker untuk diinstal dan
dikonfigurasi di lingkungan lokal, dan membutuhkan Python 3.6 untuk diinstal.

Untuk menjalankan produk yang berbeda secara lokal, Anda dapat menggunakan dua skrip berikut. Skrip runner memiliki bantuan runtime yang tersedia dengan `--help`. Untuk banyak produk (spi, vhi, dslr, rain_anomaly, dll.), Anda juga ingin menentukan tanggal dengan opsi -d YYYY-MM-DD (defaultnya menggunakan tanggal saat ini, tetapi biasanya bukan itu yang ingin Anda lakukan).

```
./run_prism_task.py PRODUCT_NAME -d 2019-06-01

./scripts/backfill_data.py PRODUCT_NAME 2019-01-01 2019-11-01
```

Perhatikan bahwa skrip ini hanyalah pembungkus untuk `./prism_process.py` yang mengatur
Panggilan Docker dan penanganan argumen default yang lebih baik.

Secara default, perintah ini menjalankan tugas PRISM "penuh", yang mencakup pembuatan tugas YAML
file konfigurasi (secara default di `./config/{country}_{task}.yml`) dan kemudian menjalankan tugas yang ditentukan oleh file itu. Jika Anda ingin memisahkan langkah-langkah ini (misalnya, buat saja file konfigurasi atau jalankan saja tugas berdasarkan file konfigurasi yang ada), Anda dapat melakukan ini:

**Hasilkan konfigurasi (jangan jalankan tugas)**
```
$ ./run_prism_task.py -o="generate_config" spi
```

**Jalankan tugas (tanpa membuat/menimpa konfigurasi)**
```
$ ./run_prism_task.py -o="run" spi
```

#### Produck tersedia
Untuk memulai, kami sarankan untuk mendapatkan akses ke data yang telah dihitung sebelumnya, setidaknya untuk rata-rata jangka panjang yang membutuhkan waktu yang sangat lama untuk dihitung.

Berikut adalah daftar berbagai produk yang tersedia. Perhatikan bahwa data yang mendasarinya mungkin tidak selalu tersedia di negara tujuan.

**Rata-rata Jangka Panjang**
- evi_longterm_average
- chirps_longterm_average
- lst_longterm_average


**Produk**
- days_since_last_rain
- flood_forecast
- vci
- tci
- vhi
- rainfall_anomaly
- spi

### Secara lokal

Untuk memulai, jalankan `make backend` dari folder utama.
## Tests & Linters

Untuk memastikan konsistensi dalam kualitas kode dan hasil penghitungan, kami menerapkan kerangka pengujian (pytest) dan linter (pep8 + serpihan8) untuk Python.

Semua fungsi backend Prism harus diuji. Ekspektasi "cakupan uji" akan ditetapkan pada 90%.