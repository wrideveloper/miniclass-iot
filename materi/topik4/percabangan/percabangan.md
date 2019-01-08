## Percabangan

### Pengertian

Percabangan adalah suatu kondisi dimana program akan menjalankan statement berdasarkan syarat suatu nilai yang bernilai `true` atau `false`

### Penggunaan

Percabangan menggunakan syntax `if` dan `else` sebagai pemisah antara statement bernilai `true` dan `false`
contoh :

```python
        a = 5
        if(a < 10):
            ...statement true...
        else:
            ...statement false...
```

dalam contoh diatas ada 2 jenis statement, apabila membutuhkan kondisi dimana nilai a berada diantara suatu nilai, maka kondisi bisa menjadi lebih dari 2 statement menggunakan `elif`
contoh :

```python
        a = 5
        if(a < 10):
            ...statement true...
        elif(a > 3):
            ...statement true with other condition...
        else:
            ...statement false...
```

jadi penggunaan `elif` dapat memberikan syarat baru untuk mendapatkan kondisi `true` sebuah nilai variabel

#### note

penulisan statement harus berada dibawah `if`, `else` atau `elif` diberikan indentasi 1 tab (4x spasi)
