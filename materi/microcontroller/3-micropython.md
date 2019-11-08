# MICROPYTHON

Telah di mention pada materi sebelumnya *micropython* merupakan sebuah project untuk mengimplementasikan Python 3 untuk dapat digunakan pada ***microcontroller*** dan ***small embedded system***.

*Micropython* pertama kali dirilis pada tahun 2013 yang ditujukan untuk penggunaan ***PyBoard***. Namun sejak versi 1.8 *micropython* telah mendukung untuk digunakan pada platform **ESP** salah satunya pada **NodeMCU**.

Pada saat booting micropython akan menjalankan file ***_boot.py*** untuk melakukan *mount* filesystem pada FlashROM. Dan jika file tersebut tidak tersedia maka module tersebut akan dibuat secara otomatis dibuat oleh system. Setelah berhasil di *mount* system akan mengeksekusi file ***boot.py*** di dalam file tersebut kita dapat melakukan apa yang kita ingin inisiasikan. Untuk program utamanya system akan mengeksekusi file ***main.py***.



## Features

Pada *micropython* versi 1.8 banyak fitur yang ditambahkan, diantaranya sebagai berikut :

| Fitur  | Detail Fungsi                                                |
| ------ | ------------------------------------------------------------ |
| pycore | - Penambahan komentar pada pengaturan variabel spesial "_" <br />- Penambahan sintaks async/await/async dan for/async <br />- Perbaikan constant folding dan inline-asm agar bisa bekerja dengan sintaks baru async |
| extmod | - Penambahan awalan modul framebuf <br />- Penambahan class generic machine.I2C dengan bit-bang I2C machine_i2c<br />- Pembacaan I2C diperbaiki dengan mengirimkan ack/nack pada byte terakhir |
| tools  | - Penambahan driver SSD1306 OLED dengan antarmuka I2C dan SPI |
| tests  | - Penambahan 6 pengujian untuk async await/for/ <br />- Penambahan file berekstensi .exp untuk pengujian async sehingga pengguna bisa menjalankannya dengan Python 3.4 <br />- Perbaikan dict1.py sehingga tidak bergantung pada urutan elemen struktur data dict {} |



## Setup

Lalu bagaimana caranya supaya *micropython* dapat digunakan pada **NodeMCU** ? Caranya cukup mudah tinggal ikuti langkah pada dibawah ini atau kunjungi referensi *Dokumentasi micropython*.

1. Download Firmware Micropython di [Download Page](http://micropython.org/download#esp8266).

2. Buka Terminal

3. Untuk **WINDOWS** silahkan download USB to UART Driver [Disini.](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers.)

4. Install esptool menggunakan pip:

   ```bash
   $ pip install esptool
   ```

   

5. Hapus flash memory pada *nodemcu*.

   ```bash
   $ esptool.py --port /dev/ttyUSB0 erase_flash
   ```

   

6. Deploy firmware micropython yang telah di download ke nodemcu.

   ```bash
   $ esptool.py --port /dev/ttyUSB0 --baud 460800 write_flash --flash_size=detect -fm dio 0 esp8266-20170108-v1.8.7.bin
   ```



## Referensi

- [micropython.org](https://micropython.org/)
- [Dokumentasi micropython](https://docs.micropython.org/)
- [codepoliten.com](https://www.codepolitan.com/micropython-1-8-telah-rilis-dukungan-pertama-micropython-untuk-esp8266)
- [instructables.com](https://www.instructables.com/id/Getting-Started-With-MicroPython-on-the-ESP8266/)