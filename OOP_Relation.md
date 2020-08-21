# Macam Macam

- Association "has-a": User *has-a* Profile
- Dependency "depen on"
- Generalization "is-a" Cat *is-a* Animal -> Cat ke Animal: Generalization. Kalau Animal ke Cat adalah Specialization.


## Association

### Kardinalitas

Hub antara satu objek dengan objek lainnya

#### 1 to 1

User 1-1 Contact Info

*garis **tidak** putus putus dan **tanpa** panah*


#### 1 to many

User and Order


#### many to many

User and Product


### Bentuk Hubungan Antar Objek

**Aggregation**: *garis tidak putus, ujun simbol diamond putih di objek yang memiliki*

Shop (shop punya seller) [diamondnya disini] - Seller

ketika shop hancur, maka gak seller tetep ada. Tapi kalau seller hancur, lapaknya juga angus.

**Composition**: *garis tidak putus, ujung simbol diamond hidam di objek yang memiliki*

User (user punya Address) [diamondnya disini] - Address
ketika user ancur, maka address juga ancur.

## Dependency

garis putus putus, punya anak panah, letaknya di dependensinya.

ShopService -> Product = ShopService butuh kepada Product

product ini, bukan attribute dari ShopService. Akan tetapi, salah satu method dari ShopService ini punya parameter berupa Product object.


# Realization / Implementation

Buat kontrak dengan semacam interface, kemudian di implementasikan ke bawahnya.

Kalau di java buat interface, dibuat kontraknya. Kemudian class yang mengimplementasi interface tersebut harus **taat** sama aturan kontraknya. 
Di bahasa lain yang tidak pakai interface bisa pakai class, yang nanti mengoverride fungsi fungsinya.
