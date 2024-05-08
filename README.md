# Jarkom-Modul-2-IT28-2024

## Anggota Kelompok IT28

| Nama  | NRP | 
| ----------- | ----------- |
| Angella Christie | 5027221047 | 
| Ahmad Fauzan Daniswara | 5027221057 | 

## No.1
Untuk membantu pertempuran di Erangel, kamu ditugaskan untuk membuat jaringan komputer yang akan digunakan sebagai alat komunikasi. Sesuaikan rancangan Topologi dengan rancangan dan pembagian yang berada di link yang telah disediakan, dengan ketentuan nodenya sebagai berikut :
- DNS Master akan diberi nama Pochinki, sesuai dengan kota tempat dibuatnya server tersebut
- Karena ada kemungkinan musuh akan mencoba menyerang Server Utama, maka buatlah DNS Slave Georgopol yang mengarah ke Pochinki
- Markas pusat juga meminta dibuatkan tiga Web Server yaitu Severny, Stalber, dan Lipovka. Sedangkan Mylta akan bertindak sebagai Load Balancer untuk server-server tersebut

### Hasil Pengerjaan 
- Topologi yang digunakan 
![image](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/7b6bb1d5-3ccb-426f-9a52-0e4e09ab2de5)

- Mengecek apakah terhubung ke internet atau tidak dengan melakukan ping
  - Erangel
  ![1-2](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/c4896e8a-1e47-4c20-9c23-18ea4ffe7ba3)

  - Pochinki
    ![1-3](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/b3b6efac-1572-4feb-9954-7a0bb823c4f5)

  - Georgopol
    ![image](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/715a56ec-078d-4f98-bc10-f93ba6a063dc)

  - Stalber
    ![1-4](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/9386dc67-3d00-4c0a-a28f-dc0a1b36b9f1)

  - Serveny
    ![image](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/c7c40865-77f3-4254-bd3c-3f83e4dc4ed5)

  - Lipovka
    ![image](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/3f48ddc0-b11f-444c-aa26-25f33a0d3838)

## No. 2
Karena para pasukan membutuhkan koordinasi untuk mengambil airdrop, maka buatlah sebuah domain yang mengarah ke Stalber dengan alamat airdrop.xxxx.com dengan alias www.airdrop.xxxx.com dimana xxxx merupakan kode kelompok. Contoh : airdrop.it01.com

## No.3
Para pasukan juga perlu mengetahui mana titik yang sedang di bombardir artileri, sehingga dibutuhkan domain lain yaitu redzone.xxxx.com dengan alias www.redzone.xxxx.com yang mengarah ke Severny

## No.4
Markas pusat meminta dibuatnya domain khusus untuk menaruh informasi persenjataan dan suplai yang tersebar. Informasi persenjataan dan suplai tersebut mengarah ke Mylta dan domain yang ingin digunakan adalah loot.xxxx.com dengan alias www.loot.xxxx.com

### Hasil Pengerjaan no 2-4

- Script yang dibuat adalah pochinki.sh
![image](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/1231ccad-eb85-44c1-98c0-2d37369a329c)

![image](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/4e421901-c218-428f-b6ed-d90941c4e99f)

- Output yang dihasilkan saat testing dengan ping
  - airdrop.it28.com
  ![2](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/aa254852-e146-414b-a7f9-7ce620977829)

  - redzone.it28.com
  ![3](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/ac880b54-4211-4baf-a237-774d5c8264a7)

  - loot.it28.com
  ![4](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/c435c357-263a-4afb-b945-6745c99f4289)

## No.5
Pastikan domain-domain tersebut dapat diakses oleh seluruh komputer (client) yang berada di Erangel

### Hasil testing semua domain yang dibuat pada no 2-4
- ![5](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/70be6424-1428-45eb-8c53-598182a97e80)


## No.6
Beberapa daerah memiliki keterbatasan yang menyebabkan hanya dapat mengakses domain secara langsung melalui alamat IP domain tersebut. Karena daerah tersebut tidak diketahui secara spesifik, pastikan semua komputer (client) dapat mengakses domain redzone.xxxx.com melalui alamat IP Severny (Notes : menggunakan pointer record)

- Menambahkan script .arpa pada named.config.local dengan membuka `nano /etc/bind/jarkom28/named.config.local`
  
  ![named config](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/256bb037-9385-4eaf-9dd5-13a5c01c7c08)

- Membuat file script baru untuk menjalankan `.arpa`

  ![bash no 6](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/46b003dd-5682-4e72-9134-9247838e55c3)

- Output yang dihasilkan setelah melakukan testing
  ![output](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/8143781d-f1c5-4188-80cf-4718b902d167)

## No.7
Akhir-akhir ini seringkali terjadi serangan siber ke DNS Server Utama, sebagai tindakan antisipasi kamu diperintahkan untuk membuat DNS Slave di Georgopol untuk semua domain yang sudah dibuat sebelumnya

### Hasil Pengerjaan 
- script yang dibuat
  Pada terminal `Pochinki`
  ![image](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/31d170de-ee4a-428e-aeb8-fca011ab4ba8)

Pada terminal `Georgopol`
![image](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/a3e85076-4445-4ee6-97c1-636f21b95959)

- Melakukan testing dengan melakukan ping 
  ![7](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/cb44431f-ed2b-452d-93e7-8d3ad0051e3c)


## No.8
Kamu juga diperintahkan untuk membuat subdomain khusus melacak airdrop berisi peralatan medis dengan subdomain medkit.airdrop.xxxx.com yang mengarah ke Lipovka

### Hasil pengerjaan 
- script yang digunakan
  ![image](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/44c785f0-0eea-4086-9dd5-508e64e89e14)

- Hasil testing dengan melakukan ping
  ![8](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/2c0b6689-29fa-4e78-a040-98d84917eccc)


## No.9
Terkadang red zone yang pada umumnya di bombardir artileri akan dijatuhi bom oleh pesawat tempur. Untuk melindungi warga, kita diperlukan untuk membuat sistem peringatan air raid dan memasukkannya ke subdomain siren.redzone.xxxx.com dalam folder siren dan pastikan dapat diakses secara mudah dengan menambahkan alias www.siren.redzone.xxxx.com dan mendelegasikan subdomain tersebut ke Georgopol dengan alamat IP menuju radar di Severny

## No.10
Markas juga meminta catatan kapan saja pesawat tempur tersebut menjatuhkan bom, maka buatlah subdomain baru di subdomain siren yaitu log.siren.redzone.xxxx.com serta aliasnya www.log.siren.redzone.xxxx.com yang juga mengarah ke Severny

## No.11
Setelah pertempuran mereda, warga Erangel dapat kembali mengakses jaringan luar, tetapi hanya warga Pochinki saja yang dapat mengakses jaringan luar secara langsung. Buatlah konfigurasi agar warga Erangel yang berada diluar Pochinki dapat mengakses jaringan luar melalui DNS Server Pochinki

## No.12
Karena pusat ingin sebuah website yang ingin digunakan untuk memantau kondisi markas lainnya maka deploy lah webiste ini (cek resource yg lb) pada severny menggunakan apache

## No.13
Tapi pusat merasa tidak puas dengan performanya karena traffic yag tinggi maka pusat meminta kita memasang load balancer pada web nya, dengan Severny, Stalber, Lipovka sebagai worker dan Mylta sebagai Load Balancer menggunakan apache sebagai web server nya dan load balancernya

## No.14
Mereka juga belum merasa puas jadi pusat meminta agar web servernya dan load balancer nya diubah menjadi nginx

## No.15
Markas pusat meminta laporan hasil benchmark dengan menggunakan apache benchmark dari load balancer dengan 2 web server yang berbeda tersebut dan meminta secara detail dengan ketentuan:
- Nama Algoritma Load Balancer
- Report hasil testing apache benchmark 
- Grafik request per second untuk masing masing algoritma. 
- Analisis

## No.16
Karena dirasa kurang aman karena masih memakai IP, markas ingin akses ke mylta memakai mylta.xxx.com dengan alias www.mylta.xxx.com (sesuai web server terbaik hasil analisis kalian)

## No.17
Agar aman, buatlah konfigurasi agar mylta.xxx.com hanya dapat diakses melalui port 14000 dan 14400.

## No.18
Apa bila ada yang mencoba mengakses IP mylta akan secara otomatis dialihkan ke www.mylta.xxx.com

## No.19
Karena probset sudah kehabisan ide masuk ke salah satu worker buatkan akses direktori listing yang mengarah ke resource worker2

## No.20
Worker tersebut harus dapat di akses dengan tamat.xxx.com dengan alias www.tamat.xxx.com

## No 9-20 menyerah mas :)
![image](https://github.com/Angel0010/Jarkom-Modul-2-IT28-2024/assets/131789727/273f906c-cb99-4106-851d-943247bc16fb)
