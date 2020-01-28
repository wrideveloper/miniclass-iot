# GPIO

## 1. Penjelasan GPIO

GPIO merupakan singkatan dari General Purpose Input Ouput, yaitu kumpulan pin yang berfungsi sebagai input dan output berupa data atau tegangan listrik, sehingga dapat digunakan untuk membaca nilai dari suatu sensor

<img src="img/nodemcu-v3-pinout.png" width="800" />

Diatas merupakan gambaran dari skema pin **NodeMCU**. Berikut merupakan penjelasan dari setiap pin tersebut :

| Pin  | Penjelasan                                                                                                  |
| ---- | ----------------------------------------------------------------------------------------------------------- |
| RST  | **_RESET_** digunakan untuk melakukan reset pada board NodeMCU.                                             |
| Vin  | **_POWER_**, digunakan untuk mengambil daya dimana daya yang keluar sama dengan daya yang masuk pada board. |
| 3.3v | **_POWER_**, digunakan untuk mengambil daya sebesar 3.3v.                                                   |
| GND  | **_GROUND_**, digunakan untuk mengambil sumber _(-)_                                                        |
| GPIO | Terminal yang digunakan untuk input output data                                                             |

## 2. Menggunakan GPIO

### 2.1 GPIO Sebagai Output

GPIO output biasa digunakan pada alat - alat yang berfungsi sebagai output, seperti led dan LCD

#### 2.1.1 Import Module

Untuk melakukan manipulasi GPIO, kita membutuhkan module yang bernama `machine`, di dalam sana terdapat sub module `Pin`, maka dari itu kita perlu mengimportnya

```python
# main.py

# import module
from machine import Pin
```

#### 2.1.2 Setup GPIO Sebagai Output

Selanjutnya, kita perlu mensetup GPIO sebagai output dengan menggunakan `Pin.OUT`

```python
# main.py

from machine import Pin

# setup GPIO 5 sebagai output
Pin(5, Pin.OUT)
```

#### 2.1.3 Manipulasi GPIO Output

Untuk melakukan manipulasi terhadap GPIO output, kita dapat menggunakan fungsi `on()`, `off()`, dan `value()`

```python
# main.py

# simpan hasil setup GPIO ke sebuah variable
led = Pin(5, Pin.OUT)

# menyalakan GPIO
led.on()

# mematikan GPIO
led.off()

# melihat value dari GPIO
led.value()
```

### 2.2 GPIO Sebagai Input

GPIO output biasa digunakan pada alat - alat yang berfungsi sebagai input, seperti button dan sensor

#### 2.2.1 Import Module

Untuk melakukan manipulasi GPIO, kita membutuhkan module yang bernama `machine`, di dalam sana terdapat sub module `Pin`, maka dari itu kita perlu mengimportnya

```python
# main.py

# import module
from machine import Pin
```

#### 2.2.2 Setup GPIO Input

Selanjutnya, kita perlu mensetup GPIO sebagai output dengan menggunakan `Pin.IN`

```python
# main.py

from machine import Pin

# setup GPIO 5 sebagai input
Pin(5, Pin.IN)
```

#### 2.2.3 Membaca Nilai GPIO Input

Untuk membaca nilai dari GPIO input, kita dapat menggunakan fungsi `value()`

```python
# main.py

# simpan hasil setup GPIO ke sebuah variable
button = Pin(5, Pin.IN)

# melihat value dari GPIO
button.value()
```
