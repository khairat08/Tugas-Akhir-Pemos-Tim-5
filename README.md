# Tugas-Akhir-Pemos-Tim-5
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Pemodelan Oseanografi 2022. Repositori ini memuat teori, metode, analisis, dan file berupa script python (py) yang dapat memproses beberapa persamaan model seperti adveksi-difusi dan hidrodinamika 1D serta 2D untuk memodelkan suatu fenomena atau dinamika oseanografi.
# INSTALASI MINICONDA DAN LIBRARY 

## MODUL 1 ADVEKSI-DIFUSI 1D
### 1.1 TEORI DASAR
### 1.1.1 Adveksi 1D
  - Persamaan Adveksi Adalah salah satu persamaan diferensial parsial yang memodelkan pergerakan suatu konsentrat dalam cairan yang mengalir, dengan asumsi konsentrat tersebut tidak mengalami proses difusi di dalam cairan. adveksi berkaitan erat dengan aktivitas atau pergerakan suatu benda dari suatu tempat ke tempat lainnya untuk waktu tertentu. persamaan adveksi merupakan bentuk khusus dari persamaan diferensial untuk hukum kekekalan.
  - Persamaan umum Adveksi 1D:
  
  

- Dimana :
   F : Konsentrasi zat pelarut (mg/L)
   u : Kecepatan
   x : ruang sumbu horisontal (meter)
   t : waktu (detik)
- Metode Pendekatan dalam pemodelan numerik secara umum dibagi menjadi 2 pendekatan yaitu eksplisit dan implisit. metode eksplisit dibagi menjadi 3 yaitu:
- FTCS (Forward in Time Central in Space)
  Metode FTCS merupakan gabungan dari selisih maju terhadap waktu dan selisih pusat terhadap ruang. Solusi FTCS juga termasuk ke dalam solusi stabil bersyarat.
- Syarat kestabilan:
  

- Leapfrog (CTCS)
Metode beda hingga ini merupakan perluasan dari metode beda tengah (central difference) terhadap ruang dan waktu. Skema Leapfrog didapatkan dari turunan deret taylor, ini adalah skema konsisten. Leapfrog ini akan konsisten apabila nilai C ≤1.

![image](https://user-images.githubusercontent.com/105967489/169653369-2e0b4f94-18e2-474d-bdc4-715cadc843c0.png)


- Upstream
 Metode ini menggunakan pendekatan beda maju untuk turunan waktu, sedangkan untuk turunan terhadap ruang dilakukan dengan melihat arah kecepatan u. jika > 0 maka turunan terhadap menggunakan pendejatan beda mundur. Sebaliknya jika u < 0 maka digunakan pendekatan beda maju. Stabilitas metode upstream adalah sebagai berikut:
- Jika u > 0, turunan terhadap ruang menggunakan pendekatan beda mundur.
 ![image](https://user-images.githubusercontent.com/105967489/169652264-8bd6d155-a798-45e3-9796-25bc1bd43538.png)
- Jika u < 0, turunan terhadap ruang menggunakan pendekatan beda maju.
 ![image](https://user-images.githubusercontent.com/105967489/169652271-5894b538-197d-4d27-9498-ee546a24e993.png)

## 1.2 METODE

## MODUL 2 ADVEKSI-DIFUSI 2D
### 2.1 TEORI DASAR
### 2.2 METODE
### 2.3 SCRIPT DAN HASIL
### 2.4 ANALISIS

## MODUL 3 HIDRODINAMIKA 1D
### 3.1 TEORI DASAR
## 3.2 METODE
## 3.3 SCRIPT DAN HASIL
## 3.4 ANALISIS

## MODUL 4 HIDRODINAMIKA 2D
### 4.1 TEORI DASAR
### 4.2 METODE
1.	Buka miniconda lalu ketik jupyter notebook uuntuk membuka jupyter notebook sebagai text editor
 import matplotlib.pyplot as plt

from siphon.simplewebservice.ndbc import NDBC

df = NDBC.realtime_observations('51101')
df.head()

fig, (ax1, ax2, ax3) = plt.subplots(3, 1, figsize=(12, 10))
ax2b = ax2.twinx()

ax1.plot(df['time'], df['pressure'], color='darkorange')
ax1.set_ylabel('Pressure [hPa]')
fig.suptitle('Baiq Lista Azkia Sulhana_26050120120004_Ose A', fontsize=18)

ax2.plot(df['time'], df['wind_speed'], color='red')
ax2.plot(df['time'], df['wind_gust'], color='olive', linestyle='--')
ax2b.plot(df['time'], df['wind_direction'], color='mediumblue', linestyle='-')
ax2.set_ylabel('Wind Speed [m/s]')
ax2b.set_ylabel('Wind Direction')

ax3.plot(df['time'],df['water_temperature'], color='deepskyblue')
ax3.set_ylabel('Water Temperature [degC]')

plt.show()
2.	Tuliskan script diatas
![image](https://user-images.githubusercontent.com/96079752/169655150-dacf34f4-5dec-49de-9459-6701322ebbf8.png)

3.	Klik run untuk menjalankan script
![image](https://user-images.githubusercontent.com/96079752/169655308-9e349f8a-89ce-435f-8b6e-df34cf960f60.png)

4.	Setelah  menunggu beberapa saat akan muncul hasil seperti berikut
![image](https://user-images.githubusercontent.com/96079752/169655608-fef24dc3-92e1-4304-8d1b-92a3721d738d.png)
 
5.	Buka lama NDBC_NOAA untuk melihat lokasi station yang diperoleh sesuai NIM dan pada kolom Station ID Search ditulis ID lalu diklik Go
![image](https://user-images.githubusercontent.com/96079752/169655359-707dbf51-564f-4d62-bc7a-ec6860293f7c.png)

6.	Maka akan muncul informasi mengenai lokasi stasiun sesuai ID yang dimasukkan seperti dibawah ini
![image](https://user-images.githubusercontent.com/96079752/169655384-2845ce3a-bc17-4f2c-9961-4f9a3e0b41a4.png)
![image](https://user-images.githubusercontent.com/96079752/169654780-becab836-e8f2-4125-8ce8-febf62ba8936.png)


### 4.3 SCRIPT DAN HASIL
Script
![image](https://user-images.githubusercontent.com/96079752/169655538-c5dcced1-9761-49dd-b7b8-3043734cced0.png)

Hasil
![image](https://user-images.githubusercontent.com/96079752/169655588-deb556af-be78-4347-8ecc-76530357ee5d.png)


### 4.4 ANALISIS
<P> Data parameter yang digunakan diantaranya tekanan, kecepatan angin, arah angin, dan temperatur air pada periode 5 minggu yaitu dari tanggal 15 maret 2022 sampai 22 april 2022. Grafik diatas diperoleh dari hasil ekstrak data NDBC (National Data Buoy Center) milik NOAA yang kemudian diplot-kan dalam bentuk grafik. Lokasi pengamatan yaitu di stastion ID 51101 yang berada di tengah samudra tepatnya di bagian samudra pasifik utara pada koordinat 24.361 N 162.075 W (24°21'40" N 162°4'30" W). Berdasarkan hasil diatas, terdapat 3 grafik dengan warna yang berbeda. Grafik pertama merupakan grafik tekanan, dari gambar tersebut tekanan di lokasi yang ditinjau menunjukkan nilai terendah sebesar 1012 hPa dan yang tertinggi 1025 hPa. Namun di setiap minggu nya grafik menggambarkan fluktuasi tekanan yang tidak konstan dimana tekanan cenderung naik turun dengan nilai terendah berada di akhir minggu pertama. Begitupula dengan grafik kecepatan angin dan arah angin yang menggambarkan fluktuasi naik turun dengan kecepatan angin tertinggi sebesar 13 m/s dan yang terendah sebesar 0,1 m/s. Arah angin berkisar di 30-100°, namun pada beberapa hari arah angin menunjukkan nilai yang tidak biasanya yaitu mencapai 320°. Hal ini mungkin bisa terjadi karena pada saat pencatatan data oleh buoy terjadi cuaca sehingga mempengaruhi pengukuran buoy di daerah tersebut yang mana membuat data arah pergerakan angin berbeda dari biasanya. Mengingat juga letak buoy yang berada di tengah samudra pasifik sangat memungkinkan untuk mendapat gangguan cuaca. Anomali yang terjadi ini dapat dikatakan hanyalah data error dan bukan siklon sebab menurut Ismail et al (2017), siklon tropis dapat terbentuk diatas lautan dengan suhu permukaan laut lebih dari 26˚C dan pada lintang kurang dari 5˚ siklon. Sedangkan dari data yang ada pada saat arah angin mencapai 320°, suhu permukaan laut tidak menghangat sampai nilai 26˚C, selain itu lokasi pencatatan tidak dilewati oleh siklon tropis. 
Untuk grafik ketika yaitu grafik temperatur yang digambarkan dengan warna biru langit menunjukkan fluktuasi yang tidak konstan dengan kisaran rat-rata berada di  24°C. Suhu tertinggi berada pada minggu pertama dengan nilai 25,2°C dan yang terendah terjadi pada minggu kedua dengan nilai 22,4°C. Dari grafik yang terlihat, suhu dan tekanan memiliki bentuk grafik yang berbanding terbalik, begitupula dengan suhu dan kecepatan angin. Artinya ketika suhu bernilai rendah, maka tekanan dan kecepatan angin tinggi. Sedangkan untuk hubungan tekanan dan kecepatan angin yaitu linier, sehingga bentuk grafik nya hampir sama. 
Tekanan udara pada permukaan bumi ditentukan oleh kerapatan massa udara. Makin rapat udara, tekanannya semakin tinggi. Kerapatan udara berhubungan erat dengan suhu, radiasi matahari, kelembaban dan gaya berat. Di suatu area dengan udara tipis, tekanan udara permukaan rendah. Di area dengan udara padat, tekanan di permukaan nya tinggi. Suhu dan tekanan sendiri memiliki hubungan yang terbalik dimana ketika suhu rendah maka tekanan tinggi disebabkan udara disana memiliki kerapatan massa yang tinggi. Sebaliknya, ketika daerah bersuhu tinggi maka tekanan udara diatasnya rendah karena kerapatan massa yang rendah. Perbedaan tekanan inilah yang selanjutnya membangkitkan pergerakan angin dan mempengaruhi kecepatan angin tersebut. Perbedaan tekanan udara pada daerah yang berbeda dengan ketinggian yang sama diakibatkan dari penerimaan radiasi matahari yang berbeda. Hal ini sejalan dengan Stewart (2008) yang menyatakan angin bergerak dari tekanan udara tinggi ke tekanan udara rendah dan kecepatan angin ditentukan oleh laju perubahan tekanan, dimana tekanan udara dapat mempengaruhi perubahan kecepatan angin.  Besar kecil nya kecepatan angin ini akan berhubungan dengan tinggi gelombang yang dibangkitkan oleh angin, ketika kecepatan angin nya tinggi maka gelombang di daerah tersebut juga akan semakin tinggi. 


## PENUTUP
