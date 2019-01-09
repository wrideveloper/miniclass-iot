# Input dan Output

### Pengertian Input dan Output

Input adalah suatu tindakan untuk memberikan masukan berupa suatu nilai yang diminta oleh sebuah program melalui console.

Output adalah suatu perintah untuk memberikan atau menampilkan sebuah nilai atau data melalui console.

### Penggunaan Input dan Output

input dalam python digunakan untuk mendapatkan sebuah nilai dari user.

```python
        nilai = input("Masukan nilai : ")
```

dalam kasus tersebut variabel nilai akan berisi masukan dari user dan secara default bertipe data String.

untuk memberikan input dengan tipe data tertentu, maka gunakan fungsi tambahan, contoh :

```python
        nilai = int(input("Masukan nilai : "))
```

dengan syntax diatas, maka variabel nilai akan bertipe data Integer

output dalam python biasanya digunakan untuk menampilkan nilai variabel maupun string.

```python
        print("Hello World")
```

membuat output berupa nilai variable dan string dalam 1 syntax

```python
        nama = "Adit"
        umur = 19
        print("Hallo nama saya {} umur {}!".format(nama, umur))
```

maka outputnya :

        Hallo nama saya Adit umur 19!

##### Note

penempatan variabel harus diurutkan berdasarkan urutan output dengan tanda `{}`
