# Membuat Raspberry Menjadi Access Point

Pada tutorial ini kita akan belajar bagaimana cara membuat raspberry menjadi access point untuk mempermudah kita menghubungkan komputer dan raspberry tanpa perlu menggunakan kabel LAN

## 1. Install Server DHCP

Hal pertama yang harus kita lakukan adalah menginstall server DHCP, DHCP merupakan protokol yang digunakan untuk memberikan IP ke client yang terkoneksi pada suatu jaringan

```bash
sudo apt install dnsmasq
```

## 2. Konfigurasi IP Statis Pada Interface wlan0

Sebelum membuat server DHCP, kita perlu memberikan ip statis pada interface wlan0 raspberry, ketikkan perintah berikut untuk mengubah file konfigurasinya

```bash
sudo nano /etc/dhcpcd.conf
```

misalnya kita ingin memberikan ip statis 192.168.1.1 pada interface wlan0, maka ketikkan perintah berikut ke dalam file `dhcpcd.conf`

```bash
interface wlan0
static ip_address=192.168.1.1/24
```

## 3. Konfigurasi Server DHCP

Setelah itu kita dapat mengkonfigurasi server DHCP dengan menentukan berapa range IP yang akan diberikan ke client, ketikkan perintah berikut untuk mengubah file konfigurasinya

```bash
sudo nano /etc/dnsmasq.conf
```

misalnya kita ingin memberikan range IP antara 192.168.1.2 hingga 192.168.1.10, maka ketikkan perintah berikut ke dalam file `dnsmasq.conf`

```bash
interface=wlan0
  dhcp-range=192.168.1.2,192.168.1.10,255.255.255.0,24h
```

## 4. Install Hostapd

Hostapd merupakan paket yang digunakan untuk membuat access point pada linux, ketikkan perintah berikut untuk menginstall hostapd

```bash
sudo apt install hostapd
```

## 5. Konfigurasi Hostapd

Setelah diinstall kita perlu melakukan konfigurasi pada hostapd, untuk melakukannya kita perlu membuat file baru bernama `hostapd.conf`

```bash
sudo nano /etc/hostapd/hostapd.conf
```

Kemudian ketikkan perintah berikut ke dalam file `hostapd.conf`

```bash
interface=wlan0
bridge=br0
hw_mode=g
channel=7
wmm_enabled=0
macaddr_acl=0
auth_algs=1
ignore_broadcast_ssid=0
wpa=2
wpa_key_mgmt=WPA-PSK
wpa_pairwise=TKIP
rsn_pairwise=CCMP
ssid=NETWORK_NAME
wpa_passphrase=PASSWORD
```

silahkan ubah **NETWORK_NAME** dan **PASSWORD** dengan nama access point dan password access point

## 6. Memuat Konfigurasi Hostapd

Setelah membuat file `hostapd.conf`, maka kita perlu memuatnya dengan cara menyertakan direktori file tersebut ke file `/etc/default/hostapd`

```bash
sudo nano /etc/default/hostapd
```

pada file ini, carilah perintah `#DAEMON_CONF=””` yang berada pada bagian bawah, kemudian ubahlah dengan perintah berikut

```bash
DAEMON_CONF="/etc/hostapd/hostapd.conf"
```
