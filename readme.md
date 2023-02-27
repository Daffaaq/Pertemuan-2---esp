# Apa itu 'REST PARAMETER' Dalam Javascript ES6

Rest parameter adalah sebuah fitur pada JavaScript yang memungkinkan sebuah fungsi untuk menerima sejumlah argumen yang tidak terbatas dalam bentuk array. Dalam fungsi, rest parameter didefinisikan menggunakan tanda tiga titik (ellipsis) di depan nama parameter, seperti contoh berikut:

```javascript
function jumlahkan(...angka) {
  let hasil = 0;
  for (let i = 0; i < angka.length; i++) {
    hasil += angka[i];
  }
  return hasil;
}

console.log(jumlahkan(1, 2, 3, 4, 5)); // Output: 15
```

Dalam contoh di atas, rest parameter `...angka` memungkinkan fungsi `jumlahkan` menerima argumen sebanyak apapun dan memasukkannya ke dalam array `angka`. Kemudian, array `angka` tersebut diiterasi dan dijumlahkan, lalu hasilnya dikembalikan dari fungsi tersebut. Dengan rest parameter, kita tidak perlu menentukan berapa banyak argumen yang akan diterima oleh sebuah fungsi, sehingga fungsi tersebut lebih fleksibel dan mudah digunakan.

## CARA MEMBUAT REST PARAMETER

Untuk membuat rest parameter pada sebuah fungsi JavaScript, Anda hanya perlu menambahkan tanda tiga titik (ellipsis) di depan nama parameter pada definisi fungsi. Berikut adalah contoh sederhana cara membuat rest parameter:

```javascript

function contohRestParameter(...argumen) {
  console.log(argumen);
}

contohRestParameter('satu', 'dua', 'tiga');
// Output: ["satu", "dua", "tiga"]
```

Dalam contoh di atas, fungsi `contohRestParameter` memiliki parameter `...argumen` yang berfungsi sebagai rest parameter. Ketika fungsi tersebut dipanggil dengan tiga argumen, argumen-argumen tersebut akan dikumpulkan ke dalam sebuah array dengan nama `argumen`. Kemudian array `argumen` tersebut dicetak pada konsol menggunakan `console.log()`.

Kita dapat mengakses elemen-elemen pada rest parameter menggunakan metode yang sama seperti mengakses elemen-elemen pada sebuah array, seperti contoh di bawah ini:

```javascript

function jumlahkan(...angka) {
  let hasil = 0;
  for (let i = 0; i < angka.length; i++) {
    hasil += angka[i];
  }
  return hasil;
}

console.log(jumlahkan(1, 2, 3, 4, 5)); // Output: 15
```

Dalam contoh di atas, rest parameter `...angka` berfungsi untuk mengumpulkan argumen-argumen yang diterima oleh fungsi `jumlahkan` ke dalam sebuah array yang dinamakan `angka`. Kemudian, array `angka` tersebut diiterasi dan dijumlahkan menggunakan perulangan `for`. Akhirnya, hasil penjumlahan dikembalikan dari fungsi tersebut.

## KAPAN MENGGUNAKAN REST PARAMETER?

Rest parameter pada JavaScript sangat berguna ketika kita ingin membuat sebuah fungsi yang dapat menerima sejumlah argumen dengan jumlah yang tidak pasti. Dengan menggunakan rest parameter, kita dapat mengumpulkan argumen-argumen tersebut ke dalam sebuah array yang dapat diakses di dalam fungsi. Beberapa contoh kasus penggunaan rest parameter pada fungsi adalah:

1. Menghitung jumlah argumen pada fungsi

Rest parameter dapat digunakan untuk menghitung jumlah argumen yang diterima oleh sebuah fungsi. Kita dapat mengakses panjang array rest parameter untuk mengetahui jumlah argumen yang diterima oleh fungsi.

Contoh:

```javascript

function hitungJumlahArgumen(...args) {
  console.log(`Jumlah argumen yang diterima: ${args.length}`);
}

hitungJumlahArgumen(); // Output: Jumlah argumen yang diterima: 0
hitungJumlahArgumen(1, 2, 3); // Output: Jumlah argumen yang diterima: 3
hitungJumlahArgumen('satu', 'dua', 'tiga', 'empat'); // Output: Jumlah argumen yang diterima: 4
```

2. Menggabungkan beberapa array

Rest parameter dapat digunakan untuk mengumpulkan beberapa array ke dalam sebuah array baru.

Contoh:

```javascript

function gabungkanArray(...arrays) {
  let hasil = [];
  for (let i = 0; i < arrays.length; i++) {
    hasil = hasil.concat(arrays[i]);
  }
  return hasil;
}

const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = [7, 8, 9];

console.log(gabungkanArray(arr1, arr2, arr3));
// Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
     
```

3. Menghitung total dari sejumlah angka

Rest parameter dapat digunakan untuk mengumpulkan sejumlah angka yang akan dijumlahkan.

Contoh:

```javascript

function jumlahkanAngka(...angka) {
  let hasil = 0;
  for (let i = 0; i < angka.length; i++) {
    hasil += angka[i];
  }
  return hasil;
}

console.log(jumlahkanAngka(1, 2, 3, 4, 5)); // Output: 15
```

## PERBEDAAN REST PARAMETER DENGAN SPREAD OPERATOR

Spread operator dan rest parameter merupakan dua fitur yang saling berhubungan pada JavaScript. Namun, keduanya memiliki perbedaan dalam cara penggunaannya.

Spread operator ditandai dengan tiga titik (ellipsis) yang digunakan untuk "menyebar" elemen-elemen dari sebuah array atau objek ke tempat lain. Berikut adalah contoh penggunaan spread operator pada array:

```javascript

const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

const arr3 = [...arr1, ...arr2];

console.log(arr3); // Output: [1, 2, 3, 4, 5, 6]
```

Dalam contoh di atas, spread operator `'...'` digunakan untuk menggabungkan elemen-elemen dari dua buah array (`arr1`dan `arr2`) ke dalam sebuah array baru yang dinamakan `arr3`. Spread operator memungkinkan kita untuk menyebar elemen-elemen dari sebuah array atau objek ke tempat lain, seperti dalam contoh di atas.

Sementara itu, rest parameter juga menggunakan tanda tiga titik, tetapi pada posisi yang berbeda. Rest parameter digunakan pada definisi sebuah fungsi dan digunakan untuk mengumpulkan argumen-argumen yang diterima oleh fungsi tersebut ke dalam sebuah array. Berikut adalah contoh penggunaan rest parameter pada sebuah fungsi:

```javascript
function jumlahkan(...angka) {
  let hasil = 0;
  for (let i = 0; i < angka.length; i++) {
    hasil += angka[i];
  }
  return hasil;
}

console.log(jumlahkan(1, 2, 3, 4, 5)); // Output: 15
```

Dalam contoh di atas, rest parameter `...angka` digunakan pada definisi fungsi `jumlahkan` untuk mengumpulkan argumen-argumen yang diterima oleh fungsi tersebut ke dalam sebuah array dengan nama `angka`. Kemudian, elemen-elemen pada array `angka` dijumlahkan dan hasilnya dikembalikan dari fungsi tersebut.

Dapat dilihat bahwa perbedaan utama antara spread operator dan rest parameter adalah pada posisi dan cara penggunaannya. Spread operator digunakan untuk menyebar elemen-elemen dari sebuah array atau objek ke tempat lain, sedangkan rest parameter digunakan untuk mengumpulkan argumen-argumen pada definisi sebuah fungsi ke dalam sebuah array
