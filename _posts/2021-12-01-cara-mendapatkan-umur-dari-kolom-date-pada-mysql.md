---
layout: post
title: Cara Mendapatkan Umur dari Kolom Date pada MySQL
subtitle: Aa Ezha
cover-img: /assets/img/path.jpg
share-img: /assets/img/mysql.png
thumbnail-img: /assets/img/mysql.png
tags: [sql, tips]
---

Sudah biasa kalau kita memiliki satu field dengan tipe data “date” untuk menyimpan tanggal lahir. Namun, bagaimana jika kita ingin mengambil usianya dari kolom tanggal lahir tersebut? Ini adalah caraku dari dulu sampai sekarang digunakan.

Anggaplah kita memiliki struktur tabel seperti ini:

```
MariaDB [test]> desc biodata;
+-------+--------------+------+-----+---------+----------------+
| Field | Type         | Null | Key | Default | Extra          |
+-------+--------------+------+-----+---------+----------------+
| id    | int(11)      | NO   | PRI | NULL    | auto_increment |
| nama  | varchar(100) | YES  |     | NULL    |                |
| ttl   | date         | YES  |     | NULL    |                |
+-------+--------------+------+-----+---------+----------------+
3 rows in set (0.011 sec)
```

Maka, begini query-ku untuk mendapatkan nilai umur:

```sql
SELECT FLOOR(DATEDIFF(curdate() , ttl) / 365.25) age from biodata;
```

```
MariaDB [test]> SELECT FLOOR(DATEDIFF(curdate() , ttl) / 365.25) age from biodata;
+------+
| age  |
+------+
|   32 |
+------+
1 row in set (0.011 sec)
```

Mudah, kan?