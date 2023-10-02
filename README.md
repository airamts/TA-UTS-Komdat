# Welcome to Our Project: Openrouteservice Maps💫
![alt text](assets/images/osr-img.jpg?raw=true)

**Oleh Kelompok 1 P1:**

| No. | Nama                               | NIM         |
| --- | ---------------------------------- | ----------- |
| 1   | Dhianita Shafa                     | G6401211016 |
| 2   | Tan, Maria Putri Ariyani           | G6401211049 |
| 3   | Muhammad Ariiq Arrafi              | G6401211062 |
| 4   | Dwi Fitriani Azhari                | G64012011072 |
| 5   | Medina Fitri Maulida               | G64012011096 |

## About Openrouteservice Maps

Openrouteservice Maps merupakan aplikasi yang memungkinkan pengguna untuk menghitung rute dan mendapatkan informasi navigasi di seluruh dunia. Layanan ini menyediakan berbagai pilihan perjalanan untuk berbagai mode transportasi. Beberapa mode transportasi yang dapat dipilih meliputi mobil, berbagai jenis sepeda, berjalan kaki, mendaki, kursi roda, dan kendaraan berat. Setiap mode transportasi ini menggunakan jaringan jalan yang telah disusun secara cermat sesuai dengan kebutuhan profilnya.

Selain itu, layanan ini juga memberikan kemungkinan untuk menyesuaikan masukan pengguna dengan pembatasan jenis jalan dan karakteristik kendaraan, sehingga pengguna dapat mengkustomisasi rute sesuai kebutuhan.


## Instalation

- Prasyarat, apa saja yang harus diinstal sebelumnya.
- Langkah instalasi dalam CLI.


## Configuration (opsional)

Setting server tambahan yang diperlukan untuk meningkatkan fungsi dan kinerja aplikasi, misalnya:
- batas upload file
- batas memori
- dll

Plugin untuk fungsi tambahan
- login dengan Google/Facebook
- editor Markdown
- dll


##  Maintenance (opsional)

Setting tambahan untuk maintenance secara periodik, misalnya:
- buat backup database tiap pekan
- hapus direktori sampah tiap hari
- dll


## Automation (opsional)

Skrip shell untuk otomatisasi instalasi, konfigurasi, dan maintenance.


## How to Use
### 1. Tampilan awal web
![alt text](assets/images/osr-img1.jpg?raw=true)
Web akan langsung menampilkan peta serta beberapa icon/fitur yang memiliki kegunaan berikut.
#### Sisi Kiri
| Icon/fitur                               | Kegunaan         |
| ---------------------------------- | ----------- |
| Icon menu                     | Membuka sidebar |
| Search bar           | Mencari tempat |
| Icon belok kanan           | Mencari rute dari satu tempat ke tempat lain |
| Icon plus/minus | Zoom in/zoom out
| Icon segi lima/empat | Menggambar bentuk poligon atau segiempat untuk menandai area yang ingin dihindari pada rute |
| Icon panah | Menggambar garis dari satu titik ke titik lain untuk menghitung jaraknya |
| Huruf "m" | Mengganti satuan jarak yang digunakan ("m" untuk meter, "M" untuk mil, "NM" untuk mil laut) |
#### Sisi Kanan
| Icon/fitur                               | Kegunaan         |
| ---------------------------------- | ----------- |
| Icon menu                     | Membuka sidebar |
| Icon layer                     | Mengganti jenis pencitraan yang digunakan pada peta |
| Icon orang                     | Memunculkan/menghilangkan tombol panah untuk menggeser tampilan peta |
| Icon GPS                         | Mencari lokasi dari device yang sedang digunakan |

### 2. Mengetahui lokasi suatu titik pada peta
![alt text](assets/images/osr-img3.jpg?raw=true)
Untuk melakukan ini, kita hanya perlu mengetikkan nama lokasi pada search bar. Jika lokasi tersebut terdapat dalam database, lokasi tersebut akan diperlihatkan pada peta. Rincian terkait lokasi tersebut, seperti nama lokasi, letak negara, layer lokasi (misal: street, venue), dan koordinat longitude-latitude.
### 3. Mengetahui rute antar lokasi (bisa 2 atau lebih)
![alt text](assets/images/osr-img4.jpg?raw=true)
Untuk melakukan ini, pertama-tama, kita perlu membuka sidebar. Pastikan bahwa yang terpilih adalah "Find & Go", bukan "Reach", lalu masukkan lokasi awal kita di kolom "Starting Place". Kemudian, kita memasukkan lokasi tujuan akhir di kolom "Destination". Jika kita ingin mencari rute yang melewati lebih dari lokasi, kita bisa memilih "Add place input" agar bisa memasukkan lokasi-lokasi tambahan. Urutan lokasi yang dikunjungi juga bisa diubah-ubah urutannya. Kita kemudian akan mendapatkan rute pada peta beserta beberapa rincian seperti jarak, waktu tempuh, instruksi jalan yang harus dilewati, altitudo jalan yang dilewati rute, dan pilihan untuk melihat permukaan (surface), steepness (kemiringan), atau jenis jalan (way types) dari jalan yang dilewati rute.

Kita juga dapat menyesuaikan sejumlah parameter untuk rute yang ditampilkan, yaitu preferensi rute (reccommended atau shortest), parameter profil (tergantung jenis mode transportasi), hal-hal yang ingin dihindari rute (fitur tertentu, perbatasan dengan negara lain, negara tertentu), dan rute alternatif.
### 4. Mengetahui jarak antar lokasi (bisa 2 atau lebih) dengan menarik garis lurus
![alt text](assets/images/osr-img5.jpg?raw=true)
### 5. Mengetahui luas daerah berdasarkan titik-titik yang ditentukan (polygon)
![alt text](assets/images/osr-img6.jpg?raw=true)
### 6. Mengetahui luas daerah berdasarkan titik-titik yang ditentukan (rectangle)
![alt text](assets/images/osr-img7.jpg?raw=true)
### 7. Mengubah mode layer tampilan map
#### Mode OpenStreetMap
![alt text](assets/images/osr-img8.jpg?raw=true)
#### Mode Satellite Imagery
![alt text](assets/images/osr-img9.jpg?raw=true)
#### Mode Topography
![alt text](assets/images/osr-img10.jpg?raw=true)
#### Mode Transport Dark
![alt text](assets/images/osr-img11.jpg?raw=true)
#### Mode Outdoors
![alt text](assets/images/osr-img12.jpg?raw=true)

## Review

- Pendapat anda tentang aplikasi web ini
    - kelebihan
    - kekurangan
- Bandingkan dengan aplikasi web lain yang sejenis


## Reference

Cantumkan tiap sumber informasi yang anda pakai.
