# Virtual Environment

## Penjelasan Virtual Environment

Saat kita menginstall package baru menggunakan `pip` maka package tersebut akan terinstall ke folder `site_packages` yang ada pada direktori sistem OS, sehingga setiap kali kita membuat proyek berbasis python maka package yang akan digunakan selalu yang ada pada direktori sistem OS tersebut

Hal ini menjadi permasalahan karena setiap proyek terkadang membutuhkan versi package yang berbeda - beda, hal ini tidak dapat dilakukan karena proyek kita akan selalu menggunakan package yang ada pada sistem OS

Solusi dari masalah tersebut dengan menggunakan virtual environment, virtual environment akan membuat sistem direktori python baru pada folder proyek kita, sehingga setiap kali kita menginstall package menggunakan `pip` maka package tersebut akan terinstall ke folder proyek kita

## Cara Menggunakan Virtual Environment

### 1. Install Virtual Environment

Kita dapat membuat dan menggunakan virtual environment baru menggunakan package yang bernama `virtualenv`

```bash
apt install virtualenv
```

### 2. Membuat Folder Proyek

Selanjutnya kita harus membuat folder proyek yang akan digunakan untuk meletakkan script - script python kita nantinya

```bash
mkdir python-project
```

### 3. Membuat Virtual Environment

Selanjutnya kita dapat membuat virtual environment baru di dalam folder proyek yang sudah kita buat

```bash
# masuk ke folder proyek
cd python-project

# python 2
virtualenv env_name

# python 3
virtualenv -p python3 env_name
```

Setelah perintah tersebut dijalankan maka folder `env_name` akan terbuat yang berisi virtual environment baru

### 4. Mengaktifkan Virtual Environment

Setelah membuat virtual environment baru maka kita harus mengaktifkannya dengan menjalankan script `bin/active` yang ada pada folder virtual environment tersebut

```bash
# menjalankan script
source env_name/bin/activate
```

Setelah menjalankan script `bin/active` maka virtual environment yang kita buat sudah aktif sehingga ketika kita menginstall package baru menggunakan `pip` maka package tersebut akan terinstall ke virtual environment tersebut

### 5. Menonaktifkan Virtual Environment

Untuk menonaktifkan virtual environment kita dapat menggunakan perintah berikut

```bash
deactivate
```

Setelah perintah tersebut dijalankan maka virtual environment kita tidak akan aktif sehingga setiap kali kita menginstall package baru menggunakan `pip` maka package tersebut akan terinstall ke sistem OS kita
