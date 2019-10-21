# Membangun Web Service Menggunakan HTTP

## Penjelasan Flask

Flask merupakan salah satu framework web yang dibangun menggunakan bahasa pemrograman python

## Membuat Web Service dengan Flask

Berikut merupakan langkah - langkah untuk membuat web service menggunakan flask

### 1. Menginstall Flask

Pertama kita harus menginstall package `flask` terlebih dahulu sebelum membuat web service

```bash
pip install Flask
```

### 2. Membuat Hello World

Untuk pemanasan mari kita membuat hello world pada flask dengan membuat file bernama `server.py` yang berisi file berikut :

```python
# server.py

# import flask
from flask import Flask

# membuat aplikasi flask menggunakan nama file saat ini
app = Flask(__name__)

# membuat rute /
@app.route("/")
def hello():
  return "Hello World!"

# menjalankan aplikasi flask
if __name__ == "__main__":
  app.run()
```

Kemudian kita dapat menjalankan script diatas dengan menggunakan perintah

```bash
python server.py
```

Setelah perintah tersebut dijalankan maka kita dapat mengunjungi http://localhost:5000 menggunakan rute `/` untuk melihat pesan `Hello World!`

### 3. Membuat Web Service

Disini kita akan membuat web service sederhana yang bertujuan untuk melakukan CRUD terhadap suatu array

```python
# server.py

from flask import Flask
from flask import request
from flask import jsonify

app = Flask(__name__)
biodata = [
    {
        "nama": "budi",
        "alamat": "malang"
    },
    {
        "nama": "ananta",
        "alamat": "malang"
    }
]


@app.route("/biodata")
def index():
    return jsonify(biodata)


@app.route("/biodata/<index>")
def show(index):
    return jsonify(biodata[int(index)])


@app.route("/biodata", methods=["POST"])
def store():
    biodata.append(request.json)
    return jsonify({"success": True})


@app.route("/biodata/<index>", methods=["PUT"])
def update(index):
    biodata[int(index)] = request.json
    return jsonify({"success": True})


@app.route("/biodata/<index>", methods=["DELETE"])
def destroy(index):
    del biodata[int(index)]
    return jsonify({"success": True})


if __name__ == "__main__":
    app.run()
```

Kemudian kita dapat menjalankan script diatas dengan menggunakan perintah

```bash
python server.py
```

Setelah perintah tersebut dijalankan maka kita dapat menggunakan web service tersebut dengan mengakses url berikut

| URL            | Method | Aksi    | Deskripsi                             |
| -------------- | ------ | ------- | ------------------------------------- |
| /biodata       | GET    | index   | Menampilkan seluruh biodata           |
| /biodata/index | GET    | show    | Menampilkan biodata berdasarkan index |
| /biodata       | POST   | store   | Membuat biodata baru                  |
| /biodata/index | PUT    | update  | Mengubah biodata berdasarkan index    |
| /biodata/index | DELETE | destroy | Menghapus biodata berdasarkan index   |

## Mengkonsumsi Web Service

Setelah membuat web service sekarang kita akan belajar bagaimana cara mengkonsumsi web service menggunakan package `requests`

### 1. Menginstall Requests

```bash
pip install requests
```

### 2. Menggunakan Requests

```bash
# client.py

import requests

# mengambil semua biodata
biodata = requests.get("http://localhost:5000/biodata")
print(biodata.json())

# mengambil biodata berdasarkan index
biodata = requests.get("http://localhost:5000/biodata/1")
print(biodata.json())

# menambahkan biodata baru
requests.post("http://localhost:5000/biodata", json={
  "nama": "halimah",
  "alamat": "malang"
})

# mengubah biodata berdasarkan index
requests.put("http://localhost:5000/biodata/1", json={
  "nama": "aisyah",
  "alamat": "probolinggo"
})

# menghapus biodata berdasarkan index
requests.delete("http://localhost:5000/biodata/1")
```
