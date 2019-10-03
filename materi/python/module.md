# Module

<img src="module.png" height="150">

## Pengertian Module

**Module** merupakan kumpulan library yang bisa diimport ke script kita agar mempermudah pekerjaan yang sedang kita kerjakan

### Cara Mengimport Module

**Mengimport seluruh module**

Pada python, kita dapat mengimport sebuah module menggunakan kata kunci `import`, misalnya :

```
import datetime
```

Misalnya pada contoh diatas kita mengimport module yang bernama `datetime`, module ini berguna untuk mengelola waktu dan tanggal, kita bisa mendapatkan waktu terkini serta operasi waktu yang lain.

**Import beberapa bagian dari module**

Kita juga bisa mengimport hanya beberapa function dari suatu module, hal ini bisa kita lakukan dengan menggunakan kata kunci `from`, misalnya

```
from datetime import date
```

Pada contoh diatas kita hanya mengimport function `date` yang terdapat pada module `datetime`

**Memberikan nama alias saat mengimport module**

Kita juga bisa memberikan nama alias pada module yang kita import, caranya adalah menggunakan kata kunci `as`, misalnya :

```
import datetime as d
```

Pada contoh diatas kita dapat mengakses module `datetime` dengan menggunakan variabel `d`, karena module `datetime` yang kita import sudah kita berikan nama alias menjadi `d`

**Untuk lebih jelasnya tentang cara mengimport module, silahkan kunjungi link berikut :**

https://www.digitalocean.com/community/tutorials/how-to-import-modules-in-python-3
