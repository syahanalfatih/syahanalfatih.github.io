---
layout: posts
title: "✨ Menggunakan SASS & SCSS di Jekyll"
date: 2025-02-22
---


Jekyll mendukung **SASS/SCSS** secara _built-in_, memungkinkan Anda membuat style yang **modular**, **rapi**, dan **mudah dirawat**.

Dengan SCSS, Anda bisa memakai variabel warna, nested rules, mixin, dan fitur lain yang membuat penulisan CSS jauh lebih powerful!

---

## 💡 Apa Itu SASS & SCSS?

| Format | Deskripsi |
|--------|-----------|
| **SASS** | Sintaks lama (tanpa `{}` dan `;`) — lebih ringkas |
| **SCSS** | Sintaks mirip CSS (umum digunakan di Jekyll) ✅ |

Contoh SCSS:

```scss
$primary: #1abc9c;

body {
  background: $primary;

  h1 {
    font-size: 2rem;
    color: white;
  }
}

🗂️ Struktur Folder SCSS Jekyll
text
Copy
Edit
.
├── _sass/              ← Partial SCSS (modular)
│   └── _variables.scss
├── assets/
│   └── css/
│       └── main.scss   ← File utama
Semua partial SCSS (awalan _) diletakkan di folder _sass.

File main.scss di-compile otomatis oleh Jekyll menjadi main.css.

🛠️ Langkah Menggunakan SCSS
1️⃣ Buat partial di _sass/_variables.scss
scss
Copy
Edit
$bg-color: #222;
$text-color: #f4f4f4;
2️⃣ Buat file assets/css/main.scss
scss
Copy
Edit
---
---

@import "variables";

body {
  background: $bg-color;
  color: $text-color;
}
Wajib ada --- di awal file agar diproses oleh Jekyll.

3️⃣ Tambahkan di layout HTML (_layouts/default.html atau lainnya)
html
Copy
Edit
<link rel="stylesheet" href="{{ '/assets/css/main.css' | relative_url }}">

⚙️ Pengaturan Output CSS (_config.yml)
yaml
Copy
Edit
sass:
  style: compressed  # atau nested | expanded | compact
compressed: CSS jadi 1 baris (untuk produksi)

expanded: CSS rapi dan mudah dibaca (untuk dev)

💎 Tips Pro SCSS
✅ Gunakan Partial Modular: Pisahkan style per komponen/layout
✅ Gunakan Variabel: Warna, ukuran font, spacing
✅ Gunakan Mixin: Buat fungsi SCSS reusable
✅ Gunakan Nested Selector: Untuk struktur CSS yang bersih

✅ Kesimpulan
🔧 SCSS di Jekyll memberi Anda kekuatan lebih untuk mengelola tampilan situs.
📁 Struktur _sass/ dan main.scss membuat style lebih modular.
🚀 Tidak butuh plugin tambahan — cukup struktur dan konfigurasi rapi!

Dengan SCSS, situs statis Anda jadi tampil lebih dinamis dan profesional!