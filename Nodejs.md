Untuk menginstal Node.js di Debian 12, Anda bisa mengikuti langkah-langkah berikut:

### Langkah 1: Perbarui Daftar Paket

Mulailah dengan memperbarui daftar paket yang tersedia di sistem Anda:

```bash
sudo apt update
```

### Langkah 2: Instal Dependensi

Pastikan Anda menginstal beberapa paket yang diperlukan untuk menambah repositori:

```bash
sudo apt install -y curl
```

### Langkah 3: Tambahkan Repositori NodeSource

Node.js tidak selalu tersedia di repositori default Debian. Anda dapat menambahkan repositori NodeSource untuk mendapatkan versi terbaru. Misalnya, untuk menginstal Node.js versi 22.x (ganti dengan versi yang diinginkan jika perlu):

```bash
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
```

### Langkah 4: Instal Node.js

Setelah repositori ditambahkan, Anda dapat menginstal Node.js dengan perintah:

```bash
sudo apt install -y nodejs
```

### Langkah 5: Verifikasi Instalasi

Setelah instalasi selesai, periksa versi Node.js dan npm (Node Package Manager) untuk memastikan semuanya terinstal dengan benar:

```bash
node -v
npm -v
```

### Langkah 6: Instalasi Paket Tambahan (Opsional)

Jika Anda ingin menggunakan npm untuk mengelola paket, Anda mungkin ingin menginstal paket tambahan yang diperlukan untuk kompilasi. Jalankan:

```bash
sudo apt install -y build-essential
```

### Kesimpulan

Dengan mengikuti langkah-langkah di atas, Anda telah berhasil menginstal Node.js di Debian 12. Node.js memungkinkan Anda untuk menjalankan JavaScript di server, dan npm memungkinkan Anda untuk mengelola paket yang dibutuhkan untuk aplikasi Anda. Selamat mencoba!
