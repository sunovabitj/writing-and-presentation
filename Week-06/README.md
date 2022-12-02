## Tugas Writing & Presentation test Week 6

&nbsp;

## **MYSQL Basic**
### **Database**
-- merupakan kumpulan informasi yang disimpan di dalam komputer secara sistematik dan saling berelasi, yang kemudian informasi di dalam database akan diolah menjadi sebuah data dan akan dikelolah oleh sistem. `Mengakses database` memerlukan sebuah DBMS (Database Management System) yang merupakan media komunikasi antara pengguna dengan data yang ada di dalam media penyimpanan.

### **Istilah-istilah yang terdapat dalam database**
- `table`, terdiri baris dan kolom, yang didalamnya berisikan atribut dari sebuah data.
- `field`, kolom dari sebuah tabel.
- `record`,  isi dari sebuah tabel.
- `SQL`, bahasa yang digunakan untuk mengakses database.
- `DDL, DML, DCL`, perintah SQL yang digunakan untuk membuat, mengubah dan menghapus struktur.
- `alter`, untuk mengubah struktur, seperti menambahkan atau menghapus kolom/field.
- `Drop`, untuk menghapus Database, Table.
- `SELECT`, untuk menyeleksi data.
- `INSERT`, untuk memasukkan data ke kolom-kolom yang terdapat pada tabel.
- dsb..

### **Database Relationships**
Relasi antar tabel dihubungkan oleh Primary key dan foreign key.
Primary key merupakan atribut yang tidak hanya mengidentifikasi secara unik suatu kejadian, tapi juga mewakili setiap kejadian suatu entitas (NIM/NIK/ID).
Sedangkan, Foreign key merupakan atribut yang melengkapi relationship dan menunjukan hubungan antara tabel induk dengan tabel anak.
- `ONE to MANY`,
Relasi ini menghubungkan 1 tabel dengan banyak tabel yang akan dituju
- `ONE to ONE`,
Relasi ini menghubungkan 1 tabel dengan 1 tabel yang dituju.
- `MANY to MANY`,
Relasi ini menghubungkan banyak tabel dengan banyak tabel yang dituju.

&nbsp;

## **MYSQL Lanjutan**
### **Memanipulasi Query**
  - `INNER JOIN`, hanya mengambil record yang memiliki keterkaitan/berhubungan.
  - `LEFT JOIN`, mengambil semua record dari tabel sisi kiri. Apabila kondisi tidak cocok, maka akan bernilai NULL.
  - `RIGHT JOIN`, mengambil semua record dari tabel sisi kanan. Apabila kondisi tidak cocok, maka akan bernilai NULL.
  - `MAX`, hanya mengambil record yang memiliki nilai paling besar.
 - `MIN`, hanya mengambil record yang memiliki nilai paling kecil.
 - `SUM`, menjumlahkan seluruh nilai record.
 - `COUNT`, menghitung jumlah record yang ada.
 - `AVG`, menghitung nilai rata-rata dari sebuah record.
 - `UNION`, menggabungkan hasil dari command SELECT.
 - `GROUP BY`, mengelompokan baris yang memiliki nilai yang sama ke dalam baris ringkasan.
 - `HAVING`, bisa digubakan sebagai pengganti WHERE apabila berjalan dengan GROUP BY.


&nbsp;

## **Authentication, Authorization & Encryption**
`Authentication`
Merupakan metode terhadap seorang pengguna mengkonfirmasi sebagai pengguna valid yang dapat mengakses sebuah akun atau informasi tertentu

`Authorization`
Merupakan proses penentuan terhadap pengguna yang terautentikasi tersebut diizinkan atau ditolak untuk melakukan satu atau lebih akses terhadap sistem.

`Encryption`
Merupakan proses pengubahan data menjadi format yang tidak bisa dibaca terkecuali apabila ada seseorang yang memiliki kunci untuk mengubah kembali data yang terenkripsi

- Jenis-jenis Autentikasi
  - `Single Factor Authentication`, Autentikasi yang sangat sederhana dan banyak digunakan di masa sekarang. Autentikasi ini berupa memasukan sebuah identitas seperti password dan username.

  - `Two Factor Authentication`, Autentikasi ini dibuat setelah Single Factor Authentication dipakai yaitu adanya tambahan autentikasi seperti OTP dan sidik jari atau wajah.

  - `Multi Factor Authentication`, Autentikasi yang mewajibkan pengguna untuk memverifikasi 3 jenis identitas seperti ID pengguna (password dan username), sidik jari, dan beberapa pertanyaan yang berhubungan dengan pengguna.

&nbsp;

## **Sequelize**
cara menggunakannya:
-  Install Express JS:
```
npm install express
```
-  Install mysql2:
```
npm install mysql2
```
-  Install sequelize-cli:
```
npm install sequelize
```
-  Inisialisasi Project:
```
npx sequelize-cli init
```
- Mengkonfigurasi database dari file config/config.js
```
require("dotenv").config();
module.exports = {
  development: {
    username: "root", 
    password: "root", 
    database: "Nama Database Yang Telah Dibuat",
    host: "127.0.0.1", //default
    dialect: "mysql"
  }
}
```
- Generate model
```
 npx sequelize-cli model:generate --name Noted -- attributes title:string
 ```
- migrasi ke dalam database
```
npm sequelize-cli db:migrate
```