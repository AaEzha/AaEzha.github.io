---
layout: post
title: "HTML Print then Close"
subtitle: Aa Ezha
cover-img: /assets/img/path.jpg
share-img: /assets/img/html.jpg
thumbnail-img: /assets/img/html.jpg
tags: [html, javascript, tips]
---

Melanjutkan artikel sebelumnya, kali ini adalah tips untuk mencetak sebuah halaman, kemudian *auto-close*.

Solusinya mudah saja. Cukup sematkan barisan JS ini pada HTML kita.

```html
<script type="text/javascript">
    window.print();
    window.onfocus = function () { setTimeout(function () { window.close(); }, 500); }
</script>
```

Cobain sendiri deh efeknya ya.