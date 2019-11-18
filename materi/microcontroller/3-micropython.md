# Micropython

## 1. Penjelasan Micropython

Micropython merupakan sebuah project untuk mengimplementasikan Python 3 agar dapat digunakan pada microcontroller.

## 2. Menginstall Micropython Pada NodeMCU

Lalu bagaimana cara agar *micropython* dapat digunakan pada **NodeMCU** ? Caranya cukup mudah tinggal ikuti langkah pada dibawah ini :

### 2.1 Download Micropython
Pertama, download terlebih dahulu firmware micropython yang akan diinstall [disini](http://micropython.org/download#esp8266)

### 2.2 Install esptool

esptool merupakan program yang akan kita gunakan untuk melakukan flashing nodemcu. Maka kita akan menginstall esptool menggunakan pip:

```bash
$ pip install esptool
```

**Catatan**  
Untuk sistem operasi **windows**, dibutuhkan driver tambahan untuk mengkoneksikan nodemcu ke USB, silahkan download USB to UART Driver [disini.](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers.)

### 2.3 Menghapus Flash Memory 

Sebelum menginstall micropython pada nodemcu, kita harus menghapus flash memory pada *nodemcu*.

```bash
$ esptool.py --port /dev/ttyUSB0 erase_flash
```

### 2.4 Install Micropython

Install firmware micropython yang telah di download ke nodemcu.

```bash
$ esptool.py --port /dev/ttyUSB0 --baud 460800 write_flash --flash_size=detect -fm dio 0 esp8266-20170108-v1.8.7.bin
```

## 3. Referensi

- [micropython.org](https://micropython.org/)
- [Dokumentasi micropython](https://docs.micropython.org/)
- [codepolitan.com](https://www.codepolitan.com/micropython-1-8-telah-rilis-dukungan-pertama-micropython-untuk-esp8266)
- [instructables.com](https://www.instructables.com/id/Getting-Started-With-MicroPython-on-the-ESP8266/)