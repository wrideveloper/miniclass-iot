# Penerapan OOP

Disini kita akan mencoba menerapkan OOP untuk membuat script button dan LED agar script kita terlihat lebih rapi dan clean

## Langkah - Langkah

### 1. Membuat Class LED

Class ini digunakan untuk menyalakan dan mematikan LED

```python
# Led.py

from RPi import GPIO

class Led:
    def __init__(self, pin, pinMode):
        self.pin = pin
        GPIO.setmode(pinMode)
        GPIO.setup(pin, GPIO.OUT)

    def on(self):
        GPIO.output(self.pin, GPIO.HIGH)

    def off(self):
        GPIO.output(pin, GPIO.LOW)
```

### 2. Membuat Class Button

Class ini digunakan untuk mengetahui kondisi dari button apakah sedang ditekan atau tidak

```python
# Button.py

from RPi import GPIO

class Button:
    def __init__(self, pin, pinMode):
        self.pin = pin
        GPIO.setmode(pinMode)
        GPIO.setup(
            pin,
            GPIO.IN,
            pull_up_down=GPIO.PUD_DOWN
        )

    def isPressed(self):
        return GPIO.input(self.pin)
```

### 3. Menggunakan Class

Setelah class `Led` dan `Button` dibuat, sekarang kita tinggal menggunakan seperti berikut

```python
# main.py

from RPi import GPIO
from Button import Button
from Led import Led

button = Button(14, GPIO.BCM)
led = Led(15, GPIO.BCM)

while(True):
    if(button.isPressed()):
        led.on()
    else:
        led.off()
```
