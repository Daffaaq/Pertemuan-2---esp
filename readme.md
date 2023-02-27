# String Template

## Pengertian String Template di JavaScript

Template string juga disebut sebagai "template literal" atau "string literal", dan diperkenalkan dalam standar ECMAScript 6 (atau ES2015). Dalam template string, kita dapat menulis string dengan cara yang lebih ekspresif dan menambahkan variabel atau ekspresi yang di dalamnya akan dievaluasi sebagai bagian dari string.

Template string ditulis dengan backtick (`), yang berbeda dengan string biasa yang ditulis dengan tanda kutip tunggal ('') atau ganda (""). Berikut ini contoh penggunaan template string:
<!-- <br> -->

```
let name = 'John';
let age = 30;
let message = `Hello, my name is ${name} and I am ${age} years old`;
console.log(message);

```

<!-- <img src="1.png"> -->

## kenapa harus menggunakan Template String di JavaScript

Ada beberapa alasan mengapa kita harus menggunakan String Template di JavaScript, di antaranya:

1. Lebih mudah untuk membaca dan menulis
   Dengan String Template, kita dapat menulis kode JavaScript dengan cara yang lebih mudah dibaca dan dipahami. Kita dapat memasukkan variabel atau ekspresi ke dalam string tanpa harus menggunakan operator konkatentasi ('+') atau escape sequence ('\'), sehingga membuat kode menjadi lebih rapi dan mudah dibaca.

2. Mencegah kesalahan penulisan
   Dalam penggunaan string biasa, kita harus memastikan tanda kutip yang digunakan sesuai dengan jenis kutip yang kita gunakan (kutip tunggal atau ganda). Jika kita salah memasang tanda kutip atau lupa menutupnya, maka akan menyebabkan kesalahan pada kode.
   Dengan String Template, kita dapat menghindari masalah ini, karena kita hanya perlu menggunakan backtick (`) untuk menulis string, tanpa perlu khawatir dengan tanda kutip.

3. Meningkatkan efisiensi pengembangan
   Dalam kode yang kompleks, terkadang kita perlu menampilkan banyak variabel atau ekspresi dalam satu string. Dengan menggunakan operator konkatentasi (+) untuk menggabungkan string dan variabel, akan memakan waktu dan membuat kode menjadi lebih panjang.
   Dalam hal ini, String Template menjadi lebih efisien, karena kita dapat menulis kode dengan lebih singkat dan menggabungkan string dengan variabel atau ekspresi secara langsung di dalam backtick (`), sehingga membuat kode lebih efisien dan efektif.
   Dengan alasan di atas, String Template menjadi alat yang sangat berguna dalam penulisan kode JavaScript, khususnya dalam penggunaan string. Hal ini juga dapat meningkatkan kejelasan kode dan efisiensi pengembangan pada aplikasi yang lebih kompleks.

## kapan harus menggunakan Template String di JavaScript
   Kita sebaiknya menggunakan String Template di JavaScript ketika kita perlu membuat string yang kompleks dengan memasukkan variabel atau ekspresi. Beberapa contoh situasi di mana String Template sebaiknya digunakan adalah:
   
1. Membuat pesan atau string yang kompleks.
   Ketika kita perlu membuat pesan atau string yang kompleks dengan memasukkan banyak variabel atau ekspresi, String Template menjadi pilihan yang tepat. Penggunaan String Template akan membuat kode lebih mudah dibaca dan efisien.

Contoh penggunaan String Template untuk membuat pesan yang kompleks:

```
let firstName = 'John';
let lastName = 'Doe';
let age = 30;

let message = `Hello, my name is ${firstName} ${lastName} and I am ${age} years old.`;

console.log(message);
// Output: Hello, my name is John Doe and I am 30 years old.

```

2. Membangun URL atau path file yang kompleks.
   Ketika kita perlu membangun URL atau path file yang kompleks dengan memasukkan variabel atau ekspresi, String Template akan mempermudah tugas kita. Dengan menggunakan String Template, kita dapat menyusun URL atau path file dengan lebih mudah dan efisien.

Contoh penggunaan String Template untuk membangun URL atau path file yang kompleks:
```
let baseUrl = 'https://example.com';
let endpoint = '/api/users';
let userId = 123;

let url = `${baseUrl}${endpoint}/${userId}`;

console.log(url);
// Output: https://example.com/api/users/123
```

## contoh source code Template string di java script
Berikut adalah contoh penggunaan String Template di JavaScript:

```
let firstName = 'John';
let lastName = 'Doe';
let age = 30;

let message = `Hello, my name is ${firstName} ${lastName} and I am ${age} years old.`;

console.log(message);
// Output: Hello, my name is John Doe and I am 30 years old.

```

Dalam contoh ini, kita menggunakan String Template untuk membuat pesan yang kompleks dengan memasukkan beberapa variabel. Kita dapat menggunakan '${}' untuk memasukkan variabel atau ekspresi ke dalam String Template.

Berikut adalah contoh lain penggunaan String Template di JavaScript:

```
let name = 'John Doe';
let amount = 1000;

let message = `Dear ${name}, your account has been credited with $${amount}.`;

console.log(message);
// Output: Dear John Doe, your account has been credited with $1000.
```

Dalam contoh ini, kita menggunakan String Template untuk membuat pesan yang kompleks dengan memasukkan variabel dan ekspresi ke dalam String Template.
