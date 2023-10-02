# Welcome to Our Project: OpenRouteService Maps💫
![alt text](assets/images/osr-img.jpg?raw=true)

**Oleh Kelompok 1 P1:**

| No. | Nama                               | NIM         |
| --- | ---------------------------------- | ----------- |
| 1   | Dhianita Shafa                     | G6401211016 |
| 2   | Tan, Maria Putri Ariyani           | G6401211049 |
| 3   | Muhammad Ariiq Arrafi              | G6401211062 |
| 4   | Dwi Fitriani Azhari                | G64012011072 |
| 5   | Medina Fitri Maulida               | G64012011096 |

## About OpenRouteService Maps

OpenRouteService Maps merupakan aplikasi yang memungkinkan pengguna untuk menghitung rute dan mendapatkan informasi navigasi di seluruh dunia. Layanan ini menyediakan berbagai pilihan perjalanan untuk berbagai mode transportasi dan kustomisasi rute yang diinginkan. Beberapa mode transportasi yang dapat dipilih meliputi mobil, berbagai jenis sepeda, berjalan kaki, mendaki, kursi roda, dan berbagai kendaraan berat. Kemudian pengguna dapat menyesuaikan rute yang dipilih, mulai dari memilih rute yang direkomendasikan oleh sistem ataupun memilih jarak yang terpendek, menghindari daerah yang tidak diinginkan dalam rute, menyesuaikan dengan kecepatan maksimal berkendara, dan sebagainya.

# Installation and Configuration

### Kebutuhan Sistem
- Unix, Linux atau Windows.
- Docker

### Pembuatan Virtual Machine
Untuk menjalankan server, kami membuat virtual machine Ubuntu Server 22.04 LTS menggunakan Microsoft Azure. Berikut langkah-langkah pembuatan virtual machine.
1. Jika belum memiliki akun, registrasi menggunakan email IPB.
2. Ambil student benefit, untuk akun yang menggunakan email IPB akan mendapat saldo $100.
3. Buat resource baru dengan meng-klik `create a resource` pada home.
4. Pilih service `Ubuntu Server 22.04 LTS` dan klik create.
5. Isi nama resource group dan virtual machine name
6. Pada bagian `Administrator account`, gunakan password sebagai authentication type, kemudian isi username dan password.
7. Pada tab `Networking`, tambahkan HTTP(80) untuk `inbound ports`.
8. Klik Review + create, kemudian create virtual machine.

### Proses Instalasi
1. Login ke dalam server menggunakan SSH. Untuk pengguna Linux dapat menggunakan `terminal`. Sedangkan, pengguna Windows dapat menggunakan `Powershell` atau `command prompt`.
    ```
    $ ssh projectkomdat@20.127.187.248
    ```

2. Pastikan seluruh paket sistem *up-to-date*, kemudian setup Docker repository untuk mengunduh `Docker`.
    ```
    $ sudo apt update
    $ sudo apt install apt-transport-https ca-certificates curl software-properties-common
    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    $ echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    ```

3. Unduh `Docker` package.
    ```
    $ sudo apt install docker-ce
    ```
    
4. Setup untuk menjalankan command docker sebagai user tanpa menggunakan sudo.
    ```
    $ sudo usermod -aG docker ${USER}
    $ su - ${USER}
    ```

3. Unduh map client untuk **OpenRouteService** dengan menggunakan git clone, kemudian pindah ke folder repository yang telah diunduh. 
    ```
    $ git clone https://github.com/GIScience/ors-map-client.git
    $ cd ors-map-client
    ```

4. Lakukan konfigurasi aplikasi dengan menyalin semua file pada `src/config-example` ke `src/config` dengan menghilangkan `-example` pada setiap nama file.
    > app-config-example.js => app-config.js<br>
    ors-map-filters-example.js => ors-map-filters.js<br>
    layer-zoom-mapping-example.js => layer-zoom-mapping.js<br>
    hooks-example.js => hooks.js<br>
    theme-example.js => theme.js<br>
    default-map-settings-example.js => default-map-settings.js<br>
    settings-options-example.js => settings-options.js
    
    Atau dapat dengan menggunakan perintah ini.
    ```
    $ cd src && cp config-examples/* config && for i in config/*-example.js; do mv -- "$i" "${i%-example.js}.js"; done
    ```
5. Pada file `app-config.js`, isi API key untuk pengembangan aplikasi dan mempersingkat url.
    - orsApiKey - didapatkan dari [website developer openrouteservice](https://openrouteservice.org/dev) dengan me-*request* API token
    - bitlyApiKey - didapatkan dari [website developer bit.ly](https://app.bitly.com/) dengan meng-*generate* API token
    - bitlyLogin - email atau username yang digunakan untuk [website developer bit.ly](https://app.bitly.com/)
    ![configkey](https://github.com/airamts/TA-UTS-Komdat/assets/86961194/fa0b1ff5-a105-46d1-9d12-7ef64b525d5f)

5. Set port yang akan dijalankan menjadi 80 dengan mengubah port pada file `docker-compose.yml`
    ![port-before](https://github.com/airamts/TA-UTS-Komdat/assets/86961194/516b05af-a78d-4480-aea6-a1efaac66a49)
    ![port-after](https://github.com/airamts/TA-UTS-Komdat/assets/86961194/b2a815ca-a782-4684-87ee-21da92f38e50)

    
6. Jalankan dengan menggunakan docker.
    ```
    $ docker compose up -d
    ```

### Akses Website
Untuk mengakses website kami, dapat menggunakan alamat IP publik maupun alamat DNS sebagai berikut.
- Public IP	: http://20.127.187.248
- DNS		: http://komdatp1kel1.eastus.cloudapp.azure.com

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
![alt text](assets/images/ors-1-titik.jpg?raw=true)
Untuk melakukan ini, kita hanya perlu mengetikkan nama lokasi pada search bar. Jika lokasi tersebut ditemukan pada database, lokasi tersebut akan diperlihatkan pada peta. Rincian terkait lokasi tersebut, seperti nama lokasi, letak negara, layer lokasi (misal: street, venue), dan koordinat longitude-latitude akan terlihat pada sidebar.
### 3. Mengetahui jarak antar lokasi (bisa 2 atau lebih)
![alt text](assets/images/osr-img4.jpg?raw=true)
Untuk melakukan ini, pertama-tama, kita perlu membuka sidebar. Pastikan bahwa yang terpilih adalah "Find & Go", bukan "Reach", lalu masukkan lokasi awal kita di kolom "Starting Place". Kemudian, kita memasukkan lokasi tujuan akhir di kolom "Destination". Jika kita ingin mencari rute yang melewati lebih dari lokasi, kita bisa memilih "Add place input" agar bisa memasukkan lokasi-lokasi tambahan. Urutan lokasi yang dikunjungi juga bisa diubah-ubah urutannya. Kita kemudian akan mendapatkan rute pada peta beserta beberapa rincian seperti jarak, waktu tempuh, instruksi jalan yang harus dilewati, altitudo jalan yang dilewati rute, dan pilihan untuk melihat permukaan (surface), steepness (kemiringan), atau jenis jalan (way types) dari jalan yang dilewati rute.

Kita juga dapat menyesuaikan sejumlah parameter untuk rute yang ditampilkan, yaitu preferensi rute (reccommended atau shortest), parameter profil (tergantung jenis mode transportasi), hal-hal yang ingin dihindari rute (fitur tertentu, perbatasan dengan negara lain, negara tertentu), dan rute alternatif.
### 4. Mengetahui jarak antar lokasi (bisa 2 atau lebih) dengan menarik garis lurus
![alt text](assets/images/osr-img5.jpg?raw=true)
### 5. Menghindari area tertentu pada peta
![alt text](assets/images/ors-segiempat-poligon.jpg?raw=true)
Untuk mencegah rute melewati suatu area yang tidak kita inginkan, kita bisa menandainya dengan menggambar segi empat atau poligon pada area tersebut menggunakan icon yang ada di sisi kiri.
![alt text](assets/images/ors-segiempat-info.jpg?raw=true)
Jika kita mengeklik gambar segi empat atau poligon yang sudah kita buat, akan muncul sebuah pop-up di kanan bawah layar yang berisi informasi luas daerah, nama daerah di peta, dan koordinat longitude-latitude (pada gambar di atas ditandai dengan panah merah).
### 7. Mengubah mode layer tampilan map
Pengguna dapat mengubah mode layer map yang diinginkan dengan mengklik simbol yang berada di pojok kanan atas berikut.
![alt text](assets/images/osr-img14.jpg?raw=true)
Berikut adalah tampilan masing-masing mode layer:
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

1. [Install Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04) - DigitalOcean
2. [OpenRouteService Installation](https://github.com/GIScience/ors-map-client) - Github
