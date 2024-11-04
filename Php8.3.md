Untuk menginstal PHP 8.3 di Debian 12, Anda bisa mengikuti langkah-langkah berikut:

### Langkah 1: Perbarui Daftar Paket

Mulailah dengan memperbarui daftar paket yang tersedia dengan perintah:

```bash
sudo apt update
```

### Langkah 2: Instal Dependensi

Instal beberapa paket yang diperlukan untuk menambah repositori dan mengelola PHP:

```bash
sudo apt install -y software-properties-common
```

### Langkah 3: Tambahkan Repositori Ondřej Surý

Debian tidak menyertakan PHP 8.3 secara default, jadi Anda perlu menambahkan repositori yang dikelola oleh Ondřej Surý:

```bash
sudo add-apt-repository ppa:ondrej/php
```

Setelah itu, perbarui daftar paket lagi:

```bash
sudo apt update
```

### Langkah 4: Instal PHP 8.3

Sekarang Anda dapat menginstal PHP 8.3 dengan perintah berikut:

```bash
sudo apt install -y php8.3
```

### Langkah 5: Instal Ekstensi PHP yang Diperlukan

Bergantung pada aplikasi Anda, Anda mungkin memerlukan beberapa ekstensi PHP. Beberapa ekstensi umum yang mungkin perlu diinstal termasuk:

```bash
sudo apt install -y php8.3-cli php8.3-fpm php8.3-mysql php8.3-xml php8.3-mbstring php8.3-curl php8.3-zip
```

Anda dapat menambahkan ekstensi lain sesuai kebutuhan.

### Langkah 6: Mulai dan Aktifkan PHP-FPM

Jika Anda menggunakan PHP-FPM, pastikan layanan tersebut berjalan:

```bash
sudo systemctl start php8.3-fpm
sudo systemctl enable php8.3-fpm
```

### Langkah 7: Verifikasi Instalasi

Untuk memastikan PHP terinstal dengan benar, jalankan:

```bash
php -v
```

Perintah ini akan menampilkan versi PHP yang terinstal.

### Langkah 8: Konfigurasi Web Server (Opsional)

Jika Anda menggunakan web server seperti Nginx atau Apache, Anda perlu mengonfigurasi server untuk menggunakan PHP 8.3. Pastikan Anda sudah menginstal web server yang diperlukan.

Untuk Nginx, tambahkan konfigurasi untuk memproses file PHP di file konfigurasi server Anda. Untuk Apache, Anda mungkin perlu menginstal modul PHP dan mengaktifkannya.

### Kesimpulan

Dengan mengikuti langkah-langkah di atas, Anda seharusnya dapat menginstal PHP 8.3 di Debian 12 dengan sukses. Pastikan untuk melakukan pengujian untuk memastikan bahwa PHP berfungsi dengan baik dengan aplikasi yang Anda jalankan.
