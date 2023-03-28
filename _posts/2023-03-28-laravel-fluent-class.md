---
layout: post
title: "Class Fluent, Class Ajaib di Laravel"
subtitle: Aa Ezha
cover-img: /assets/img/laravel.png
share-img: /assets/img/laravel.png
thumbnail-img: /assets/img/laravel.png
tags: [php, laravel]
---

Tau nggak sih kenapa barisan kode sederhana seperti ini bisa mengeluarkan output dengan berbagai cara?

```php
$user = \App\Models\User::inRandomOrder()->first();
```

Dengan keluaran sebagai `array`, bisa...

```php
$user['name']; // output: John
```

Dengan keluaran sebagai `object`, bisa juga...

```php
$user->; // output: John
```

Jawabannya adalah karena ada suatu class yang namanya Fluent. Class ini secara ajaib melakukan mutasi kepada data agar bisa diakses dalam berbagai metode. Salah duanya adalah seperti yang sudah penulis jabarkan di atas.

Sebelum penulis berikan berbagai contoh penggunaannya, mari kita kenalan dengan class Fluent ini.

```php
use Illuminate\Support\Fluent;

$attributes = ['name' => 'Reza'];
$data = new Fluent($attributes);
```

Selanjutnya adalah ada berbagai metode yang bisa dilakukan oleh class Fluent ini. Penulis langsung jabarkan melalui contoh satu per satu ya.

---

```php
$data->get('name', 'Nurfachmi');
```

Kode di atas akan mengembalikan nilai dari `name` atau `Nurfachmi` jika `name` belum di-set nilainya.

---

```php
$data->getAttributes();
```

Kode di atas akan mengembalikan seluruh atribut yang sudah di-set, termasuk yang baru dibuat, misalnya:

```php
$data->last_name = "Nurfachmi";

print_r($data->getAttributes());
/***
Output:
Array ( [name] => Reza [last_name] => Nurfachmi )
***/
```

---

```php
$data->toArray();
```

Kode di atas akan mengembalikan data sebagai array.

---

```php
$data->toJson();
```

Kode di atas akan mengembalikan data sebagai json.

---

Fluent adalah sebuah utiliti class yang disediakan oleh Laravel sendiri agar kita dapat secara *luwes* mengolah data.