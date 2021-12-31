---
layout: post
title: "Exclude Contents When Printing"
subtitle: Aa Ezha
cover-img: /assets/img/path.jpg
share-img: /assets/img/html.jpg
thumbnail-img: /assets/img/html.jpg
tags: [html, css, tips]
---

Ada kalanya, ketika develop web untuk halaman yang dicetak, ada beberapa hal yang tidak ingin kita ikut cetak pula. Bagaimana caranya? Begini aja. Semoga mudah.

![exclude contents when printing](https://pbs.twimg.com/media/FH6e0iGUUAEcHhl?format=jpg&name=large)

Ini bentuk yang bisa di-*copas*-nya

CSS
```css
@media print {
    .no-print {
        display: none;
    }
}
```

HTML
```html
<body>
    <p>Text to print</p>

    <div class="no-print">
        everything located inside this div will not be printed out
    </div>

</body>
```

Semoga bermafaat, ya!