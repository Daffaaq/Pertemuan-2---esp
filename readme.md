# Apa itu Spread Operator

Spread Operator (juga dikenal sebagai "rest parameter") adalah fitur baru di ES6 JavaScript yang memungkinkan kita untuk menguraikan elemen dari sebuah array atau properti dari sebuah objek ke dalam argumen atau elemen yang terpisah. Fitur ini ditandai dengan tanda titik tiga (…) dan dapat digunakan dalam beberapa konteks.

Contohnya, kita dapat menggunakan Spread Operator untuk menggabungkan dua atau lebih array ke dalam satu array:

```
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

const combinedArr = [...arr1, ...arr2];

console.log(combinedArr); // Output: [1, 2, 3, 4, 5, 6]

```
Kita juga dapat menggunakan Spread Operator untuk mengcopy array atau objek ke dalam array atau objek yang baru:

```
const originalArr = [1, 2, 3];
const copiedArr = [...originalArr];

console.log(copiedArr); // Output: [1, 2, 3]
```
Spread Operator juga dapat digunakan untuk mengambil argumen variadic (argumen yang jumlahnya tidak pasti) dalam sebuah fungsi:

```
function sum(...numbers) {
  return numbers.reduce((acc, curr) => acc + curr, 0);
}

console.log(sum(1, 2, 3)); // Output: 6
```
Dengan Spread Operator, kita dapat mempermudah dan mempersingkat penulisan kode di dalam JavaScript.

# Kapan Menggunakan Spread Operator
Berikut beberapa kasus di mana kita dapat menggunakan Spread Operator di JavaScript ES6:
1. Menggabungkan dua atau lebih array menjadi satu array:
```
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

const combinedArr = [...arr1, ...arr2];

console.log(combinedArr); // Output: [1, 2, 3, 4, 5, 6]
```
2. Mencopy array atau objek ke dalam array atau objek yang baru:
```
const originalArr = [1, 2, 3];
const copiedArr = [...originalArr];

console.log(copiedArr); // Output: [1, 2, 3]
```
3. Memasukkan nilai dalam array atau objek ke dalam argumen sebuah fungsi:
```
function sum(a, b, c) {
  return a + b + c;
}

const numbers = [1, 2, 3];

console.log(sum(...numbers)); // Output: 6
```
4. Membuat array atau objek baru dengan menambahkan atau mengubah properti:
```
const person = { name: 'John', age: 30 };
const newPerson = { ...person, age: 31 };

console.log(newPerson); // Output: { name: 'John', age: 31 }
```
Dalam beberapa kasus, Spread Operator dapat mempermudah dan mempersingkat penulisan kode di dalam JavaScript. Namun, penggunaan Spread Operator juga harus dipertimbangkan dengan hati-hati tergantung pada konteks dan kebutuhan spesifik pada kode yang sedang dibuat.

# contoh source code Spread Operator
Berikut adalah beberapa contoh penggunaan Spread Operator di JavaScript ES6:
1. Menggabungkan dua atau lebih array menjadi satu array:
```
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

const combinedArr = [...arr1, ...arr2];

console.log(combinedArr); // Output: [1, 2, 3, 4, 5, 6]
```

2. Mencopy array atau objek ke dalam array atau objek yang baru:
```
const originalArr = [1, 2, 3];
const copiedArr = [...originalArr];

console.log(copiedArr); // Output: [1, 2, 3]
```
3. Memasukkan nilai dalam array atau objek ke dalam argumen sebuah fungsi:
```
function sum(a, b, c) {
  return a + b + c;
}

const numbers = [1, 2, 3];

console.log(sum(...numbers)); // Output: 6
```
4. Menerima argumen variadic (argumen yang jumlahnya tidak pasti) dalam sebuah fungsi:
```
function sum(...numbers) {
  return numbers.reduce((acc, curr) => acc + curr, 0);
}

console.log(sum(1, 2, 3)); // Output: 6
```
5. Membuat salinan array dan menghapus beberapa elemen: 
```
const originalArr = [1, 2, 3, 4, 5];
const newArr = [...originalArr.slice(0, 2), ...originalArr.slice(3)];

console.log(newArr); // Output: [1, 2, 4, 5]
```
