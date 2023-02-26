# Apa yang dimaksud dengan multiple impor/ekspor javascript?
Dalam JavaScript, istilah "impor" dan "ekspor" digunakan untuk menentukan bagaimana modul diatur dan dibagikan di berbagai bagian aplikasi.<br>
Pernyataan "Impor" digunakan untuk memuat modul ke dalam file, sedangkan pernyataan "ekspor" digunakan untuk mengekspos bagian modul untuk digunakan di file lain. Beberapa impor/ekspor mengacu pada kemampuan untuk mengimpor dan mengekspor beberapa item dalam satu pernyataan.<br>
## contoh "import" untuk memuat banyak item dari modul seperti ini:<br>
```
import { item1, item2, item3 } from './myModule';<br>
Dalam hal ini, item "item1", "item2", dan "item3" sedang diimpor dari file "myModule".<br>
```
## contoh "ekspor" untuk mengekspor beberapa item dari modul seperti ini:
```
export { item1, item2, item3 };
```
<br>
Dalam hal ini, item "item1", "item2", dan "item3" diekspor dari modul.<br><br>
Beberapa pernyataan impor/ekspor dapat membuat kode lebih ringkas dan lebih mudah dibaca dengan mengurangi jumlah baris kode yang diperlukan untuk mengimpor atau mengekspor beberapa item<br><br>
# Kapan bisa menggunakan banyak impor/ekspor javascript?<br>
Beberapa pernyataan impor/ekspor dapat digunakan setiap kali ada banyak item dalam modul yang perlu diimpor atau diekspor. Ini sering terjadi ketika modul berisi kumpulan fungsi, kelas, atau konstanta terkait yang digunakan di berbagai bagian aplikasi.<br>
Misalnya, modul bernama "utils" yang berisi beberapa fungsi pembantu, serta beberapa konstanta dan kelas:<br>

```
// utils.js

export const PI = 3.14159;

export function square(x) {<br>
  return x * x;<br>
}<br>

export function cube(x) {<br>
  return x * x * x;<br>
}<br>

export class Point {<br>
  constructor(x, y) {<br>
    this.x = x;<br>
    this.y = y;<br>
  }<br>

  distance() {<br>
    return Math.sqrt(this.x * this.x + this.y * this.y);<br>
  }<br>
}
```

Untuk menggunakan item ini di modul lain, Anda dapat menggunakan beberapa pernyataan import seperti ini:<br>
```
// main.js

import { PI, square, cube, Point } from './utils';

console.log(PI);<br>
console.log(square(3));<br>
console.log(cube(3));<br>

const p = new Point(3, 4);<br>
console.log(p.distance());<br>
```
Dalam contoh ini, menggunakan pernyataan impor tunggal untuk mengimpor beberapa item dari modul "utils". Kami kemudian dapat menggunakan item ini dalam kode kami sesuai kebutuhan.<br>
### Secara keseluruhan, menggunakan beberapa pernyataan impor/ekspor dapat membantu membuat kode Anda lebih modular, lebih mudah dibaca, dan lebih mudah dipelihara, terutama dalam aplikasi besar yang memiliki banyak modul dan file berbeda.



=======================================================================================================================================================================

# Export Default
## 1. Apa itu "export default" pada javascript module
Export default adalah sintaks JavaScript yang digunakan untuk mengekspor nilai default dari sebuah modul. Dalam JavaScript, modul adalah unit kode yang dapat diimpor dan diekspor ke modul lain. Ketika Anda mengekspor sebuah nilai dari sebuah modul menggunakan export default, nilai tersebut dapat diimpor ke modul lain tanpa harus menyebutkan nama ekspor.

Berikut adalah contoh penggunaan export default:

```javascript
// di dalam moduleA.js
const nilaiDefault = 'Ini nilai default';
export default nilaiDefault;
```
```javascript
// di dalam moduleB.js
import nilaiDefault from './moduleA.js';
console.log(nilaiDefault); // Output: Ini nilai default
```
Dalam contoh di atas, nilaiDefault diekspor sebagai nilai default dari moduleA.js. Kemudian, di dalam moduleB.js, nilai default tersebut diimpor dengan menggunakan sintaks import nilaiDefault from './moduleA.js' dan kemudian digunakan di dalam console.log.

Jika sebuah modul hanya memiliki satu nilai yang ingin diekspor, export default dapat digunakan untuk membuat ekspor tersebut lebih mudah dan sederhana untuk diimpor di modul lain. Namun, jika modul memiliki beberapa nilai yang ingin diekspor, sebaiknya menggunakan export biasa.

## 2. kapan kita harus menggunakan export default 
Anda dapat menggunakan export default ketika Anda ingin mengekspor satu nilai sebagai nilai default dari sebuah modul. Beberapa contoh penggunaan export default antara lain:
1. Ketika Anda membuat sebuah fungsi yang akan digunakan sebagai entry point aplikasi, seperti fungsi main() di C/C++, atau fungsi public static void main() di Java. Dalam hal ini, Anda dapat mengekspor fungsi tersebut sebagai nilai default dari sebuah modul.
```javascript
// di dalam moduleA.js
export default function main() {
  // kode untuk aplikasi
}
```

```javascript
// di dalam index.js
import main from './moduleA.js';
main();
```
2. Ketika Anda ingin mengekspor sebuah kelas. Dalam hal ini, Anda dapat mengekspor kelas tersebut sebagai nilai default dari sebuah modul.
```javascript
// di dalam moduleA.js
export default class MyClass {
  // definisi kelas
}
```

```javascript
// di dalam index.js
import MyClass from './moduleA.js';
const myObj = new MyClass();
```
3. Ketika Anda ingin mengekspor sebuah nilai yang paling sering digunakan atau utama dari sebuah modul. Dalam hal ini, Anda dapat mengekspor nilai tersebut sebagai nilai default dari sebuah modul.
```javascript
// di dalam moduleA.js
const nilaiUtama = 'Ini nilai utama';
export default nilaiUtama;
export const nilaiLain = 'Ini nilai lain';
```

```javascript
// di dalam index.js
import nilaiUtama from './moduleA.js';
console.log(nilaiUtama);
```
Dalam situasi-situasi seperti di atas, penggunaan export default dapat membuat kode menjadi lebih mudah dibaca dan lebih sederhana ketika kita mengimpor nilai dari sebuah modul. Namun, jika modul memiliki beberapa nilai yang ingin diekspor, sebaiknya menggunakan export biasa.

## 3. perbedaan export dan export default pada javascript modul
1. export digunakan untuk mengekspor satu atau lebih nilai dari modul JavaScript, sedangkan export default digunakan untuk mengekspor nilai default dari modul JavaScript.
2. Dalam satu modul, kita dapat menggunakan export untuk mengekspor banyak nilai, sedangkan export default hanya dapat digunakan untuk mengekspor satu nilai default.
3. Saat mengimpor nilai yang diekspor menggunakan export, kita harus menyertakan nama variabel atau fungsi yang diekspor, sedangkan saat mengimpor nilai yang diekspor menggunakan export default, kita dapat memberikan nama apapun pada variabel yang digunakan untuk menyimpan nilai tersebut.
4. Saat mengimpor nilai yang diekspor menggunakan export, kita dapat mengimpor nilai tersebut secara spesifik atau keseluruhan dengan menggunakan tanda {}. Namun, saat mengimpor nilai yang diekspor menggunakan export default, kita hanya perlu menggunakan nama variabel tanpa tanda kurung kurawal.

Contoh penggunaan export:

```javascript
// file module.js
export const name = 'John';
export const age = 25;
```

Contoh penggunaan export default:

```javascript
// file module.js
const data = { name: 'John', age: 25 };
export default data;
```

Contoh penggunaan import:

```javascript
// mengimpor nilai yang diekspor menggunakan export
import { name, age } from './module.js';

// mengimpor nilai yang diekspor menggunakan export default
import data from './module.js';
```

Dalam contoh di atas, name dan age diekspor menggunakan export, sedangkan data diekspor menggunakan export default. Saat mengimpor, kita dapat menggunakan {} untuk nilai yang diekspor menggunakan export, sedangkan kita hanya perlu menggunakan nama variabel untuk nilai yang diekspor menggunakan export default.

## 4. Cara memproses export default pada javascript modul
Untuk memproses export default pada JavaScript modul, langkah-langkahnya adalah sebagai berikut:

1. Buat file JavaScript yang akan diekspor nilai defaultnya.
2. Tambahkan nilai default yang ingin diekspor menggunakan sintaks 'export default'.
3. Simpan file dengan nama yang sesuai dengan nilai yang diekspor dan ekstensi '.js'.
4. Di dalam file JavaScript lain yang ingin mengimpor nilai default, gunakan sintaks 'import' dengan menambahkan nama variabel yang ingin digunakan untuk menyimpan nilai default.
5. Selesaikan proses import.

Berikut adalah contoh cara memproses export default pada JavaScript modul:
1. Buat file greetings.js dengan kode berikut:
```javascript
const greeting = {
  en: 'Hello',
  id: 'Halo',
  fr: 'Bonjour'
};

export default greeting;

```
2. Simpan file 'greetings.js'.
3. Buat file JavaScript lain yang ingin mengimpor nilai default dari 'greetings.js'. Misalnya, 'index.js'.
4. Di dalam file 'index.js', gunakan sintaks 'import' untuk mengimpor nilai default dari 'greetings.js'. Di sini, kita akan menyimpan nilai default di dalam variabel 'greet'.
```javascript
import greet from './greetings.js';

console.log(greet.en); // Output: 'Hello'
console.log(greet.id); // Output: 'Halo'
console.log(greet.fr); // Output: 'Bonjour'
```
5. Selesaikan proses import. Dalam contoh di atas, kita mengimpor nilai default dari 'greetings.js' dan menyimpannya dalam variabel 'greet'. Kita dapat menggunakan variabel 'greet' untuk mengakses nilai default yang diekspor dari 'greetings.js'.

=======================================================================================================================================================================

=======================================================================================================================================================================
