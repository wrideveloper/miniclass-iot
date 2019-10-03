# Perulangan

## Penjelasan

Perulangan merupakan cara untuk menjalankan suatu perintah secara berulang - ulang, ada dua jenis perulangan dalam bahasa pemrograman python, yaitu `for` dan `while`

`for` digunakan untuk melakukan perulangan yang jumlahnya sudah kita ketahui (counted loop), sedangkan `while` digunakan untuk melakukan perulangan yang jumlahnya tidak diketahui (uncounted loop)

## Perulangan For

Berikut merupakan bentuk umum dari perulangan for

```python
for index in range(banyak_perulangan):
  # perintah disini akan diulang
  # perintah disini juga akan diulang
# perintah disini tidak diulang karena berada di luar for
```

Contoh penggunaannya adalah sebagai berikut

```python
for index in range(5):
  print("Perulangan ke-" + str(index))
```

Pada script tersebut kita melakukan perulangan sebanyak 5 kali, variabel `index` akan berisi index perulangan saat ini, sehingga hasilnya akan menjadi seperti berikut

```python
Perulangan ke-0
Perulangan ke-1
Perulangan ke-2
Perulangan ke-3
Perulangan ke-4
```

Kita juga bisa menggunakan for untuk menampilkan isi dari suatu list

```python
minuman = ["teh hangat", "es jeruk", "soda gembira"]

for item in minuman:
  print item
```

Pada script diatas kita akan mengambil isi dari list minuman, kemudian meletakkan nilainya ke variabel `item` kemudian menampilkan nilai dari variabel `item`, sehingga hasilnya akan menjadi seperti berikut

```python
teh hangat
es jeruk
soda gembira
```

**note:** menggunakan `for` dengan list pada bahasa pemrograman python mirip dengan `foreach` pada bahasa pemrograman lain

## Perulangan While

bentuk umum dari perulangan while adalah sebagai berikut

```python
while(kondisi):
  # perintah disini akan diulang
  # perintah disini juga akan diulang
# perintah disini tidak akan diulang karena berada di luar while
```

Contoh penggunaannya adalah sebagai berikut

```python
jawab = "y"
hitung = 0

while(jawab == "y"):
    hitung += 1
    jawab = input("Ulang lagi tidak? ")

print ("Total perulangan: " + str(hitung))
```

Disini kita akan melakukan perulangan selama variabel `jawab` bernilai `"y"`, maka dari itu perulangan akan terus dilakukan selama user menginputkan `"y"`, setelah perulangan selesai maka akan ditampilkan jumlah dari perulangan yang telah dilakukan

```python
Ulang lagi tidak? y
Ulang lagi tidak? y
Ulang lagi tidak? y
Ulang lagi tidak? y
Ulang lagi tidak? y
Ulang lagi tidak? y
Ulang lagi tidak? y
Ulang lagi tidak? n
Total perulangan: 8
```
