# **Week1**
## Writing & Presentation

## Unix Commad Line

- ### Shell
    Agar bisa terhubung dengan komputer maka user akan memerlukan penerjemah. Maka dari itu user memerlukan yang namanya shell. Definisi shell secara harfiah sendiri adalah program yang digunakan untuk berkomunikasi atau memerintah sistem.
- ### CLI (Command Line Interface)
    Merupakan sebuah program yang memungkinkan user mengetik perintah atau command yang akan mmemerintahkan perangkat komputer untuk melakukan suatu tugas tertentu.
- ### Terminal
    User dan komputer dihubungkan dengan namanya terminal, yaitu tempat/aplikasi dimana user dapat mengetikan atau memberikan suatu perintah. Disinilah tempat dimana shell akan berperan.
- ### File System Structure
    Struktur dimana mengatur cara bagaimana data disimpan dalam sistem. Contoh dalam Sistem Operasi Windows struktur file yang disimpan menggunakan struktur yang bentuknya mirip sebuah pohon seperti gambar dibawah.

- ### Command

  - pwd (`print working directory`), untuk melihat current working directory
  - cd (`change directory`), untuk pindah directory
  - ls (`list`), untuk melihat isi file di dalam directory
  - mkdir (`make directory`), untuk membuat direktori atau folder
  - rmdir (`remove directory`), untuk menghapus direktori yang kosong dan tidak terpakai lagi
  - touch, untuk membuat file directory
  - cp (`copy`), untuk menyalin file directory
  - mv (`move`), untuk memindahkan file directory
  - rm (`remove`), untuk menghapus file directory

  &nbsp;

## Git & Github

- *Git*
    merupakan software untuk melacak suatu perubahan yang terjadi di suatu folder ataupun file, yang biasanya digunakan oleh programmer sebagai tempat untuk menyimpan file programan mereka karena lebih efektif.

- *Github*
    merupakan vendor penyedia layanan git yang dimiliki oleh microsoft atau secara definisi merupakan layanan hosting berbasis web sebagai repositori git.

-  ### **Mengapa wajib menggunakan Git & Github?**
    Alasan utamanya adalah untuk memudahkan programmer agar bisa bekerja sama dalam sebuah tim. Tujuan besarnya adalah programmer bisa berkolaborasi dengan programmer lainnya dengan mengerjakan proyek yang sama tanpa harus repot copy paste folder aplikasi yang terupdate.

- ### Command di dalam Git & Github

  - `git init`, untuk membuat repositori baru
  - `git add .` , untuk menambahkan file ke index
  - `git commit -m "pesan checkout"`, untuk melakukan commit atau menyimpan perubahan pada version control pada git. Dan kita bisa menambahkan pesan untuk membeikan checkout pada setiap perbuahan.
  - git config, yang bisa digunakan untuk mengatur konfigurasi tertentu sesuai keinginan pengguna (email dan nama)
    - `git config --global user.email "sam@google.com"`
    - `git config --global user.name "sam"`
  - `git status`, untuk menampilkan daftar file yang berubah bersama dengan file yang ingin di tambahkan atau di-commit
  - `git remote add origin <URL>`, membuat user terhubung ke remote repository
  - `git push origin master`, untuk mempublish file atau aplikasi ke github


## HTML

- *HTML*
merupakan bahasa komputer yang digunakan untuk membuat kerangka atau struktur untuk Web pages (halaman website) di internet. Bagaimana peran HTML pada web development? Web browser seperti Chrome, Firefox, Edge, Safari, dll, dan akan membaca dokumen HTML. Dokumen HTML yang berisi tag-tag HTML akan memberitahu browser bagaimana cara menampilkan sebuah konten.

- *HTML Sederhana*
  
  ```html
  <html>
    <head>
    <title>
         Judul Website
    </title>
    <body>
        saya sedang belajar pemrograman HTML dasar.
        </body>
  </html>
  ```


- *Tag HTML*
 adalah sebauh penanda awalan dan akhiran dari sebuah elemen di HTML. Tag dibuat dengan kurung siku (<...>), lalu di dalamnya berisi nama tag dan kadang juga ditambahkan dengan atribut.
    Tag selalu ditulis berpasangan. Ada tag pembuka dan ada tag penutupnya. Namun, ada juga beberapa tag yang tidak memiliki pasangan penutup. Tag penutup ditulis dengan menambahkan garis miring (/) di depan nama tag.

- Macam-macam *tag* HTML
  - Tag untuk membuat tulisan tebal dan miring

    ```html
    <b>Tebal</b> <i>Miring</i>
    ```
  - Tag HTML Untuk Membuat tulisan dengan link

    ```html
    <a href="">Welcome To AMMAN Coding Bootcamp BATCH 3</a>
    ```
  - Tag Untuk Membuat Daftar/List

    - Ordered List

      ```html
      <ol>
        Dafunda
        <li>Dafunda Tekno</li>
        <li>Dafunda Otaku</li>
        <li>Dafunda Games</li>
      </ol>
      ```
    - Unordered List

      ```html
      <ul>
        Dafunda
        <li>Dafunda Tekno</li>
        <li>Dafunda Otaku</li>
        <li>Dafunda Games</li>
      </ul>
      ```
     - Tag HTML Untuk Menampilkan gambar

      ```html
      <img src="https://bit.ly/2FKluzq" alt="Si Kucing"></img>
     ```

- Deploy HTML
adalah sebuah proses untuk menyebarkan aplikasi yang sudah kita kerjakan supaya bisa digunakan oleh orang-orang. Jika aplikasi kita HTML atau Web App kita perlu mendeploy ke server. Untuk melakukan hal tersebut kita bisa menggunakan layanan yang bernama Netlify

  &nbsp;

## CSS

- CSS adalah bahasa komputer yang digunakan untuk menambahkan design ke suatu halaman website di internet agar terlihat lebih cantik/menarik. CSS adalah singkatan dari Cascading Style Sheets. Kita ibaratkan HTML adalah kerangka yang memberi sturuktur pada website, maka CSS adalah baju yang memberi warna dan layout pada website.
- Cara Menggunakan CSS

  1. Inline Styles

     dengan cara menambahkann CSS langsung pada atribut HTML

     ```html
     <p style="color:red">Tulisan ini berwarna merah</p>
     ```

  2. Internal CSS

     dengan cara menggunakan element/tag `<style>` untuk menyisipkan kode CSS. element/tag `<style>` diletakkan di dalam element `<head>`

     ```html
     <!DOCTYPE html>
     <html>
       <head>
         <title>Website Pertamaku</title>
         <style>
           body {
             background-color: yellow;
           }
           h1 {
             color: blue;
           }
           p {
             color: red;
           }
         </style>
       </head>
       <body>
         <h1>Website Pertamaku</h1>
         <p>Selamat Datang</p>
       </body>
     </html>
     ```

  3. Eksternal CSS

     dengan cara akan menyisipkan kode CSS dengan cara membuat file CSS terpisah, dan lalu menyambungkannya dengan file HTML dengan menggunakan element <link>. Element <link> tersebut diletakkan di dalam element <head>

     Contoh:

     dengan menggunakan dua file, yaitu: `index.html` untuk file HTML-nya dan `styles.css` untuk file CSS-nya.

     ```html
     <!-- File index.html -->

     <!DOCTYPE html>
     <html>
       <head>
         <title>Website Pertamaku</title>
         <link rel="stylesheet" href="styles.css" />
       </head>
       <body>
         <h1>Website Pertamaku</h1>
         <p>Selamat Datang</p>
       </body>
     </html>
     ```

     ```css
     /* File styles.css */

     body {
       background-color: pink;
     }
     h1 {
       color: blue;
     }
     p {
       color: black;
     }
     ```

     &nbsp;

- CSS Syntax adalah syntax yang digunakan untuk menunjuk atau memilih HTML element mana yang ingin diberi style (dihias). CSS syntax terdiri dari selector, property, dan value.

  Syntaxnya seperti ini:

  ```css
  p {
    color: red;
  }
  ```

  Penjelasan :

  - p, merupakan sebuah selector berupa element HTML yang akan diubah

  - color, merupakan sebuah properti berupa bagian mana dari element HTML yang akan diubah. Contoh diatas kita akan mengubah warna dari teks yang ada di element p

  - red, merupakan value yaitu nilai/hiasan berupa warna merah

  &nbsp;

## Algoritma dan Struktur Data

- Algortima Adalah deskripsi berupa step-step yang dibutuhkan untuk menyelesaikan suatu masalah. Untuk menyelesaikan suatu masalah, tentunya kita harus mempunyai data struktur, nah data inilah yang akan kita gunakan untuk menyelesaikan suatu masalah dengan menggunakan algoritma.

  - Manfaat algoritma:

    - Membantu menyederhanakan suatu program yang rumit dan juga besar.
    - Mempermudah pembuatan program yang dapat menyelesaikan masalah tertentu.
    - Membantu menyelesaikan suatu masalah dengan logika dan juga sistematis.

  - Penggunaan Algortima

      - Mulai
      - Deklarasi variabel n, hasil_convert
      - Menambahkan nilai n
      - <div align="justify">Melakukan proses (n jam = n \* 3600" lalu disimpan ke dalam hasil_convert
      - Menampilkan hasil convert (n jam) = + "detik"
      - Stop

    &nbsp;

- Pseudocode

  - Pseudocode adalah menuliskan algoritma sebelum kita implementasikan ke bahasa pemograman tertentu.

    &nbsp;

- Conditional

    Conditional digunakan saat dibutuhkan percabangan kasus. Komputer akan melakukan suatu tindakan jika suatu kondisi terpenuhi.

    Jika hari ini tidak hujan, maka Bob pergi ke pasar,

    jika tidak maka Bob dirumah aja.

      ```
      IF "bright"
      DO "go to the market"
      ELSE
      DO "stay at home"
      ```

    &nbsp;

- Looping

    Komputer dapat melakukan sebuah proses yang sama berulang-ulang.

    Jika membutuhkan perulangan dalam kasus tertentu, kita bisa menggunakan Looping.

     Contoh :

      ```
      STORE "count" t0 1

      WHILE "count" < 11
      DISPLAY "count"
      CALCULATE "count" mod 2
      STORE "reminder" value with calculation result
      IF "reminder" equals to 0
      DISPLAY "EVEN!"
      ELSE
      DISPLAY "ODD!"
      ```