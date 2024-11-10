# Daftar Perintah systemctl

`systemctl` adalah utilitas baris perintah yang digunakan untuk mengontrol sistem dan layanan manajemen systemd. Berikut adalah beberapa perintah umum yang sering digunakan:

## Perintah untuk Mengelola Layanan

- **`systemctl start [nama-layanan]`**
  Memulai layanan yang ditentukan.
  ```sh
  sudo systemctl start nginx
  ```

- **`systemctl stop [nama-layanan]`**
  Menghentikan layanan yang ditentukan.

  ```sh
  sudo systemctl stop nginx
  ```

- **`systemctl restart [nama-layanan]`**
  Menghentikan dan memulai kembali layanan yang ditentukan.

  ```sh
  sudo systemctl restart nginx
  ```

- **`systemctl reload [nama-layanan]`**
  Memuat ulang konfigurasi layanan tanpa menghentikan layanan.

  ```sh
  sudo systemctl reload nginx
  ```

- **`systemctl enable [nama-layanan]`**
  Mengaktifkan layanan untuk memulai secara otomatis saat booting.

  ```sh
  sudo systemctl enable nginx
  ```

- **`systemctl disable [nama-layanan]`**
  Menonaktifkan layanan agar tidak memulai secara otomatis saat booting.

  ```sh
  sudo systemctl disable nginx
  ```

- **`systemctl status [nama-layanan]`**
  Menampilkan status saat ini dari layanan yang ditentukan.
  ```sh
  sudo systemctl status nginx
  ```

## Perintah untuk Mengelola Sistem

- **`systemctl reboot`**
  Merestart sistem.

  ```sh
  sudo systemctl reboot
  ```

- **`systemctl poweroff`**
  Mematikan sistem.

  ```sh
  sudo systemctl poweroff
  ```

- **`systemctl suspend`**
  Menangguhkan sistem ke mode tidur.

  ```sh
  sudo systemctl suspend
  ```

- **`systemctl hibernate`**
  Menghibernasi sistem.

  ```sh
  sudo systemctl hibernate
  ```

- **`systemctl hybrid-sleep`**
  Kombinasi dari suspend dan hibernate.
  ```sh
  sudo systemctl hybrid-sleep
  ```

## Perintah untuk Mengelola Unit

- **`systemctl list-units`**
  Menampilkan semua unit yang diaktifkan.

  ```sh
  systemctl list-units
  ```

- **`systemctl list-unit-files`**
  Menampilkan semua file unit yang tersedia.

  ```sh
  systemctl list-unit-files
  ```

- **`systemctl daemon-reload`**
  Memuat ulang file unit systemd setelah membuat perubahan konfigurasi.
  ```sh
  sudo systemctl daemon-reload
  ```

## Perintah untuk Log dan Debugging

- **`systemctl is-active [nama-layanan]`**
  Mengecek apakah layanan sedang aktif.

  ```sh
  systemctl is-active nginx
  ```

- **`systemctl is-enabled [nama-layanan]`**
  Mengecek apakah layanan diatur untuk memulai secara otomatis saat booting.

  ```sh
  systemctl is-enabled nginx
  ```

- **`journalctl -u [nama-layanan]`**
  Menampilkan log dari layanan yang ditentukan.
  ```sh
  journalctl -u nginx
  ```

Daftar ini mencakup beberapa perintah dasar `systemctl` yang sering digunakan. Setiap perintah dapat digunakan untuk berbagai keperluan dalam mengelola layanan dan sistem pada distribusi Linux yang menggunakan systemd.
