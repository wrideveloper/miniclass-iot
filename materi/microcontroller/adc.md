# Analog Digital Converter (ADC)

## 1. Penjelasan ADC

ADC digunakan untuk membaca nilai dari sensor analog seperti potentiometer, LDR, dan lain lain.

## 2. Cara Menggunakan ADC

```python
# import class ADC dari package machine
from machine import ADC

# setup ADC
pot = ADC(0)

# membaca nilai ADC
pot.read()
```

Disitu kita membuat variable bernama `pot` yang digunakan untuk menyimpan object dari class `ADC`. Parameter yang dimasukkan adalah `0` karena pada nodemcu hanya mensupport pin `A0` untuk membaca nilai analog
