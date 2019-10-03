# Object Oriented Programming

Pada topik ini kita akan membahas implementasi object oriented programming menggunakan bahasa pemrograman python, untuk dasar dari OOP tidak akan dibahas disini

## Pembuatan Class

Untuk membuat suatu class menggunakan python, caranya adalah seperti berikut

```python
class Mobil:
  # attribute (boleh tidak ditulis apabila sudah diinisialisasi di constructor)
  merk = ""
  warna = ""

  # constructor
  def __init__(self, merk, warna):
    self.merk = merk
    self.warna = warna

  # method
  def tampilkan_info(self):
    print("mobil dengan merk " + self.merk + " berwarna " + self.warna)
```

Pada script diatas kita membuat sebuah class bernama mobil, disana terdapat dua attribute, yaitu `merk` dan `kecepatan`, pada constructor kita menginisialisasi nilai dari kedua attribute tersebut, kemudian dengan memanggil method `tampilkan_info` kita bisa menampilkan informasi dari mobil yang telah dibuat

## Membuat Object

Setelah membuat class maka kita bisa membuat object dari class tersebut, caranya adalah sebagai berikut

```python
mobil1 = Mobil("toyota", "merah")
mobil1.tampilkan_info() # mobil dengan merk toyota berwarna merah

mobil1 = Mobil("suzuki", "biru")
mobil1.tampilkan_info() # mobil dengan merk suzuki berwarna biru
```

## Mengakses Attribute

Setelah membuat object kita bisa mengakses attribute yang ada pada class tersebut, misalnya pada class mobil kita bisa mendapatkan dan mengisi attribute `merk` dan `warna`

```python
mobil1 = Mobil("honda", "merah")
print(mobil1.merk) # honda

mobil1.merk = "yamaha"
print(mobil1.merk) # yamaha
```

## Penjelasan Kata Kunci Self

Pada class python, kata kunci `self` digunakan sebagai pengganti `this` pada bahasa pemrograman java, fungsi dari kata kunci `self` yaitu digunakan untuk mengakses attribute atau method yang ada di dalam class itu sendiri

Semua method yang kita buat didalam suatu class wajib memiliki paramater `self` sebagai parameter pertama, nilai dari `self` ini tidak perlu kita isi saat pemanggilan method, kita bisa langsung mengisi nilai dari parameter kedua dan seterusnya
