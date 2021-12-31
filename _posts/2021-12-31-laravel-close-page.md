---
layout: post
title: "Laravel Close Page"
subtitle: Aa Ezha
cover-img: /assets/img/path.jpg
share-img: /assets/img/php.jpg
thumbnail-img: /assets/img/php.jpg
tags: [php, tips]
---

Kadang, saya butuh halaman yang menandakan bahwa aksinya belum bisa dilakukan, lalu halaman tersebut tertutup begitu saja karena emang gak ada hal lain yang bisa ditampilkan. Begini metode yang saya lakukan selama ini. 

file `routes/web.php`

```php
Route::view('close', 'close')->name('close');
```

file `resources/views/close.blade.php`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Forbidden</title>
</head>
<body>
    <script>
        alert('Belum bisa melakukan aksi ini'); window.close();
    </script>
</body>
</html>
```

Jadi, halaman ini akan menampilkan alert dialog sederhana, lalu halamannya akan tertutup sendiri.

Adapun cara mengaksesnya, cukup seperti ini dalam controller.

```php
return redirect()->route('close');
```

Nah, semoga bermanfaat.