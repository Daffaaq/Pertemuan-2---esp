# Apa itu "Class dan Object" pada Javascript ES6

## A. Class pada Javascript ES6

Class merupakan salah satu fitur baru pada ES6 yang memudahkan programmer dalam membuat object pada Javascript. Dalam konsepnya, class merupakan sebuah blueprint atau template yang digunakan untuk membuat object yang memiliki properti dan method yang sama.

### Macam-macam class pada JavaScript ES6

1. Class Expression
Class Expression adalah sebuah cara untuk membuat class tanpa harus memberikan nama pada class tersebut. Class Expression biasanya digunakan untuk membuat class yang hanya dibutuhkan pada suatu tempat saja dan tidak perlu didefinisikan ulanvg.

Contoh penggunaan:

```javascript
const myClass = class {
  constructor() {
    // Constructor code
  }
}
```

2. Class Declaration
Class Declaration adalah sebuah cara untuk membuat class dengan memberikan nama pada class tersebut. Class Declaration digunakan untuk membuat class yang bisa digunakan di mana saja dalam kode JavaScript.

Contoh penggunaan:

```javascript
class MyClass {
  constructor() {
    // Constructor code
  }
}
```

### Cara penggunaan class pada JavaScript ES6

1. Membuat objek baru dari sebuah class

Untuk membuat objek baru dari sebuah class, kita dapat menggunakan kata kunci "new" diikuti dengan nama class dan parameter yang dibutuhkan oleh constructor class tersebut.

Contoh penggunaan:

```javascript
const myObj = new MyClass();
```

<br>

2. Menggunakan metode dalam class

Untuk menggunakan metode yang ada dalam class, kita dapat menggunakan objek yang telah dibuat dan memanggil metode tersebut menggunakan dot notation.

Contoh penggunaan:

```javascript
myObj.myMethod();
```

<br>
3. Mewarisi class

Untuk membuat class baru yang mewarisi properti dan metode dari class lain, kita dapat menggunakan kata kunci "extends" diikuti dengan nama class yang ingin diwarisi.

Contoh penggunaan:

```javascript
class MyChildClass extends MyClass {
  constructor() {
    super();
    // Child constructor code
  }
}
```

<br>
<br>

## B. Object pada Javascript ES6

Object pada JavaScript ES6 adalah tipe data kompleks yang digunakan untuk merepresentasikan objek dalam dunia nyata. Object adalah kumpulan dari properti dan metode yang digunakan untuk mengelola data dan perilaku objek. Properti pada object adalah data yang dimiliki oleh objek, sedangkan metode pada object adalah fungsi yang digunakan untuk memanipulasi properti pada objek.

### Cara untuk membuat object pada JavaScript ES6

1. Object Literal
Object Literal adalah cara untuk membuat object dengan menuliskan properti dan metode dalam kurung kurawal {}.

Contoh penggunaan:

```javascript
const myObj = {
  prop1: "value1",
  prop2: "value2",
  myMethod() {
    // Method code
  }
};
```

2. Object Constructor
Object Constructor adalah cara untuk membuat object dengan menggunakan function constructor yang mengembalikan object yang baru.

Contoh penggunaan:

```javascript
function MyClass(prop1, prop2) {
  this.prop1 = prop1;
  this.prop2 = prop2;
  this.myMethod = function() {
    // Method code
  }
}

const myObj = new MyClass("value1", "value2");
```

3. Object.create
Object.create adalah cara untuk membuat object baru dengan mewarisi properti dan metode dari object yang sudah ada.

Contoh penggunaan:

```javascript
const myObj = {
  prop1: "value1",
  prop2: "value2",
  myMethod() {
    // Method code
  }
};

const myNewObj = Object.create(myObj);
```

<br>

### Hal-hal lain terkait object pada JavaScript ES6

<b>1. Property Shorthand</b>

Property Shorthand adalah cara singkat untuk membuat properti pada object jika properti memiliki nama yang sama dengan variabel yang digunakan untuk mengisinya.

Contoh penggunaan:

```javascript
const prop1 = "value1";
const prop2 = "value2";

const myObj = {
  prop1,
  prop2,
  myMethod() {
    // Method code
  }
};
```

<b>2. Computed Property Name</b>

Computed Property Name merupakan salah satu fitur baru pada Javascript ES6 yang memungkinkan kita untuk menggunakan sebuah ekspresi sebagai nama properti pada object. Dalam konsepnya, Computed Property Name memungkinkan kita untuk membuat properti dengan nama yang dinamis atau tergantung pada variabel yang digunakan.

Contoh penggunaan:

```javascript
const prop1 = "value1";

const myObj = {
  [prop1]: "value2",
  myMethod() {
    // Method code
  }
};
```

Dalam penggunaannya, Computed Property Name memungkinkan kita untuk membuat object dengan properti yang dinamis atau tergantung pada situasi. Misalnya, ketika kita ingin membuat object yang propertinya dinamis tergantung pada input pengguna atau data dari server.

Contoh:

```javascript
const inputName = "username";
const obj = {
  [inputName]: "John Doe"
};

console.log(obj.username); // John Doe
```

Pada contoh di atas, kita membuat properti dengan nama username yang diambil dari variabel inputName. Nama properti yang dihasilkan pada object obj bergantung pada input yang diberikan oleh pengguna.

<br>

<b>3. Method Shorthand</b>

Method Shorthand pada Javascript ES6 adalah fitur baru yang memudahkan kita untuk mendefinisikan method pada object dengan lebih singkat dan efisien. Dalam konsepnya, Method Shorthand memungkinkan kita untuk mendefinisikan method pada object tanpa harus menuliskan kata kunci `function`.

Contoh penggunaan:

```javascript
const myObj = {
  myMethod() {
    // Method code
  }
};
```

Dalam penggunaannya, Method Shorthand sangat berguna saat kita ingin membuat object dengan beberapa method yang memiliki kode yang relatif singkat. Misalnya, pada kasus implementasi method untuk melakukan aksi-aksi dasar pada object seperti `get()`, `set()`, `add()`, atau `remove()`.

contoh :

```javascript
const obj = {
  data: [],
  get(index) {
    return this.data[index];
  },
  set(index, value) {
    this.data[index] = value;
  },
  add(value) {
    this.data.push(value);
  },
  remove(index) {
    this.data.splice(index, 1);
  }
};

```

Pada contoh di atas, kita membuat object obj dengan beberapa method yang diimplementasikan menggunakan Method Shorthand. Method `get()`, `set()`, `add()`, dan `remove()` memungkinkan kita untuk melakukan operasi dasar pada array data yang dimiliki oleh object.

<br>

<b>4. Object Destructuring</b>

Object Destructuring adalah salah satu fitur baru pada Javascript ES6 yang memungkinkan kita untuk mengekstrak nilai dari sebuah object ke dalam beberapa variabel yang terpisah secara otomatis. Dengan Object Destructuring, kita dapat menuliskan kode yang lebih ringkas dan efisien dalam memanipulasi nilai-nilai pada object.

Contoh penggunaan:

```javascript
const user = {
  name: "John Doe",
  age: 25,
  email: "johndoe@example.com"
};

const { name, age, email } = user;

console.log(name); // John Doe
console.log(age); // 25
console.log(email); // johndoe@example.com
```

Object Destructuring juga memungkinkan kita untuk memberikan nama variabel yang berbeda dengan nama properti pada object. Hal ini berguna jika kita ingin menggunakan nama variabel yang lebih singkat atau lebih deskriptif daripada nama properti pada object. Untuk memberikan alias pada variabel, kita dapat menuliskan nama variabel yang diinginkan setelah nama properti pada object, dipisahkan dengan tanda titik dua :. Contoh:

```javascript
const user = {
  name: "John Doe",
  age: 25,
  email: "johndoe@example.com"
};

const { name: fullName, age, email: userEmail } = user;

console.log(fullName); // John Doe
console.log(age); // 25
console.log(userEmail); // johndoe@example.com
```

<br>

<b>5. Object Spread Operator</b>
Object Spread Operator merupakan salah satu fitur baru pada Javascript ES6 yang memungkinkan kita untuk menyalin nilai dari sebuah object ke dalam object yang baru. Dengan menggunakan Object Spread Operator, kita dapat melakukan manipulasi object dengan cara yang lebih ringkas dan mudah dibaca.

Contoh penggunaan:

```javascript
const myObj = {
  prop1: "value1",
  prop2: "value2",
  myMethod() {
    // Method code
  }
};

const myNewObj = {
  ...myObj
};
```
