# WiFi Connection

## 1. Penjelasan

Agar NodeMCU dapat mengirim data ke internet. Maka perlu dilakukan koneksi ke Wifi terlebih dahulu

## 2. Jenis Interface

Terdapat dua jenis interface pada NodeMCU. Yaitu :

### 2.1. Access Point

Berguna untuk menyambungkan perangkat lain ke NodeMCU. Berikut cara untuk mengakses interface access point

```python
import network
ap_if = network.WLAN(network.AP_IF)
```

### 2.2. Station

Berguna untuk menyambungkan NodeMCU ke WiFi. Berikut cara untuk mengakses interface station

```python
import network
sta_if = network.WLAN(network.STA_IF)
```

## 3. Method yang dapat Digunakan

Setelah memilih dan melakukan instansiasi interface. Maka kita dapat menggunakan method - method berikut

`active()` - memeriksa apakah interface menyala atau tidak

`active(Boolean)` - menyalakan atau mematikan interface

`isconnected()` - memeriksa apakah interface tersambung atau tidak

`connect('<your ESSID>', '<your password>')` - menyambungkan interface dengan wifi

`ifconfig()` - memeriksa konfigurasi IP dari interface

## 4. Cara Menyambungkan NodeMCU ke WiFi

Berikut cara untuk menyambungkan NodeMCU ke WiFi

```python
# import module network
import network

# mengakses interface station
sta_if = network.WLAN(network.STA_IF)

# periksa apakah interface station belum tersambung ke wifi
if not sta_if.isconnected():
  print('connecting to network...')

  # menyalakan interface station
  sta_if.active(True)

  # menyambungkan interface station ke wifi
  sta_if.connect('<essid>', '<password>')

  # menunggu hingga interface tersambung
  while not sta_if.isconnected():
    pass

  # tampilkan konfigurasi IP saat interface station tersambung
  print('network config:', sta_if.ifconfig())
```
