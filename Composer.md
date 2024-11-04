Untuk menginstal Composer, manajer paket PHP, di Debian 12, ikuti langkah-langkah berikut:

### Langkah 1: Perbarui Daftar Paket

Pertama, pastikan sistem Anda diperbarui dengan menjalankan perintah berikut:

```bash
sudo apt update
```

### Langkah 2: Instal Dependensi

Composer membutuhkan PHP dan beberapa ekstensi untuk berjalan. Pastikan PHP terinstal. Anda juga mungkin perlu menginstal beberapa ekstensi tambahan:

```bash
sudo apt install php php-cli php-mbstring unzip
```

### Langkah 3: Unduh dan Instal Composer

Sekarang, Anda dapat mengunduh Composer menggunakan perintah berikut:

```bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
```

Verifikasi checksum untuk memastikan file yang diunduh tidak rusak:

```bash
php -r "if (hash_file('sha384', 'composer-setup.php') === 'c9f8f26c85cabc5e2efcd205c8a73edcd69f0b7fbc1544c5450e471f2a6639e3c58200ca1b166b229b5c7cd8ec257ef3') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
```

_Catatan:_ Anda mungkin perlu memperbarui checksum hash jika versi Composer berubah. Anda dapat menemukan hash terbaru di [halaman resmi Composer](https://getcomposer.org/download/).

Setelah diverifikasi, jalankan perintah berikut untuk menginstal Composer secara global:

```bash
php composer-setup.php --install-dir=/usr/local/bin --filename=composer
```

### Langkah 4: Hapus Installer

Setelah instalasi selesai, Anda dapat menghapus file installer yang tidak diperlukan:

```bash
php -r "unlink('composer-setup.php');"
```

### Langkah 5: Verifikasi Instalasi

Untuk memeriksa apakah Composer telah terinstal dengan benar, jalankan:

```bash
composer --version
```

Perintah ini akan menampilkan versi Composer yang terinstal.

### Langkah 6: Menggunakan Composer

Sekarang Composer sudah siap digunakan. Anda dapat mulai menggunakan perintah Composer untuk mengelola dependensi dalam proyek PHP Anda. Misalnya, untuk membuat file `composer.json`, Anda dapat menggunakan:

```bash
composer init
```

### Kesimpulan

Dengan mengikuti langkah-langkah di atas, Anda telah berhasil menginstal Composer di Debian 12. Composer adalah alat yang sangat berguna untuk mengelola dependensi dalam proyek PHP, sehingga memudahkan pengembangan aplikasi Anda.
