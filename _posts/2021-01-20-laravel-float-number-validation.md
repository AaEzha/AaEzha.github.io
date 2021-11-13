---
layout: post
title:  "Laravel Float Number Validation"
date:   2021-01-20 15:44:58 +0700
categories: blog
---

Assalamualaikum warahmatullahi wabarakatuh

Ini adalah salah satu pertanyaan dari grup diskusi WhatsApp yang aku kelola, grup khusus membahas Laravel tapi gak menutup untuk membahas hal lain selagi masih berhubungan dengan teknologi atau pemrograman berbasis web.

Jadi, pertanyaannya adalah bagaimana membuat validasi input dalam form yang mengharuskan orang itu mengisi dalam bentuk float seperti 0.5, 18.8, dan sejenisnya?

Karena tidak disediakan secara khusus untuk floating point, maka ada beberapa solusi yang terpikirkan.

## Regular Expression

Namun, saya sendiri belum familiar dengan yang namanya Regex, jadi belum aku bahas dulu. Nanti aku update kalau ketemu jawabannya.

## Buat Validation Rule-mu Sendiri!

Nah, mungkin ini bisa membantu untuk kasus ini atau kasus lain yang ingin memvalidasi input dengan seenaknya sendiri. Hehehe.

### Langkah pertama

Buat Rule baru
`php artisan make:rule FloatValidator`

### Langkah kedua

Kemudian buka file yang baru dibuat tadi. Seharusnya ada di lokasi `app\Rules\FloatValidator.php`.

Lalu, silahkan ditulis menjadi seperti ini:

```php
public function passes($attribute, $value)
{
    return is_float($value + 0);
}

public function message()
{
    return 'Harus bentuk float.';
}
```

### Langkah ketiga

Pada controller, tinggal tambahkan validasimu.

```php
use App\Rules\FloatValidator;

...

public function store(Request $request)
{
    $request->validate([
        'angka' => new FloatValidator()
    ]);

    return $request->angka;
}
```

Nah, kira-kira begitu sih kalau mau membuat validasi untuk floating number atau mau membuat validasi sendiri.
