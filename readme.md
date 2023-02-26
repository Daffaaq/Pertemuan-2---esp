# Apa itu "Processing Object" pada Javascript ES6

## Object pada Javascript ES6

Dalam JavaScript, objek adalah kumpulan pasangan kunci-nilai, di mana kuncinya adalah string atau simbol dan nilainya dapat berupa tipe data apa pun, termasuk objek lain.

Berikut adalah contoh sederhana pembuatan object dalam JavaScript :

```javascript
let person = {
  name: "John",
  age: 30,
  gender: "Male",
  occupation: "Developer",
};
```

## Cara memproses object dalam Javascript ES6

Ada beberapa cara untuk memproses objek dalam JavaScript, antara lain:

1. Mengakses properti objek <br>
   Anda dapat mengakses properti objek menggunakan notasi titik atau notasi braket. Misalnya, jika Anda memiliki objek bernama person dengan properti name, Anda dapat mengaksesnya menggunakan person.name atau person['name'].

```javascript
let person = {
  name: "John",
  age: 30,
};

console.log(person.name); // Output: 'John'
console.log(person["name"]); // Output: 'John'
```

2. Menambahkan atau memodifikasi properti objek <br>
   Anda dapat menambahkan atau memodifikasi properti objek menggunakan notasi titik atau notasi braket. Misalnya, Anda dapat menambahkan properti usia baru ke objek person menggunakan person.age = 30 atau person['age'] = 30.

```javascript
let person = {
  name: "John",
  gender: "Male",
  occupation: "Developer",
};

person.age = 30;
person["age"] = 30;

console.log(person.age); //Outuput: '30'
```

3. Menghapus properti objek <br>
   Anda dapat menghapus properti dari objek menggunakan operator hapus. Misalnya, Anda dapat menghapus properti usia dari objek person menggunakan delete person.age atau delete person['age'].

```javascript
let person = {
  name: "John",
  age: 30,
  gender: "Male",
  occupation: "Developer",
};

console.log(person.age); //Output '30'

delete person.age;
delete person["age"];

console.log(person.age); //Outuput Undifined
```

4. Mengulangi properti objek <br>
   Anda dapat mengulang properti objek menggunakan for...in loop. Misalnya, Anda dapat mengulangi properti objek person menggunakan kode berikut:

```javascript
let person = {
  name: "John",
  age: 30,
  gender: "Male",
  occupation: "Developer",
};

for (let key in person) {
  console.log(key + ": " + person[key]);
} //Output
//'name: John'
//'age: 30'
//'gender: Male'
//'occupation: Developer'
```

5. Memeriksa apakah suatu objek memiliki properti <br>
   Anda dapat memeriksa apakah suatu objek memiliki properti tertentu menggunakan operator in atau metode hasOwnProperty. Misalnya, Anda dapat memeriksa apakah objek person memiliki properti name menggunakan if ('name' in person) atau if (person.hasOwnProperty('name')).

<b> a. Operator in </b> digunakan untuk memeriksa apakah sebuah properti tertentu terdapat dalam sebuah objek. Operator in akan mengembalikan nilai boolean true jika properti tersebut terdapat dalam objek dan false jika tidak.

Berikut adalah contoh penggunaan operator in dalam JavaScript:

```javascript
let person = {
  name: "John",
  age: 30,
  gender: "Male",
};

console.log("name" in person); // Output: true
console.log("address" in person); // Output: false
```

<b> b. hasOwnProperty </b> adalah sebuah method bawaan dari Object di JavaScript yang digunakan untuk memeriksa apakah sebuah properti (atau key) tertentu terdapat dalam objek. Method ini mengembalikan nilai boolean true jika properti tersebut ditemukan dalam objek, dan false jika tidak ditemukan.

Berikut adalah contoh penggunaan hasOwnProperty dalam JavaScript:

```javascript
let person = {
  name: "John",
  age: 30,
  gender: "Male",
};

console.log(person.hasOwnProperty("name")); // Output: true
console.log(person.hasOwnProperty("address")); // Output: false
```

6. Menyalin objek <br>
   Anda dapat menyalin objek menggunakan metode Object.assign() atau operator spread (...).

<b> a. Metode Object.assign() </b> adalah metode bawaan dari objek JavaScript yang digunakan untuk menyalin nilai properti dari satu atau lebih objek ke objek target. Metode ini mengembalikan objek target yang telah dimodifikasi dengan nilai properti yang disalin dari objek sumber.

Berikut adalah contoh penggunaan Object.assign() dalam JavaScript:

```javascript
let obj1 = { a: 10, b: 20, c: 30 };
let obj2 = { b: 40, d: 50 };

let obj3 = Object.assign({}, obj1, obj2);

console.log(obj3); // Output: { a: 10, b: 40, c: 30, d: 50 }
```

Pada contoh di atas, kita memiliki dua buah objek yaitu obj1 dan obj2. Kita ingin menyalin semua properti dari obj1 dan obj2 ke dalam objek baru obj3.

Kita menggunakan metode Object.assign() pada objek target kosong {} dan objek sumber obj1 dan obj2. Metode ini akan menyalin semua properti dari obj1 dan obj2 ke objek target obj3.

Setelah metode Object.assign() dijalankan, objek obj3 akan memiliki nilai properti { a: 10, b: 40, c: 30, d: 50 }. Properti a, b, dan c disalin dari objek obj1, sedangkan properti b dan d disalin dari objek obj2. Perlu diperhatikan bahwa nilai properti b akan diambil dari objek sumber terakhir, yaitu objek obj2. Oleh karena itu, nilai properti b pada objek obj3 adalah 40 bukan 20.

<b> b. Operator spread (...) </b> adalah fitur terbaru pada JavaScript yang memungkinkan kita untuk menyebar (spread) nilai dari sebuah array atau objek ke dalam tempat lain seperti parameter fungsi, array baru, objek baru, dan sebagainya.

Berikut adalah contoh penggunaan operator spread pada array dalam JavaScript:

```javascript
let obj1 = { a: 10, b: 20 };
let obj2 = { c: 30, d: 40 };
let obj3 = { ...obj1, ...obj2 };

console.log(obj3); // Output: { a: 10, b: 20, c: 30, d: 40 }
```

Pada contoh di atas, kita memiliki dua buah objek yaitu obj1 dan obj2. Kita ingin menggabungkan kedua objek tersebut menjadi sebuah objek baru obj3.

Kita menggunakan operator spread (...) pada objek obj1 dan obj2 dalam deklarasi objek obj3. Operator spread ini akan menyebar nilai dari objek obj1 dan obj2 ke dalam objek obj3.

Setelah operator spread dijalankan, objek obj3 akan memiliki nilai { a: 10, b: 20, c: 30, d: 40 }. Properti a dan b berasal dari objek obj1, sedangkan properti c dan d berasal dari objek obj2.
