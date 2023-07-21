# BAB 2
# PERSIAPAN LINGKUNGAN PENGEMBANGAN
## 2.1 Instalasi Golang
### 2.1.1 Instalasi Golang di Windows
Golang adalah bahasa pemrograman yang kuat dan efisien untuk pengembangan aplikasi. Untuk memulai pengembangan dengan Golang di sistem operasi Windows, Anda perlu mengikuti langkah-langkah instalasi yang tertera di bawah ini:
1. Kunjungi situs resmi Golang di https://golang.org/dl/.
2. Di halaman unduhan, Anda akan melihat daftar paket instalasi yang tersedia. Pilih paket instalasi yang sesuai dengan arsitektur komputer Anda (32-bit atau 64-bit).
   
 ![1](https://github.com/juliardimegah/Aplikasi-CRUD-dengan-Golang-MySQL-dan-HMTL-Memahami-Konsep-dan-Implementasi-Praktis/assets/98504755/9d0cc8db-a2c8-4252-992d-b247088d2f99)
Gambar 2.1 Halaman Download Golang dengan Versi 1.19.1

Jika Anda tidak yakin dengan arsitektur komputer Anda, Anda dapat memeriksa informasi tersebut dengan mengklik kanan pada "Computer" atau "My Computer" di desktop Anda, memilih "Properties", dan mencari informasi arsitektur sistem.
3. Setelah memilih paket instalasi yang tepat (dalam pengembangan aplikasi CRUD yang dibahas dalam buku ini, versi yang digunakan adalah 1.19), unduh file installer dengan mengklik tautan yang sesuai.

 ![image](https://github.com/juliardimegah/Aplikasi-CRUD-dengan-Golang-MySQL-dan-HMTL-Memahami-Konsep-dan-Implementasi-Praktis/assets/98504755/ffb798f2-337e-4b14-ac1a-97e94fe1ae8a)
Gambar 2.2 Download Golang 1.19.1

4. Setelah file installer Golang berhasil diunduh, buka file tersebut untuk memulai proses instalasi.

![image](https://github.com/juliardimegah/Aplikasi-CRUD-dengan-Golang-MySQL-dan-HMTL-Memahami-Konsep-dan-Implementasi-Praktis/assets/98504755/934ff426-5f1c-4e72-b68e-daa970ae905a)
Gambar 2.3 Tampilan Instalasi Golang

5. Anda akan disambut dengan jendela instalasi Golang. Ikuti petunjuk instalasi yang muncul di layar.
6. Pilih direktori instalasi Golang. Secara default, direktori instalasi yang disarankan adalah "C:\Go\". Anda dapat memilih direktori lain jika diinginkan.
7. Pada halaman instalasi, pastikan opsi "Add Go to PATH" diaktifkan. Opsi ini akan menambahkan Golang ke PATH sistem, sehingga Anda dapat mengakses perintah Go dari Command Prompt atau PowerShell secara langsung.
8. Klik tombol "Install" atau "Next" untuk memulai instalasi.
9. Tunggu hingga proses instalasi selesai. Setelah selesai, Anda akan melihat pesan bahwa instalasi Golang berhasil.

 ![image](https://github.com/juliardimegah/Aplikasi-CRUD-dengan-Golang-MySQL-dan-HMTL-Memahami-Konsep-dan-Implementasi-Praktis/assets/98504755/58269344-81fa-49fa-8bb4-775cc6c8c48e)
Gambar 2.4 Tampilan saat instalasi Golang

10. Untuk memastikan instalasi berhasil, buka Command Prompt atau PowerShell dan ketik perintah `go version`. Jika instalasi sukses, Anda akan melihat versi Golang yang terpasang.

 ![image](https://github.com/juliardimegah/Aplikasi-CRUD-dengan-Golang-MySQL-dan-HMTL-Memahami-Konsep-dan-Implementasi-Praktis/assets/98504755/cbea0c88-6594-4109-ae61-f07e1f760bca)
Gambar 2.5 Tampilan setelah perintah go version dijalankan

### 2.1.2 Instalasi Golang di macOS
Untuk memulai pengembangan dengan Golang di sistem operasi macOS, Anda perlu mengikuti langkah-langkah instalasi yang tertera di bawah ini:
Tentu! Berikut adalah tutorial langkah demi langkah untuk menginstal dan menggunakan Go (Golang) di macOS:
1. Buka browser web dan kunjungi situs resmi Go di https://golang.org/dl/.
   
  ![image](https://github.com/juliardimegah/Aplikasi-CRUD-dengan-Golang-MySQL-dan-HMTL-Memahami-Konsep-dan-Implementasi-Praktis/assets/98504755/ffb798f2-337e-4b14-ac1a-97e94fe1ae8a)
  
Gambar 2.6 Halaman download Golang
2. Unduh paket instalasi sesuai dengan arsitektur macOS yang Anda gunakan (misalnya, macOS 64-bit).
3. Tunggu hingga unduhan selesai.
4. Setelah unduhan selesai, buka berkas `.pkg` yang telah Anda unduh.
5. Ikuti wizard instalasi yang muncul.
6. Pilih lokasi instalasi yang sesuai. Secara default, Go akan diinstal di `/usr/local/go`.
7. Lanjutkan dengan instalasi dan tunggu hingga selesai.
8. Setelah instalasi selesai, jendela terminal baru perlu dibuka agar perubahan konfigurasi berlaku.

### 2.1.3 Instalasi Golang di Linux
1. Buka browser web dan kunjungi situs resmi Go di https://golang.org/dl/.
 ![image](https://github.com/juliardimegah/Aplikasi-CRUD-dengan-Golang-MySQL-dan-HMTL-Memahami-Konsep-dan-Implementasi-Praktis/assets/98504755/ffb798f2-337e-4b14-ac1a-97e94fe1ae8a)
Gambar 2.7 Halaman Download Golang

2. Unduh paket instalasi sesuai dengan arsitektur Linux yang Anda gunakan (misalnya, Linux 64-bit). Tunggu hingga unduhan selesai.
3. Buka terminal Linux.
4. Ekstrak paket instalasi yang telah Anda unduh dengan perintah berikut (gantikan `nama_file.tar.gz` dengan nama file yang sesuai):
 ``` tar -C /usr/local -xzf nama_file.tar.gz ```

4. Setelah ekstraksi selesai, atur variabel lingkungan `GOROOT` dengan perintah berikut:
 ``` export GOROOT=/usr/local/go ```

5. Tambahkan direktori `bin` Go ke variabel lingkungan `PATH`:
 ```export PATH=$PATH:$GOROOT/bin ```

6. Agar perubahan ini berlaku secara permanen, tambahkan perintah yang sama ke berkas profil shell yang sesuai (misalnya, `~/.bashrc` atau `~/.bash_profile`).
7. Verifikasi instalasi Go dengan menjalankan perintah `go version`. Jika versi Go muncul, instalasi telah berhasil.

Setelah mengikuti langkah-langkah di atas, Anda telah berhasil menginstal Golang di perangkat Anda. Anda siap untuk melangkah ke langkah berikutnya dalam persiapan lingkungan pengembangan. Pastikan untuk memperbarui Golang secara teratur dengan mengunjungi situs resmi Golang untuk mendapatkan versi terbaru dan pembaruan yang diperlukan.

## 2.2 Konfigurasi Database MySQL
### 2.1.1. Konfigurasi Database MySQL di Windows dengan XAMPP
XAMPP adalah paket pengembangan yang populer digunakan untuk membuat lingkungan pengembangan web di sistem operasi Windows. Untuk mengkonfigurasi database MySQL menggunakan XAMPP, ikuti langkah-langkah berikut:
1. Pastikan Anda telah mengunduh dan menginstal XAMPP dari situs resmi XAMPP (https://www.apachefriends.org/index.html) sesuai dengan versi sistem operasi Windows Anda.
 
 ![image](https://github.com/juliardimegah/Aplikasi-CRUD-dengan-Golang-MySQL-dan-HMTL-Memahami-Konsep-dan-Implementasi-Praktis/assets/98504755/ffb798f2-337e-4b14-ac1a-97e94fe1ae8a)
 
Gambar 2.8 Halaman Download XAMPP
2. Setelah menginstal XAMPP, buka XAMPP Control Panel. Anda dapat melakukannya dengan menavigasi ke direktori instalasi XAMPP (biasanya di `C:\xampp`) dan menjalankan file `xampp-control.exe`.
3. Pada XAMPP Control Panel, Anda akan melihat daftar modul yang tersedia. Pastikan modul MySQL diaktifkan dengan mengklik tombol "Start" di sampingnya. Ini akan menjalankan server MySQL.
4. Setelah server MySQL berjalan, klik tombol "Admin" di sebelah modul MySQL untuk membuka phpMyAdmin di browser Anda. PhpMyAdmin adalah alat administrasi database MySQL yang akan membantu kita mengelola basis data.
5. Di phpMyAdmin, buat basis data baru untuk aplikasi CRUD Anda. Klik tombol "New" di bagian kiri, masukkan nama basis data yang diinginkan, dan pilih kolasi (collation) yang sesuai. Misalnya, Anda dapat memberi nama basis data "aplikasi_crud" dan pilih kolasi "utf8_general_ci".
6. Setelah membuat basis data, Anda dapat membuat tabel dan mengelola skema basis data sesuai kebutuhan aplikasi CRUD Anda menggunakan antarmuka phpMyAdmin yang intuitif.
7. Pastikan Anda mencatat nama basis data, nama tabel, dan struktur kolom yang akan digunakan dalam aplikasi CRUD Anda. Informasi ini akan diperlukan dalam pengembangan selanjutnya.

### 2.1.2. Konfigurasi Database MySQL di macOS dengan XAMPP
XAMPP adalah paket pengembangan yang populer digunakan untuk membuat lingkungan pengembangan web di berbagai sistem operasi, termasuk macOS. Untuk mengkonfigurasi database MySQL menggunakan XAMPP di macOS, ikuti langkah-langkah berikut:
1. Pastikan Anda telah mengunduh dan menginstal XAMPP dari situs resmi XAMPP (https://www.apachefriends.org/index.html) sesuai dengan versi macOS yang Anda gunakan.
2. Setelah menginstal XAMPP, buka XAMPP Control Panel. Anda dapat menemukannya dalam folder "Applications" atau menggunakan Spotlight dengan menekan tombol Command + Spasi, lalu ketik "XAMPP Control" dan tekan Enter.
3. Pada XAMPP Control Panel, Anda akan melihat daftar modul yang tersedia. Pastikan modul MySQL diaktifkan dengan mengklik tombol "Start" di sebelahnya. Ini akan menjalankan server MySQL.
4. Setelah server MySQL berjalan, Anda dapat membuka phpMyAdmin di browser untuk mengelola basis data. Buka browser dan kunjungi URL http://localhost/phpmyadmin/.
5. Di phpMyAdmin, buat basis data baru untuk aplikasi CRUD Anda. Klik tombol "New" di bagian kiri, masukkan nama basis data yang diinginkan, dan pilih kolasi (collation) yang sesuai. Misalnya, Anda dapat memberi nama basis data "aplikasi_crud" dan pilih kolasi "utf8_general_ci".
6. Setelah membuat basis data, Anda dapat membuat tabel dan mengelola skema basis data sesuai kebutuhan aplikasi CRUD Anda menggunakan antarmuka phpMyAdmin yang intuitif.
7. Pastikan Anda mencatat nama basis data, nama tabel, dan struktur kolom yang akan digunakan dalam aplikasi CRUD Anda. Informasi ini akan diperlukan dalam pengembangan selanjutnya.

### 2.2.3. Konfigurasi Database MySQL di Linux dengan XAMPP
XAMPP adalah paket pengembangan yang populer digunakan untuk membuat lingkungan pengembangan web di sistem operasi Linux. Untuk mengkonfigurasi database MySQL menggunakan XAMPP di Linux, ikuti langkah-langkah berikut:
1. Unduh paket XAMPP terbaru dari situs resmi XAMPP (https://www.apachefriends.org/index.html) sesuai dengan distribusi Linux yang Anda gunakan. Pastikan Anda memilih versi yang sesuai dengan arsitektur CPU Anda (32-bit atau 64-bit).
2. Setelah selesai mengunduh, buka terminal di Linux.
3. Pindah ke direktori tempat Anda menyimpan berkas unduhan XAMPP dengan menggunakan perintah `cd` (misalnya, `cd ~/Downloads` jika Anda menyimpannya di direktori "Downloads").
4. Ekstrak berkas XAMPP dengan perintah berikut:
    ```tar xvfz xampp-linux-x64-<versi>.tar.gz```
6. Gantilah `<versi>` dengan versi yang tepat sesuai dengan berkas yang Anda unduh.
7. Setelah ekstraksi selesai, pindah ke direktori XAMPP yang baru dibuat dengan perintah `cd xampp`.
8. Jalankan installer XAMPP dengan perintah `sudo ./xampp-linux-x64-<versi>-installer.run`. Gantilah `<versi>` dengan versi yang sesuai dengan berkas yang Anda unduh.
9. Ikuti petunjuk di layar untuk menyelesaikan proses instalasi XAMPP. Anda mungkin perlu memasukkan kata sandi superuser (root) Linux Anda.
10. Setelah instalasi selesai, buka terminal dan jalankan XAMPP Control Panel dengan perintah `sudo /opt/lampp/manager-linux-x64.run`.
11. Di XAMPP Control Panel, aktifkan modul MySQL dengan mengklik kotak centang di sebelah "MySQL". Ini akan menjalankan server MySQL.
12. Setelah server MySQL berjalan, Anda dapat membuka phpMyAdmin di browser untuk mengelola basis data. Buka browser dan kunjungi URL http://localhost/phpmyadmin/.
13. Di phpMyAdmin, buat basis data baru untuk aplikasi CRUD Anda. Klik tombol "New" di bagian kiri, masukkan nama basis data yang diinginkan, dan pilih kolasi (collation) yang sesuai. Misalnya, Anda dapat memberi nama basis data "aplikasi_crud" dan pilih kolasi "utf8_general_ci".
14. Setelah membuat basis data, Anda dapat membuat tabel dan mengelola skema basis data sesuai kebutuhan aplikasi CRUD Anda menggunakan antarmuka phpMyAdmin yang intuitif.
15. Pastikan Anda mencatat nama basis data, nama tabel, dan struktur kolom yang akan digunakan dalam aplikasi CRUD Anda. Informasi ini akan diperlukan dalam pengembangan selanjutnya.
Dengan mengikuti langkah-langkah di atas, Anda telah berhasil mengkonfigurasi database pada perangkat Anda menggunakan XAMPP.

## 2.3 Pengaturan Proyek Golang dan Struktur Folder
Setelah Anda berhasil menginstal Golang dan mengkonfigurasi database MySQL, langkah berikutnya adalah mengatur proyek Golang Anda dan membuat struktur folder yang terstruktur. Dalam bagian ini, kita akan membahas langkah-langkah yang perlu diambil untuk mengatur proyek Golang dan struktur folder yang memungkinkan pengembangan aplikasi CRUD yang terorganisir dan mudah dikelola.
Berikut adalah langkah-langkah yang perlu Anda ikuti:
1. Buatlah direktori proyek baru di lokasi yang Anda inginkan di sistem file Anda. Misalnya, Anda dapat membuat direktori "aplikasi-crud" di direktori kerja Anda.
2. Di dalam direktori proyek, buatlah direktori bernama "src". Direktori ini akan berfungsi sebagai direktori utama tempat Anda menyimpan semua file kode Go Anda.
3. Di dalam direktori "src", buatlah direktori dengan nama "controllers". Direktori ini akan berisi file-file yang mengatur logika pengendalian aplikasi.
4. Buatlah direktori lainnya di dalam direktori "src" sesuai dengan kebutuhan aplikasi Anda. Misalnya, Anda dapat membuat direktori "models" untuk menyimpan file-file yang mengatur struktur data dan koneksi ke database.
5. Selanjutnya, buatlah direktori "views" di luar direktori "src". Direktori "views" akan berisi file-file HTML yang digunakan untuk merancang tampilan frontend aplikasi.
6. Di dalam direktori "views", buatlah sub-direktori sesuai dengan kebutuhan aplikasi Anda. Misalnya, Anda dapat membuat sub-direktori "templates" untuk menyimpan file-file template HTML yang akan digunakan dalam aplikasi.

Setelah Anda selesai mengatur struktur folder proyek, proyek Golang Anda akan terlihat seperti ini:
  ``` 
aplikasi-crud/
├── src/
│   ├── controllers/
│   └── models/
└── views/
    └── templates/

```

Dengan struktur folder yang terorganisir, Anda dapat memisahkan kode Golang, file template HTML, dan sumber daya lainnya dengan jelas. Ini akan membantu Anda dalam mengelola proyek dan memudahkan tim pengembangan jika Anda bekerja dalam tim.
Pastikan untuk memberikan nama direktori yang deskriptif sesuai dengan fungsinya agar mudah dipahami dan dikelola oleh Anda dan anggota tim. Selain itu, Anda juga dapat menyesuaikan struktur folder sesuai dengan kebutuhan proyek Anda.
Dengan struktur folder yang teratur, Anda telah menyiapkan proyek Golang Anda untuk pengembangan aplikasi CRUD. Pada tahap selanjutnya, kita akan mulai mengimplementasikan komponen-komponen dasar seperti routing, logika pengendalian, dan interaksi dengan database MySQL.
