# Jarkom-Modul-4-A15-2021

Laporan Resmi Modul 4 Jaringan Komputer Kelompok A15

### Anggota Kelompok :

|      NRP       |     Nama     |
| :------------: | :----------: |
| 05111940000034 | Aimar Wibowo |
| 05111940000064 | Ifanu Antoni |

### Nomor 1

![soal](img/soal1.png)

**Catatan**

1. Deadline hari Selasa, 23 November 2021 pukul 22.00
2. Soal shiift dikerjakan pada Cisco Packet Tracer dan GNS3 menggunakan metode perhitungan CLASSLESS yang berbeda.
   Keterangan: Bila di CPT menggunakan VLSM, maka di GNS3 menggunakan CIDR atau Sebaliknya
3. Jika tidak ada pemberitahuan revisi soal dari asisten, berarti semua soal BERSIFAT BENAR dan DAPAT DIKERJAKAN.
4. Untuk di GNS3 CLOUD merupakan NAT1 jangan sampai salah agar bisa terkoneksi internet.
5. Pembagian IP menggunakan Prefix IP yang telah ditentukan pada modul pengenalan
6. Pembagian IP dan routing harus SE-EFISIEN MUNGKIN.
7. Pastikan semua NODE pada GNS3 dapat melakukan ping ke `its.ac.id`

#### Perhitungan dengan Metode CIDR

Menentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan melakukan labeling netmask berdasarkan jumlah IP

![1.1](img/1.1.png)

Melakukan penggabungan dari subnet yang paling jauh hingga menjadi satu subnet penuh
Kami menggunakan bantuan `tabel` untuk melakukan penggabungan subnet
![1.2](img/2.1.png)

Membagi IP menggunakan pohon IP

![1.2](img/2.2.png)

#### Configurasi pada GNS3

Berdasarkan pohon IP yang sudah terdapat data `network ID` dan `netmask`, Pada GNS3 pada setiap network address dilakukan labelling

![1.2](img/2.3.png)

**Configurasi IP**
Lakukan configurasi IP dan netmask pada setiap `client` dan `router` sesuai dengan dengan **data labelling GNS3** yang ada
Pada `router` dan `client`

1.  klik kanan
2.  pilih configure
3.  pilih edit
4.  lakukan configurasi pada semua router dan client
    `router foosha`
    ![1.6](img/2.5.png)
    `router water7`
    ![1.2](img/2.4.png)
    `client fukurou`
    ![1.2](img/2.6.png)

**Static Routing**
Lakukan static routing pada setiap `router`

`router foosha`
![1.8](img/2.7.png)

`router water7`
![1.8](img/2.8.png)

`router pucci`
![1.8](img/2.9.png)

`router guanhao`
![1.8](img/2.10.png)

`router alabasta`
![1.8](img/2.11.png)

`router oimo`
![1.8](img/2.13.png)

`router seaston`
![1.8](img/2.14.png)

Lakukan iptables pada foosha `iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE`
Sekarang semua `router` dan `client` sudah terhubung dan bisa mengakses internet

![1.7](img/2.16.png)

![1.7](img/2.18.png)
![1.7](img/2.19.png)

#### Perhitungan dengan Metode VLSM

Menentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan melakukan labeling netmask berdasarkan jumlah IP

![1.1](img/1.1.png)

| Subnet | Jumlah IP | Netmask |
| :----: | :-------: | :------ |
|   A1   |    101    | /25     |
|   A2   |   2021    | /21     |
|   A3   |     2     | /30     |
|   A4   |    701    | /22     |
|   A5   |     2     | /30     |
|   A6   |   1001    | /22     |
|   A7   |     2     | /30     |
|   A8   |     2     | /30     |
|   A9   |    521    | /22     |
|  A10   |    502    | /23     |
|  A11   |    13     | /28     |
|  A12   |     2     | /30     |
|  A13   |    252    | /24     |
|  A14   |    721    | /22     |
|  A15   |     2     | /30     |
| TOTAL  |   5845    | /19     |

Membagi IP menggunakan pohon IP

![1.2](img/1.2.png)

Sehingga didapatkan data subneting seperti tabel berikut
![1.3](img/1.3.png)
![1.4](img/1.4.png)
![1.5](img/1.5.png)

#### Configurasi pada Cisco Packet Tracer

**Configurasi IP**
Lakukan configurasi IP dan netmask pada setiap `client` dan `router` sesuai dengan dengan **data tabel subneting** yang ada
Pada `router`

1.  klik 2 kali `router`
2.  pilih config
3.  pilih interfaces yang di ingin di config
4.  lakukan configurasi pada semua router
    ![1.6](img/1.6.png)

Pada `client`

1.  klik 2 kali `client`
2.  pilih desktop
3.  pilih ip configuration
4.  lakukan configurasi pada semua client
    ![1.7](img/1.7.png)

**Static Routing**
Lakukan static routing pada setiap `router`

`router foosha`
![1.8](img/1.8.png)
![1.8](img/1.9.png)
![1.8](img/1.10.png)

`router water7`
![1.8](img/1.11.png)

`router pucci`
![1.8](img/1.12.png)

`router guanhao`
![1.8](img/1.13.png)

`router alabasta`
![1.8](img/1.14.png)

`router oimo`
![1.8](img/1.15.png)

`router seaston`
![1.8](img/1.16.png)

Sekarang semua `router` dan `client` sudah terhubung
![1.7](img/1.17.png)

-

## Kendala

1. Materi CIDR yang cukup sedikit
