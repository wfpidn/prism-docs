# Frontend

Ini adalah pedoman untuk antarmuka front-end PRISM. Ini menampilkan data, prakiraan, dan proyeksi dampak pada antarmuka peta yang dapat dikonfigurasi.

## Fungsionalitas

Frontend PRISM yang baru dibuat sebagai situs web statis untuk meminimalkan ketergantungan silang dan menyederhanakan penerapan sebanyak mungkin. Saat ini, frontend PRISM menyediakan kemampuan untuk:
- Muat batas administratif sebagai GeoJSON (`src/config/admin_boundaries.json`)
- Muat data dasar sebagai JSON, dan tautkan ke batas administratif
- Menampilkan lapisan WMS dari Geoserver atau titik akhir Open Data Cube, dengan kemampuan pemilihan tanggal
- Menampilkan tabel CSV di panel sisi kiri

## Konfigurasi

Konfigurasi dibagi menjadi empat file yang dapat Anda temukan di `src/config`:
- i. `prism.json`
- ii. `layers.json`
- iii. `tables.json`
- iv. `baseline.ts`

### prism.json
Ini adalah file konfigurasi utama. Anda dapat menentukan:
- endpoint server
- Pengaturan peta (titik awal, zoom)
- Kategori

Kategori default adalah `baseline`, `climate`, `impact` dan `tables`.
Untuk setiap kategori, Anda dapat mendefinisikan subkategori sebagai "nama_subkategori": [layer], daftar layer dari `layers.json`.

### layers.json
Ada 3 jenis utama layer:

#### raster
Layer ini hanya diproses sebagai gambar raster dari server.
```
"pasture_anomaly": {
    "title": "Pasture anomaly",
    "server_type": "wms",
    "server_layer": "ModisAnomaly",
    "server_uri": "https://mongolia.sibelius-datacube.org:5000/wms?layers=ModisAnomaly",
    "has_date": true,
    "date_interval": "days",
    "opacity": 0.3,
    "legend_text": "Converts  NDVI to pasture (kg/ha) values and divides the current period by the long term average to calculate pasture anomaly.",
    "legend": [
        { "value": "12000", "color": "#ff0000" },
        { "value": "14000", "color": "#ff5900" },
        { "value": "16000", "color": "#ff8400" },
        { "value": "18000", "color": "#ffce63" },
        { "value": "19000", "color": "#ffdd94" },
        { "value": "20000", "color": "#ffffbf" },
        { "value": "21000", "color": "#dee09f" },
        { "value": "22000", "color": "#bbbf7c" },
        { "value": "24000", "color": "#9da360" },
        { "value": "26000", "color": "#7e8745" },
        { "value": "28000", "color": "#5b6e00" }
    ]
}
```

#### baseline

Layer-layer diperoleh dengan mencocokkan data dari bidang `data` dengan batas administratif.
Kolom `data` harus mengarah ke kumpulan data yang ditentukan dalam `baseline.ts`

```
"population_below_poverty": {
    "title": "Population below national poverty line (%)",	    "title": "Poverty Headcount",
    "server_type": "wms",	    "type": "json",
    "server_uri": "https://mng-wfp.ovio.org:8443/geoserver/prism/wms?service=WMS&layers=poverty_HC",	    "data": "nsoPoverty",
    "admin_code": "CODE1",
    "has_date": false,	    "has_date": false,
    "opacity": 0.3,	    "opacity": 0.3,
    "legend_text": "Source: Susenas"	    "legend": [
      { "value": "25", "color": "#fef0d9" },
      { "value": "30", "color": "#fdcc8a" },
      { "value": "35", "color": "#fc8d59" },
      { "value": "40", "color": "#e34a33" },
      { "value": "45", "color": "#b30000" }
    ],
    "legend_text": "The poverty headcount is the share of the population whose consumption / expenditure is below the poverty line by Aimag. Year: 2018. Source: National Statistics Office"
}
```

#### impact

```
"herd_pasture_impact": {
    "title": "Number of herder households exposed to severe pasture anomaly",
    "hazard_layer": "pasture_anomaly",
    "baseline_layer": "nsoHerders",
    "threshold": " <= 25000",
    "opacity": 0.3,
    "legend_text": "Number of herder households within ADMIN2 in an area where the median pasture anomaly is <= -50%",
    "legend": [
      { "value": "25", "color": "#ffeda0”" },
      { "value": "30", "color": "#feb24c”" },
      { "value": "35", "color": "#f03b20”" }
    ]
}
```

### baseline.ts
File ini digunakan untuk memuat set data sebelumnya dan memastikan bahwa mereka diformat dengan benar. Berkat TypeScript, ini membatasi potensi ketidakcocokan dan pemuatan yang gagal.

## Teknis - Packages/Dependencies

Proyek ini di-bootstrap dengan [Create React App](https://github.com/facebook/create-react-app), menggunakan [Redux](https://redux.js.org/) dan [Redux Toolkit](https://redux-toolkit.js.org/) template dengan TypeScript.

- **Styling & UI Library** Menggunakan [Material UI](https://material-ui.com/). Perhatikan bahwa untuk menggunakan [styles API](https://material-ui.com/styles/basics/) anda dapat `import @material-ui/core/styles`.
- **Routing** Menggunakan [React Router](https://reacttraining.com/react-router/web/guides/quick-start).
- **Mapping** Menggunakan [MapBox](https://docs.mapbox.com/mapbox.js/api/v3.2.1/). Untuk menggunakan aplikasi ini, Anda perlu membuat token dan menambahkannya sebagai `REACT_APP_MAPBOX_TOKEN` di sebuah file `.env` pada folder root.
- **Monitoring** Menggunakan [Sentry.io](https://sentry.io). Untuk mengirim info pemantauan ke Sentry, cukup atur url `Sentry` dengan menambahkan sebagai `REACT_SENTRY_URL` dalam sebuah file `.env` pada folder root.
- **State Management** Menggunakan [Redux](https://redux.js.org/introduction/getting-started)
- **Testing** Menggunakan [Jest](https://jestjs.io/) dengan [Enzyme](https://enzymejs.github.io/enzyme/)

### Skrip yang tersedia

Di direktori proyek, Anda dapat menjalankan:

#### `yarn start`

Menjalankan aplikasi dalam mode pengembangan.<br />
Buka [http://localhost:3000](http://localhost:3000) untuk menampilkan di browser.

Halaman akan dimuat ulang jika Anda melakukan pengeditan.<br />
Anda juga akan melihat lint error di konsol.
#### `yarn test`

Meluncurkan test runner dalam mode interactive watch mode.<br />
Lihat bagian tentang [menjalankan pengujian](https://facebook.github.io/create-react-app/docs/running-tests) untuk informasi selengkapnya.
#### `yarn build`

Membangun aplikasi untuk produksi ke folder `build`.<br />
Ini menggabungkan React dengan benar dalam mode produksi dan mengoptimalkan build untuk performa terbaik.

Build diperkecil dan nama file menyertakan hash.<br />
Aplikasi Anda siap di-deploy!

Lihat bagian tentang [deployment](https://facebook.github.io/create-react-app/docs/deployment) untuk informasi lebih lanjut.

#### `yarn lint`

Menjalankan `eslint` untuk semua file sumber. Kami menggunakan konfigurasi Eslint khusus di `./eslintrc` bersama dengan [`prettier`](https://prettier.io/) (dikonfigurasi dengan `./.prettierrc`) untuk menegakkan konsistensi dan kualitas kode. Jika Anda ingin eslint mencoba "memperbaiki" file secara otomatis jika bisa, jalankan `yarn lint --fix`.

### Committing Code

Secara default, hook pra-komit didefinisikan untuk menjalankan tugas linting pada semua kode _staged_ sebelum mengizinkan komit. Ini terjadi menggunakan paket [lint-staged](https://github.com/okonet/lint-staged), dan dapat dikonfigurasi di `./package.json#lint-staged`. Tugas precommit dapat dijalankan secara manual menggunakan `yarn precommit`.
