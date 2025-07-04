# UTS APBO A KELOMPOK 3 

Repositori ini berisi hasil Ujian Tengah Semester (UTS) mata kuliah Analisis Pemrograman Berbasis Objek (APBO) - Kelas A 

## Dosen Pengampu
Adi Wahyu Pribadi, S.Si., M.Kom

## Anggota Kelompok 3
| No | Nama Anggota          | NPM         |
|----|-----------------------|-------------|
| 1  | Arga Bona Simarmata   | 4523210020  |
| 2  | Aditya Nur Lintang    | 4523210003  |
| 3  | Alip Khoeril Akbar    | 4523210009  |
| 4  | Andra Teguh Ramadhan  | 4523210017  |
| 5  | Andre Alfre           | 4523210018  |


## Ketering Mama Iin
Bisnis yang kami pilih untuk dianalisis dalam pembuatan suatu sistem informasi yang dapat membantu pelaku bisnis tersebut adalah usaha katering tetangga dari salah satu anggota kami. Usaha Katering ini bersifat rumahan dengan skala kecil yang menjual berbagai menu lauk dan sayur kepada pembeli di lingkungan rumah penjual. Seluruh transaksi jual beli dilakukan melalui aplikasi WhatsApp saja karena sang penjual termasuk ke dalam orang yang kurang mengerti teknologi dalam konteks IT. Metode pembayaran dari usaha Katering ini hanya melayani cash saja tanpa ada opsi lainnya.

Proses dari usaha katering ini cukup sederhana yaitu dimulai proses pemasarannya menggunakan status WhatsApp agar pembeli tau menu apa saja yang akan dijual pada keesokan harinya. Lanjut ke proses produksi dengan membeli bahan di pagi hari,  lalu memulai masak pada siang hari. Dan makanan yang sudah matang akan diantarkan pada sore harinya.

![image](https://github.com/user-attachments/assets/b0eb08a2-a1eb-40d5-abee-fec383bbaea7)


### 1. Aktor/Role

A. Penjual
Berperan sebagai pengelola sistem yang bertanggung jawab dalam pengelolaan menu, memproses pesanan yang masuk, mengelola data pesanan, dan menerima pembayaran.

B. Pembeli
Berperan sebagai pengguna sistem yang melakukan pemesanan makanan, mengisi data pribadi, memilih metode pembayaran, dan menerima notifikasi pesanan.


### 2. Use Case Diagram
![APBO UTS-Use Case drawio (1)](https://github.com/user-attachments/assets/9a031879-f424-40c3-876b-6c12cb09171d)

### 3. Entitas Utama

#### A. Pembeli

| Nama Atribut  | Tipe Data    | Keterangan                 |
|---------------|--------------|----------------------------|
| id_pembeli    | String (PK)  | ID unik milik pembeli      |
| nama_pembeli  | String       | Nama lengkap pembeli       |
| alamat        | String       | Alamat lengkap pembeli     |
| notelp        | String       | Nomor telepon pembeli      |

#### B. Makanan

| Nama Atribut   | Tipe Data    | Keterangan                  |
|----------------|--------------|-----------------------------|
| id_makanan     | String (PK)  | ID unik makanan             |
| nama_makanan   | String       | Nama makanan                |
| stok           | Int          | Stok tersedia               |
| harga          | Double       | Harga makanan               |
| foto           | String       | File foto makanan           |
| deskripsi      | String       | Deskripsi makanan           |

#### C. Pesanan

| Nama Atribut  | Tipe Data    | Keterangan                          |
|---------------|--------------|-------------------------------------|
| id_pesanan    | String (PK)  | ID unik pesanan                     |
| id_pembeli    | String (FK)  | Relasi ke tabel Pembeli            |
| id_makanan    | String (FK)  | Relasi ke tabel Makanan            |
| jumlah        | Int          | Jumlah makanan yang dipesan        |
| subtotal      | Double       | Harga dikali jumlah                |
| waktu_pesan   | Datetime     | Waktu pemesanan                    |

#### D. Pembayaran

| Nama Atribut      | Tipe Data    | Keterangan                                         |
|-------------------|--------------|----------------------------------------------------|
| id_pembayaran     | String (PK)  | ID unik pembayaran                                 |
| id_pesanan        | String (FK)  | Relasi ke tabel Pesanan                            |
| subtotal          | Double       | Total harga yang dibayarkan                        |
| metode            | String       | Metode pembayaran (ENUM: COD, Transfer)        |
| waktu_pembayaran  | Datetime     | Waktu pembayaran dilakukan                         |

#### E. Notifikasi

| Nama Atribut | Tipe Data    | Keterangan                                   |
|--------------|--------------|----------------------------------------------|
| id_notif     | String (PK)  | ID unik notifikasi                           |
| id_pesanan   | String (FK)  | Relasi ke tabel Pesanan                      |
| konfirmasi   | Boolean      | Status konfirmasi pembayaran                 |
| status       | String       | Status pesanan (pending, selesai)        |
| notif        | String       | Pesan notifikasi                             |

### 4. Relasi
![APBO UTS-Entitiy Diagram drawio](https://github.com/user-attachments/assets/8ac50d36-6de0-4144-8bbc-602955429b13)


### 5. Class Diagram
![APBO UTS-Class Diagram (8)](https://github.com/user-attachments/assets/4c0eb1db-3ca8-47d5-8064-c778efc079d0)


### 6. Wireframe/Mockup
#### A. Mengelola Data Makanan - Penjual
![APBO UTS-Wireframe Tambah Menu drawio (1)](https://github.com/user-attachments/assets/c2ea3716-c0fe-482d-bd2d-ecdac530608b)


#### B. Daftar Makanan  - Penjual, Pembeli
![APBO UTS-Wireframe Makanan drawio](https://github.com/user-attachments/assets/99ec88a5-37a6-44f5-8a30-bc61822b92db)


#### C. Pesan Makanan - Pembeli
![APBO UTS-Wireframe Pesan drawio](https://github.com/user-attachments/assets/1bbb4a5b-a9b9-4773-b102-b5b68ee19447)


#### D. Data Diri - Pembeli
![APBO UTS-Wireframe Data Diri drawio (1)](https://github.com/user-attachments/assets/5a00ee35-adc8-48a7-8390-88cc4527d070)

 
#### E. Pembayaran - Pembeli
![APBO UTS-Wireframe Pembayaran](https://github.com/user-attachments/assets/47355e7c-b9a7-4ac4-89c6-7d314bd14ac9)


#### F. Konfirmasi, Melihat Daftar Pesanan - Penjual
![APBO UTS-Wireframe Konfirmasi drawio](https://github.com/user-attachments/assets/1348a782-d779-4f2d-a571-09f05d32ad7b)


#### G. Notifikasi - Pembeli
![APBO UTS-Wireframe Notifikasi](https://github.com/user-attachments/assets/da87a565-13a5-44ab-9338-ecab14dec2fc)
