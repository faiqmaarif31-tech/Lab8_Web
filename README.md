Lab8Web -- Praktikum 8 PHP dan Database MySQL
Repository ini berisi hasil pengerjaan Praktikum 8 Pemrograman Web OBE
tentang pembuatan aplikasi CRUD sederhana menggunakan PHP dan database
MySQL.
Tujuan Praktikum
1. Memahami konsep dasar database.
2. Memahami konsep dasar CRUD menggunakan PHP.
3. Membuat program CRUD sederhana menggunakan PHP.
Persiapan
Perangkat dan aplikasi yang digunakan:
- XAMPP (Apache dan MySQL)
- Visual Studio Code
- Browser
- phpMyAdmin
Struktur Folder
lab8_php_database/
├── koneksi.php
├── index.php
├── tambah.php
├── ubah.php
├── hapus.php
├── style.css
└── gambar/
Folder gambar digunakan untuk menyimpan gambar barang yang diunggah
melalui formulir.
Langkah Praktikum
1. Menjalankan XAMPP
Jalankan Apache dan MySQL melalui XAMPP Control Panel. Pastikan kedua
layanan aktif sebelum membuka phpMyAdmin atau menjalankan aplikasi PHP.

Screenshot: > Tambahkan screenshot XAMPP dengan Apache dan MySQL
aktif di sini.
2. Membuat Database
Buka http://localhost/phpmyadmin/, lalu jalankan perintah SQL berikut
untuk membuat database:
CREATE DATABASE latihan1;
Pilih database latihan1, kemudian buat tabel data_barang:
CREATE TABLE data_barang (
    id_barang INT(10) AUTO_INCREMENT PRIMARY KEY,
    kategori VARCHAR(30),
    nama VARCHAR(30),
    gambar VARCHAR(100),
    harga_beli DECIMAL(10,0),
    harga_jual DECIMAL(10,0),
    stok INT(4)
);
3. Menambahkan Data Awal
Masukkan tiga data barang sesuai modul praktikum:
INSERT INTO data_barang
(kategori, nama, gambar, harga_beli, harga_jual, stok)
VALUES
('Elektronik', 'HP Samsung Android', 'hp_samsung.jpg', 2000000, 2400000, 5),
('Elektronik', 'HP Xiaomi Android', 'hp_xiaomi.jpg', 1000000, 1400000, 5),
('Elektronik', 'HP OPPO Android', 'hp_oppo.jpg', 1800000, 2300000, 5);
Screenshot: > Tambahkan screenshot struktur tabel dan data awal
pada phpMyAdmin di sini.
4. Membuat Koneksi Database (koneksi.php)
File koneksi.php digunakan untuk menghubungkan PHP dengan database
MySQL. Pengaturan koneksi menggunakan host localhost, username root,
password kosong (sesuai konfigurasi XAMPP standar), dan database
latihan1.

Program menggunakan fungsi mysqli_connect(). Jika koneksi gagal,
program menampilkan pesan kesalahan koneksi.

Screenshot: > Tambahkan screenshot kode koneksi.php dan hasil
pengujian koneksi di sini.
5. Menampilkan Data (index.php) -- Read
File index.php menampilkan data dari tabel data_barang. Program
menjalankan query SELECT * FROM data_barang, kemudian menampilkan
hasilnya dalam tabel.

Informasi yang ditampilkan meliputi gambar, nama barang, kategori, harga
beli, harga jual, stok, dan aksi. Tombol Tambah Barang membuka
tambah.php, sedangkan tombol Ubah dan Hapus digunakan untuk
mengelola data yang dipilih.

Screenshot: > Tambahkan screenshot halaman utama yang menampilkan
data barang di sini.
6. Menambahkan Data (tambah.php) -- Create
File tambah.php menyediakan formulir untuk memasukkan nama barang,
kategori, harga jual, harga beli, stok, dan file gambar.

Data formulir diterima menggunakan $_POST, sedangkan file gambar
diterima menggunakan $_FILES. Perintah SQL INSERT INTO digunakan
untuk menyimpan data baru ke tabel data_barang.

Screenshot: > Tambahkan screenshot formulir tambah barang dan hasil
penambahan data di sini.
7. Mengubah Data (ubah.php) -- Update
File ubah.php digunakan untuk mengubah data barang berdasarkan
id_barang. ID barang dikirim melalui parameter URL. Program mengambil
data lama untuk ditampilkan pada formulir, kemudian menggunakan query
UPDATE untuk menyimpan perubahan.

Screenshot: > Tambahkan screenshot formulir ubah barang dan hasil
perubahan data di sini.
8. Menghapus Data (hapus.php) -- Delete
File hapus.php menghapus data berdasarkan id_barang menggunakan
query DELETE FROM. Setelah proses penghapusan, pengguna diarahkan
kembali ke halaman index.php.

Screenshot: > Tambahkan screenshot konfirmasi penghapusan dan
tampilan setelah data dihapus di sini.
9. Mengatur Tampilan (style.css)
File style.css digunakan untuk mengatur tampilan halaman, tabel, dan
formulir. File CSS dihubungkan ke halaman PHP menggunakan elemen
<link> pada bagian <head>.

Pada tampilan tombol, digunakan warna berbeda untuk membedakan fungsi:
- Hijau: tombol Tambah Barang.
- Kuning: tombol Ubah.
- Merah: tombol Hapus.
Screenshot: > Tambahkan screenshot tampilan akhir website setelah
CSS diterapkan di sini.
Pengujian CRUD
Pengujian dilakukan untuk memeriksa fungsi utama aplikasi:

  Operasi   Fungsi
  Create    Menambahkan data barang baru.
Read      Menampilkan data barang dari database.
Update    Mengubah data barang berdasarkan ID.
Delete    Menghapus data barang berdasarkan ID.
Cara Menjalankan Aplikasi
1. Letakkan folder lab8_php_database di dalam direktori htdocs
   XAMPP.
2. Jalankan Apache dan MySQL melalui XAMPP.
3. Buat database latihan1, tabel data_barang, dan data awal melalui
   phpMyAdmin sesuai langkah di atas.
4. Sesuaikan pengaturan koneksi pada koneksi.php dengan konfigurasi
   MySQL lokal.
5. Buka browser dan akses:
   http://localhost/lab8_php_database/
Kesimpulan
Praktikum ini menerapkan konsep CRUD menggunakan PHP dan MySQL. Aplikasi
menghubungkan PHP dengan database, menampilkan data barang, menambahkan
data, mengubah data, dan menghapus data. CSS digunakan untuk mengatur
tampilan halaman agar lebih rapi dan mudah digunakan.