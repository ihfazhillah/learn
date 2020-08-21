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
