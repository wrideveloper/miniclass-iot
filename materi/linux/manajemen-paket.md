# Manajemen Paket Pada Linux

<img src="img/package-management1.png" width="300" />

## 1. Format Paket

Berbeda dengan windows yang menggunakan extensi `.exe`, linux memiliki banyak extensi untuk paketnya, tergantung distro yang digunakan

![Format](img/format-linux.png)

## 2. Software Repository

Dalam linux, kita akan mengenal istilah **software repository**, dimana semua software yang kita butuhkan terdapat pada sebuah server, sehingga apabila kita membutuhkan aplikasi, kita cukup mencarinya di dalam repository tersebut, aplikasi yang terdapat pada server tersebut sudah diuji keamanannya dari bug dan virus, sehingga lebih aman daripada kita menginstall aplikasi bebas dari internet yang rawan terdapat virus.

**Untuk menginstall aplikasi melalui software repository, kita bisa menggunakan tool berikut :**

[`apt`](https://itsfoss.com/apt-command-guide/) - digunakan pada debian / ubuntu

[`yum`](https://www.tecmint.com/20-linux-yum-yellowdog-updater-modified-commands-for-package-mangement/) - digunakan pada redhat / centos

[`dnf`](https://www.tecmint.com/dnf-commands-for-fedora-rpm-package-management/) - digunakan pada fedora

## 3. Manajemen Paket Ubuntu Menggunakan APT

### 3.1 Menginstall paket baru

Gunakan perintah berikut untuk menginstall paket baru

```bash
# perintah
sudo apt install [nama-paket]

# contoh : menginstall git
sudo apt install git
```

### 3.2 Meguninstall paket

Gunakan perintah berikut untuk menguninstall paket

```bash
# perintah
sudo apt remove [nama-paket]

# contoh : menguninstall git
sudo apt remove git
```

### 3.3 Memeriksa update

Gunakan perintah berikut untuk memeriksa apakah ada update pada paket yang sudah kita install atau tidak

```bash
sudo apt update
```

### 3.4 Menginstall update

Gunakan perintah berikut untuk menginstall update apabila memang ada update pada paket yang sudah kita install

```bash
sudo apt upgrade
```
