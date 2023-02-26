# Array and Object Destruction

Array and Object Destruction adalah fitur dalam JavaScript yang memungkinkan Anda mengekstrak nilai dari array atau objek dan menetapkannya ke variabel dengan cara yang lebih ringkas dan mudah dibaca.

## Array Destruction:

Dengan destrukturisasi array, Anda dapat mengekstraksi nilai dari array dan menetapkannya ke variabel dalam satu langkah. Berikut contohnya:

```javascript
const myArray = [1, 2, 3];
const [a, b, c] = myArray;

console.log(a); // output: 1
console.log(b); // output: 2
console.log(c); // output: 3
```

Dalam contoh ini, kita mendefinisikan array myArray dengan tiga elemen. Kami kemudian menggunakan destrukturisasi array untuk mengekstrak nilai dari myArraydan menetapkannya ke variabel a, b, dan c.

## Object Destruction:

Destrukturisasi objek mirip dengan destrukturisasi array, tetapi alih-alih mengekstraksi nilai dari array, Anda mengekstrak nilai dari objek. Ini contohnya:

```javascript
const myObject = { x: 1, y: 2, z: 3 };
const { x, y, z } = myObject;

console.log(x); // output: 1
console.log(y); // output: 2
console.log(z); // output: 3
```

Dalam contoh ini, kita mendefinisikan objek myObject dengan tiga properti x, y, dan z. Kami kemudian menggunakan destrukturisasi objek untuk mengekstrak nilai properti tersebut dan menugaskannya ke variabel x, y, dan z.

Anda juga dapat menggunakan destrukturisasi objek untuk menetapkan nama alias ke variabel. Berikut contohnya:

```javascript
const myObject = { x: 1, y: 2, z: 3 };
const { x: a, y: b, z: c } = myObject;

console.log(a); // output: 1
console.log(b); // output: 2
console.log(c); // output: 3
```

Dalam contoh ini, kita mendefinisikan objek myObject dengan tiga properti x, y, dan z. Kami kemudian menggunakan destrukturisasi objek untuk mengekstraksi nilai properti tersebut dan menugaskannya ke variabel a, b, dan c, masing-masing.

## Nested Destructuring

Destrukturisasi juga dapat digunakan dengan array atau objek bersarang. Nested Destructuring memungkinkan Anda mengekstrak nilai dari array dan objek bersarang dan menetapkannya ke variabel dengan cara yang ringkas dan mudah dibaca.Berikut beberapa contoh nested array dan objek destructuring:<br>

### Nested Array Destruction:

```javascript
const myArray = [1, [2, 3], 4];
const [a, [b, c], d] = myArray;

console.log(a); // output: 1
console.log(b); // output: 2
console.log(c); // output: 3
console.log(d); // output: 4
```

Dalam contoh ini, kita mendefinisikan array myArray dengan tiga elemen, di mana elemen kedua adalah array bersarang. Kami kemudian menggunakan destrukturisasi array bersarang untuk mengekstrak nilai dari myArraydan menugaskannya ke variabel a, b, c, dan d.

### Nested Object Destruction:

```CSS
        const myObject = {
        name: "Alice",
        age: 25,
        address: {
        street: "123 Main St",
        city: "Anytown",
        state: "CA"
        }
        };
        const { name, age, address: { street, city, state } } = myObject;

        console.log(name); // output: "Alice"
        console.log(age); // output: 25
        console.log(street); // output: "123 Main St"
        console.log(city); // output: "Anytown"
        console.log(state); // output: "CA"
```

Dalam contoh ini, kita mendefinisikan objek myObject dengan tiga properti, di mana address properti tersebut adalah objek bersarang. Kami kemudian menggunakan nested object destruction untuk mengekstrak nilai dari myObject dan menugaskannya ke variabel name, age, street, city, dan state.

Anda juga dapat menetapkan nama alias ke variabel yang didestrukturisasi:

```javascript
const myArray = [1, [2, 3], 4];
const [a, [b, c], d] = myArray;
const [x, [y, z], w] = myArray;

console.log(a, b, c, d); // output: 1 2 3 4
console.log(x, y, z, w); // output: 1 2 3 4
```

Dalam contoh ini, kita mendefinisikan array myArray dengan tiga elemen, di mana elemen kedua adalah array bersarang. Kami kemudian menggunakan destrukturisasi array bersarang untuk mengekstrak nilai dari myArray dan menugaskannya ke variabel a, b, c, dan d. Kami kemudian menggunakan destrukturisasi array bersarang lagi untuk menetapkan nilai yang sama ke variabel x, y, z, dan w.

Anda juga dapat menggunakan nilai default untuk perusakan bersarang:

```javascript
const myArray = [1, [2], 4];
const [a, [b, c = 0], d] = myArray;

console.log(a); // output: 1
console.log(b); // output: 2
console.log(c); // output: 0
console.log(d); // output: 4
```

Dalam contoh ini, kita mendefinisikan array myArraydengan tiga elemen, di mana elemen kedua adalah array bersarang dengan hanya satu elemen. Kami kemudian menggunakan destrukturisasi array bersarang untuk mengekstrak nilai dari myArraydan menugaskannya ke variabel a, b, dan c. Kami menetapkan nilai default 0ke c.

## Penggunaan Array and Object Destruction dalam Javascript ES6

Destrukturisasi array dan objek adalah fitur canggih dari ES6 yang dapat membantu menyederhanakan kode dan membuatnya lebih ringkas dan mudah dibaca. Berikut adalah beberapa kasus penggunaan umum destrukturisasi array dan objek di JavaScript ES6:
<br><br>
<b>1. Menetapkan elemen array ke variabel:</b><br>

```javascript
const myArray = [1, 2, 3];
const [a, b, c] = myArray;
console.log(a); // output: 1
console.log(b); // output: 2
console.log(c); // output: 3
```

Dalam contoh ini, kami menggunakan destrukturisasi array untuk menetapkan nilai dari myArrayke variabel a, b, dan c.
<br><br>
<b>2. Bertukar variabel:</b><br>

```CSS
        let a = 1;
        let b = 2;
        [a, b] = [b, a];
        console.log(a); // output: 2
        console.log(b); // output: 1
```

Dalam contoh ini, kami menggunakan destrukturisasi array untuk menukar nilai adan b.
<br><br>
<b>3. Parameter fungsi:</b><br>

```SCSS
        function myFunction([a, b, c]) {
        console.log(a); // output: 1
        console.log(b); // output: 2
        console.log(c); // output: 3
        }
        myFunction([1, 2, 3]);
```

Dalam contoh ini, kami menggunakan destrukturisasi struktur array untuk merusak parameter fungsi myFunction.
<br><br>
<b>4. Menetapkan properti objek ke variabel:</b><br>

```javascript
const myObject = {
  name: "Alice",
  age: 25,
};
const { name, age } = myObject;
console.log(name); // output: "Alice"
console.log(age); // output: 25
```

Dalam contoh ini, kami menggunakan destrukturisasi objek untuk menetapkan properti myObject ke variabel name dan age.
<br><br>
<b>5. Mengganti nama properti objek:</b><br>

```javascript
const myObject = {
  firstName: "Alice",
  lastName: "Smith",
};
const { firstName: name, lastName: surname } = myObject;
console.log(name); // output: "Alice"
console.log(surname); // output: "Smith"
```

Dalam contoh ini, kami menggunakan destrukturisasi objek untuk mengganti nama properti myObject dan menugaskannya ke variabel name dan surname.
<br><br>
<b>6. Memberikan nilai default:</b><br>

```javascript
const myObject = {
  name: "Alice",
  age: 25,
};
const { name, age, gender = "unknown" } = myObject;
console.log(name); // output: "Alice"
console.log(age); // output: 25
console.log(gender); // output: "unknown"
```

Dalam contoh ini, kami menggunakan destrukturisasi objek untuk menetapkan properti dari myObjectvariabel name, age, dan gender. Kami memberikan nilai default "unknown"untuk genderproperti jika tidak ditentukan dalam myObject.

Secara keseluruhan, destrukturisasi array dan objek dapat sangat berguna dalam banyak situasi di JavaScript ES6, dan dapat membuat kode Anda lebih ringkas, mudah dibaca, dan efisien.
