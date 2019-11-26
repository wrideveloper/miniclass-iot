# GPIO Input Handling

Setelah mempelajari tentang GPIO input, disini kita akan belajar bagaimana cara menghandle GPIO input

## 1. Polling

Cara yang paling sederhana untuk melakukan handling terhadap GPIO input yaitu dengan memeriksa nilai dari GPIO input tersebut menggunakan IF, cara ini disebut dengan polling

```python
from RPi import GPIO

GPIO.setmode(GPIO.BCM)

channel = 15
GPIO.setup(channel, GPIO.IN)

while(True):
  if (GPIO.input(channel)):
    print("Input High")
  else:
    print("Input Low")
```

## 2. Edge Detection

Edge merupakan perubahan status dari suatu input. Terdapat tiga jenis edge, yaitu :

1. **Rising** (dari low ke high)
2. **Falling** (dari high ke low)
3. **Both** (keduanya)

Terdapat dua cara untuk menghandle GPIO input menggunakan metode edge detection

### 2.1. Wait For Edge

Wait for edge akan memblok eksekusi dari suatu program hingga ada edge yang terjadi

```python
from RPi import GPIO

GPIO.setmode(GPIO.BCM)

channel = 15
GPIO.setup(channel, GPIO.IN)

while(True):
  # menunggu hingga terjadi edge rising
  GPIO.wait_for_edge(channel, GPIO.RISING)

  print("Edge Rising Detected on Channel 15")
```

### 2.2. Event Detect

Event detect mirip dengan wait for edge, yaitu akan mengeksekusi suatu perintah apabila ada edge yang terdeteksi, namun bedanya adalah event detect tidak memblok eksekusi dari suatu program

Terdapat dua cara untuk mendeteksi edge menggunakan menggunakan event detect, yaitu :

#### 2.2.1. Menggunakan IF

Disini kita akan memanggil method `GPIO.event_detected` dan memeriksa nilainya menggunakan if, apabila edge terdeteksi maka baris perintah if akan dieksekusi

```python
from RPi import GPIO

GPIO.setmode(GPIO.BCM)

channel = 15
GPIO.setup(channel, GPIO.IN)

# menambahkan deteksi edge rising
GPIO.add_event_detect(channel, GPIO.RISING)

while(True):
  # periksa apakah terjadi edge rising pada channel 15
  if GPIO.event_detected(channel):
    print("Input High")
```

#### 2.2.2. Menggunakan Callback

Disini kita akan membuat method baru yang akan dijalankan setiap kali edge terdeteksi, method ini disebut dengan callback

```python
from RPi import GPIO

GPIO.setmode(GPIO.BCM)

channel = 15
GPIO.setup(channel, GPIO.IN)

# method yang dijalankan apabila edge rising terdeteksi
def my_callback(channel):
  print("Input High")

# menambahkan deteksi edge rising kemudian menjalankan callback
GPIO.add_event_detect(channel, GPIO.RISING, callback=my_callback)
```

#### 2.2.3. Tambahan : Switch Debounce

Terkadang method callback yang kita buat terpanggil lebih dari satu kali ketika suatu edge terdeteksi, ini disebut dengan switch debounce, untuk menangani masalah ini kita bisa menambahkan `bouncetime` pada saat menambahkan deteksi edge

```python
GPIO.add_event_detect(channel, GPIO.RISING, callback=my_callback, bouncetime=200)
```
