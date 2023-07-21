# BAB 1
# PENGENALAN CRUD DAN KONSEP DASAR

## 1.1 Pengertian CRUD
Dalam pengembangan aplikasi web, CRUD (Create, Read, Update, Delete) adalah salah satu konsep fundamental yang digunakan untuk mengelola data. Konsep ini mengacu pada empat operasi dasar yang sering diperlukan dalam interaksi dengan basis data: membuat (create), membaca (read), mengubah (update), dan menghapus (delete) data.
### 1.1.1 Membuat (Create)
Operasi membuat (create) berfungsi untuk memasukkan data baru ke dalam database. Contohnya, ketika pengguna mengisi formulir pendaftaran, data yang diisi akan disimpan ke dalam basis data sebagai entitas baru. Operasi ini melibatkan pengambilan data dari pengguna melalui antarmuka pengguna (user interface) dan penambahan data tersebut ke dalam tabel yang sesuai di basis data.
### 1.1.2 Membaca (Read)
Operasi membaca (read) dilakukan untuk mengambil data yang sudah ada dari basis data dan menampilkannya kepada pengguna. Ketika pengguna mengakses halaman atau mengajukan permintaan tertentu, aplikasi akan mengambil data yang relevan dari basis data dan menampilkannya di antarmuka pengguna. Operasi ini penting untuk memberikan informasi yang dibutuhkan oleh pengguna, seperti menampilkan daftar pengguna yang terdaftar.
### 1.1.3 Mengubah (Update)
Operasi mengubah (update) berfungsi untuk memperbarui data yang ada di database. Ketika pengguna ingin mengubah informasi yang sudah mereka masukkan sebelumnya, aplikasi akan melakukan operasi pengubahan data di basis data sesuai dengan permintaan pengguna. Misalnya, ketika pengguna mengklik tombol "Ubah Profil" dan memperbarui alamat email mereka, data tersebut akan diubah di basis data.
### 1.1.4 Menghapus (Delete)
Operasi menghapus (delete) berfungsi untuk menghapus data terpilih yang ada di basis data. Misalnya, ketika pengguna memutuskan untuk menghapus kiriman blog yang sudah tidak relevan, aplikasi akan melakukan operasi penghapusan data di basis data sesuai dengan permintaan pengguna. Operasi ini penting untuk mengelola data yang tidak diperlukan lagi atau data yang ingin dihapus dari sistem.

## 1.2 Komponen Utama: Golang, MySQL, dan HTML
Dalam membangun aplikasi CRUD, kita akan menggunakan tiga komponen utama yang saling berinteraksi secara sinergis: Golang sebagai bahasa pemrograman backend, MySQL sebagai sistem manajemen basis data, dan HTML sebagai bahasa markup untuk frontend. Mari kita bahas masing-masing komponen ini secara detail:
### 1.2.1 Golang (Backend)
Golang, atau yang dikenal juga sebagai Go, adalah bahasa pemrograman yang dibangun oleh Google. Golang memiliki fitur-fitur yang memungkinkan kita untuk membangun aplikasi backend yang efisien, tangguh, dan mudah di-maintain. Beberapa keunggulan Golang adalah pemrosesan konkuren yang ringan (goroutine), pengelolaan memori yang efisien, dan pengembangan yang cepat.
Dalam konteks aplikasi CRUD, Golang berperan sebagai backend yang akan menangani permintaan dari frontend dan melakukan operasi CRUD terhadap basis data. Kita akan menggunakan Golang untuk membuat server HTTP, mengelola routing, menghubungkan ke basis data MySQL, serta menangani validasi dan pemrosesan data.
### 1.2.2 MySQL (Basis Data)
MySQL adalah salah satu sistem manajemen basis data relasional (RDBMS) yang paling sering digunakan dalam pengembangan aplikasi web. MySQL menyediakan cara yang efisien untuk menyimpan dan mengelola data dalam bentuk tabel terstruktur. Dengan MySQL, kita dapat membuat, mengubah, dan menghapus data dengan mudah menggunakan bahasa SQL (Structured Query Language).
Dalam aplikasi CRUD, MySQL akan menjadi penyimpanan data yang digunakan oleh aplikasi. Kita akan menggunakan MySQL untuk membuat tabel dan skema yang sesuai dengan kebutuhan aplikasi, serta melakukan operasi CRUD seperti menyimpan data baru, mengambil data yang sudah ada, mengubah data, dan menghapus data.
### 1.2.3 HTML (Frontend)
HTML (Hypertext Markup Language) adalah bahasa markup yang sering digunakan untuk menyusun struktur dan tampilan halaman web. HTML digunakan untuk mendefinisikan elemen-elemen pada halaman web seperti teks, gambar, tabel, formulir, dan lain-lain. Dengan HTML, kita dapat membuat antarmuka pengguna yang interaktif dan responsif.
Dalam konteks aplikasi CRUD, HTML akan digunakan untuk membuat tampilan frontend yang akan diakses oleh pengguna. Kita akan menggunakan HTML untuk membuat formulir pengisian data, menampilkan data dalam tabel, dan memberikan antarmuka pengguna yang intuitif dan mudah digunakan.
Melalui kombinasi Golang sebagai backend, MySQL sebagai basis data, dan HTML sebagai frontend, kita dapat membangun aplikasi CRUD yang tangguh, efisien, dan mudah dikembangkan. Kombinasi ini memungkinkan kita untuk memisahkan logika bisnis dari tampilan, membuat basis data yang terstruktur, dan memberikan pengalaman pengguna yang baik.

## 1.3 Alur Kerja Aplikasi CRUD
Dalam membangun aplikasi CRUD dengan Golang, MySQL, dan HTML, terdapat alur kerja yang harus kita pahami. Pada bagian ini, kita akan membahas alur kerja aplikasi CRUD secara detail. Alur kerja ini menggambarkan bagaimana komponen-komponen aplikasi berinteraksi satu sama lain untuk melaksanakan operasi CRUD. Berikut adalah alur kerja aplikasi CRUD yang umum digunakan:
### 1.3.1 Permintaan dari Pengguna
Alur kerja aplikasi CRUD dimulai dengan permintaan dari pengguna. Pengguna berinteraksi dengan antarmuka pengguna (frontend) yang telah kita buat menggunakan HTML. Permintaan ini dapat berupa membuat data baru, membaca data yang ada, mengubah data, atau menghapus data.
### 1.3.2 Pengiriman Permintaan ke Backend
Setelah menerima permintaan dari pengguna, antarmuka pengguna akan mengirimkan permintaan tersebut ke backend menggunakan protokol HTTP. Permintaan ini akan mencakup informasi yang diperlukan, seperti jenis operasi CRUD yang diminta (create, read, update, delete) dan data yang terkait.
### 1.3.3 Routing di Backend
Setelah menerima permintaan, backend akan menggunakan routing untuk menentukan aksi atau fungsi yang akan dipanggil berdasarkan permintaan tersebut. Routing akan memetakan URL yang diterima ke fungsi-fungsi yang sesuai dalam kode backend.
### 1.3.4 Proses Validasi dan Pengolahan Data
Setelah routing dilakukan, backend akan memulai proses validasi dan pengolahan data. Pada tahap ini, backend akan memeriksa data yang diterima dari permintaan pengguna untuk memastikan data tersebut valid dan sesuai dengan aturan yang telah ditetapkan. Proses validasi ini melibatkan pemeriksaan tipe data, keberadaan data yang diperlukan, atau aturan bisnis tertentu.
### 1.3.5 Interaksi dengan Basis Data
Setelah data divalidasi, backend akan berinteraksi dengan basis data MySQL. Interaksi ini meliputi operasi CRUD yang sesuai dengan permintaan pengguna. Misalnya, jika permintaan adalah untuk membuat data baru, backend akan memasukkan data tersebut ke dalam tabel yang sesuai di basis data. Jika permintaan adalah untuk membaca data, backend akan mengambil data tersebut dari basis data dan mengirimkannya kembali ke antarmuka pengguna.
### 1.3.6 Respon ke Antarmuka Pengguna
Setelah proses interaksi dengan basis data selesai, backend akan mengirimkan respon kembali ke antarmuka pengguna. Respon ini akan berisi informasi yang relevan dengan operasi yang telah dilakukan, seperti konfirmasi data berhasil ditambahkan, data yang diambil dari basis data, atau pesan kesalahan jika terjadi kegagalan.
### 1.3.7 Tampilan dan Interaksi di Antarmuka Pengguna
Antarmuka pengguna akan menampilkan respon yang diterima dari backend kepada pengguna. Hal ini dapat berupa menampilkan pesan sukses, menampilkan data yang diambil dari basis data dalam bentuk tabel, atau memperbarui tampilan dengan data yang baru diubah.
Dengan memahami alur kerja aplikasi CRUD yang terdiri dari permintaan dari pengguna, pengiriman permintaan ke backend, routing, validasi dan pengolahan data, interaksi dengan basis data, respon ke antarmuka pengguna, serta tampilan dan interaksi di antarmuka pengguna, kita dapat membangun aplikasi CRUD yang berfungsi dengan baik.

## 1.4 Tools yang Perlu Dipersiapkan
Setelah memahami tentang CRUD, ada baiknya kita mengetahui apa saja tools yang harus dipersiapkan dalam pengembangan aplikasi CRUD yang dijelaskan pada buku ini. Berikut adalah tools yang perlu dipersiapkan.
### 1.4.1 Instalasi Golang
Untuk mengembangkan aplikasi menggunakan Golang, Anda perlu menginstal Golang pada sistem Anda. Buku ini akan menjelaskan langkah-langkah instalasi Golang dengan jelas, termasuk pengaturan variabel lingkungan (environment variable) yang diperlukan agar Golang dapat berjalan dengan baik di komputer Anda.
### 1.4.2 Konfigurasi Database MySQL
MySQL adalah salah satu sistem manajemen basis data (DBMS) yang populer dan sering digunakan dalam pengembangan aplikasi. Buku ini akan memberikan panduan langkah demi langkah tentang bagaimana menginstal MySQL dan melakukan konfigurasi awal, termasuk pembuatan database, tabel, dan pengaturan hak akses pengguna.
### 1.4.3 Pengaturan Proyek Golang dan Struktur Folder
Sebelum mulai mengembangkan aplikasi CRUD, penting untuk memiliki struktur folder yang terorganisir dengan baik untuk proyek Anda. Buku ini akan menjelaskan cara mengatur proyek Golang dan membuat struktur folder yang sesuai untuk memudahkan pengembangan dan pemeliharaan kode Anda.
Selain persiapan teknis di atas, juga penting untuk memiliki pemahaman dasar tentang bahasa pemrograman Golang, HTML, dan pemrograman web secara umum. 
