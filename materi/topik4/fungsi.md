# Fungsi

## Penjelasan

Apabila kita memiliki aplikasi yang fiturnya banyak, tentu saja baris kode yang digunakan untuk membuat fitur tersebut juga banyak, sehingga akan susah untuk membaca dan memahami keseluruhan kodenya.

Agar lebih mudah dipahami, kita dapat memecah keseluruhan kode program menjadi beberapa sub program yang lebih kecil, untuk melakukan hal tersebut kita bisa menggunakan fungsi

## Cara Menggunakan Fungsi

### Deklarasi

Sebelum dapat digunakan, kita perlu membuat atau mendeklarasikan fungsi baru terlebih dahulu

```python
def nama_fungsi():
    print "Hello ini Fungsi"
```

fungsi diawali dengan kata kunci `def` diikuti dengan nama fungsi, kemudian kita bisa memasukkan isi dari fungsi tersebut, misalnya `print "Hello ini Fungsi"`

### Pemanggilan

Setalah fungsi selesai dideklarasikan, kita bisa langsung menggunakannya dengan memanggil nama fungsi tersebut

```python
nama_fungsi() # Hello ini Fungsi
```

Bahkan kita bisa memanggil sebuah fungi berulang kali

```python
nama_fungsi() # Hello ini Fungsi
nama_fungsi() # Hello ini Fungsi
nama_fungsi() # Hello ini Fungsi
```

### Parameter Fungsi

Kita bisa memberikan suatu inputan kedalam sebuah fungsi menggunakan parameter, caranya seperti berikut

```python
def beri_salam(nama):
  print("Selamat datang" + str(nama))

beri_salam("budi")  # Selamat datang budi
beri_salam("andi")  # Selamat datang andi
beri_salam("yuli")  # Selamat datang yuli
```

### Fungsi yang Mengembalikan Nilai

Misalnya pada suatu fungsi ada proses perhitungan, setalah dihitung kita ingin mengambil nilai tersebut dan mengolahnya kembali, disini kita bisa menggunakan kata kunci `return`

```python
def hitungLuas(panjang, lebar):
  luas = panjang * lebar
  return luas

luasPersegiPanjang = hitungLuas(5, 2)
print(luasPersegiPanjang)
```
