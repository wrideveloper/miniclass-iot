# Mengakses Micropython NodeMCU

Micropython juga telah menyediakan tools untuk dapat mengakses masuk ke dalam board nodemcu dengan menggunakan **rshell**. Selain itu, nodeMCU juga telah menyediakan Python Intepreter yang disebut dengan **REPL** *(Read Eval Print Loop)*. 



## Penggunaan

Buka terminal atau command prompt. Sebelumnya install terlebih dahulu rshellnya jika belum terinstall :

```bash
$ pip install rshell
```

Lalu ketikkan perintah sesuai format dibawah ini :

```bash
$ rshell --port <port yang digunakan nodemcu>
```

Jika belum mengetahui port mana yang digunakan. Untuk yang menggunakan windows cukup membuka device manager dan untuk yang menggunakan biasanya akan menggunakan directory */dev/ttyACM<1-100>* bisa dicek disana.

Perintah diatas maksudnya adalah melakukan remote shell ke dalam micropython pada board **NodeMCU**. Setelah berhasil melakukan remote shell silahkan membaca *dokumentasi rshell* untuk mengetahui perintah-perintah yang dapat digunakan pada remote shell. Salah satunya adalah seperti berikut :

```bas
> repl
```

Perintah diatas akan berpindah dari remote shell ke dalam python interpreter. Dimana kita dapat menuliskan kode python disana.



Selain menggunakan cara diatas ada cara yang lebih simple untuk digunakan namun tentunya cara diatas merupakan cara yang wajib diketahui. Cara lainnya yaitu menggunakan **webrepl** atau *(Web Browser Interactive Prompt)*. WebREPL tersebut menggunakan Web Socket yang dapat diakses pada browser namun tentunya micropython dan nodemcu sudah harus terhubung pada sebuah jaringan sebagai access point maupun client.



## Upload

Lalu bagaimana jika kita ingin menulis program di komputer kita dan mengunggahnya sebagai file ***boot.py***  untuk proses booting atau bahkan sebagai file ***main.py*** untuk process utamanya. Untuk memudahkan tersebut dapat mengikuti langkah-langkah dibawah ini :

```bash
$ pip install ampy-adafruit
```

Contoh dari penggunaan dari tools ampy tersebut seperti berikut :

***get***, digunakan untuk melakukan download dari system micropython yang berada di nodemcu.

```bas
$ ampy --port /dev/ttyUSB0 --baud 115200 get boot.py
```

***put***, digunakan untuk melakukan upload dari directory active ke system micropython.

```bas
$ ampy --port /dev/ttyUSB0 --baud 115200 put boot.py
```

Untuk perintah lebih lengkapnya dapat dibaca di dokumentasi ampy-adafruit



## Referensi

- [Dokumentasi rshell](https://github.com/dhylands/rshell)
- [Dokumentasi ampy-adafruit](https://learn.adafruit.com/micropython-basics-load-files-and-run-code/install-ampy)