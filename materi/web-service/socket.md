# Socket

<img src="./websocket.jpg" width="600" />

## Penjelasan Socket

Socket merupakan protokol komunikasi baru yang diimplementasikan ke web server dan client. Setelah client dan server terkoneksi maka koneksi tersebut bersifat permanen dan keduanya dapat saling mengirim data secara dua arah, inilah yang membedakan protokol HTTP dengan web socket. Dalam dunia IOT, web socket sangat direkomendasikan karena dapat mengirimkan data secara realtime.

## Membuat Socket

Disini kita akan membuat socket sederhana menggunakan socket io

### 1. Menginstall Socket IO

Sebelumnya kita perlu menginstall package yang bernama `python-socketio` dan satu package lagi yang bernama `eventlet`, dimana eventlet ini merupakan web server yang mendukung fitur WSGI yang akan digunakan sebagai wadah untuk menjalankan web socket kita

```bash
pip install python-socketio
pip install eventlet
```

### 2. Membuat Web Socket

Disini kita akan membuat sebuah web socket yang akan memberitahukan apabila ada pesan yang dikirim oleh client kemudian menyebarkan pesan tersebut ke seluruh client yang terkoneksi, selain itu web socket ini juga memberitahukan apabila ada client yang terkoneksi dan terputus

```python
# server.py

import eventlet
import socketio

sio = socketio.Server()
app = socketio.WSGIApp(sio)

@sio.on('connect')
def connect(sid, environ):
    print('new client connected ', sid)

@sio.on('message')
def message(sid, message):
    print('new message ', message)
    sio.emit("message", message)

@sio.on('disconnect')
def disconnect(sid):
    print('client disconnect ', sid)

if __name__ == '__main__':
    eventlet.wsgi.server(eventlet.listen(('', 5000)), app)
```

## Mengkonsumsi Web Socket

Disini kita akan membuat dua jenis client untuk mengkonsumsi web socket yang sudah dibuat, yang pertama `receiver.py` dimana ia akan selalu mendengarkan event socket dari server, dan yang kedua `sender.py` dimana ia akan selalu meng-emit event ke server

### 1. Sender

```python
# sender.py

from socketio import Client

socketio = Client()
socketio.connect("http://localhost:5000")


while True:
  message = input("message to send : ")
  socketio.emit("message", message)
```

### 2. Receiver

```bash
# receiver.py

from socketio import Client

socketio = Client()
socketio.connect("http://localhost:5000")


@socketio.on("message")
def on_message(message):
  print("receive message : " + message)

socketio.wait()
```
