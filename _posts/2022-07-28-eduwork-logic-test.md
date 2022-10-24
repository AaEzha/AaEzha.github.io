---
layout: post
title: "EduWork Logic Test"
subtitle: Aa Ezha
cover-img: /assets/img/path.jpg
share-img: /assets/img/php.svg
thumbnail-img: /assets/img/php.svg
tags: [php, logic, test]
---

Beberapa bulan terakhir ini, saya terdaftar menjadi salah satu mentor di sebuah platform mentorship yang juga menjanjikan pekerjaan untuk para siswanya. Namun, foto saya tidak terpampang di situ karena bukan termasuk pekerja di perusahaan start-up terkemuka. Hihihi.

Setelah beberapa bulan berjalan, sampailah siswa-siswa saya dianggap “lulus” dan harus mengerjakan soal mengenai logika. Begini soalnya dan begitu jawaban dari saya. Hihihi.

Harus diingat, jawaban ini bukanlah satu-satunya jawaban dan belum tentu jawaban terbaik. Jadi, silahkan kirimkan komentar kalau teman-teman punya jawaban yang lebih baik ya.

---

```php
Buatlah fungsi sebagai berikut :
Apabila terdapat int = 4, maka outputnya 24 (prosesnya : 4*3*2*1)
Apabila terdapat int = 8, maka outputnya 40320 (prosesnya : 8*7*6*5*4*3*2*1)
```

Jawaban

```php
$int = 4; // ubah angka di sini

for($i = $int - 1; $i >= 1; $i--) {
    $int *= $i;
}

echo $int; // output: 24
```

---

```php
Buatlah fungsi untuk reverse sebuah string
Apabila input = “abcde”, maka outputnya = “edcba”
Dilarang menggunakan function reverse, buatlah logika sendiri
```

Jawaban

```php
$input = "abcde";

$n = strlen($input);

for ($i = 1; $i <= $n; $i++) {
  $val = $input[-$i];
  echo $val;
}

// output: edcba
```

---

```php
Buatlah fungsi untuk menampilkan jumlah digit angka tergantung dimana posisi atau tempat dari angka dalam sebuah string “9.86-A5.321”! 
Contoh: printDigitValue(‘9.86-A5.321’);
Hasil :
9865321
9000000
800000
60000
5000
300
20
1
```

Jawaban

```php
echo printDigitValue('9.86-A5.321');

function printDigitValue($value)
{
  $n = strlen($value);
  $result = "";

  for ($i = 0; $i <= $n; $i++) {
    if (!is_numeric($value[$i])) {
      continue;
    }
    $result .= $value[$i];
  }

  echo $result . "\n";

  $n = strlen($result);

  for ($i = 0; $i <= $n; $i++) {
    echo str_pad($result[$i], $n - $i, '0', STR_PAD_RIGHT) . "\n";
  }
}
```

---

```php
Ketik kode untuk swap 2 integer variables tanpa VARIABLE TAMBAHAN 
Contoh : let a = 3, let b = 7 => hasilnya a = 7, b = 3
```

Jawaban

```php
$a = 3;
$b = 7;

$a = $a + $b;
$b = $a - $b;
$a = $a - $b;
```

---

```php
Buatlah fungsi sebagai berikut :
int : 4, maka outputnya adalah : empat
int : 20, maka outputnya adalah : dua puluh
int : 39, maka outputnya adalah : tiga puluh sembilan
int : 104, maka outputnya adalah : silahkan masukkan bilangan 1-100
```

Jawaban

```php
$angka = 101;
echo penyebut($angka);

function penyebut($nilai)
{
  $nilai = abs($nilai);
  $huruf = array("", "satu", "dua", "tiga", "empat", "lima", "enam", "tujuh", "delapan", "sembilan", "sepuluh", "sebelas");
  $temp = "";
  if ($nilai <= 0 or $nilai > 100) {
    echo "silahkan masukkan bilangan 1-100";
  } else if ($nilai < 12) {
    $temp = " " . $huruf[$nilai];
  } else if ($nilai < 20) {
    $temp = penyebut($nilai - 10) . " belas";
  } else if ($nilai < 100) {
    $temp = penyebut($nilai / 10) . " puluh" . penyebut($nilai % 10);
  } else {
    echo "seratus";
  }

  return $temp;
}
```

---

```php
Apabila terdapat sebuah data : 
array data =  [1,4,7,9,12], 
int low = 2,
int high = 15,
maka akan menghasilkan ouput [4,7,9,12]
```

Jawaban

```php
$array = [1, 4, 7, 9, 12];
$low = 2;
$high = 15;

$result = [];

foreach ($array as $key => $value) {
  if ($value >= $low && $value <= $high) {
    $result[] = $value;
  }
}

var_dump ($result);
```

---

```php
Dari soal nomor 6, buatlah juga untuk menghasilkan output total ada berapa angka yg termasuk dari bagian low dan high
array data =  [1,4,7,9,12], 
int low = 2,
int high = 15,
maka akan menghasilkan ouput = 4
```

Jawaban

```php
$array = [1, 4, 7, 9, 12];
$low = 2;
$high = 15;

$result = [];

foreach ($array as $key => $value) {
  if ($value >= $low && $value <= $high) {
    $result[] = $value;
  }
}

echo count($result);
```

---

```php
Apabila terdapat int = 15, maka akan mencetak output berikut :
1
2
Edu
4
Work
6
7
8
Edu
10
11
Edu
13
14
EduWork

keterangan : string edu untuk kelipatan 3, string work untuk kelipatan 5, string eduwork untuk kelipatan 3 dan 5
```

Jawaban

```php
$int = 15;

for ($i=1; $i <= $int; $i++) { 
  if ($i % 3 == 0 && $i % 5 == 0) {
    echo "EduWork";
  } else if ($i % 3 == 0) {
    echo "Edu";
  } else if ($i % 5 == 0) {
    echo "Work";
  } else {
    echo $i;
  }
}
```

---

```php
Buatlah fungsi untuk menentukan bilangan terkecil dan terbesar dari sebuah array
Contoh : array [4,2,6,88,3,11]
Maka outputnya adalah low : 2, high : 88
dilarang menggunakan built in function
```

Jawaban

```php
$array = [4, 2, 6, 88, 3, 11];
$low = $array[0];
$high = $array[0];
$n = count($array);

for ($i = 0; $i < $n; $i++) {
  if ($low < $array[$i]) { 
    $low = $array[$i]; 
  } 

  if ($high > $array[$i]) {
    $high = $array[$i];
  }
}

echo "low : $low, high : $high";
```

---

```php
Buatlah fungsi untuk mengecek tahun kabisat
input : 2021
output : 2021 bukan tahun kabisat

input : 2024
output : 2024 adalah tahun kabisat
```

Jawaban

```php
$input = 2021;

if ($input % 4 == 0) {
  echo "$input adalah tahun kabisat";
} else if ($input % 4 != 0) {
  echo "$input bukan tahun kabisat";
}
```

---

Perhatian. Jangan anggap ini sebagai kunci jawaban karena EduWork bisa mengubah soal-soal di atas kapan pun. Yang saya ingin sampaikan adalah PAHAMI jawaban-jawaban di atas sehingga logika kita bisa semakin terasah jika diberikan soal logika lainnya.