# Week3
## **Writing & Presentation**


## **JAVASCRIPT INTERMEDIATE**
### **Array**
- Array merupakan pengorganisasian data dan tempat penyimpanan data
- Array adalah tipe data list order yang dapat menyimpan tipe data apapun dialamnya seperti string, number, boolean dan lainnya
- Membuat Array : Array didefinisikan dengan square brackets []
- Mengakses Array : Array pada javascript dihitung mulai dari index ke- 0
- Const in Array
   - Apabila menggunakan let, array dapat diubah dengan nilai  yang baru
   - Const tidak dapat melakukan update data. Namun dapat melakukan update konten nilai di dalam array
   - Tidak dapat mengubah array dengan array baru jika menggunakan const
- Array Properti. Array memiliki 5 properti yang sering digunakan yaitu : constructor
 - length
 - index
 - input
 - prototype
- Array Method atau biasa disebut dengan built in methods
 - .push adalah method untuk menambahkan item array pada urutan yang paling akhir
 - .pop adalah method yang menghapus item array index terakhir
 - .shift adalah method untuk menghapus item array pada index pertama
 - .unshift adalah method untuk menambahkan array pada index pertama
 - .sort adalah method untuk mengurutkan array secara ascending atau descending
- Looping pada Array. Built in methods untuk melakukan looping pada array ada .map dan .forEach
 - .forEach adalah method untuk melakukan looping pada setiap elemen array
 - .map adalah method untuk melakukan perulangan dengan membuat array baru

&nbsp;

### **Multidimensional Array**
- Multidimensional array bisa dianalogikan sebagai array of array
- Multidimensional array sama seperti matriks yaitu memiliki 2 dimensi (x,y)
- Mengakses multidimensional array
- Penggunaan built in method pada multidimensional array
- Operation using map in multidimensional array
- Looping pada Multidimensional array


- 


### **Javascript Object**
- Object adalah benda mati maupun benda hidup adalah object. Pada programming object adalah sebuah tipe data pada variabel yg menyimpan properti dan fungsi (method)
- Properti adalah data lengkap dari sebuah object
- Method adalah action dari sebuah object.
- Method : jika value yang dimasukkan pada properti berupa function
- console adalah global javascript object dan log adalah properti yang berupa function dari object console
- Nested Object
- Pass by reference : mengubah data pada object melalui function dan memasukkan object sebagai parameter function
- Looping pada object
- Array of object

### **Javascript Recursive**
- Recursive adalah fungsi yang memanggil dirinya sendiri sampai suatu kondisi tertentu terpenuhi
- A new paradigm :
  - Procedural
  - Conditional
  - Looping
  - Modular (function)
  - Recursive
- Ciri dari recursive:
  - Fungsi recursive memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti.
  - fungsi recursive selalu memaanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya.


### **Javascript Regex**
- Regex adalah susunan karakter/karakter spesial yang menggambarkan pattern/pola untuk pencarian text pada sebuah string atau document
REGEX = Text Matching

- Contoh penggunaan Regex :
  - Validasi input dari sebuah form
  - Mencari keyword tertentu pada email atau halaman web
  - Mencari IP adress dalam kisaran tertentu
- Membuat Pola Regex
  - Literals adalah konsep regex adalah konsep yang paling sederhana yaitu dengan membuat regex sesuai dengan text yang ingin dicari
- Built in Method Regex
  - test() yaitu built in method untuk regex yang mengembalikan nilai Boolean untuk kecocokan sebuah nilai yang dicari
- Karakter Set digunakan untuk mencari minimal 1 karakter yabg sesuai. Karakter set menggunakan bracket square []
- match() yaitu method yang mengembalikan nilai array dari karakter yang match
- Flags pada javascript :
i : untuk menghandle case-sensitive. Tidak mempermasalhkan besar kecilnya karakter
g : untuk mencari kedalam seluruh string yang ingin dicari. Jika tidak menggunakan flags g maka sistem akan mengembalikan nilai array pertama yang ditemukan tanpa melanjutkan pencarian
- Karakter Set Short Syntax
\d : seluruh number/digit character
\w : alphanumeric character
\s : whitespace character (space,tab,newline)
- Negasi dari set short syntax yaitu menggunakan tanda ^
- Quantifiers berfungsi untuk membuat format regex menjadi lebih rapi.
- Quantifiers ditandai dengan format {} contoh saat mencari roa{3}r maka akan match dengan string 'roaaar'
- Quantifiers besifat greedy akan mengambil nilai yang paling besar atau maksimal contoh saat mencari roa{3,5}r maka akan match dengan 'roaaar' dan 'roaaaaar' maka yang akan didapatkan adalah yang 'roaaaaar'
- Anchor yaitu digunakan jika ingin mencari karakter yang sama persis.
- Anchor diawali dengan ^ dan diakhiri dengan $
- Alternation yaitu digunakan untuk mencari karakter yang sama persis dengan lebih dari 1 kalimat
- Alternation ditandai dengan format (|)

### **Javascript OOP**
- OOP atau Object Oriented Programming adalah suatu paradigma dalam pemrograman
- 4 Pilar dalam OOP :
  - Encapsulation adalah cara untuk membatasi akses langsung ke properti atau method dari sebuah objek
  - Inheritance adalah sebuah proses dimana sebuah kelas mewariskan properti dan method ke kelas lain atau childnya
  - Polymorpishm adalah kemampuan dari suatu objek untuk memiliki banyak bentuk
  - Abstraction adalah teknik untuk menyembunyikan detail tertentu dari sebuah object atau method dan hanya menampilkan fitur penting dari objek tersebut


### **Javascript Modules**
- Modules memungkinkan untuk memecah kode menjadi file terpisah sehingga mempermudah untuk maintain code
- JavaScript Module bergantung pada pernyataan impor dan ekspor

### **Web Storage**
- Web Storage adalah wadah untuk sebuah data yang digunakan untuk penyimpanan data yang terikat di browsernya
- Jenis Web Storage yang umum digunakan yaitu :
  - Local Storage
  - Session storage
  - IndexDB
  - Cookies

### **Asynchronus**
- Asynchronous sebuah teknik yang menyelesaikan fungsi secara paralel
- Penggunaan asynchronous dapat dilakukan jika kita ingin mengambil data dari database
- Mengapa perlu menggunakan asynchronous? Asynchronous dibutuhkan ketika ada proses yangg membutuhkan waktu lama. Jadi kita bisa mengerjakan proses yg lain secara paralel.
- Callbacks adalah suatu function namun cara pengeksekusiannya yang berbeda yaitu hanya mengeksekusi pada point tertentu.
- Salah satu function yang digunakan untuk mengatur penjadwalan asynchronous adalah setTimeout function
- Asynchronous - Promise
Asynchronous - Promise merupakan suatu object dan digunakan hanya untuk satu event dengan menyimpan hasil dari sebuah operasi asynchronous baik itu hasil yang diinginkan (resolved value) atau alasan kenapa operasi itu gagal (failure reason)
- Asynchronous - Async-Await
Asynchronous - Async-Await merupakan fitur yang hadir sejak ES2017 bekerja dengan cara menunda eksekusi hingga proses asynchronous selesai
- Asynchronous - Fetch
Asynchronous - Fetch merupakan cara baru dalam melakukan network request yang memanfaatkan sebuah Promise dalam penggunaanya. Karen Fetch mengembalikan sebuah Promise maka respon handling yang digunakan adalah then jika promise mengembalikan resolve dan catch jika promise mengembalikan nilai reject
- API dan HTTP Request
    - **API**
     - API sebagai alat untuk berbicra antar perangkat lunak
     - API dapat digunakan untuk sistem berbasis web,sistem operasi, sistem basis data dan perangkat lunak

    - **HTTP**
     - HTTP di desain untuk memungkinkan komunikasi antar klien dan server.
     - HTTP berfungsi sebagai protokol Request-Response antara klien dan server.
     - HTTP Request yaitu Keadaan dimana server membaca apa yang dikirimkan oleh client melalui aplikasi web server
     - HTTP Method :
         - GET digunakan untuk meminta data dari sumber tertentu
         - POST digunakan untuk mengirim data ke server untuk membuat/memperbarui resource
         - PUT digunakan untuk mengirim data ke server untuk membuat/memperbarui resource.
         - DELETE untuk menghapus spesifiksi resource
