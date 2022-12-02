## Tugas Writing & Presentation test Week 7

&nbsp;

## **ORM (Object Relational Mapping)**
-- merupakan teknik pemetaan object perangkat lunak terhadap tabel database tanpa harus menulis query basis data apapun, ORM juga mampu mendukung banyak database contohnya seperti MYSQL, SQLite, dan Postgree.

### **2 cara penggunaan sequelize**
- `Dengan Migration` Migration adalah menyimpan history perubahan pada table yaitu dengan cara setiap create/delete/update kolom otomatis disimpan perubahan dan bisa kembali lagi ke versi tabel sebelumnya dengan menggunakan undo. Dengan langkah sebagai berikut:
  - untuk menginstall sequelize
  ```
  npm install --save-dev sequelize-cli
  ```
  - untuk menginstall database mysql
  ```
  npm install sequelize mysql2
  ```
  - untuk membuat confid, file models, file migration dan file seeders
  ```
  npx sequelize-cli init
  ```
  - ket. file-filenya
    - `config`, untuk menghubungkan atau connecting ke database.
    - file `models`, untuk merepresentasikan tabel yang ada di database.
    - File `migration`, untuk melakukan migrasi ke database atau create database ke database ke mysql.
    - File `seeders`, untuk melakukan penambahan atau mengedit database dengan cara menggunakan async await dan bulkInsert.

- `Tanpa Migration` Jika tanpa menggunakan migration maka kita bisa melakukan install dengan cara
  - npm install --save sequelize
  - npm install --save mysql2 (tergantung menggunakan database)

&nbsp;

## **Associate**
-- merupakan langkah untuk menghubungkan satu tabel dengan tabel lainnya adapun beberapa argumen Association sebagai berikut :
- `hasOne`(one to one),perbedaan dengan belongsTo adalah kunci asing(FK) akan ditentukan pada model target dapat dilakukan dengn cara menambahkan kunci asing ke target dan mixin asosiasi tunggal ke sumbernya.
- `belongsTo`(one to one),dapat dilakukan dengan cara menambahkan kunci asing dan campuran asosiasi tunggal ke sumbernya.
- `hasMany`(one to many),dapat dilakukan dengan cara menambahkan kunci asing ke target dan campuran asosiasi jamak ke sumbernya.
- `belongsToMany`(Many to Many),dapat dilakukan dengan cara membuat asosiasi N:M dengan tabel gabungan dan menambahkan mixin asosiasi jamak ke sumbernya. Tabel persimpangan dibuat dengan sourceId dan targetId.

&nbsp;

## **Mongodb**
-- merupakan salah satu `database no sql` dan sering dipakai untuk aplikasi berbasis cloud big data maupun grid computing serta berorientasi dokumen lintas platform. Karena berbasis no sql, maka mongodb sangatlah berbeda dengan mysql.

### **Schema Mongodb**
Di dalam mongodb terdapat dua cara untuk menyebarkan data, yaitu secara langsung (`embed`) dan mereferensikan bagian data lain (`Referencing`) hal ini mirip dengan join pada sql.

### **Relationship dalam Mongodb**
- One-to-one
- One-to-Few
misalnya adalah satu orang bisa memiliki beberapa alamat rumah
- One-to-many
- One-to-Squilions
Berfungsi jika setiap dokumen memiliki banyak subdokumen yang mungkin melebihi batas aturan yaitu 16mb, biasanya dipakai untuk sebuah host yang memiliki banyak message.
- Many-to-Many

### **CRUD**

- Create
  - db.collection.insertMany()
  - db.collection.insertOne()
  ```
  db.users.insertOne(
      {
         name : "Adnisa",
         age  : 20,
         city : "Tangerang Selatan"
      }
   );
  ```

- Read
  - db.collection.find()
  ```
  db.users.find(
      { age : {$gt:20}}
   ).limit(5);
  ```

- Update
  - db.collection.updateOne()
  - b.collection.updatemany()
  - db.collection.replaceOne()
  ```
  db.users.updateMany(
      {age: {&lt:20}},
      {$set: {city : "single"}}
   )
  ```
  - ket. bahwa `age: 20` adalah filter dan `set: single` merupakan updatenya, jadi semua yang berumur 20 diganti menjadi single

- Delete
  - db.collection.deletOne()
  - db.collection.deletMany()
  ```
  db.users.deleteMany(
      {city : "Tangerang Selatan"}
   )
  ```

&nbsp;

## **Mongoose**
-- merupakan sebuah Object Document Mapper (ODM). Biasanya dipakai untuk mongodb, oleh karena itu mongoose harus bisa melakukan crud terhadap mongodb.
ket.: Semua crud ditaruh di dalam router
- Setting project dengan cara
  ```
  npm init;
  npm install express mongoose
  ```
- buat file server.js
  ```
  const express = require("express");
  const mongoose = require("mongoose");
  const foodRouter = require("./routes/foodRoutes.js");

  const app = express();

  app.use(express.json());

    mongoose.connect(
    "mongodb+srv://madmin:<password>@clustername.mongodb.net/<dbname>?retryWrites=true&w=majority",
    {
    useNewUrlParser: true,
    useFindAndModify: false,
    useUnifiedTopology: true
    }
    );

    app.use(foodRouter);

    app.listen(3000, () => {
  console.log("Server is running...");
  ```
- buat schema dengan membuat models food
  ```
  const mongoose = require("mongoose");

      const FoodSchema = new mongoose.Schema({
        name: {
          type: String,
          required: true,
          trim: true,
          lowercase: true,
        },
        calories: {
          type: Number,
          default: 0,
          validate(value) {
            if (value < 0) throw new Error("Negative calories aren't real.");
          },
        },
      });

      const Food = mongoose.model("Food", FoodSchema);

      module.exports = Food;
  ```
- routes, dimulai dari read/get
  ```
  const express = require("express");
    const foodModel = require("../models/food");
    const app = express();

    app.get("/foods", async (request, response) => {
      const foods = await foodModel.find({});

      try {
        response.send(foods);
      } catch (error) {
        response.status(500).send(error);
      }
    });

    module.exports = app;
  ```
- post/data dokumen baru
  ```
  app.post("/food", async (request, response) => {
    const food = new foodModel(request.body);

    try {
      await food.save();
      response.send(food);
    } catch (error) {
      response.status(500).send(error);
    }
  });

  ```
- update atau patch
  ```
  app.patch("/food/:id", async (request, response) => {
    try {
      await foodModel.findByIdAndUpdate(request.params.id, request.body);
      await foodModel.save();
      response.send(food);
    } catch (error) {
      response.status(500).send(error);
    }
  });
  ```
- delete
  ```
  app.delete("/food/:id", async (request, response) => {
    try {
      const food = await foodModel.findByIdAndDelete(request.params.id);

      if (!food) response.status(404).send("No item found");
      response.status(200).send();
    } catch (error) {
      response.status(500).send(error);
    }
  });
  ```

&nbsp;

## **Docker**
-- merupakan layanan yang mampu untuk mengemas dan menjalankan sebuah aplikasi dalam sebuah lingkungan yang terisolasi. Docker berfungsi ketika ada user yang mengerjakan project di komputer A dan ingin melanjutkannya di komputer B tetapi antara dua komputer tersebut memiliki perbedaan pada OS, biasanya akan terjadi issue yang timbul, hal tersebutlah yang melatar belakangi munculnya Docker.

Cara kerja Docker dengan men-sharing kernel dari host OS serta melakukan atau membuat container suatu aplikasi agar dapat dijalankan dimana saja dan kapan saja serta bersifat terisolasi sehingga tidak terpengaruh oleh faktor luar.

### **perintah dasar docker**

- melihat image `$ docker images`
- download images `$ docker pull [option]`
- melihat Docker containe yang running `$ docker cotainer ls`
- membuat docker container `$ docker container create --name`
- mencari images `$ docker search name_find`
- enghapus container `$ docker container rm name`
- mengetahui versi docker `$ docker --version[option]`
- membuat container dari image `$ docker run [options] image [command] [arg...]`
- melakukan push dari image/repo ke registry `$ docker push [option]`

`Docker compose`
Perlu diketahui bahwasannya kita dapat menjalankan lebih dari 1 container secara bersama-sama dan saling terhubung caranya adalah menjalankan perintah docker-compose nama.file.yaml up.

[...](https://github.com/Hafizhabiyyu777/-Writing-and-Presentation-Test-/blob/main/Week%207/writingWeek7.md)
