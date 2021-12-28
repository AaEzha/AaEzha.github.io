---
layout: post
title: "HTML Set Print Landscape"
subtitle: Aa Ezha
cover-img: /assets/img/path.jpg
share-img: /assets/img/html.jpg
thumbnail-img: /assets/img/html.jpg
tags: [html, css, tips]
---

Sebagai Back-End Developer, saya sering mendapatkan kasus untuk mencetak sesuatu seperti *invoice*, *purchase order*, dan lain sebagainya. Secara *default*, bawaan dari browser saat ingin mencetak sesuatu adalah halamannya diset sebagai potrait. Bagaimana kalau ingin langsung *landscape* saat ingin mencetak?

Ternyata setelah *googling* sana-sini, solusinya mudah saja. Cukup sematkan barisan CSS ini pada HTML kita.

```html
<style type="text/css">
    @media print {
        @page {size: landscape}
    }
</style>
```

Cobain sendiri deh efeknya ya.