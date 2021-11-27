---
layout: post
title: Auto Created dan Updated field
subtitle: created_at & updated_at otomatis
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [sql, tips]
---

Untuk pengguna Laravel, pasti gak asing dengan kolom `created_at` dan `updated_at`, kan? Kalau masih asing, gak apa-apa, toh saya jelasin dulu sebentar di bawah ini. _Yuk lanjut..._

Pada setiap tabel, hendaknya ada kolom `created_at` dan `updated_at` sebagai informasi data tersebut kapan dibuat pertama kali dan kapan terakhir diubah. Lebih jauh lagi, boleh ditambahkan kolom `created_by` dan `updated_by` untuk menyimpan informasi usernya. Nah, sampai sini paham, ya?

Di Laravel, kita tak perlu pusing dengan query untuk kedua field tersebut karena sudah di-_handle_ oleh eloquent. Namun, bagaimana bisa diaplikasikan untuk projek yang tidak menggunakan Laravel? Lebih umum lagi untuk semua aplikasi.

Jawabannya adalah kita otomatiskan saja!

Kolom `created_at` otomatis terisi ketika kita input data.

Kolom `updated_at` otomatis terisi setiap kita update data.

Bagaimana query-nya? Menurutku begini...

```sql
CREATE TABLE users (
    id bigint auto_increment primary key,
    email varchar(100) not null unique,
    password varchar(100) not null,
    name varchar(100) not null,
    created_at datetime default current_timestamp,
    updated_at datetime default current_timestamp on update current_timestamp
)
```

Dengan demikian kolom `created_at` dan `updated_at` tidak perlu kita sentuh sama sekali di query-query yang akan datang. Kedua kolom tersebut akan otomatis terisi sesuai dengan eventnya.