# Mengakses Micropython

## 1. Mengakses Program Micropython

### 1.1 Jenis File Python Pada Micropython

Terdapat dua jenis file python yang dapat kita ubah, yaitu : 

1. `boot.py` - program yang dijalankan saat micropython melakukan booting
2. `main.py` - program utama yang digunakan micropython

### 1.2 Mengubah File Python Pada Micropython

Lalu bagaimana jika kita ingin menulis program di komputer kita dan mengunggahnya sebagai file ***boot.py***  untuk proses booting atau bahkan sebagai file ***main.py*** untuk process utamanya.

#### 1.2.1 Install amp-adafruit

amp-adafruit merupakan program yang digunakan untuk mendownload dan mengupload file python pada micropython

```bash
$ pip install ampy-adafruit
```

#### 1.2.2 Download File Python Pada Micropython

Gunakan perintah `get` Untuk mendownload file python yang ada pada micropython

```bash
# download file boot.py
$ ampy --port /dev/ttyUSB0 --baud 115200 get boot.py

# download file main.py
$ ampy --port /dev/ttyUSB0 --baud 115200 get boot.py
```

#### 1.2.3 Upload File Python Pada Micropython

Gunakan perintah `put` untuk mengupload file python pada komputer kita ke dalam micropython

```bash
# upload file boot.py
$ ampy --port /dev/ttyUSB0 --baud 115200 put boot.py

# upload file main.py
$ ampy --port /dev/ttyUSB0 --baud 115200 put main.py
```

## 2. Mengakses Shell Micropython
 
### 2.1 Menginstall rshell

Untuk mengakses shell pada micropython, kita dapat menggunakan program yang bernama rshell, kita dapat menginstallnya menggunakan perintah berikut :

```bash
$ pip install rshell
```

### 2.2 Masuk ke Shell Micropython

Selanjutnya, kita dapat masuk ke dalam shell mycropython dengan rshell menggunakan perintah berikut :

```bash
$ rshell --port <port yang digunakan nodemcu>
```

Jika belum mengetahui port mana yang digunakan. Untuk yang menggunakan windows cukup membuka device manager

## 3. Referensi

- [Dokumentasi rshell](https://github.com/dhylands/rshell)
- [Dokumentasi ampy-adafruit](https://learn.adafruit.com/micropython-basics-load-files-and-run-code/install-ampy)