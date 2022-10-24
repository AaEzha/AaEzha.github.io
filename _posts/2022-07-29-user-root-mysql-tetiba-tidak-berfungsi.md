---
layout: post
title: "User root MySQL Tetiba Tidak Berfungsi"
subtitle: Aa Ezha
cover-img: /assets/img/mysql-thumb.jpg
share-img: /assets/img/mysql.png
thumbnail-img: /assets/img/mysql.png
tags: [mysql, root]
---

Pagi ini saya mendapatkan notifikasi untuk update versi MySQL terbaru pada laptop yang terinstall LinuxMint dan dipakai rutin untuk kerja setiap hari. Tentunya lebih banyak antara Senin sampai Jum’at saja, karena work life balance itu perlu dan penting.

Tepat setelah update, saya mulai membuka projek Laravel dan mendapati bahwa ada kesalahan password pada user root yang dipakai.

```sql
$ mysql -uroot -p
Enter password: 
ERROR 1698 (28000): Access denied for user 'root'@'localhost'
```

Jeng jeng…


Bingung lah saya mendapati error seperti itu yang bahkan kurang dari 24 jam lalu masih lancar jaya gemah ripah low jinawi!

Apa yang terjadi dengan laptop saya? Apakah ada yang mencoba mengirim santet ke user root saya? Apakah user root saya terkena dampak inflasi negara Sri Lanka?

Selidik punya selidik, saya tidak menemukan alasan kenapa semua ini bisa terjadi dan menimpa seorang ayah dengan 1 anak dan 1 istri ini. Namun, solusinya cukup sederhana sesuai dengan pengalaman saya selama ini.

Saya coba login menggunakan sudo, alhamdulillah bisa. Kemudian saya tuliskan 1 baris sederhana yang mungkin nantinya berguna untuk teman-teman dan diri saya di masa yang akan datang.

```sql
alter user 'root'@'localhost' identified with mysql_native_password by '';
```

Dan akhirnya MySQL saya kembali seperti semula. Alhamdulillah.

```sql
$ mysql -uroot -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 26
Server version: 8.0.30-0ubuntu0.20.04.2 (Ubuntu)

Copyright (c) 2000, 2022, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>
```