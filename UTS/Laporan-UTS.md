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


### 1. Functional Requirements
1. Login dan Akses Pengguna
   - Sistem harus menyediakan fitur login menggunakan akun pengguna.
   - Sistem harus memungkinkan pengguna masuk sebagai tamu menggunakan QR scan.
2. Pengelolaan Data
   - Sistem harus memungkinkan admin untuk mengelola profil dan status katering.
   - Sistem harus memungkinkan admin untuk mengelola data makanan (tambah, ubah, hapus menu makanan).
3. Menu Makanan
   - Sistem harus menampilkan daftar menu makanan yang tersedia kepada semua pengguna (akun dan tamu).
   - Sistem harus memungkinkan pengguna untuk memberikan penilaian terhadap menu makanan.
4. Proses Pemesanan
   - Sistem harus memungkinkan pengguna memilih makanan dan membuat pesanan.
   - Sistem harus meminta pengguna untuk mengisi data diri sebelum menyelesaikan pemesanan.
   - Sistem harus menyediakan pilihan metode pembayaran.
   - Sistem harus menampilkan daftar pesanan yang telah dibuat oleh pengguna.
5. Pembayaran
   - Sistem harus memungkinkan pengguna mengkonfirmasi pembayaran setelah memilih metode pembayaran.
   - Sistem harus menampilkan daftar transaksi yang telah dilakukan pengguna.
6. Notifikasi
   - Sistem harus mengirim notifikasi kepada pengguna ketika pesanan berhasil dibuat atau status pesanan berubah.
7. Konfirmasi
   - Sistem harus memungkinkan pengguna melakukan konfirmasi terhadap pesanan yang dibuat.

  
### 2. Aktor/Role

A. Penjual
Berperan sebagai pengelola sistem yang bertanggung jawab dalam pengelolaan menu, memproses pesanan yang masuk, mengelola data pesanan, dan menerima pembayaran.

B. Pembeli
Berperan sebagai pengguna sistem yang melakukan pemesanan makanan, mengisi data pribadi, memilih metode pembayaran, dan menerima notifikasi pesanan.


### 3. Use Case Diagram
![APBO UTS-Use Case drawio (2)](https://github.com/user-attachments/assets/0cc1e423-3eb9-48c0-8da9-d4dec2e78e28)


### 4. Entitas Utama

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

### 5. Relasi
![APBO UTS-Entitiy Diagram drawio](https://github.com/user-attachments/assets/8ac50d36-6de0-4144-8bbc-602955429b13)


### 6. Class Diagram
![APBO UTS-Class Diagram (8)](https://github.com/user-attachments/assets/4c0eb1db-3ca8-47d5-8064-c778efc079d0)


### 7. Wireframe/Mock UP
#### A. Penjual
- Halaman Daftar Menu

![Screenshot 2025-07-06 220846](https://github.com/user-attachments/assets/36104cbb-4cdc-4421-be12-106e1438050e) 
![Screenshot 2025-07-06 221053](https://github.com/user-attachments/assets/ee001b55-f7c6-4d25-8fc3-cc57ee344525)
  
- Halaman Mengelola Data Menu

![Screenshot 2025-07-06 220957](https://github.com/user-attachments/assets/56c74e0a-eb88-4666-849a-ed0a7c84caa8)
![Screenshot 2025-07-06 221115](https://github.com/user-attachments/assets/93bf60bc-e295-4620-a53d-54180f30d9ab)

- Halaman Konfirmasi Pesanan

![Screenshot 2025-07-06 222013](https://github.com/user-attachments/assets/f9dc8451-e538-4e91-8482-5b006e0658fb)
![Screenshot 2025-07-06 222029](https://github.com/user-attachments/assets/47580f7f-7da3-4018-977b-86ddb2228c75)
![Screenshot 2025-07-06 222050](https://github.com/user-attachments/assets/c5848804-de97-451a-a696-722816b21584)
![Screenshot 2025-07-06 221410](https://github.com/user-attachments/assets/3caa6ecb-055b-4112-8eba-dd8a547d8c92)
![Screenshot 2025-07-06 221427](https://github.com/user-attachments/assets/e017b428-023c-4a22-a031-26c2432034a4)
![Screenshot 2025-07-06 221456](https://github.com/user-attachments/assets/4fcb4177-fe1a-4ee4-acaa-cc3208513468)


- Halaman Riwayat Transaksi

![Screenshot 2025-07-06 222934](https://github.com/user-attachments/assets/6df4f530-b13e-41a8-a39b-8ece399076c7)
  ![Screenshot 20![Uploading Screenshot 2025-07-06 222934.png…]()
25-07-06 221523](https://github.com/user-attachments/assets/de88d197-2301-4e4a-b0fe-26fb0c1e341f)

- Halaman Profil

![Screenshot 2025-07-06 224709](https://github.com/user-attachments/assets/bc2ecebe-089e-4d8b-9ce1-eda0c4b73627)
![Screenshot 2025-07-06 221543](https://github.com/user-attachments/assets/5a1946ab-6ba8-4609-b6a2-8805fd020a72)

#### B. Pembeli
- Halaman Main Menu

  ![Screenshot 2025-07-06 224113](https://github.com/user-attachments/assets/0fe0dafb-c76e-4377-92e6-6dfb82277503)
![Screenshot 2025-07-06 224217](https://github.com/user-attachments/assets/885be72a-099c-467f-9731-5962b795acd2)

- Halaman Daftar Menu

![Screenshot 2025-07-06 223258](https://github.com/user-attachments/assets/69f6350c-3d55-45ad-8138-541b5a9ed86e)
  ![Screenshot 2025-07-06 222257](https://github.com/user-attachments/assets/ed3639ef-deb2-4e06-a8c3-e7ff07313e7c)

- Halaman Pemesanan

![Screenshot 2025-07-06 223319](https://github.com/user-attachments/assets/91603687-2a4b-447c-a230-a3a2606264ad)
  ![Screenshot 2025-07-06 222315](https://github.com/user-attachments/assets/6d61d79e-9d35-4e4a-8e74-088480ef83df)

- Halaman Isi Data Diri dan Metode Pembayaran

![Screenshot 2025-07-06 223333](https://github.com/user-attachments/assets/1a743416-191d-4df1-a5ec-ef13e6142bb2)
  ![Screenshot 2025-07-06 222331](https://github.com/user-attachments/assets/040c1852-50b7-4525-aa9b-615dc7802387)

- Halaman Notifikasi dan Detail Pemesanan

![Screenshot 2025-07-06 225202](https://github.com/user-attachments/assets/afb0d6ea-88bf-4a4e-a00c-fe5b6a74ce92)
![Screenshot 2025-07-06 225659](https://github.com/user-attachments/assets/a41742e3-614c-4a7f-b8be-0eeff89a96d4)

- Halaman Riwayat Transaksi

![Screenshot 2025-07-06 231049](https://github.com/user-attachments/assets/3ef94b07-59b0-458a-9a30-485233e1f937)
![Screenshot 2025-07-06 231114](https://github.com/user-attachments/assets/aea83a45-4e5b-4352-9c11-8e100e79e16c)
   ![Screenshot 2025-07-06 222411](https://github.com/user-attachments/assets/380b976a-333b-4e5d-bc87-ec4aa9c06c49)
![Screenshot 2025-07-06 222424](https://github.com/user-attachments/assets/5f779f1c-410a-4417-ba9a-94471a14a6a7)

- Halaman Profil

![Screenshot 2025-07-06 223235](https://github.com/user-attachments/assets/7b2646f3-b8c5-4464-87ac-882368526eed)
  ![Screenshot 2025-07-06 222436](https://github.com/user-attachments/assets/30467788-64a5-48dd-9046-3c3562df8c02)

- Halaman Ulasan

![Screenshot 2025-07-06 223143](https://github.com/user-attachments/assets/6a297dc8-8b6c-4f9a-9fc7-3cc1e08fd480)
  ![Screenshot 2025-07-06 222449](https://github.com/user-attachments/assets/ecb07ebe-0342-405a-ac88-673dd66b7df7)
