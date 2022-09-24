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
