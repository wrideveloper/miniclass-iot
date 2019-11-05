# Module

<img src="module.png" height="150">

## 1. Pengertian Module

**Module** merupakan kumpulan fungsi atau variable yang bisa diimport ke script kita agar mempermudah pekerjaan yang sedang kita kerjakan

## 2. Cara Membuat Module

Pertama, kita akan membuat sebuah module yang bertujuan untuk menghitung luas dan keliling persegi yang nantinya dapat digunakan berkali - kali pada file python manapun

### 2.1 Membuat File Baru

Buatlah sebuah file python baru yang terpisah dengan file utama, misalnya `persegi.py`, modul ini bertujuan untuk menyimpan fungsi untuk menghitung luas dan keliling persegi

### 2.2 Membuat Fungsi

Selanjutnya, kita akan menambahkan dua fungsi kedalam file `persegi.py`, dengan nama `hitungLuas` dan `hitungKeliling`

```python
# persegi.py

# hitung luas persegi
def hitungLuas(sisi):
  print(sisi * sisi)

# hitung keliling persegi
def hitungKeliling(sisi):
  print(sisi + sisi + sisi + sisi)
```

### 2.3 Selesai

Kita telah membuat sebuah module bernama `persegi`, sekarang kita dapat menggunakan fungsi `hitungLuas` dan `hitungKeliling` pada file manapun

## 3. Cara Mengimport Module

Setelah kita membuat module, kita dapat mengimport fungsi dan variable yang ada pada module tersebut pada file python manapun, buatlah satu file python lagi yang bernama `main.py`, file ini akan kita gunakan untuk mengimport fungsi - fungsi yang ada pada file `persegi.py`

### 3.1 Mengimport Seluruh Module

Pertama, kita akan mengimport seluruh fungsi yang ada pada file `persegi.py`, caranya sebagai berikut

```python
# main.py

# import semua fungsi yang ada pada file persegi
import persegi

# menentukan sisi persegi
sisi = 5

# menghitung luas persegi
persegi.hitungLuas(sisi)

# menghitung keliling persegi
persegi.hitungKeliling(sisi)
```

### 3.2 Import Beberapa Bagian dari Module

Kita juga bisa mengimport hanya beberapa fungsi dari suatu module, caranya sebagai berikut

```python
# main.py

# import fungsi hitungLuas yang ada pada file persegi
from persegi import hitungLuas

# menentukan sisi persegi
sisi = 5

# menghitung luas persegi
hitungLuas(sisi)
```

### 3.3 Memberikan Nama Alias Saat Mengimport Module

Kita juga bisa memberikan nama alias pada module yang kita import, caranya sebagai berikut :

```python
# main.py

# import semua fungsi yang ada pada file persegi
import persegi as psg

# menentukan sisi persegi
sisi = 5

# menghitung luas persegi
psg.hitungLuas(sisi)

# menghitung keliling persegi
psg.hitungKeliling(sisi)
```

## 4. Built in Module

Pada python, terdapat beberapa module yang sudah siap dipakai tanpa perlu kita buat terlebih dahulu, contohnya :

1. `datetime` - menampilkan data waktu
2. `request` - mengirim dan mengambil data dari backend
