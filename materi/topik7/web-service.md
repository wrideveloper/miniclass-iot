# Web Service

<img src="webservice.png" width="500">

## Penjelasan Web Service

Web Service merupakan sebuah web yang bertugas untuk menerima, mengirim, dan mengelola data yang dikirimkan dari aplikasi frontend, web service tidak memiliki view atau tampilan untuk end user, inilah yang membedakan web service dengan website. Web service bisa menerima data dari beberapa aplikasi, misalnya mobile app, frontend web, desktop app, dan sebagainya.

## Penjelasan Flask

Flask merupakan salah satu framework web yang dibangun menggunakan bahasa pemrograman python

## Membuat Web Service dengan Flask

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