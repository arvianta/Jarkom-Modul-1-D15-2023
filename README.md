# Jarkom-Modul-1-D15-2023

## Detail Kelompok

### Nama Kelompok

Kelas: Jarkom D
<br>
Kelompok: D15

### Anggota Kelompok

<table>
  <thead>
    <tr>
      <th>Nama</th>
      <th>NRP</th>
      <th>Angkatan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Rayhan Arvianta Bayuputra </td>
      <td>5025211217</td>
      <td>2021</td>
    </tr>
    <tr>
      <td>Yehezkiel Wiradhika</td>
      <td>5025201086</td>
      <td>2020</td>
    </tr>
  </tbody>
</table>

## Soal dan Jawaban

### Soal

<ol type="1">
  <!-- no 1 -->
  <li>
    User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
    <ol type='a'>
      <li>Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?</li>
      <li>Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?</li>
      <li>Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?</li>
      <li>Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?</li>
    </ol>
  </li>
  <!-- no 2 -->
  <li>Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!</li>
  <!-- no 3 -->
  <li>Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
    <ol type='a'>
      <li>Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?</li>
      <li>Protokol layer transport apa yang digunakan?</li>
    </ol>
  </li>
  <!-- no 4 -->
  <li>Berapa nilai checksum yang didapat dari header pada paket nomor 130?</li>
  <!-- no 5 -->
  <li>Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
    <ol type='a'>
      <li>Berapa banyak packet yang berhasil di capture dari file pcap tersebut?</li>
      <li>Port berapakah pada server yang digunakan untuk service SMTP?</li>
      <li>Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?</li>
    </ol>
  </li>
  <!-- no 6 -->
  <li>
  Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
  </li>
  <!-- no 7 -->
  <li>
  Berapa jumlah packet yang menuju IP 184.87.193.88?
  </li>
  <!-- no 8 -->
  <li>
  Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad) 
  </li>
  <!-- no 9 -->
  <li>
  Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
  </li>
  <!-- no 10 -->
  <li>Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet</li>
</ol>

### Jawaban

#### Soal 1

<strong>Soal</strong>: User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

Dari soal di atas kita tahu bahwa kita akan melakukan filter terhadap display filter yang memiliki tipe protokol FTP (File Transfer Protocol) dari kata kunci "mengunggah suatu file" kemudian kita juga akan memfilter dari hasil filter protokol FTP tersebut kata kunci untuk mengupload / mengunggah suatu file, yakni "STOR" yang merupakan perintah upload file

Berikut merupakan langkah pengerjaannya:

Buka wireshark kemudian buka file soal1.pcapng

<img src="assets/soal 1/1.png">
<img src="assets/soal 1/2.png">

maka akan muncul tampilan sebagai berikut
<img src="assets/soal 1/3.png">

Kemudian lakukan display filter dengan kata kunci "ftp" untuk memfilter response-request bertipe ftp

<img src="assets/soal 1/4.png">
<img src="assets/soal 1/5.png">

setelah itu dari hasil display filter ftp, kita melakukan search packet list dengan keyword "STOR" yang menandakan pengunggahan suatu file

<img src="assets/soal 1/6.png">

<strong>soal poin a</strong>: Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?

dari paket tersebut, kita analisis sequence numbernya di layer TCP (Transport Control Protocol)

<img src="assets/soal 1/7.png">

kita akan mendapat sequence number (raw) dari packet tersebut

<img src="assets/soal 1/8.png">

setelah kita membuka netcat soal akan muncul pertanyaan dan jika kita jawab soal poin a dengan sequence number (raw) yang kita dapatkan di atas, maka akan muncul sebagai tampilan berikut

<img src="assets/soal 1/9.png">

<strong>soal poin b</strong>: Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?

dari TCP layer yang kita lihat sebelumnya, kita juga akan mendapat acknowledge number (raw) sebagai berikut:

<img src="assets/soal 1/10.png">
<img src="assets/soal 1/11.png">

<strong>soal poin c</strong>: Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

dari packet 147 (yang merupakan packet yang mengandung request file menggunakan protokol ftp) kita dapat melihat packet response request tersebut tepat di bawahnya (setelah kita melakukan filter ftp), yakni packet 149.

<img src="assets/soal 1/12.png">

Hal ini dapat kita konfirmasi dengan melihat source dan destination kedua packet yang saling matching sebagai berikut:

<img src="assets/soal 1/13.png">

dari situ kita akan mendapat sequence number (raw) nya dengan melihat pada layer tcp packet tersebut di bagian sequence number (raw) dan apabila kita mengechecknya menggunakan netcat pada poin c, kita akan mendapatkan hasil sebagai berikut:

<img src="assets/soal 1/14.png">

<strong>soal poin d</strong>: Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

apabila kita melihat ack number dari packet tersebut, kita akan mendapatkan value sebagai berikut:

<img src="assets/soal 1/15.png">

dan apabila kita mengechecknya dengan netcat:

<img src="assets/soal 1/16.png">

voila! Kita mendapatkan correct answer dan flagnya.

#### Soal 2

<strong>Soal</strong>: Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

Dari situ kita tahu bahwa web portal merupakan suatu file html yang terdapat pada protokol HTTP, sehingga kita akan melakukan display filter HTTP pada soal ini

Langkah pengerjaan:

pertama, buka soal2.pcapng, kemudian kita lakukan display filter HTTP sebagai berikut:

<img src="assets/soal 2/1.png">

setelah itu, kita lakukan search <strong>packet list</strong> "GET / HTTP/1.1" untuk mendapatkan <strong>request packet</strong> web portal, karena website portal biasanya bertipe request GET dan root folder "/" sebagai berikut:

<img src="assets/soal 2/2.png">

dari ip yang didapatkan sebagai berikut:

<img src="assets/soal 2/3.png">

kita kemudian melakukan filter ip destination dari request tersebut tetapi kita memfilter ip souce disini karena kita menginginkan response dari ip tersebut, sebagai berikut:

<img src="assets/soal 2/4.png">

dari hasil filter tersebut, kita menemukan beberapa response, tapi yang kita inginkan merupakan response yang memiliki tipe file text/html karena web portal merupakan sebuah website bertipe file html

<img src="assets/soal 2/5.png">

Dari situ, apabila kita membuka layer HTTP dari paket tersebut (paket 1092 [mengandung website portal]) kita akan melihat server yang digunakan packet tersebut

<img src="assets/soal 2/6.png">

apabila kita mengetesnya menggunakan netcat, kita akan mendapatkan flagnya

<img src="assets/soal 2/7.png">

#### Soal 3

<strong>Soal</strong>: Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut

hal yang pertama kita lakukan adalah membuka soal3.pcapng menggunakan wireshark kemudian membuka netcat program yang telah disediakan melalui terminal linux

<strong>soal poin a</strong>: Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702

dari poin di atas kita melakukan display filter sebagai berikut

```
ip.addr == 239.255.255.250 && (tcp.port == 3702 or udp.port == 3702)
```

penjelasan dari filter diatas adalah kita mengcapture semua ip yang berasal dan menuju ke port <code>239.255.255.250</code> dengan filter <code>ip.addr == 239.255.255.250</code> kemudian karena kita menginginkan kondisi dimana filter mencakup filtter ip address sebelumnya dan yang menuju ke port 3702 dan karena hanya terdapat 2 macam transport layer dari port, yakni tcp dan udp kita mengcapture semua kemungkinan yang ada dengan <code>tcp.port == 3702 or udp.port == 3702</code> dan menggabungkannya menjadi seperti sebagai berikut:

<img src="assets/soal 3/1.png">

dari situ kita harus melihat ke bagian bawah tampilan wireshark dan kita akan mendapatkan sebagai berikut:

<img src="assets/soal 3/2.png">

apabila kita mengechecknya menggunakan program netcat pada poin a akan didapat hasil sebagai berikut:

<img src="assets/soal 3/3.png">

<strong>soal poin b</strong>: Protokol layer transport apa yang digunakan?

Dari filter, kita hanya mendapatkan paket2 yang ber protokol UDP

<img src="assets/soal 3/4.png">

apabila kita mengecheck jawaban tersebut dengan netcat kita akan mendapatkan flagnya:

<img src="assets/soal 3/5.png">
