# NodeMCU
Merupakan sebuah *microcontroller* yang sudah dilengkapi dengan ***module ESP8266***. Namun, sejarah  dari **nodemcu** sendiri juga merupakan pengembangan dari module ***ESP8266*** yang dilengkapi dengan USB Port yang dapat digunakan sebagai power supply maupun flashing.

Awalnya **NodeMCU** menggunakan firmware **eLua** *(Embedded Lua)* dan bahasa pemrograman Lua (Bahasa lua merupakan bahasa yang hampir mirip dengan bahasa javascript). Namun karena board *NodeMCU* ini merupakan project *open source* sehingga banyak yang mengembangkan sehingga dapat didevelop menggunakan berbagai firmware salah satunya menggunakan **micropython** yang akan digunakan pada miniclass ini.



## Versi NodeMCU
1. V1 (Generasi Pertama / board v0.9)
   Board versi 0.9 sering disebut di pasar sebagai V.1 adalah versi asli yang berdimensi 47mm x 31mm. Memiliki inti ESP-12 dengan flash memory berukuran 4MB
   
2. V2 (Generasi Kedua / board v1.0)
   Generasi kedua adalah pengembangan dari versi sebelumnya, dengan chip yang ditingkatkan dari sebelumnya ESP12 menjadi ESP12E. Dan IC Serial diubah dari CHG340 menjadi  CP2102

3. V3 (Generasi Ketiga / board v1.0 / Versi unofficial)
   belum ada versi resmi untuk V3 NodeMCU. V3 hanyalah versi yang diciptakan oleh produsen LoLin dengan perbaikan minor terhadap V2. Diklaim memiliki antarmuka USB yang lebih cepat.
   
   *Note : Pada miniclass ini akan menggunakan **NodeMCU V3***
   
   

## Pin Pada NodeMCU
![](img/2-nodemcu-v3-pinout.png)
Diatas merupakan gambaran dari pinout **NodeMCU**. Berikut merupakan penjelasan dari setiap pin tersebut :

| Pin  | Penjelasan                                                   |
| ---- | ------------------------------------------------------------ |
| RST  | ***RESET*** digunakan untuk melakukan reset pada board NodeMCU. |
| Vin  | ***POWER***, digunakan untuk mengambil daya dimana daya yang keluar sama dengan daya yang masuk pada board. |
| 3.3v | ***POWER***, digunakan untuk mengambil daya sebesar 3.3v.    |
| GND  | ***GROUND***, digunakan untuk mengambil sumber *(-)*         |
| GPIO | Terminal yang digunakan untuk input output data              |



## Referensi
[nodemcu.com](https://www.nodemcu.com/index_en.html)
[kelasrobot.com](https://kelasrobot.com/apa-itu-nodemcu-esp8266-bagaimana-cara-pakenya/)