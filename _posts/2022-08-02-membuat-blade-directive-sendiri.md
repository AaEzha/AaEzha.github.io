---
layout: post
title: "Membuat Blade Directive Sendiri"
subtitle: Aa Ezha
cover-img: /assets/img/laravel.png
share-img: /assets/img/laravel.png
thumbnail-img: /assets/img/laravel.png
tags: [php, laravel, blade]
---

Sebagai salah satu programmer yang menggunakan Laravel, tentunya setiap hari saya berjibaku dengan file berekstensikan `*.blade.php`. Tak jarang pula saya membuat beberapa fungsi untuk mempermudah hal-hal yang sulit atau berulang. Salah satu yang sering saya lakukan adalah untuk menampilkan data uang.

Misalnya, dari database hanya menampilkan `150000`, tetapi saya ingin hasil akhirnya adalah `IDR 150.000`.

Normalnya akan melakukan hal seperti ini:

```php
<p>IDR {{ number_format($data->price, 0, ',', '.') }}</p>
```

Namun, saya melakukannya dengan cara lain, yakni seperti ini:

```php
<p>@idr($data->price)</p>
```

Bagaimana cara melakukannya?

*Insyaallah* mudah. Yuk sambil dipraktekkan.

Caranya adalah dengan mendaftarkan directive blade kita ke **app/Providers/AppServiceProvider.php** di dalam method `boot()`.

```php
public function boot()
{
    Blade::directive('idr', function ($string) {
        return "<?php echo 'IDR ' . number_format($data->price, 0, ',', '.'); ?>";
    });
}
```

Perhatikan bahwa kita tidak hanya me-return string biasa, melainkan lengkap dengan tag pembuka dan penutup serta *echo*-nya seakan menuliskan kode PHP di dalam PHP. Mengapa demikian?

Karena directive ini akan dijalankan di tengah-tengah blok kode HTML, meskipun ekstensi filenya `.php`.

Kalau teman-teman ingin mendaftarkan blade directive lainnya, silahkan tambahkan saja di bawah barisan kode tadi ya.

**Happy coding!**