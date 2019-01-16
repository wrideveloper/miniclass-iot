# Pengenalan GPIO

![Gambar](img/gpio-pins.jpg)

## Penjelasan

GPIO adalah singkatan dari General Purpose Input Ouput, yaitu kumpulan pin yang terdapat di Raspberry yang berfungsi sebagai input dan output berupa data atau tegangan listrik, sehingga dapat digunakan untuk membaca nilai dari suatu sensor

Selain pada Raspberry, GPIO ini juga dimiliki oleh Arduino, Orange Pi, ESP, dan segala jenis device mikro lainnya.

## Cara Memilih GPIO

![gpio](img/gpio-pin.png)

Sebelum kita belajar bagaimana cara mengontrol raspberry dengan python, kita perlu tau bagaimana cara memilih gpio yang akan kita gunakan, terdapat dua cara untuk memilih nomor gpio, yaitu :

### Berdasarkan Nomor Board

Apabila kita menggunakan mode ini maka kita dapat memilih gpio berdasarkan urutan pin yang ada pada board raspberry, misalnya apabila kita memilih nomor 8 maka kita akan memilih GPIO 14

### Berdasarkan Nomor Pin GPIO (BCM)

Dengan cara ini kita bisa langsung menentukan nomor pin GPIO yang akan kita gunakan, misalnya kita memilih nomor 24 maka kita akan memilih GPIO 24

## GPIO Programming dengan Python

Kita dapat mengontrol penggunaan GPIO pada raspberry menggunakan bahasa pemrograman python

### Menginstall Package GPIO untuk Python

Sebelum kita dapat menggunakan GPIO pada python, kita perlu menginstall package `python-rpi.gpio` terlebih dahulu

```bash
sudo apt install python-rpi.gpio
```

### Menentukan Mode Pemilihan GPIO

Sebelumnya kita sudah tau bahwa terdapat dua cara untuk memilih GPIO, yaitu berdasarkan urutan pin pada board dan berdasarkan nomor gpio itu sendiri

```python
import RPi.GPIO as GPIO

GPIO.setmode(GPIO.BOARD) # Memilih GPIO berdasarkan urutan pin pada board
GPIO.setmode(GPIO.BCM) # Memilih GPIO berdasarkan nomor GPIO
```

### Menentukan Fungsi GPIO

Setelah menentukan mode pemilihan gpio, maka kita bisa langsung menentukan gpio mana yang akan kita gunakan sekaligus fungsi dari gpio tersebut apakah sebagai input atau sebagai output

```python
GPIO.setup(18, GPIO.OUT) # menggunakan pin sebagai output
GPIO.setup(15, GPIO.IN) # menggunakan pin sebagai input
```

Tips untuk menentukan suatu pin apakah digunakan sebagai input atau output adalah berdasarkan alat apa yang akan ditancapkan pada pin tersebut, apabila alat tersebut berupa alat output seperti lampu, LCD, dan lain lain maka gunakanlah pin tersebut sebagai output, sebaliknya apabila alat tersebut berupa sensor seperti sensor suara, jarak, cahaya, atau tombol maka gunakan pin tersebut sebagai input

### Menulis dan Membaca Nilai Pada GPIO

**Cara menulis suatu nilai pada GPIO**

```python
GPIO.setup(18, GPIO.OUT) # menggunakan pin sebagai output
GPIO.output(18, GPIO.LOW) # menulis nilai low pada pin
GPIO.output(18, GPIO.HIGH) # menulis nilai high pada pin
```

Untuk menulis nilai pada suatu pin, maka kita perlu mengeset mode pin tersebut sebagai output, baru setelah itu kita bisa menulis suatu nilai pada pin tersebut menggunakan `GPIO.output`

Apabila pin tersebut ditancapkan lampu, maka lampu tersebut akan menyala apabila pinnya kita beri nilai high, sebaliknya lampu akan mati apabila pinnya kita beri nilai low

**Cara membaca suatu nilai pada GPIO**

```python
GPIO.setup(15, GPIO.IN)
print(GPIO.input(15)) # true or false
```

Untuk membaca nilai pada suatu pin, maka kita perlu mengeset mode pin tersebut sebagai input, kemudian kita bisa membaca nilai dari pin tersebut menggunakan `GPIO.input`

Apabila pin tersebut ditancapkan tombol, maka pin akan bernilai true apabila tombol ditekan, sedangkan false apabila tombol dilepas
