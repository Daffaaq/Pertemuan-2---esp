# Apa itu Const?

Variabel const merupakan ketika kita sudah mendeklarasikannya dan memasukkan sebuah nilai, kita tidak lagi bisa mengubahnya. Kita perlu membuat variabel dengan nama yang berbeda baru bisa memasukkan nilai yang diiginkan.

- var : bersifat global,dapat di ubah dimana pun. memiliki sifat hoisting dan dapat di deklarasikan ulang dimana pun.
- let : bersifat scoop area, dapat di ubah. tidak dapat di deklarasikan ulang. (Dapat diupdate)
- const : bersifat scoop area, immutable (tidak dapat dirubah), tidak dapat di deklarasikan ulang. biasa digunakan untuk object. (bersifat statis atau tetap dan tidak bisa diupdate)

## Contoh

- var buah = "labu"
- const harga = 42000
- var mobil = "sedan"
- const harga = 93000000
- console.log("harga labu adalah", harga)
- //SyntaxError: Identifier 'harga' has already been declared

Variabel const tidak diizinkan mendeklarasikan variabel dengan nama yang sama ketika menggunakan const hal ini akan sangat membantu ketika membuat aplikasi berskala besar dengan nama variabel yang bermacam macam.

Variabel const memiliki nilai yang statis dan bersifat read-only. Walaupun sebenarnya nilai pada variabel tersebut statis, ada beberapa cara yang dapat dilakukan untuk mengubah nilai dari variabel constant itu sendiri. const merupakan variabel block-scoped yaitu ia hanya dapat dipanggil oleh program dalam 1 blok yang sama, atau program di dalam tanda { }.

## Contoh

- const buah = {}
- buah.nama = "labu"
- console.log(buah)
- //OUTPUT { nama: 'labu' }

Variabel const sebenarnya yang dirubah bukanlah nilai variabelnya tetapi property dari variabel yang kita buat.

# Kapan digunakan Const?

Variabel ini biasanya digunakan ketika membuat konstanta dalam operasi matematika. const lebih sering digunakan untuk mendeklarsaikan object atau array

## Constoh const digunakan dalam operasi matematika

- const PI = 3.14
- var keliling, radius = 4
- keliling = 2 _ PI _ radius

Hal ini karena nilai dari pi sudah mutlak dan tidak mungkin berubah. Biasanya penamaan const menggunakan huruf kapital digunakan untuk menghindari kerancuan.

## Constoh const digunakan sebagai object

- const greeting = {
  message : "say Hi",
  times : 4
  }
- greeting.message = "hello world";
- console.log(greeting.message)//=>"hello world"
