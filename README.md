# Jarkom-Modul-1-C08-2022

## Anggota Kelompok

1. 5025201043 - Fahmi Muhazir
2. 5025201204 - Moh Akmal Ali Dzikri
3. 5025201214 - Ferry Nur Alfian Eka Putra

Soal
## 1. Mahasiswa diminta untuk mencari informasi dari file `.pcap` yang diberikan. Tujuan pencarian tersebut adalah untuk menemukan web server yang digunakan pada "monta.if.its.ac.id" .

Untuk itu, diterapkan filter yang dapat menampilkan semua paket dengan protokol HTTP dan host `monta.if.its.ac.id` .

Jawaban : Menggunakan display filter 
```
tcp contains monta.if.its.ac.id
```
sehingga mendapatkan hasil 
![Screenshot (1453)](https://user-images.githubusercontent.com/103355300/192077689-a7373d83-69be-4f39-9cf6-e4d08d2e0de2.png)

Selanjutnya "follow tcp stream" dari salah satu package untuk mendapat informasi tentang webserver yang digunakan yaitu "nginx/1.10.3"
![Screenshot (1462)](https://user-images.githubusercontent.com/103355300/192078046-0c2ba108-d2f3-4c2a-b8ff-591c8eee1f4d.png)

## 2. Mahasiswa diminta untuk mencari informasi dari file `.pcap` yang diberikan. Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq ?

Untuk itu, diterapkan filter yang menampilkan semua paket protokol HTTP dan string "detail"
Jawaban: Menggunakan display filter
```
http contains "detail"
```
sehingga mendapatkan hasil

![Screenshot (1466)](https://user-images.githubusercontent.com/103355300/192079244-d2c9e174-1190-4dd9-83e5-8e42a16f5413.png)

Selanjutnya "follow tcp stream" dan didapatkan link sebagai berikut : http://monta.if.its.ac.id/index.php/topik/detailTopik/194 
![Screenshot (1467)](https://user-images.githubusercontent.com/103355300/192079405-d04102fe-1edf-4bdd-a932-bc4aa3a6190f.png)
sehingga mendapatkan hasil seperti ini :
![WhatsApp Image 2022-09-19 at 21 36 54](https://user-images.githubusercontent.com/103355300/192079579-ec03d9f7-2572-4b4e-b977-094ce96db436.jpeg)

Dengan ditemukannya judul Topik TA yang dibuka : "Evaluasi untuk kerja User Space Filesystem (FUSE)"

## 3. Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!
Kata kunci pada soal ini adalah "**menuju**", dapat disimpulkan bahwa attribut filternya berupa dst (destination). Maka kita bisa menerapkan filternya sebagai berikut: 
```
tcp.dstport == 80 || udp.dstport == 80 
```
![image](https://user-images.githubusercontent.com/80556314/192085007-09f5869e-3dc2-4f8c-9e2f-e2e375a84d05.png)

tcp dan udp merupaka protokol, dstport merupakan filter yang kita cari untuk menampilkan paket yang menuju port 80. 

## 4. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!
Kata kunci pada soal ini adalah "**berasal**", dapat disimpulkan bahwa attribut filternya berupa src (source). Maka kita bisa menerapkan filternya sebagai berikut : 
```
tcp.srcport == 21 || udp.srcport == 21 
```
![image](https://user-images.githubusercontent.com/80556314/192085048-66bc37f0-28b9-40a3-a003-4cbdf6c0350b.png)

tcp dan udp merupaka protokol, dstport merupakan filter yang kita cari untuk menampilkan paket yang **berasal** dari port 21. 

## 5. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!
Kata kunci pada soal ini adalah "**berasal**", dapat disimpulkan bahwa attribut filternya berupa src (source). Maka kita bisa menerapkan filternya sebagai berikut : 
```
tcp.srcport == 443 || udp.srcport == 443
```
![image](https://user-images.githubusercontent.com/80556314/192085065-8f145bda-3122-460f-bb6a-725c091825f9.png)

tcp dan udp merupaka protokol, dstport merupakan filter yang kita cari untuk menampilkan paket yang **berasal** dari port 443.

## 6. Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id !
Pada soal ini bisa dilakukan seperti soal sebelum nya, tapi yang menjadi kendala bagaimana kita bisa mendapat **IP** dari website lipi?. Caranya adalah kita dapat menggunakan command prompt dengan command 
```
"tracert lipi.go.id". 
```
![image](https://user-images.githubusercontent.com/80556314/192085108-3a9bcedc-7fe8-46cb-84f3-718ca4e3309f.png)

Barulah kita mendapatkan ip dari website selanjutnya tinggal menggunakan filter seperti berikut:
```
ip.dst == 203.160.128.158
```
![image](https://user-images.githubusercontent.com/80556314/192085150-6e49cb79-6e65-4617-91c4-0423f9de6c23.png)

paket yang kita cari jelas menuju ke website lipi maka dari itu kita menggunakan ipnya dan dst sebagai attribut filternya.
