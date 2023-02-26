# Apa itu "Array Method forEach() dan map()" pada Javascript ES6

Metode `forEach()` dan `map()` adalah dua metode yang sering digunakan dalam pemrograman JavaScript untuk memanipulasi dan mengolah data dalam array.

Metode `forEach()` adalah metode yang digunakan untuk menjalankan sebuah fungsi pada setiap elemen di dalam array. Metode ini tidak mengembalikan array baru, melainkan hanya melakukan tindakan pada setiap elemen. Contohnya:

```javascript
const angka = [1, 2, 3, 4, 5];

angka.forEach(function(angka) {
  console.log(angka * 2);
});

// Output:
// 2
// 4
// 6
// 8
// 10
```

Metode `map()` adalah metode yang digunakan untuk membuat array baru dengan melakukan operasi pada setiap elemen dari array yang ada. Metode ini mengembalikan array baru yang terdiri dari hasil operasi pada setiap elemen. Contohnya:

```javascript
const angka = [1, 2, 3, 4, 5];

const kaliDua = angka.map(function(angka) {
  return angka * 2;
});

console.log(kaliDua);

// Output:
// [2, 4, 6, 8, 10]
```

Perbedaan antara metode `forEach()` dan `map()` adalah bahwa `forEach()` hanya menjalankan fungsi pada setiap elemen dan tidak mengembalikan nilai apa pun, sedangkan `map()` mengembalikan array baru yang terdiri dari hasil operasi pada setiap elemen.

Dalam pemilihan antara kedua metode, tergantung pada kebutuhan dalam memanipulasi data dalam array. Jika hanya ingin melakukan perubahan pada setiap elemen di dalam array, tanpa memerlukan array baru, maka metode `forEach() `dapat digunakan. Namun, jika ingin membuat array baru yang dihasilkan dari operasi pada setiap elemen di dalam array yang sudah ada, maka metode `map()` dapat digunakan.

### <b> Kapan Menggunakan foreach() dan map()? <b>

Ketika memilih antara metode `map()` dan `forEach()`, Anda perlu mempertimbangkan tujuan Anda dalam memanipulasi array. Berikut ini adalah beberapa kasus penggunaan masing-masing metode:

Gunakan `forEach()` jika Anda ingin melakukan iterasi pada setiap elemen dalam array dan melakukan tindakan atau manipulasi pada setiap elemen. Namun, perlu diingat bahwa `forEach()` tidak mengembalikan nilai apa pun dan hanya melakukan tindakan pada setiap elemen.

Gunakan `map()` jika Anda ingin membuat array baru yang terdiri dari hasil operasi pada setiap elemen di dalam array yang sudah ada. Metode `map()` mengembalikan array baru dan tidak memodifikasi array asli. Jadi, jika Anda ingin membuat array baru dengan hasil manipulasi pada array asli, `map()` adalah pilihan yang tepat.

Berikut contoh penggunaan masing-masing metode:

```javascript
// menggunakan forEach()
const angka = [1, 2, 3, 4, 5];
angka.forEach(function(angka) {
  console.log(angka * 2);
});
// Output: 2 4 6 8 10

// menggunakan map()
const angka = [1, 2, 3, 4, 5];
const hasil = angka.map(function(angka) {
  return angka * 2;
});
console.log(hasil);
// Output: [2, 4, 6, 8, 10]
```

Dalam kasus di atas, jika hanya ingin menampilkan hasil operasi pada setiap elemen dalam array, maka dapat digunakan metode `forEach()`. Namun, jika ingin membuat array baru dengan hasil operasi pada setiap elemen, maka dapat digunakan metode map().

## <b> A. Metode forEach() <b>

Metode `forEach()` adalah salah satu metode bawaan pada objek array di JavaScript. Metode ini memungkinkan kita untuk mengulang setiap elemen pada array dan melakukan sesuatu dengan setiap elemennya.

Berikut adalah sintaks dari metode `forEach()`:

```javascript
array.forEach(function(currentValue, index, array) {
  // code to be executed on each element
});
```

Parameter pertama adalah fungsi yang akan dieksekusi pada setiap elemen. Fungsi ini memiliki tiga parameter opsional:

* `currentValue`: Nilai dari elemen saat ini
* `index`: Indeks elemen saat ini
* `array`: Array yang sedang diulang

Ketika fungsi `forEach()` dijalankan, ia akan memanggil fungsi yang diberikan untuk setiap elemen dalam array. Fungsi tersebut dapat melakukan apa saja dengan elemen, seperti mencetaknya ke konsol, mengubah nilai elemen, atau melakukan operasi apa pun yang diinginkan.

Contoh penggunaan `forEach()`:

```javascript
const array = [1, 2, 3, 4, 5];

array.forEach(function(currentValue, index, array) {
  console.log("Index ke-" + index + " memiliki nilai " + currentValue);
});
```

Output:

```javascript
Index ke-0 memiliki nilai 1
Index ke-1 memiliki nilai 2
Index ke-2 memiliki nilai 3
Index ke-3 memiliki nilai 4
Index ke-4 memiliki nilai 5
```

Dalam contoh di atas, setiap elemen dalam array diulang dan dicetak ke konsol menggunakan `console.log()`.

### 1. Cara Penggunaan forEach()

Menggunakan metode `forEach()` pada objek array di JavaScript dengan melakukan hal-hal berikut:

1. Tentukan array yang akan diulang.

Contoh:

```javascript
const myArray = [1, 2, 3, 4, 5];
```

2. Panggil metode `forEach()` pada array tersebut dan berikan fungsi yang akan dieksekusi untuk setiap elemen.

Contoh:

```javascript
myArray.forEach(function(element) {
  console.log(element);
});
```

Dalam contoh di atas, setiap elemen diulang dan dicetak ke konsol menggunakan `console.log()`.

3. Dapat menggunakan arrow function untuk membuat sintaks lebih pendek.

Contoh:

```javascript
myArray.forEach(element => {
  console.log(element);
});
```

4. Dapat menggunakan indeks elemen dan array yang sedang diulang di dalam fungsi.

Contoh:

```javascript
myArray.forEach(function(element, index, array) {
  console.log("Elemen " + element + " berada pada indeks " + index + " dari array " + array);
});
```

Dalam contoh di atas, fungsi menerima tiga parameter - elemen saat ini, indeks elemen, dan array yang sedang diulang. Setiap elemen dicetak ke konsol bersama dengan indeks dan array yang sedang diulang.

### 2. Kesalahan dalam penggunaan forEach()

Beberapa kesalahan yang umum dilakukan saat menggunakan metode `forEach()` pada objek array di JavaScript adalah:

1. Tidak memberikan argumen pada fungsi yang diberikan ke metode `forEach()`.

Contoh kesalahan:

```javascript
const myArray = [1, 2, 3, 4, 5];

myArray.forEach(); // akan menghasilkan error
```

2. Tidak memeriksa apakah array kosong sebelum menggunakan `forEach()`.

Contoh kesalahan:

```javascript
const myArray = [];

myArray.forEach(function(element) {
  console.log(element); // tidak akan dijalankan karena array kosong
});
```

3. Tidak memperbarui nilai elemen dalam array.

Contoh kesalahan:
```javascript
const myArray = [1, 2, 3, 4, 5];

myArray.forEach(function(element) {
  element += 1; // tidak akan memperbarui nilai elemen dalam array
});

console.log(myArray); // akan mencetak [1, 2, 3, 4, 5]
```

4. Memodifikasi array saat melakukan iterasi dengan `forEach()`.

Contoh kesalahan:
```javascript
const myArray = [1, 2, 3, 4, 5];

myArray.forEach(function(element, index) {
  myArray.splice(index, 1); // akan menghasilkan hasil yang tidak terduga
});

console.log(myArray); // dapat menghasilkan [2, 4]
```

5. Menggunakan return di dalam fungsi yang diberikan ke `forEach()`.

Contoh kesalahan:

```javascript
const myArray = [1, 2, 3, 4, 5];

myArray.forEach(function(element) {
  return element; // tidak berpengaruh pada iterasi
});
```

### 3. Hal yang mempengaruhi terjadinya kesalahan saat menggunakan forEach()

Beberapa faktor yang dapat mempengaruhi kesalahan saat menggunakan metode `forEach()` pada objek array di JavaScript adalah:

1. Bentuk dan tipe data dari array yang sedang diulang.

Misalnya, jika array adalah array multidimensi, maka metode `forEach()` hanya akan berfungsi untuk mengulang elemen dalam dimensi pertama. Jika array berisi objek dengan tipe data yang berbeda, maka perlu memastikan bahwa fungsi yang diberikan ke `forEach()` dapat menangani tipe data yang berbeda tersebut.

2. Fungsi yang diberikan ke metode `forEach()`.

Fungsi yang diberikan ke `forEach()` harus menerima parameter yang benar dan mengembalikan hasil yang benar.

3. Perubahan pada array selama melakukan iterasi dengan metode `forEach()`.

Perubahan pada array selama melakukan iterasi dengan `forEach()` dapat menghasilkan hasil yang tidak terduga atau menghasilkan infinite loop. Oleh karena itu, perlu memperhatikan bahwa array tidak berubah selama melakukan iterasi.

4. Memeriksa nilai kembalian dari metode `forEach()`.

Metode `forEach()` tidak mengembalikan nilai apa pun, sehingga perlu memperhatikan bahwa hasil yang diharapkan dari `forEach()` adalah hasil sampingan dari operasi yang dilakukan pada array.

Untuk menghindari kesalahan saat menggunakan metode `forEach()`, perlu memperhatikan semua faktor di atas dan selalu memeriksa dokumentasi dan contoh penggunaannya sebelum menggunakannya.

## <b> B. Metode map() <b>

Metode `map()` adalah sebuah metode pada objek array dalam JavaScript yang digunakan untuk membuat array baru dengan memanggil fungsi pada setiap elemen dalam array asli.

Secara umum, sintaksis dari metode map() adalah sebagai berikut:

```javascript
array.map(function(currentValue, index, arr), thisValue)
```

`function(currentValue, index, arr)` adalah fungsi yang akan dipanggil untuk setiap elemen dalam array. Fungsi ini dapat memiliki tiga parameter:

* `currentValue` - nilai elemen saat ini dalam array.

* `index` - indeks elemen saat ini dalam array.

* `arr` - array asli yang sedang diproses.

`thisValue` (opsional) - nilai yang digunakan sebagai this saat menjalankan fungsi di atas.

Contoh penggunaan metode `map() `adalah sebagai berikut:

```javascript
const numbers = [1, 2, 3, 4, 5];
const squareNumbers = numbers.map(function(num) {
  return num * num;
});

console.log(squareNumbers); // [1, 4, 9, 16, 25]
```

Pada contoh di atas, metode `map()` dipanggil pada array `numbers` dan meneruskan fungsi untuk mengalikan setiap elemen dalam array dengan dirinya sendiri. Metode `map()` kemudian menghasilkan array baru yang berisi hasil dari operasi tersebut, yang disimpan dalam variabel `squareNumbers`.

### 1. Cara Penggunaan map()

Dapat menggunakan metode `map()` pada objek array dalam JavaScript untuk memproses setiap elemen array dan membuat array baru dengan hasilnya.

Berikut ini adalah contoh cara menggunakan metode `map()`:

```javascript
const numbers = [1, 2, 3, 4, 5];

const squaredNumbers = numbers.map(function(number) {
  return number * number;
});

console.log(squaredNumbers); // Output: [1, 4, 9, 16, 25]
```

Pada contoh di atas, `map()` dipanggil pada array `numbers`. Fungsi yang diberikan sebagai argumen ke `map() `kemudian dijalankan untuk setiap elemen dalam array `numbers`. Fungsi ini mengembalikan hasil perkalian setiap elemen dengan dirinya sendiri, yang disimpan dalam array `squaredNumbers`.

Dapat juga menuliskan fungsi yang dijadikan argumen ke dalam metode `map()` dalam bentuk fungsi arrow, seperti berikut:

```javascript
const numbers = [1, 2, 3, 4, 5];

const squaredNumbers = numbers.map(number => number * number);

console.log(squaredNumbers); // Output: [1, 4, 9, 16, 25]
```

Pada contoh di atas, fungsi arrow `number => number * number` digunakan sebagai argumen untuk `map()`. Fungsi ini melakukan perkalian setiap elemen dengan dirinya sendiri dan mengembalikan hasilnya, yang disimpan dalam array `squaredNumbers`.

Anda juga dapat mengakses indeks dari setiap elemen dalam array dengan menambahkan parameter kedua dalam fungsi yang dijadikan argumen ke dalam `map()`, seperti berikut:

```javascript
const numbers = [1, 2, 3, 4, 5];

const squaredNumbers = numbers.map((number, index) => {
  return `Element ${index} squared: ${number * number}`;
});

console.log(squaredNumbers);
// Output: [
//   "Element 0 squared: 1",
//   "Element 1 squared: 4",
//   "Element 2 squared: 9",
//   "Element 3 squared: 16",
//   "Element 4 squared: 25"
// ]
```
Pada contoh di atas, indeks setiap elemen dalam array `numbers` diakses dan digunakan dalam fungsi yang diberikan sebagai argumen ke `map()`. Fungsi ini mengembalikan string yang berisi indeks elemen dan hasil kuadrat dari setiap elemen, yang disimpan dalam array `squaredNumbers`.

### 2. Cara Penggunaan map() yang salah

Berikut adalah contoh penggunaan metode map() yang salah:

```javascript
const numbers = [1, 2, 3, 4, 5];

numbers.map(function(number) {
  console.log(number * number);
});
```

Pada contoh di atas, `map()` digunakan untuk memproses setiap elemen dalam array `numbers` dan melakukan operasi perkalian setiap elemen dengan dirinya sendiri. Namun, nilai hasil perkalian tidak disimpan dalam variabel atau dijadikan nilai kembalian dari fungsi.

Karena tidak ada variabel atau nilai kembalian dari fungsi yang dihasilkan oleh `map()`, maka hasil operasi perkalian setiap elemen dalam array tidak dapat digunakan di tempat lain dalam program. Selain itu, karena tidak ada nilai yang dikembalikan, maka fungsi dijadikan argumen ke `map()` tidak memiliki efek apa pun pada array `numbers`. Ini dapat terjadi jika kita lupa menambahkan `return` di dalam fungsi, atau jika kita tidak memperhatikan nilai kembalian yang seharusnya dikembalikan oleh fungsi.

Untuk mengatasi kesalahan ini, kita perlu mengubah fungsi yang dijadikan argumen ke `map()` sehingga mengembalikan nilai yang sesuai dari operasi yang dilakukan. Misalnya, kita dapat mengembalikan hasil perkalian setiap elemen array, seperti ini:

```javascript
const numbers = [1, 2, 3, 4, 5];

const result = numbers.map(function(number) {
  return number * number;
});

console.log(result);
```

Pada contoh ini, fungsi yang dijadikan argumen ke `map()` mengembalikan hasil perkalian setiap elemen array dengan dirinya sendiri. Hasil `map()` kemudian disimpan dalam variabel result dan dapat digunakan di tempat lain dalam program.

### 3. Beberapa kesalahan saat menggunakan map()

Beberapa kesalahan umum yang biasanya dilakukan saat menggunakan metode `map()` pada objek array dalam JavaScript antara lain:

1. Tidak menyimpan hasil `map()` pada variabel:

Karena `map()` mengembalikan sebuah array baru, maka hasilnya perlu disimpan dalam variabel agar bisa digunakan di tempat lain dalam program. Jadi pastikan untuk menyimpan hasil `map()` dalam variabel.

2. Tidak mengembalikan nilai dari fungsi yang dijadikan argumen:

Fungsi yang dijadikan argumen ke `map()` harus mengembalikan nilai agar hasil `map()` bisa disimpan dalam variabel atau digunakan dalam operasi lain. Pastikan fungsi tersebut mengembalikan nilai.

3. Tidak menggunakan `return` dalam fungsi:

Jika fungsi yang dijadikan argumen ke `map()` memiliki lebih dari satu baris kode, pastikan untuk menggunakan kata kunci `return` untuk mengembalikan nilai dari fungsi tersebut.

4. Mengubah array asli:

Metode `map()` hanya membuat array baru dengan hasil pemrosesan pada setiap elemen array asli. Jadi pastikan untuk tidak mengubah array asli dalam fungsi yang dijadikan argumen ke `map()`.

5. Tidak mengakses setiap elemen dalam fungsi:

Fungsi yang dijadikan argumen ke `map()` harus mengakses setiap elemen dalam array. Jika fungsi tersebut tidak mengakses setiap elemen, maka hasil `map()` tidak akan memproses seluruh elemen dalam array.

6. Tidak menggunakan parameter kedua untuk mengatur nilai `this`:

Jika Anda ingin mengatur nilai `this` dalam fungsi yang dijadikan argumen ke `map()`, maka Anda perlu menggunakan parameter kedua untuk mengaturnya. Jika tidak, nilai `this` akan menjadi `undefined`.

7. Tidak mengecek argumen fungsi:

Pastikan argumen fungsi yang dijadikan argumen ke `map()` sesuai dengan apa yang dibutuhkan oleh fungsi tersebut. Jika argumen tidak sesuai, maka akan terjadi kesalahan saat menjalankan program.
