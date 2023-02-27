# String Template

## Pengertian

Templat string adalah fitur dalam bahasa pemrograman yang memungkinkan Anda menentukan string dengan placeholder yang dapat diganti dengan nilai saat runtime. Template string menyediakan cara mudah untuk membuat string yang menggabungkan teks tetap dengan data dinamis, seperti input pengguna atau hasil perhitungan. Di sebagian besar bahasa pemrograman, templat string ditentukan menggunakan sintaks khusus yang menunjukkan lokasi placeholder. Misalnya, dengan Python, Anda dapat menentukan templat string menggunakan sintaks f-string, yang terlihat seperti ini:

<!-- <br> -->

```
name = "Alice"
age = 30
message = f"My name is {name} and I am {age} years old."
```

<!-- <img src="1.png"> -->

## Contoh kode program template string

Berikut adalah contoh penggunaan templat string dengan Python:

<!-- <br> -->

```
name = "John"
age = 35
occupation = "software engineer"

# using f-string (formatted string literals)
message = f"My name is {name} and I am a{occupation}. I am {age} years old."
print(message)

#using str.format()
message = "hello, my name is{} and I am a {}. I am {} years old.".format(name, occupation, age)
print(message)

#using %-formatting (old-style string formatting)
message = "hello, my name is%s and I am a %s. I am %d years old."% (name, occupation, age)
print(message)
```

<!-- <img src="2.png"> -->

Dalam contoh ini, kami mendefinisikan tiga variabel name, age, dan occupationyang menyimpan beberapa data dinamis. Kami kemudian menggunakan tiga cara berbeda untuk membuat string pesan yang menyertakan data ini:

Menggunakan f-string (literal string yang diformat) dengan kurung kurawal untuk menginterpolasi variabel langsung ke dalam string.
Menggunakan str.format()metode untuk memasukkan variabel ke dalam string menggunakan placeholder bernomor.
Menggunakan %-formatting, cara lama untuk memformat string yang menggunakan %placeholder.
Ketiga pendekatan tersebut menghasilkan string pesan yang sama. Saat kami menjalankan kode, kami mendapatkan output berikut :

```
hello, my name is John and I am a software engineer. I am 35 years old.
hello, my name is John and I am a software engineer. I am 35 years old.
hello, my name is John and I am a software engineer. I am 35 years old.
```

<!-- <img src="3.png"> -->

## Contoh penggunaan string template yang benar

1. Substitusi variabel sederhana:
   <!-- <img src="4.png"> -->

   ```
   form string import Template

   name = "John"
   age = 30
   occupation = "programmer"

   template_str = Template("Hello, my name is $name and I am a $occupation. I am $age years old.")
   message = template_str.substitute(name=name, age=age, occupation=occupation)

   print(message) # output: hello, my name is John and I am a Programmer. I am 30 years old
   ```

   Dalam contoh ini, kami membuat string template yang memiliki tiga placeholder ($name, $age, dan $occupation), lalu menggunakan metode substitute()untuk mengganti placeholder ini dengan nilai yang sesuai. Kami meneruskan nilai sebagai argumen kata kunci ke substitute()metode.

2. Melarikan diri dari karakter placeholder :
   <!-- <img src="5.png"> -->

   ```
   form string import Template

   product = "apples"
   price = "$2.00"
   template_str = Template("The price of ${product}s is {price}.")
   message = template_str.substitute(product=product, price=price)

   print(message) # output: The price of apples is $2.00
   ```

   Dalam contoh ini, kami menggunakan kurung kurawal untuk mengapit productvariabel di placeholder untuk menghindari kebingungan dengan variabel $2in price. Kami keluar dari kurung kurawal dengan menggandakannya (${product}s) untuk menunjukkan bahwa mereka adalah bagian dari string templat, bukan placeholder.

3. Pernyataan bersyarat :
   <!-- <img src="6.png"> -->

   ```
   form string import Template

   score = 80
   template_str = Template("You ${verb} the exam${suffix}.")
   message = template_str.substitute(verb= "passed" if score >=60 else "failed", suffix="with a score of " + str(score) if score < 60 else "")

   print(message) # output: You passed the exam.
   ```
   Dalam contoh ini, kami menggunakan ekspresi bersyarat ( x if condition else y) untuk menentukan apakah siswa "lulus" atau "gagal" ujian berdasarkan nilai mereka. Kami juga menggunakan ekspresi bersyarat untuk menambahkan scoreakhiran ke pesan hanya jika siswa gagal dalam ujian. Kami menggabungkan string kosong ke akhiran jika siswa lulus, secara efektif melewatkannya.
   
