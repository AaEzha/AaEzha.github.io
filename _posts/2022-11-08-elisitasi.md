---
layout: post
title: "Elisitasi"
subtitle: Aa Ezha
cover-img: /assets/img/analis.png
share-img: /assets/img/analis.png
thumbnail-img: /assets/img/analis.png
tags: [sistem, analis, elisitasi]
---

Sesungguhnya ini hanyalah catatan dari apa yang saya pelajari saat kuliah. Saya lupa mata kuliah apa tepatnya. *So*, mari kita lanjutin aja yaaa...

Elisitasi adalah seperangkat data terkait kebutuhan sistem baru dari aktivitas pengguna sistem atau stakeholder yang memiliki keterkaitan/hubungan langsung dengan penggunaan sistem maupun dengan pengembangan sistem. [^1]

Sederhananya, proses elisitasi adalah proses eliminasi terhadap *requirements* dari *user* melalui 3 tahap dan final elisitasi.

1. Elisitasi Tahap 1
    Berisi seluruh rancangan sistem baru yang diusulkan oleh pihak manajemen terkait melalui proses wawancara.

2. Elisitasi Tahap 2
    Merupakan hasil pengklasifikasian dari elisitasi tahap I berdasarkan metode MDI. Metode MDI ini bertujuan untuk memisahkan antara rancangan sistem yang penting dan harus ada pada sistem baru dengan rancangan yang disanggupi oleh penulis untuk dieksekusi.

    1. “M” pada MDI itu artinya ***Mandatory*** (penting). Maksudnya requirement tersebut harus ada dan tidak boleh dihilangkan pada saat membuat sistem baru.
    2. “D” pada MDI itu artinya ***Desirable***. Maksudnya requirement tersebut tidak terlalu penting dan boleh dihilangkan. Tetapi jika requirement tersebut digunakan dalam pembuatan sistem, akan membuat sistem tersebut lebih sempurna.
    3. “I” pada MDI itu artinya ***Inessential***. Maksudnya bahwa requirement tersebut bukanlah bagian dari sistem yang dibahas dan merupakan bagian dari luar sistem.

3. Elisitasi Tahap 3
    Merupakan hasil penyusutan dari elisitasi tahap II dengancara mengeliminasi semua requirement yang optionnya I pada metode MDI. Selanjutnya semua requirement yang tersisa diklasifikasikan kembali melalui metode TOE, yaitu sebagai berikut:

    1. T artinya ***Technical***, maksudnya bagaimana tata cara/teknik pembuatan requirement tersebut dalam sistem yang diusulkan.
    2. O artinya ***Operational***, maksudnya bagaimana tata cara penggunaan requirement tersebut dalam sistem yang akan dikembangkan.
    3. E artinya ***Economy***, maksudnya berapakah biaya yang diperlukan guna membangun requirement tersebut didalam sistem.

    Metode TOE tersebut dibagi kembali menjadi beberapa option, yaitu:

    1. ***High*** (H) : Sulit untuk dikerjakan, karena tehnik pembuatan dan pemakaiannya sulit serta biayanya mahal, sehingga requirement tersebut harus dieliminasi.
    2. ***Middle*** (M) : Mampu untuk dikerjakan.
    3. ***Low*** (L) : Mudah untuk dikerjakan.

4. Final Draft Elisitasi
    Merupakan hasil akhir yang dicapai dari suatu proses elisitasi yang dapat digunakan sebagai dasar pembuatan suatu sistem yang akan dikembangkan.

Biar gak bingung, mari kita lihat contohnya saja ya.

1. Elisitasi Tahap 1
    ![Elisitasi Tahap 1](/assets/img/elisitasi-1.png)
2. Elisitasi Tahap 2
    ![Elisitasi Tahap 2](/assets/img/elisitasi-2.png)
3. Elisitasi Tahap 3
    ![Elisitasi Tahap 3](/assets/img/elisitasi-3.png)
4. Final Draft Elisitasi
    ![Final Draft Elisitasi](/assets/img/elisitasi-final.png)

Hasil di atas tentu belum final, karena masih sebagai Draft. Semuanya masih bisa diolah lagi, bahkan bisa berulang ke Tahap 1 lagi berdasarkan data pada Final Draft-nya.

Nah, kurang lebih demikian tentang elisitasi.

Sumber: [Widuri](https://widuri.raharja.info/index.php?title=SI1422481557)

[^1]: Yousuf, Masooma, and M. Asger. “Comparison of Various Requirements Elicitation Techniques”. International Jurnal of Computer Applications Vol.116 No.4, April 2015 ISSN 0975-8887.