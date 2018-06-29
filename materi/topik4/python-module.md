# **Python Module**

Pengertian


### Cara Mengimport Module

Di Python, untuk memakai modul lain dalam script yang kita buat, kita perlu Mengimport modul tersebut dengan cara :

    import sys

Modul yang kita import bernama `sys`, modul 'sys' digunakan untuk

Jika nama modul yang ingin dipakai sudah diketahui dari awal, kita bisa menuliskannya secara langsung dalam kode yang kita buat. Namun bagaimana jika nama modul tersebut belum diketahui dari awal sehingga harus dapat diimpor belakangan secara dinamis?

Python menyediakan fasilitas ini melalui fungsi       

    __import__

yang menerima parameter berupa nama modul dalam bentuk string. Berikut ini adalah cara menggunakannya.

    import sys
    __import__("sebuah.modul")
    modul = sys.modules["sebuah.modul"]

Variabel modul di atas akan menjadi “perwakilan” dari modul bernama `sebuah.modul`. Melalui modul inilah isi dari modul `sebuah.modul` dapat diakses.

<!-- Module sekumpulan library atau fucntion -->
