Untuk menginstal Nginx di Debian 12, ikuti langkah-langkah berikut:

### 1. Update Sistem

Sebelum menginstal Nginx, pastikan sistem Anda terbaru. Jalankan perintah berikut untuk memperbarui paket-paket di sistem:

```bash
sudo apt update
sudo apt upgrade -y
```

### 2. Instal Nginx

Setelah sistem diperbarui, Anda bisa menginstal Nginx dengan perintah berikut:

```bash
sudo apt install nginx -y
```

### 3. Cek Status Nginx

Setelah instalasi selesai, Anda bisa mengecek status Nginx untuk memastikan bahwa layanan sudah berjalan:

```bash
sudo systemctl status nginx
```

Jika Nginx berjalan, Anda akan melihat status aktif. Anda dapat menekan `q` untuk keluar dari tampilan status.

### 4. Mengaktifkan Nginx di Boot

Agar Nginx otomatis mulai saat booting, jalankan perintah berikut:

```bash
sudo systemctl enable nginx
```

### 5. Konfigurasi Firewall (Opsional)

Jika Anda menggunakan UFW (Uncomplicated Firewall), Anda perlu mengizinkan lalu lintas HTTP dan HTTPS:

```bash
sudo ufw allow 'Nginx Full'
```

### 6. Uji Instalasi

Anda dapat menguji instalasi Nginx dengan membuka browser dan mengetikkan alamat IP server Anda atau `http://localhost` jika Anda mengaksesnya dari server langsung. Anda harus melihat halaman sambutan Nginx.

### 7. Konfigurasi Nginx

File konfigurasi Nginx biasanya terletak di `/etc/nginx/nginx.conf` dan untuk site-specific di `/etc/nginx/sites-available/`. Anda bisa membuat file konfigurasi baru untuk aplikasi Anda di sana.

### 8. Restart Nginx Setelah Mengubah Konfigurasi

Setelah Anda mengubah konfigurasi, restart Nginx agar perubahan berlaku:

```bash
sudo systemctl restart nginx
```

### 9. Cek Log

Jika ada masalah, Anda dapat memeriksa log untuk mencari tahu penyebabnya:

- Log akses: `/var/log/nginx/access.log`
- Log kesalahan: `/var/log/nginx/error.log`

### Kesimpulan

Dengan langkah-langkah di atas, Anda seharusnya telah berhasil menginstal dan mengkonfigurasi Nginx di Debian 12. Anda bisa melanjutkan dengan menyesuaikan konfigurasi sesuai kebutuhan aplikasi yang akan dijalankan.
