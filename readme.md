# ASYNC JAVASCRIPT PROMISE

## *Apa pengertian dari async javascript promise?*

Async JavaScript Promise adalah konsep di dalam bahasa pemrograman JavaScript yang membantu developer mengelola dan menangani operasi asinkron (asynchronous) yang kompleks.

Promise adalah sebuah objek yang merepresentasikan nilai yang belum tersedia, namun akan tersedia di masa depan ketika operasi asinkron selesai. Dalam praktiknya, Promise digunakan untuk menghindari callback hell dan membuat kode menjadi lebih mudah dipahami dan dikelola.

Async/await adalah fitur baru yang diperkenalkan pada ES8/ES2017 yang memungkinkan penulisan kode asinkron dengan gaya yang mirip dengan kode sinkron. Dengan async/await, pengguna dapat menulis kode asinkron seperti menulis kode sinkron, tanpa harus berurusan dengan callback atau Promise yang kompleks.

Dalam async JavaScript Promise, Anda dapat menggunakan promise untuk melakukan operasi asinkron seperti memuat data dari server atau mengeksekusi fungsi yang membutuhkan waktu yang lama untuk dijalankan, dan kemudian menggunakan async/await untuk menunggu hasil operasi tersebut selesai sebelum melanjutkan eksekusi kode.

## *Kapan menggunakan async javascript promise?*

Async JavaScript Promise digunakan ketika Anda ingin menangani operasi asinkron (asynchronous) dalam kode JavaScript.

Beberapa contoh operasi asinkron yang umum dilakukan dalam JavaScript meliputi:

1. Memuat data dari server
2. Mengambil data dari API
3. Menjalankan operasi I/O yang membutuhkan waktu yang lama, seperti membaca atau menulis file
4. Menggunakan timer, seperti setTimeout() dan setInterval()

Dalam kasus-kasus seperti ini, Anda dapat menggunakan Promise untuk melakukan operasi asinkron dan menentukan tindakan yang akan diambil ketika operasi selesai, baik berhasil atau gagal. Promise memungkinkan Anda untuk menuliskan kode yang bersifat non-blocking, sehingga tidak menghentikan eksekusi kode pada saat menunggu hasil operasi asinkron.

Selain Promise, Anda juga dapat menggunakan async/await untuk menangani operasi asinkron. async/await adalah cara baru dan lebih mudah untuk menulis kode asinkron, di mana Anda dapat menunggu hasil operasi asinkron sebelum melanjutkan eksekusi kode. async/await sangat berguna ketika Anda ingin menulis kode asinkron yang bersifat sinkronus, karena kode yang ditulis dengan cara ini lebih mudah dibaca dan dipahami.

## *Kapan menggunakan async javascript promise dan contohnya*

Async JavaScript Promise digunakan ketika Anda ingin menangani operasi asinkron dalam JavaScript, seperti memuat data dari server, mengambil data dari API, atau mengeksekusi fungsi yang membutuhkan waktu yang lama untuk dijalankan. Berikut ini adalah beberapa contoh penggunaan async JavaScript Promise:

1. Memuat data dari server dengan XMLHttpRequest

```javascript

function loadData(url) {
  return new Promise(function(resolve, reject) {
    var xhr = new XMLHttpRequest();
    xhr.open('GET', url);
    xhr.onload = function() {
      if (xhr.status === 200) {
        resolve(xhr.responseText);
      } else {
        reject(xhr.statusText);
      }
    };
    xhr.onerror = function() {
      reject(xhr.statusText);
    };
    xhr.send();
  });
}

loadData('https://example.com/data')
  .then(function(response) {
    console.log(response);
  })
  .catch(function(error) {
    console.error(error);
  });
```

2. Mengambil data dari API dengan fetch()

```javascript

fetch('https://api.example.com/data')
  .then(function(response) {
    if (!response.ok) {
      throw new Error(response.statusText);
    }
    return response.json();
  })
  .then(function(data) {
    console.log(data);
  })
  .catch(function(error) {
    console.error(error);
  });
```

3. Menjalankan operasi I/O yang membutuhkan waktu yang lama

```javascript
function readFile(filePath) {
  return new Promise(function(resolve, reject) {
    var fs = require('fs');
    fs.readFile(filePath, 'utf8', function(error, data) {
      if (error) {
        reject(error);
      } else {
        resolve(data);
      }
    });
  });
}

readFile('/path/to/file')
  .then(function(data) {
    console.log(data);
  })
  .catch(function(error) {
    console.error(error);
  });
```

Dalam ketiga contoh di atas, Promise digunakan untuk menangani operasi asinkron dan menentukan tindakan yang akan diambil ketika operasi selesai, baik berhasil atau gagal. Anda dapat menggunakan then() untuk menentukan tindakan yang akan diambil ketika Promise berhasil di-resolve, atau catch() untuk menentukan tindakan yang akan diambil ketika Promise di-reject.

## *Cara Penggunaan Async JavaScript Promise*

Berikut ini adalah cara penggunaan async JavaScript Promise:

1. Membuat Promise

Untuk membuat Promise, Anda dapat menggunakan constructor Promise yang memiliki satu parameter yaitu fungsi callback yang berisi dua parameter yaitu resolve dan reject. Fungsi resolve digunakan untuk menyelesaikan Promise dengan nilai tertentu, sedangkan fungsi reject digunakan untuk menolak Promise dengan alasan tertentu.

Berikut contoh penggunaannya:

```javascript
const myPromise = new Promise((resolve, reject) => {
  // melakukan operasi asinkron
  // jika operasi berhasil, panggil resolve dengan nilai yang diinginkan
  // jika operasi gagal, panggil reject dengan alasan yang diinginkan
});
```

2. Menggunakan then() dan catch() untuk menangani Promise

Setelah Promise dibuat, Anda dapat menangani hasilnya dengan then() dan catch(). Metode then() digunakan untuk menentukan tindakan yang akan diambil ketika Promise berhasil di-resolve, sedangkan catch() digunakan untuk menentukan tindakan yang akan diambil ketika Promise di-reject.

Berikut contoh penggunaannya:

```javascript
myPromise
  .then((result) => {
    // tindakan yang akan diambil jika Promise berhasil di-resolve
  })
  .catch((error) => {
    // tindakan yang akan diambil jika Promise di-reject
  });
```

3. Menggabungkan Promise dengan Promise.all()

Jika Anda memiliki beberapa Promise yang perlu dijalankan secara paralel, Anda dapat menggunakan Promise.all() untuk menunggu semua Promise selesai dan mengembalikan nilai hasil dari semua Promise.

Berikut contoh penggunaannya:

```javascript
const promises = [
  promise1(),
  promise2(),
  promise3()
];

Promise.all(promises)
  .then((results) => {
    // tindakan yang akan diambil ketika semua Promise berhasil di-resolve
  })
  .catch((error) => {
    // tindakan yang akan diambil jika ada Promise yang di-reject
  });
```

4. Menggunakan async/await

async/await adalah fitur baru dalam JavaScript yang memungkinkan penulisan kode asinkron dengan gaya yang mirip dengan kode sinkron. Dalam async/await, Anda dapat menunggu hasil operasi asinkron sebelum melanjutkan eksekusi kode.

Berikut contoh penggunaannya:

```javascript
async function myFunction() {
  try {
    const result1 = await promise1();
    const result2 = await promise2();
    const result3 = await promise3();
    // tindakan yang akan diambil jika semua Promise berhasil di-resolve
  } catch (error) {
    // tindakan yang akan diambil jika ada Promise yang di-reject
  }
}
```

## *Kesalahan penggunaan async javascript promise dan contohnya*

Berikut adalah beberapa kesalahan umum dalam penggunaan async JavaScript Promise:

1. Tidak menangani error dengan benar

Jika Promise di-reject, Anda harus menangani error dengan benar menggunakan catch(). Jika Anda tidak menangani error, maka aplikasi akan mengalami kegagalan dan sulit untuk debug.

Berikut contoh kesalahan penggunaannya:

```javascript
myPromise
  .then((result) => {
    // tindakan yang akan diambil jika Promise berhasil di-resolve
  });
  // tidak menangani error dengan catch()
```

2. Tidak mengembalikan Promise dari fungsi asinkron

Jika Anda membuat fungsi asinkron, pastikan Anda mengembalikan Promise dari fungsi tersebut agar dapat menangani hasilnya dengan then() atau catch(). Jika Anda tidak mengembalikan Promise, maka fungsi tersebut akan mengembalikan nilai undefined dan sulit untuk menangani hasilnya.

Berikut contoh kesalahan penggunaannya:

```javascript
async function myFunction() {
  // tidak mengembalikan Promise
}

myFunction().then((result) => {
  // tindakan yang akan diambil ketika fungsi berhasil dijalankan
});
```

3. Menggunakan then() secara berantai secara berlebihan

Jika Anda memiliki banyak operasi asinkron yang perlu dijalankan, Anda dapat menggunakan then() secara berantai. Namun, jika Anda menggunakan then() secara berlebihan, kode akan menjadi sulit dibaca dan sulit untuk di-maintain.

Berikut contoh kesalahan penggunaannya:

```javascript
myPromise
  .then((result1) => {
    // tindakan yang akan diambil jika Promise 1 berhasil di-resolve
    return anotherPromise();
  })
  .then((result2) => {
    // tindakan yang akan diambil jika Promise 2 berhasil di-resolve
    return yetAnotherPromise();
  })
  .then((result3) => {
    // tindakan yang akan diambil jika Promise 3 berhasil di-resolve
  });
```

Sebagai alternatif, Anda dapat menggunakan async/await untuk membuat kode lebih mudah dibaca dan di-maintain.

## *Hal yang mempengaruhi terjadinya kesalahan saat menggunakan async javascript promise*

Beberapa faktor yang mempengaruhi terjadinya kesalahan saat menggunakan async JavaScript Promise adalah:

1. Kurangnya pemahaman tentang konsep Promise

Kurangnya pemahaman tentang konsep Promise dan cara kerjanya dapat menyebabkan kesalahan dalam membuat, menangani, dan menggabungkan Promise. Penting untuk memahami konsep dasar seperti fungsi resolve dan reject, cara mengembalikan nilai dari Promise, serta cara menangani error dengan catch().

2. Kurangnya pengalaman dalam menangani kode asinkron

Kode asinkron dapat lebih sulit untuk dipahami dan di-maintain daripada kode sinkron. Kurangnya pengalaman dalam menangani kode asinkron dapat menyebabkan kesalahan dalam membuat atau menangani Promise.

3. Kurangnya pengalaman dalam debugging kode asinkron

Debugging kode asinkron dapat lebih sulit daripada kode sinkron karena ketidakpastian kapan operasi asinkron akan selesai. Jika ada kesalahan dalam kode asinkron, maka sulit untuk menentukan di mana kesalahan terjadi. Penting untuk menggunakan alat debugging seperti console.log() atau debugger statement untuk membantu menemukan kesalahan.

4. Penggunaan callback yang tidak sinkron dengan benar

Jika Anda menggunakan callback yang tidak sinkron dengan benar, maka dapat menyebabkan kesalahan saat membuat atau menangani Promise. Misalnya, jika Anda menggunakan callback dalam Promise constructor, pastikan callback tersebut bersifat sinkron dan tidak mengandung operasi asinkron.

5. Kesalahan sintaksis dalam kode JavaScript

Kesalahan sintaksis dalam kode JavaScript dapat menyebabkan kesalahan saat menggunakan Promise. Pastikan kode JavaScript Anda bebas dari kesalahan sintaksis dan dapat dijalankan dengan benar.


# ASYNC JAVASCRIPT AWAITS

## *Pengertian dari async awaits*

Async/await adalah fitur dalam pemrograman asinkron pada bahasa pemrograman modern seperti JavaScript yang memungkinkan pengembang untuk menulis kode asinkron dengan lebih mudah dan intuitif.

Dalam program asinkron, sebuah operasi atau tugas mungkin memerlukan waktu yang lama untuk dieksekusi dan menyelesaikan, seperti mengambil data dari database atau memanggil API. Selama menunggu operasi selesai, program dapat melakukan tugas lain yang tidak memerlukan waktu yang lama.

Async/await memungkinkan pengembang untuk menulis kode yang tidak memblokir atau menghentikan eksekusi program, dan akan berlanjut ketika operasi asinkron selesai. Async/await memungkinkan pengembang untuk menulis kode asinkron seperti kode synchronous, membuatnya lebih mudah untuk membaca, memahami, dan memelihara kode.

Ketika kode diawali dengan kata kunci "async", itu menunjukkan bahwa kode tersebut adalah fungsi asinkron, dan dalam fungsi asinkron, operator "await" digunakan untuk menunda eksekusi kode sampai operasi asinkron selesai. Setelah operasi selesai, nilai yang dihasilkan oleh operasi asinkron dapat diakses dan digunakan oleh kode berikutnya.

## *Kapan menggunakan async awaits?*

Async/await biasanya digunakan dalam kasus-kasus di mana program perlu melakukan operasi yang memerlukan waktu yang lama, seperti mengambil data dari server atau melakukan operasi I/O. Beberapa kasus penggunaan async/await antara lain:

1. Mengambil data dari server

Saat mengambil data dari server, Anda harus menunggu hingga server merespons permintaan Anda sebelum melanjutkan eksekusi program. Async/await memungkinkan Anda untuk menangani operasi ini secara asinkron tanpa menghentikan eksekusi program.

2. Operasi I/O

Ketika melakukan operasi I/O seperti membaca atau menulis file, waktu yang dibutuhkan untuk menyelesaikan operasi tersebut mungkin cukup lama. Async/await memungkinkan program untuk melanjutkan eksekusi saat operasi I/O sedang berlangsung, sehingga program tidak terblokir dan masih dapat melakukan tugas-tugas lain.

3. Tugas-tugas berulang

Jika Anda perlu menjalankan beberapa tugas berulang atau tugas yang saling bergantung, async/await memungkinkan Anda untuk mengeksekusinya secara asinkron, sehingga program dapat melanjutkan tugas lainnya selama tugas asinkron sedang berjalan.

4. Komunikasi dengan API

Saat berinteraksi dengan API, program harus menunggu hingga permintaan ke API selesai dan respon diterima. Async/await memungkinkan program untuk menangani operasi ini secara asinkron, sehingga program dapat melanjutkan eksekusi dan melakukan tugas-tugas lain selama menunggu respon dari API.

Dalam ringkasan, async/await digunakan ketika Anda ingin melakukan operasi yang membutuhkan waktu yang lama atau operasi yang memerlukan akses ke sumber daya eksternal, dan Anda ingin menghindari pemblokiran eksekusi program ketika menunggu operasi selesai.

## *Kapan menggunakan async awaits*

Async/await cocok digunakan ketika program harus melakukan operasi yang membutuhkan waktu yang lama atau operasi yang memerlukan akses ke sumber daya eksternal seperti server atau database. Ini mencegah program terjebak atau terblokir saat menunggu operasi selesai. Beberapa contoh penggunaan async/await adalah:

1. Mengambil data dari server

Ketika program perlu mengambil data dari server, penggunaan async/await memungkinkan program untuk menunggu hingga data diterima tanpa memblokir atau menghentikan eksekusi program.

````javascript

async function getDataFromServer() {
  const response = await fetch('https://example.com/data');
  const data = await response.json();
  console.log(data);
}
````

2. Operasi I/O

Ketika program melakukan operasi I/O seperti membaca atau menulis file, penggunaan async/await memungkinkan program untuk melanjutkan eksekusi saat operasi I/O sedang berlangsung, sehingga program tidak terblokir.

````javascript
async function readFile() {
  const fileHandle = await fs.promises.open('/path/to/file', 'r');
  const contents = await fileHandle.readFile();
  console.log(contents);
  await fileHandle.close();
}
````

3. Tugas-tugas berulang
Jika program perlu menjalankan beberapa tugas berulang atau tugas yang saling bergantung, penggunaan async/await memungkinkan program untuk mengeksekusinya secara asinkron, sehingga program dapat melanjutkan tugas lainnya selama tugas asinkron sedang berjalan.

````javascript
async function doTasks() {
  const task1 = await doTask1();
  const task2 = await doTask2(task1);
  const task3 = await doTask3(task2);
  console.log(task3);
}
````

4. Komunikasi dengan API

Ketika program berinteraksi dengan API, penggunaan async/await memungkinkan program untuk menangani operasi ini secara asinkron, sehingga program dapat melanjutkan eksekusi dan melakukan tugas-tugas lain selama menunggu respon dari API.

````javascript
async function fetchDataFromAPI() {
  const response = await fetch('https://api.example.com/data');
  const data = await response.json();
  console.log(data);
}
````

Dalam semua contoh di atas, penggunaan async/await memungkinkan program untuk menangani operasi asinkron secara mudah dan intuitif, dan mencegah program terjebak atau terblokir saat menunggu operasi selesai.

## *Cara menggunakan async awaits*

Async/await adalah fitur JavaScript yang memungkinkan Anda menangani operasi asinkron dengan cara yang lebih mudah dan intuitif. Berikut adalah langkah-langkah untuk menggunakan async/await:

Deklarasikan fungsi sebagai async dengan menambahkan kata kunci "async" sebelum kata kunci "function".

````javascript
async function myAsyncFunction() {
  // ...
}
````

Di dalam fungsi async, gunakan kata kunci "await" sebelum operasi asinkron yang ingin Anda tangani.

````javascript
async function myAsyncFunction() {
  const result = await doSomethingAsynchronous();
  // ...
}
````

Fungsi async mengembalikan nilai Promise, sehingga Anda dapat menggunakan metode .then() atau await lagi di luar fungsi async untuk menangani hasilnya.

````javascript
async function myAsyncFunction() {
  const result = await doSomethingAsynchronous();
  return result;
}
myAsyncFunction()
  .then(result => console.log(result))
  .catch(error => console.error(error));
````

Jika ada beberapa operasi asinkron yang perlu dijalankan secara bersamaan, Anda dapat menggunakan Promise.all() untuk menunggu semua operasi selesai.

````javascript
async function myAsyncFunction() {
  const [result1, result2, result3] = await Promise.all([
    doSomethingAsynchronous1(),
    doSomethingAsynchronous2(),
    doSomethingAsynchronous3(),
  ]);
  // ...
}
````

Jika ada beberapa operasi asinkron yang saling bergantung, Anda dapat menggunakan await untuk menunggu hasil operasi sebelumnya selesai.

````javascript
async function myAsyncFunction() {
  const result1 = await doSomethingAsynchronous1();
  const result2 = await doSomethingAsynchronous2(result1);
  const result3 = await doSomethingAsynchronous3(result2);
  // ...
}
````

Dalam kesimpulan, async/await adalah fitur yang sangat berguna dalam JavaScript untuk menangani operasi asinkron. Dengan mengikuti langkah-langkah di atas, Anda dapat menggunakan async/await dengan mudah dan menghindari callback hell atau kode yang sulit dibaca dan dipahami.

## *Kesalahan penggunaan async awaits dan contohnya*

Beberapa kesalahan umum dalam penggunaan async/await adalah:

1. Tidak menangani error dengan benar

Karena async/await adalah fitur yang sangat baru, beberapa pengembang mungkin tidak menyadari bahwa Anda masih perlu menangani error seperti yang dilakukan dengan Promise. Ini dapat mengakibatkan kesalahan yang sulit dilacak dan mempengaruhi kinerja aplikasi.

````javascript
// contoh kesalahan
async function myAsyncFunction() {
  const response = await fetch('https://example.com/data');
  const data = await response.json();
  console.log(data);
}
````

Jika request ke server gagal, kode di atas tidak akan menangani error. Seharusnya ditangani dengan try/catch:

````javascript
async function myAsyncFunction() {
  try {
    const response = await fetch('https://example.com/data');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}
````

2. Tidak mengeksekusi fungsi async dengan benar

Fungsi async harus dipanggil dengan menambahkan tanda kurung setelah nama fungsi. Jika tidak, itu hanya akan mengembalikan Promise dan tidak akan mengeksekusi kode di dalam fungsi.

````javascript
// contoh kesalahan
async function myAsyncFunction() {
  // ...
}

myAsyncFunction; // tidak dieksekusi

// harusnya
myAsyncFunction(); // dieksekusi
````

3. Tidak menunggu Promise selesai

Salah satu manfaat dari async/await adalah dapat menunggu Promise selesai dengan menggunakan kata kunci await. Namun, jika tidak menunggu Promise selesai, itu bisa menyebabkan kode yang tidak konsisten dan tidak diharapkan.

````javascript
// contoh kesalahan
async function myAsyncFunction() {
  const result = doSomethingAsynchronous();
  console.log(result);
}

// harusnya
async function myAsyncFunction() {
  const result = await doSomethingAsynchronous();
  console.log(result);
}
````

Dalam kesimpulan, async/await adalah fitur yang sangat berguna dalam JavaScript, tetapi bisa menjadi sulit dipahami jika tidak digunakan dengan benar. Untuk menghindari kesalahan, pastikan Anda menangani error, mengeksekusi fungsi async dengan benar, dan menunggu Promise selesai dengan kata kunci await.

## *Hal yang mempengaruhi terjadinya kesalahan saat menggunakan async awaits*

Beberapa hal yang mempengaruhi terjadinya kesalahan saat menggunakan async/await adalah sebagai berikut:

1. Kesalahan logika program

Kesalahan logika program dapat terjadi jika pengembang tidak memahami konsep dasar async/await atau tidak memperhatikan bagaimana data diproses di dalam fungsi asinkron.

Contoh kesalahan logika program adalah melakukan operasi synchronously di dalam fungsi async, atau melakukan operasi secara parallel tanpa memperhatikan dependensi antar operasi.

2. Tidak menangani error

Jika operasi asinkron yang dilakukan mengalami kesalahan atau terjadi kesalahan di dalam fungsi asinkron, dan error tidak ditangani dengan benar, hal ini dapat menyebabkan program gagal dan menyebabkan bug yang sulit dilacak.

3. Callback hell

Kode yang menggunakan callback hell atau penggunaan callback yang terlalu dalam akan menyebabkan kode sulit dibaca dan dipahami. Penggunaan async/await untuk mengatasi callback hell sangat disarankan untuk meningkatkan keterbacaan dan memudahkan dalam penanganan error.

4. Ketidaksinkronan data

Jika data yang diproses secara asinkron tidak disinkronkan dengan benar, ini dapat menyebabkan kesalahan dalam program. Hal ini dapat terjadi jika data tidak dikembalikan dengan benar atau ketika ada operasi asinkron yang tidak dijalankan dengan benar.

5. Kesalahan dalam pemanggilan fungsi

Kesalahan ini dapat terjadi ketika fungsi async tidak dipanggil dengan benar atau jika ada kesalahan dalam menunggu hasil dari fungsi async. Hal ini dapat terjadi jika pengembang tidak memahami konsep dasar async/await atau tidak memperhatikan bagaimana data diproses di dalam fungsi asinkron.

Untuk menghindari kesalahan saat menggunakan async/await, penting untuk memahami konsep dasar async/await dan memperhatikan bagaimana data diproses di dalam fungsi asinkron. Selain itu, pastikan untuk menangani error dengan benar, menghindari callback hell, dan sinkronkan data dengan benar.


# ASYNC JAVASCRIPT PROMISE

## *Callback vs Promise dan contohnya*

Callback dan Promise adalah dua pendekatan yang digunakan dalam JavaScript untuk menangani kode asinkron.

Berikut perbandingan antara Callback dan Promise:

Callback :

1. Menggunakan fungsi callback untuk menangani kode asinkron
2. Callback biasanya memiliki dua parameter, yaitu error dan data
3. Callback bersifat asinkron dan dijalankan saat operasi asinkron selesai
4. Callback dapat di-nesting atau di-chain secara berlebihan, yang dapat mengakibatkan callback hell
5. Callback tidak dapat menangani beberapa operasi asinkron secara bersamaan

Promise :

1. Menggunakan objek Promise untuk menangani kode asinkron
2. Promise memiliki tiga status, yaitu pending, fulfilled, dan rejected
3. Promise bersifat asinkron dan dijalankan saat operasi asinkron selesai
4. Promise dapat di-chaining menggunakan then() dan catch(), yang membuat kode lebih mudah dibaca dan di-maintain
5. Promise dapat menangani beberapa operasi asinkron secara bersamaan menggunakan Promise.all() atau Promise.race()

Keuntungan menggunakan Promise adalah kode lebih mudah dibaca dan di-maintain, lebih mudah untuk menangani error, dan dapat menangani beberapa operasi asinkron secara bersamaan.

Sedangkan kekurangannya adalah lebih kompleks daripada callback dan memerlukan waktu dan usaha untuk mempelajarinya.

Keuntungan menggunakan Callback adalah mudah dipelajari dan digunakan, dan cocok untuk skenario sederhana.

Namun, kelemahannya adalah kode sulit dibaca dan di-maintain jika terlalu banyak nested callback, sulit untuk menangani error, dan tidak dapat menangani beberapa operasi asinkron secara bersamaan.

Seiring dengan kemajuan teknologi, penggunaan Promise lebih direkomendasikan daripada Callback. Namun, terkadang Callback masih digunakan dalam beberapa kasus tertentu, seperti pada kode legacy atau integrasi dengan library lama yang masih menggunakan Callback.

Berikut adalah perbandingan antara Callback dan Promise beserta contoh penggunaannya:

Callback:

```scss
// Contoh penggunaan callback
function getUser(userId, callback) {
  setTimeout(() => {
    if (userId === 1) {
      callback(null, { id: 1, name: "John" });
    } else {
      callback("User not found", null);
    }
  }, 1000);
}

// Memanggil fungsi getUser dengan callback
getUser(1, (err, user) => {
  if (err) {
    console.log(err);
  } else {
    console.log(user);
  }
});
```

Pada contoh di atas, kita menggunakan callback untuk menangani kode asinkron pada fungsi getUser yang akan mengambil data user berdasarkan ID-nya dari database. Fungsi getUser akan mengeksekusi callback setelah operasi asinkron selesai, dengan mengembalikan error atau data user.

Promise:

```javascript
// Contoh penggunaan Promise
function getUser(userId) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      if (userId === 1) {
        resolve({ id: 1, name: "John" });
      } else {
        reject("User not found");
      }
    }, 1000);
  });
}

// Memanggil fungsi getUser dengan Promise
getUser(1)
  .then((user) => {
    console.log(user);
  })
  .catch((err) => {
    console.log(err);
  });
```

Pada contoh di atas, kita menggunakan Promise untuk menangani kode asinkron pada fungsi getUser yang akan mengambil data user berdasarkan ID-nya dari database. Fungsi getUser akan mengembalikan objek Promise yang memiliki tiga status, yaitu pending, fulfilled, dan rejected. Kita dapat menangani status Promise menggunakan metode then() dan catch(), yang akan dieksekusi saat Promise fulfilled atau rejected.

Dalam kedua contoh di atas, keduanya digunakan untuk menangani kode asinkron dalam mengambil data user dari database. Namun, dengan menggunakan Promise, kode menjadi lebih mudah dibaca dan di-maintain daripada menggunakan callback.
