# Pembuatan Server SSH VNC FTP

<img src="img/server.png" height="200">

## Server SSH

SSH (Secure Shell) merupakan protokol yang digunakan untuk mengakses terminal komputer lain melalui jaringan komputer secara aman, untuk dapat diakses maka komputer harus terinstall server ssh terlebih dahulu, dan komputer yang ingin mengaksesnya harus memiliki ssh client

Untuk menginstall **server** ssh pada ubuntu, kita harus menginstall paket yang bernama `openssh-server`

```bash
sudo apt install openssh-server
```

Untuk menginstall **client** ssh pada ubuntu, kita harus menginstall paket yang bernama `ssh`

```bash
sudo apt install ssh
```

Untuk mengakses server ssh, kita dapat menjalankan perintah berikut pada komputer client

```bash
# melakukan ssh ke ip 192.168.1.1
ssh 192.168.1.1

# melakukan ssh ke ip 192168.1.1 dengan user budi
ssh budi@192.168.1.1
```

## Server VNC

VNC merupakan protokol yang digunakan untuk mengontrol komputer melalui jaringan komputer secara GUI, sehingga kita dapat menggerakkan cursor, melihat desktop, serta mengganti wallpaper komputer yang kita kontrol, berbeda dengan SSH yang hanya mengakses terminalnya saja.

Server VNC dapat diinstall dengan menggunakan paket yang bernama `tightvncserver`

```bash
sudo apt install tightvncserver
```

Untuk mengontrol komputer yang sudah terinstall server VNC kita dapat menggunakan aplikasi yang bernama **VNC Viewer** yang dapat didownload pada link berikut :

https://www.realvnc.com/en/connect/download/viewer/

## Server FTP

FTP merupakan protokol yang digunakan untuk mengupload dan mendownload file dari komputer lain melalui jaringan komputer

Untuk menginstall Server FTP kita bisa menggunakan paket yang bernama `vsftpd`

```bash
sudo apt install vsftpd
```

Untuk melakukan koneksi ke server ftp, kita bisa menggunakan aplikasi bernama **filezilla** yang bisa didownload pada link berikut

https://filezilla-project.org/download.php?type=client
