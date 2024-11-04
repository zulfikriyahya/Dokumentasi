Untuk menginstal CUPS (Common Unix Printing System) di Debian 12, Anda dapat mengikuti langkah-langkah berikut:

### Langkah 1: Update Sistem

Pertama, pastikan sistem Anda diperbarui. Buka terminal dan jalankan perintah berikut:

```bash
sudo apt update
sudo apt upgrade
```

### Langkah 2: Instal CUPS

Setelah sistem diperbarui, Anda dapat menginstal CUPS dengan menjalankan perintah berikut:

```bash
sudo apt install cups
```

### Langkah 3: Mulai dan Aktifkan Layanan CUPS

Setelah instalasi selesai, Anda perlu memulai layanan CUPS dan memastikan bahwa layanan ini otomatis berjalan saat booting. Jalankan perintah berikut:

```bash
sudo systemctl start cups
sudo systemctl enable cups
```

### Langkah 4: Konfigurasi Firewall (Jika Diperlukan)

Jika Anda menggunakan firewall (seperti `ufw`), pastikan untuk membuka port yang digunakan oleh CUPS. Jalankan perintah berikut:

```bash
sudo ufw allow 631
```

### Langkah 5: Akses Antarmuka Web CUPS

CUPS menyediakan antarmuka web untuk konfigurasi. Anda dapat mengaksesnya dengan membuka browser dan mengetikkan alamat berikut:

```
http://localhost:631
```

### Langkah 6: Tambahkan Printer

Setelah mengakses antarmuka web, Anda dapat menambahkan printer dengan mengikuti langkah-langkah yang tersedia di dalam antarmuka.

1. Klik pada tab **Administration**.
2. Pilih **Add Printer**.
3. Ikuti petunjuk untuk memilih dan mengkonfigurasi printer Anda.

### Langkah 7: Uji Printer

Setelah printer ditambahkan, Anda dapat mencetak halaman uji untuk memastikan semuanya berfungsi dengan baik.

1. Klik pada printer yang telah Anda tambahkan di antarmuka web CUPS.
2. Pilih opsi **Print Test Page**.

### Selesai

Sekarang Anda telah berhasil menginstal dan mengkonfigurasi CUPS di Debian 12. Jika Anda mengalami masalah, pastikan untuk memeriksa log CUPS untuk mendapatkan informasi lebih lanjut.

Selamat mencoba! Jika ada yang ingin ditanyakan lebih lanjut, silakan beri tahu.
