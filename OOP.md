OOP = Visualisasi kode dengan sesuatu yang mirip dengan kehidupan nyata

Class = Blueprint / Template yang terdiri dari property (sifat) atau function (aksi)


# Pilars Of OOP

- inheritance (pewarisan)
- Encaptulation (Mengisolasi data, sehingga tidak bisa diakses dari luar secara langsung. Harus pakai setter atau getter).
- Abstraction (Mekanisme saat proses dalam sebuah objek disembunyikan)
- Polymorphism (Kemampuan suatu objek untuk memiliki beberapa bentuk)


### Inheritance

Superclass -> SubClass

### Macam macam?

1. Single (Class yang dibuat cuman mewarisi satu class): classA inherit classB
2. MultiLevel (class yang dibuat mewarisi suatu class yang mewarisi class lain): classA inherit classB, dimana classB adalah anak juga dari classC
3. Multiple (class yang dibuat mewarisi beberapa class, seperti mixin) **Java gak bisa kecuali memanfaatkan interface**
4. Heararchical (Superclass diwarisi beberapa subclass). Animal, punya beberapa child seperti Carnivora. Nah Carnivora sendiri, ada banyak semisal Cat, Dog, etc.
5. Hybrid -> Kombinasi

### Enscaptulation

Tujuan: 
1. lebih leluasa untuk merubah nilai tanpa harus mengakses property secara langsung
2. kode yang ada di app diringkas berdasarkan bagiannya

Note: **Encaputlation bukan menyembunyikan data, tapi menyebabkan data tersembunyi**


## Abstraction

- Fokus pada apa yang dilakukan oleh objek (what) bukan bagaimana (how)
- Menyembunyikan implementasi

### Abstraction Layer
Cara untuk memisahkan 2 kompleksitas sebuah system. Tujuannya untuk menyembunyikan detail implementasi sehingga kita hanya tahu yang dilakukan oleh objek, bukan bagaimana detail alur implementasinya.


## Polymorphism

1. Compile time (saat kompilasi dipanggil) -> method overloading. Ada 2:
	- parameter type : parameter jumlah nya sama tapi beda type
	- parameter count: parameter dengan jumlah yang berbeda
2. Runtime (saat runtime) -> method overriding. Kenapa? ketika proses kompilasi, kompiler gak tahu fungsi mana yang dipanggil. Subclass or Superclass? Namanya sama. JVM nanti yangg menentukan.
