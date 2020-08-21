arsitektur: bentuk
design: hubungan antar komponen

kalau dalam software: arsitektur: high level, design: low level.

Definisi lain dari design: interkoneksi antar modul dan beberapa intitas perangkat lunak


# Prinsip: 3 sifat design yang perlu dihindari

- Rigidity: Kaku, susah diubah. 
- Fragility: Rapuh, mesti ada salah dibeebrapa bagian setiap kali melakukan perubahan.
- Immobility: tidak bisa digunakan kembali dari proyek lain, atau bagian dari proyek lain yang mirip.

# Tujuan SOLID
- extensible
- maintainable
- understanable
- bisa dipakai lagi untuk system yang lainnya


## SRP (Single Responsibility Principle)

digunakan untuk mengatur tanggung jawab dari sebuah entitas yang berada dalam sebuah proyek.

Setiap klass hanya punya tanggung jawab berdasarkan fungsinya.

### Contoh penerapan

FoodService (punya fungsi berikut):
- addToCart
- isExpired

ada dua responsibility di sini. Perlu dipisah.

FoodService:
- addToCard

FoodExpiry:
- isExpired

## OCP (Open Close Principle)

**terbuka untuk ditambahkan, tertutup untuk dimodifikasi**

1. kalau butuh fitur baru, tinggal nambahin
2. kalau butuh fitur baru, gak perlu memodifikasi system yang sudah ada

Manfaatkan interface dan abstraksasi. Tujuannya agar mudah diperbaiki setelah pengembangan tanpa harus mengganggu kelas yang mewarisi. Kalau ingin buat fungsi baru, tinggal buat kelas baru dan warisi interface atau abstraksi tsb.

### Contoh penerapan

Product:

ShippingOrderService:
- checkout [product, shippingType]

shippingType ini enum: JNE, TIKI

oke, system berjalan dengan baik. Tapi suatu hari kita diminta untuk menambahkan POSINDO ? Kalau kita tambahkan langsung, maka akan merubah kode. Dan melangggar prinsip OCP ini.

Solusi:

1. Enum ini buat klass sendiri, jadi nanti ada klass JNE, TIKI, POSINDO
2. semuanya implement interface Shipping yang punya calculate.
3. nah, parameter shippingType, instead menggunakan enum, kita tinggal isi dengan shipping object, dan panggil calculate fungsinya.

## LSP (Liskov Subtitution Principle)

Barbara Liskov : "If for each object o1 of type S there is an object o2 of type T such that for all programs P defined in terms of T, the behavior of P is unchanged when o1 is subtituted of o2 then S is a subtype of T"

Sederhananya **aturan untuk Hireraki Inheritance**

1. Contravariant & Covariant
Fungsi di subclass memiliki jumlah parameter dan type paramater yang sama & pengembalian nilai dari fungsi yang berada pada subclass dan parent
2. Precondition & PostCondition
3. Invariant
invarian adalah penjelasan dari kondisi suatu proses yang benar, sebelum proses tersebut dimulai dan benar setelahnya.
Intinya: asumsi dari suatu fungsi untuk proses sebelum fungsi ini dijalankan.
4. Constraint
Pembatasan yang ditentukan superclass terhadap perubahan keadaan sebuah objek. Contoh: Super memiliki objek dengan nilai tetap (constant), maka subclass gak boleh ubah.

## ISP (Interface Segregation Principle)

Tujuan: mengurangi jumlah ketergantungan class ke interface class yang tidak dibutuhkan.
- Semacam pembuatan mixin

## DIP (Dependency Inversion Principle)
- high level module tidak boleh bergantung pada low level module. Keduanya harus berkandung pada abstraksi
- abstraksi tidak diperbolehkan untuk bergantuk pada detail. Detail harus bergantung pada abstraksi

semisal layering dalam aplikasi.
