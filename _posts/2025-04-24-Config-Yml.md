---
layout: posts
title: "⚙️ Panduan Lengkap: Mengenal dan Mengatur _config.yml pada Jekyll"
date: 2025-04-24
---


File `_config.yml` adalah jantung dari konfigurasi situs Jekyll. Semua pengaturan utama seperti judul, URL, tema, plugin, dan bahkan perilaku build situs diatur dari file ini.

Memahami struktur dan penggunaan `_config.yml` akan memudahkan Anda mengelola situs Jekyll secara efisien dan profesional.

---

## 📁 Apa Itu `_config.yml`?

File `_config.yml` ditulis dalam format **YAML** (YAML Ain’t Markup Language) dan digunakan untuk:

- Menyimpan **metadata** situs seperti nama, deskripsi, dan penulis.
- Mengatur **struktur URL** (permalink) untuk halaman dan postingan.
- Mengaktifkan **plugin** dan tema.
- Mengelola **koleksi khusus**, pagination, serta opsi build lainnya.

Jekyll membaca file ini setiap kali Anda menjalankan `jekyll build` atau `jekyll serve`.

---

## 🧰 Contoh Struktur Dasar `_config.yml`

```yml
title: "Blog Teknologi"
description: "Kumpulan tulisan seputar coding, web, dan open source"
baseurl: "" # Kosongkan jika domain utama
url: "https://namasitus.github.io"

author:
  name: "Nama Anda"
  email: "email@domain.com"

theme: minima

permalink: /:categories/:title/

plugins:
  - jekyll-feed
  - jekyll-seo-tag
  - jekyll-sitemap

🔍 Penjelasan Konfigurasi
Kunci	Fungsi
title	Judul situs, muncul di tab browser dan halaman utama.
description	Deskripsi singkat situs, penting untuk SEO.
baseurl	Digunakan jika situs dihosting dalam subdirektori (misal /blog).
url	URL utama situs Anda (sertakan https://).
author	Informasi tentang penulis. Bisa ditampilkan di footer atau bio.
theme	Tema yang digunakan situs (contoh: minima).
permalink	Menentukan format URL halaman/postingan.
plugins	Plugin yang diaktifkan untuk memperluas fungsi situs.

⚙️ Konfigurasi Lanjutan
Anda bisa menambahkan pengaturan lebih kompleks untuk menyesuaikan kebutuhan proyek:

yml
Copy
Edit
markdown: kramdown
highlighter: rouge
paginate: 5
paginate_path: "/page:num/"

collections:
  tutorials:
    output: true
    permalink: /tutorials/:path/
Penjelasan:

markdown: Engine untuk memproses Markdown. Default: kramdown.

highlighter: Syntax highlighting untuk kode. Default: rouge.

paginate: Jumlah postingan per halaman.

paginate_path: Format URL untuk pagination.

collections: Koleksi konten tambahan selain _posts.

🌐 Konfigurasi untuk GitHub Pages
Jika Anda menggunakan GitHub Pages:

yml
Copy
Edit
remote_theme: jekyll/minima
plugins:
  - jekyll-feed
  - jekyll-seo-tag

# Optional: baseurl & url
baseurl: "" # jika di root, kosongkan
url: "https://username.github.io"
Tambahkan juga file .nojekyll di root untuk mencegah GitHub Pages mengabaikan folder yang dimulai dengan _.

🌍 Mengelola Beberapa Environment (Dev vs Prod)
Gunakan beberapa file konfigurasi untuk memisahkan konfigurasi development dan production:

_config.yml (utama):

yml
Copy
Edit
title: "Blog Saya"
url: "https://namasitus.com"
_config_dev.yml (khusus development):

yml
Copy
Edit
url: "http://localhost:4000"
Lalu jalankan dengan:

bash
Copy
Edit
jekyll serve --config _config.yml,_config_dev.yml

💡 Tips Penggunaan
Gunakan spasi, bukan tab — YAML sangat sensitif terhadap indentasi.

Setelah mengubah _config.yml, restart server (ctrl + c lalu jekyll serve) agar perubahan diterapkan.

Validasi file YAML Anda secara online atau dengan linter jika perlu.

✅ Kesimpulan
_config.yml adalah pusat pengaturan proyek Jekyll Anda.

File ini mengontrol layout, plugin, struktur URL, dan lainnya.

Menguasai YAML dan memahami struktur file ini akan membuat Anda lebih leluasa dalam membangun dan mengelola situs.

