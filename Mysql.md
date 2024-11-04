Untuk menginstal MySQL Server di Debian 12, ikuti langkah-langkah berikut:

### Langkah 1: Perbarui Daftar Paket

Sebelum menginstal MySQL, perbarui daftar paket dengan menjalankan perintah berikut di terminal:

```bash
sudo apt update
```

### Langkah 2: Instal MySQL Server

Setelah daftar paket diperbarui, instal MySQL Server dengan perintah berikut:

```bash
sudo apt install mysql-server
```

### Langkah 3: Amankan Instalasi MySQL

Setelah instalasi selesai, jalankan skrip keamanan untuk mengamankan instalasi MySQL:

```bash
sudo mysql_secure_installation
```

Skrip ini akan meminta beberapa konfigurasi, seperti:

- Menetapkan kata sandi untuk akun root MySQL
- Menghapus pengguna anonim
- Menonaktifkan login root jarak jauh
- Menghapus database pengujian
- Memperbarui tabel hak akses

Ikuti petunjuk sesuai keinginan Anda.

### Langkah 4: Mulai dan Aktifkan Layanan MySQL

Pastikan layanan MySQL berjalan dan aktif secara otomatis saat boot:

```bash
sudo systemctl start mysql
sudo systemctl enable mysql
```

### Langkah 5: Verifikasi Instalasi

Untuk memverifikasi bahwa MySQL terinstal dan berjalan dengan baik, gunakan perintah:

```bash
sudo systemctl status mysql
```

Jika semuanya berjalan dengan baik, Anda seharusnya melihat status "active (running)".

### Langkah 6: Masuk ke MySQL

Anda dapat masuk ke konsol MySQL dengan perintah berikut:

```bash
sudo mysql -u root -p
```

Masukkan kata sandi yang telah Anda tetapkan sebelumnya.

### Langkah 7: Konfigurasi Tambahan (Opsional)

Setelah berhasil masuk, Anda dapat membuat pengguna baru, mengatur hak akses, dan melakukan konfigurasi tambahan sesuai kebutuhan.

Dengan mengikuti langkah-langkah di atas, Anda seharusnya dapat menginstal dan mengkonfigurasi MySQL Server di Debian 12 dengan sukses.
