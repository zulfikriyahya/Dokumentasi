Untuk menginstal VirtualBox di Debian 12, Anda dapat mengikuti langkah-langkah berikut:

### Langkah 1: Perbarui Sistem

Sebelum menginstal VirtualBox, disarankan untuk memperbarui sistem Anda. Buka terminal dan jalankan perintah berikut:

```bash
sudo apt update
sudo apt upgrade
```

### Langkah 2: Tambahkan Repository VirtualBox

Debian tidak menyertakan VirtualBox di repositori standar. Anda perlu menambahkan repositori resmi dari Oracle. Pertama, instal paket yang diperlukan untuk menambahkan repositori:

```bash
sudo apt install -y software-properties-common
```

Kemudian, tambahkan repository VirtualBox:

```bash
echo "deb [arch=amd64] https://www.virtualbox.org/download/debian bullseye contrib" | sudo tee /etc/apt/sources.list.d/virtualbox.list
```

### Langkah 3: Tambahkan Kunci GPG Oracle

Setelah menambahkan repositori, Anda perlu mengimpor kunci GPG untuk verifikasi paket:

```bash
wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
```

### Langkah 4: Perbarui Daftar Paket

Setelah menambahkan repositori dan kunci GPG, perbarui daftar paket lagi:

```bash
sudo apt update
```

### Langkah 5: Instal VirtualBox

Sekarang, Anda bisa menginstal VirtualBox. Untuk menginstal versi terbaru, gunakan perintah berikut:

```bash
sudo apt install virtualbox-6.1
```

### Langkah 6: Instal VirtualBox Extension Pack (Opsional)

Jika Anda memerlukan fitur tambahan, seperti dukungan USB 2.0 dan 3.0, Anda bisa menginstal Extension Pack. Pertama, unduh Extension Pack dari situs resmi:

```bash
wget https://download.virtualbox.org/virtualbox/6.1.34/Oracle_VM_VirtualBox_Extension_Pack-6.1.34.vbox-extpack
```

Setelah mengunduh, instal Extension Pack dengan perintah:

```bash
sudo VBoxManage extpack install Oracle_VM_VirtualBox_Extension_Pack-6.1.34.vbox-extpack
```

### Langkah 7: Jalankan VirtualBox

Setelah instalasi selesai, Anda dapat menjalankan VirtualBox dari menu aplikasi atau dengan menjalankan perintah berikut di terminal:

```bash
virtualbox
```

### Catatan

- Pastikan Anda menjalankan versi Debian 12 (Bullseye) untuk mengikuti langkah-langkah ini.
- Jika Anda mengalami masalah dengan instalasi, periksa dokumentasi resmi VirtualBox atau forum komunitas Debian untuk mendapatkan bantuan lebih lanjut.

Sekarang Anda sudah siap menggunakan VirtualBox di Debian 12!
