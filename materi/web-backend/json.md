# Parsing Data dari JSON

JSON adalah salah satu format standar pertukaran data antar aplikasi.

Biasanya JSON banyak kita temukan ketika bermain dengan web service atau RESTful API.

![Gambar](img/json.png)

Cara Parsing File JSON di Python
Penguraian JSON pada bahasa pemrograman Python, membutuhkan modul **json** dan **urllib** untuk mendown-load JSON dari web service. Kedua modul ini sudah disediakan oleh Python.

## Membuat File Json

```json
{
    "nama" : "Workshop Riset Informatika",
    "alamat" : "Malang",
    "media" : {
        "facebook" : "wripolinema",
        "github" : "wrideveloper",
        "instagram " : "wri_polinema"
    }
}
```
## Mengurai File Json
Kita menggunakan fungsi **open()** untuk membuka file JSON. Kemudian, kita menggunakan fungsi **loads(**) dari modul **json** untuk me-load data **JSON**.

Data **JSON** disimpan pada variabel data dalam bentuk dictionary. Dengan demikian, kita bisa leluasa mengurai data **JSON**-nya.

```import
import json

#buka file json
file_json = open("faris.json")

#load file json
data = json.loads(file_json.read())

#cetak data json
print(data)

print("nama \t: %s" %data['nama'])
print("alamat \t %s" %data['alamat'])
print("media sosial :")
for sosial in data['media']:
    print("\t%s \t: %s" %(sosial, data['media'][sosial]))
```

## Referensi Python Guide : JSON
```json 
https://docs.python-guide.org/scenarios/json/
```