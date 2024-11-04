Berikut adalah langkah-langkah untuk menginstal Nextcloud di Debian 12:

### 1. Persiapan Sistem

Pastikan sistem Anda sudah diperbarui dan semua paket penting sudah terpasang.

```bash
sudo apt update
sudo apt upgrade -y
```

### 2. Instal Apache, MariaDB, dan PHP

Nextcloud membutuhkan web server, database, dan PHP agar dapat berjalan. Untuk itu, kita akan menginstal Apache, MariaDB, dan PHP beserta modul-modul yang diperlukan.

```bash
sudo apt install apache2 mariadb-server libapache2-mod-php php-gd php-mysql php-curl php-mbstring php-intl php-xml php-zip php-apcu php-imagick php-gmp -y
```

### 3. Konfigurasi MariaDB

Selanjutnya, amankan instalasi MariaDB dan buat database untuk Nextcloud.

```bash
sudo mysql_secure_installation
```

Ikuti petunjuk di layar untuk mengamankan instalasi MariaDB (biasanya dengan menekan `Y` pada setiap prompt).

#### Buat Database dan Pengguna untuk Nextcloud

Masuk ke MariaDB dan buat database serta pengguna baru untuk Nextcloud.

```bash
sudo mysql -u root -p
```

Kemudian masukkan perintah berikut di dalam MariaDB prompt:

```sql
CREATE DATABASE nextcloud;
CREATE USER 'nextclouduser'@'localhost' IDENTIFIED BY 'password_kuat';
GRANT ALL PRIVILEGES ON nextcloud.* TO 'nextclouduser'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

Gantilah `password_kuat` dengan kata sandi yang kuat.

### 4. Unduh Nextcloud

Unduh file Nextcloud terbaru dari situs resminya.

```bash
cd /tmp
wget https://download.nextcloud.com/server/releases/nextcloud-30.0.1.zip
```

Ekstrak file ZIP ke direktori root web.

```bash
sudo unzip nextcloud-30.0.1.zip -d /var/www/
```

### 5. Atur Kepemilikan Direktori Nextcloud

Setelah Nextcloud diekstrak, ubah kepemilikan direktori agar Apache memiliki akses penuh.

```bash
sudo chown -R www-data:www-data /var/www/nextcloud/
sudo chmod -R 755 /var/www/nextcloud/
```

### 6. Konfigurasi Virtual Host di Apache

Buat file konfigurasi virtual host untuk Nextcloud.

```bash
sudo nano /etc/apache2/sites-available/nextcloud.conf
```

Tambahkan konfigurasi berikut:

```apache
<VirtualHost *:80>
    ServerAdmin admin@example.com
    DocumentRoot /var/www/nextcloud
    ServerName nextcloud.example.com

    <Directory /var/www/nextcloud/>
        AllowOverride All
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/nextcloud_error.log
    CustomLog ${APACHE_LOG_DIR}/nextcloud_access.log combined
</VirtualHost>
```

Gantilah `nextcloud.example.com` dengan domain atau alamat IP server Anda.

Simpan dan keluar dari editor.

### 7. Aktifkan Konfigurasi Apache dan Modul-Modul yang Diperlukan

Aktifkan situs Nextcloud di Apache serta beberapa modul yang diperlukan.

```bash
sudo a2ensite nextcloud.conf
sudo a2enmod rewrite headers env dir mime setenvif
```

Kemudian restart Apache:

```bash
sudo systemctl restart apache2
```

### 8. Konfigurasi PHP

Edit konfigurasi PHP agar sesuai dengan kebutuhan Nextcloud.

```bash
sudo nano /etc/php/8.3/apache2/php.ini
```

Cari dan sesuaikan nilai berikut:

```ini
memory_limit = 512M
upload_max_filesize = 100M
post_max_size = 100M
max_execution_time = 300
```

Simpan dan keluar, kemudian restart Apache lagi.

```bash
sudo systemctl restart apache2
```

### 9. Selesaikan Instalasi Nextcloud via Browser

Buka browser dan akses `http://nextcloud.example.com` atau `http://[alamat_IP_server]`.

Di sana, Anda akan diminta untuk:

1. Membuat akun admin Nextcloud.
2. Mengisi detail database (`username`, `password`, dan `database name` yang sudah kita buat sebelumnya).
3. Menentukan lokasi data Nextcloud (biarkan default jika tidak diperlukan perubahan).

Setelah selesai, klik **Install**.

### 10. (Opsional) Amankan Nextcloud dengan HTTPS

Disarankan untuk menggunakan HTTPS untuk keamanan tambahan. Anda dapat menginstal Let's Encrypt untuk mendapatkan sertifikat SSL gratis.

```bash
sudo apt install certbot python3-certbot-apache -y
sudo certbot --apache -d nextcloud.example.com
```

Ikuti petunjuk untuk mendapatkan sertifikat SSL.

### Selesai!

Nextcloud Anda sekarang sudah terinstal dan siap digunakan di Debian 12.
