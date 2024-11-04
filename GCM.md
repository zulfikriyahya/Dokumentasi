Berikut adalah langkah-langkah untuk menginstal dan mengonfigurasi Git di Debian 12:

### Install Git

```bash
sudo apt install git -y
```

### Install GCM

```bash
wget https://github.com/git-ecosystem/git-credential-manager/releases/download/v2.6.0/gcm-linux_amd64.2.6.0.deb
```

```bash
sudo dpkg -i gcm-linux_amd64.2.6.0.deb
git-credential-manager configure
```

### Uninstall GCM

```bash
git-credential-manager unconfigure
sudo dpkg -r gcm
```

### Setup Git

```bash
git init
git add .
git commit -m "Init"
git branch -M main
git remote add origin https://github.com/<username>/<repository>.git
git push -u origin main
git config --global credential.credentialStore gpg
```
