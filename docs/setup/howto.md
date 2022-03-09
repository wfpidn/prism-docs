# Cara instalasi PRISM

Repositori untuk mengembangkan aplikasi PRISM tersedia di Github. Ini dibagi menjadi 2 komponen utama:

- **[Backend](/setup/backend)** Ini berisi kode yang mengunduh dan mengekstrak data dari berbagai sumber mentah, melakukan perhitungan, dan menghasilkan produk data. Ini juga berisi pengaturan untuk [Geoserver](http://geoserver.org/) yang menyajikan produk data ke front-end.

- **[Frontend](/setup/frontend)** Ini berisi aplikasi web yang terhubung ke [Geoserver](http://geoserver.org/) dan memungkinkan pengguna untuk melihat dan berinteraksi dengan data yang dihasilkan oleh [backend](/setup/backend).

## Pedoman Pengembangan

Untuk memaksimalkan kualitas kode dan kompatibilitas platform PRISM di berbagai tim dan negara pengembangan, kami telah menetapkan pedoman tentang proses pengkodean & tinjauan kode. Silakan hubungi hello@ovio.org untuk pertanyaan atau masalah apa pun yang terkait dengan proses ini.

### Code style
Jika memungkinkan, ikuti praktik terbaik yang sudah ada untuk style kode dalam bahasa Anda. Untuk Python, ini berarti menggunakan [PEP8](https://www.python.org/dev/peps/pep-0008/). Linting-tools dapat digunakan untuk menerapkan style.

### Struktur Kode

#### Repositori Tunggal
Basis kode PRISM digunakan oleh banyak negara, masing-masing mengonfigurasi platform dan mengembangkan fitur khusus negara. Kode diatur ke dalam satu repositori (repo) yang berisi frontend (atau aplikasi) dan backend (atau runner). Tujuan utama organisasi ini adalah untuk menghindari perubahan yang berbeda dan menyederhanakan penerapan.

#### Master Branch
Komponen dan file dasar akan di-host di cabang `master`. Cabang ini akan menjadi target dari semua pengembangan fitur kecuali fitur khusus negara. Setiap commit yang digabungkan ke `master` harus diuji dengan baik dan siap untuk rilis langsung (dan/atau digabungkan ke cabang negara). Cabang ini akan dilindungi di Github, dan anggota tim tidak akan dapat bergabung tanpa persetujuan & kaitan (1 tinjauan kode yang disetujui + pengujian pada CI). Penggabungan ke `master` akan mengikuti Praktik Terbaik Permintaan Tarik (lihat di bawah).

Kami akan secara berkala menandai “versi yang dirilis” dari kode pada `master` mengikuti [konvensi pembuatan versi semantik](https://www.jvandemo.com/a-simple-guide-to-semantic-versioning/). Versi ini akan menjalani QA menyeluruh dalam lingkungan live-staging dan harus dianggap aman untuk penerapan dan/atau penggabungan ke cabang negara.

### Pull Requests - Best Practices

#### Small and Atomic Pull Requests
Engineer harus menyimpan pull request mereka sebagai PR kecil dan terperinci. PR harus mewakili perubahan Atom dan memiliki **nama yang menjelaskan diri sendiri**. Tidak ada aturan yang spesifik, tetapi umumnya jika pull request melibatkan lebih dari beberapa 100 baris kode yang diubah, itu harus dipisahkan menjadi beberapa PR yang lebih kecil yang masing-masing menangani perubahan independen.

#### Dokumentasi Pull Request
Untuk membantu peninjau memahami perubahan yang dibuat dan melakukan pekerjaan yang lebih baik dengan meninjau kode secara efisien, PR harus memiliki dokumentasi yang jelas. Ini harus mencakup deskripsi singkat tentang perubahan yang dibuat pada tingkat tinggi, tangkapan layar antarmuka baru (untuk perubahan yang dihadapi pengguna), serta pertanyaan, masalah, atau area tertentu yang secara khusus memerlukan pengujian. Jika PR terkait dengan Masalah spesifik yang didokumentasikan di Github, PR tersebut harus merujuk masalah tersebut dalam deskripsi (mis. “Perbaikan #12”).

Peninjau harus memposting pertanyaan dan diskusi tentang perubahan yang diusulkan pada antarmuka Github PR sehingga diskusi & pertimbangan desain dapat dirujuk nanti jika diperlukan.

#### Merge - Squash Commits dan PR Merges
Saat menggabungkan PR, komit harus di-squashed untuk menjaga cabang master tetap bersih (sehingga setiap PR sesuai dengan satu komit dalam riwayat `master`). Sekarang Anda dapat melakukannya secara otomatis saat menggabungkan PR Anda melalui antarmuka web GitHub. Atau Anda dapat menggunakan perintah `git rebase master -i` untuk mengontrol proses. Apa pun itu, satu squashed komit ke `master` harus memiliki deskripsi satu baris yang ringkas (tidak lebih dari 100 karakter) yang berisi referensi (mis. #15) ke nomor PR Github.

#### Satu aturan Approver
Pull Request TIDAK boleh digabungkan ke cabang `country_name-master` atau `master` tanpa disetujui oleh anggota tim lain. Setelah cabang Anda siap, Anda harus membuat PR yang diarahkan ke cabang yang sesuai dan menugaskan seseorang yang mampu meninjau bagian kode ini. Penggabungan PR diblokir di Github kecuali PR menerima setidaknya satu persetujuan dari pengembang.

#### Bacaan
[The anatomy of a perfect pull request](https://medium.com/@hugooodias/the-anatomy-of-a-perfect-pull-request-567382bb6067)


### Tests

#### Menulis Tests yang jelas
Menulis tes yang baik memiliki banyak manfaat. Salah satunya adalah memastikan kode melakukan apa yang seharusnya. Jika ada tes bagus yang lulus, kemungkinan kodenya berfungsi. Namun, ini bukan pengganti untuk menjalankan kode sebelum mengirimkannya ke PR. Menjalankan kode di lingkungan QA dapat mengungkapkan bug yang disebabkan oleh lingkungan yang berbeda, atau sesuatu yang tidak diuji.

#### Tests sebagai Documentasi
Ada alasan besar lain untuk menulis tes: tes berfungsi ganda sebagai dokumentasi. Pengembang berpengalaman akan melihat cerita pengguna dan mulai dengan menulis tes penerimaan untuk itu. Ini adalah alasan lain mengapa cerita pengguna yang baik diperlukan, sehingga pengembang dapat menulis tes yang baik dan akhirnya menarik permintaan yang baik.

Ketika pengembang lain datang untuk meninjau kode yang ditulis seseorang, akan sangat membantu jika mereka dapat melihat tes untuk melihat apa yang dicakup oleh PR ini.