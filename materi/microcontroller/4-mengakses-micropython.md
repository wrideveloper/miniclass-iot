# Mengakses Micropython

## 1. Membuat Program Pada Micropython

### 1.1 Install adafruit-ampy

amp-adafruit merupakan program yang digunakan untuk mendownload dan mengupload file python pada nodemcu. Pertama install terlebih dahulu `adafruit-ampy` ini

```bash
$ pip install adafruit-ampy
```

### 1.2 Menjalankan File Python dari Komputer

Selanjutnya, kita bisa mencoba menjalankan file python yang ada di komputer ke nodemcu. Untuk melakukannya, kita bisa menggunakan perintah `run`

```bash
# menjalankan file hello.py yang ada di komputer
$ ampy --port /dev/ttyUSB0 --baud 115200 run hello.py
```

### 1.3 Upload File Python

Setelah file python yang ada di komputer berhasil dijalankan pada nodemcu, selanjutnya kita bisa mengupload file python tersebut ke nodemcu. Untuk melakukannya, kita bisa menggunakan perintah `put`

```bash
# upload file hello.py
$ ampy --port /dev/ttyUSB0 --baud 115200 put hello.py
```

### 1.4 Melihat Isi File Python

Untuk memastikan apakah file python telah sukses diupload, kita bisa menggunakan perintah `get` untuk melihat isi file python yang sudah diupload ke nodemcu

```bash
# melihat isi file hello.py
$ ampy --port /dev/ttyUSB0 --baud 115200 get hello.py
```

## 2. Referensi

- [Dokumentasi rshell](https://github.com/dhylands/rshell)
- [Dokumentasi ampy-adafruit](https://learn.adafruit.com/micropython-basics-load-files-and-run-code/install-ampy)