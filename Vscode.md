Untuk menginstal Visual Studio Code (VSCode) di Debian 12, Anda bisa mengikuti langkah-langkah berikut:

### Langkah 1: Perbarui Daftar Paket

Mulailah dengan memperbarui daftar paket sistem Anda:

```bash
sudo apt update
```

### Langkah 2: Instal Dependensi

Pastikan Anda menginstal beberapa paket yang diperlukan sebelum menginstal VSCode:

```bash
sudo apt install -y software-properties-common apt-transport-https wget
```

### Langkah 3: Tambahkan Kunci GPG Microsoft

Anda perlu menambahkan kunci GPG dari Microsoft agar paket dapat diandalkan:

```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
```

### Langkah 4: Tambahkan Repositori VSCode

Tambahkan repositori Microsoft untuk Visual Studio Code:

```bash
echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
```

### Langkah 5: Perbarui Daftar Paket Lagi

Setelah menambahkan repositori, perbarui daftar paket lagi untuk mengakui repositori baru:

```bash
sudo apt update
```

### Langkah 6: Instal Visual Studio Code

Sekarang Anda dapat menginstal Visual Studio Code dengan perintah:

```bash
sudo apt install -y code
```

### Langkah 7: Verifikasi Instalasi

Setelah instalasi selesai, Anda dapat memulai VSCode dengan menjalankan perintah berikut di terminal:

```bash
code
```

Atau, Anda juga dapat mencarinya di menu aplikasi Anda.

### Langkah 8: Instal Ekstensi (Opsional)

Setelah VSCode terinstal, Anda bisa menambahkan ekstensi sesuai kebutuhan melalui Marketplace yang tersedia di dalam aplikasi.

### Kesimpulan

Dengan mengikuti langkah-langkah di atas, Anda telah berhasil menginstal Visual Studio Code di Debian 12. VSCode adalah editor kode sumber yang kuat dan fleksibel, ideal untuk pengembangan berbagai jenis aplikasi. Selamat berkoding!
