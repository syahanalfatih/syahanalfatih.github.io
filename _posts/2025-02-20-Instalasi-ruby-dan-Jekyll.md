---
layout: post
title: "🚀 Panduan Lengkap Instalasi Ruby, Jekyll & GitHub Pages"
---

> 📘 *Panduan step-by-step membuat personal website statis menggunakan Ruby, Jekyll, dan GitHub Pages. Ideal untuk pemula dan menengah.*

---

## 🧰 1. Persiapan Awal

### ✅ Cek Ruby 
1. **Cek apakah Ruby sudah terpasang**  
   Buka terminal atau Command Prompt, lalu ketik:  
   ```bash
   ruby -v
   ```
   Jika Ruby sudah terpasang, maka akan muncul versi Ruby. Jika belum, ikuti langkah berikutnya.  

2. **Cek RubyGems**  
   Ketik perintah berikut:  
   ```bash
   gem -v
   ```

3. **Cek GCC dan Make**  
   Ketik perintah berikut:  
   ```bash
   gcc -v
   g++ -v
   make -v
   ```
   Jika belum tersedia, install melalui:

🟦 MinGW

🐧 sudo apt install build-essential (Linux)  

 **Download Ruby Installer**  
   - Buka link berikut: [https://rubyinstaller.org](https://rubyinstaller.org)  
   - Pilih versi **Ruby 2.7.0** atau lebih tinggi.  
   - Ikuti instruksi instalasi hingga selesai.  

✅ Install Jekyll & Bundler
bash
Copy
Edit
gem install jekyll bundler

---

🛠️ Install Pendukung
💡 Git (Version Control)
bash
Copy
Edit
git --version
🔗 Download Git lalu install sesuai OS kamu.

---

🧑‍💻 VSCode (Text Editor)
🔗 Download VSCode

---

🌐 Google Chrome (Browser)
🔗 Download Chrome 

---

Chrome

🌍 Siapkan GitHub & Repository
🐙 Buat Akun GitHub
🔗 github.com


---

🧱 Buat Repository Baru
Gunakan format: username.github.io
Contoh: faiza.github.io

---

💻 Mulai Proyek Jekyll
🔁 Clone Repo GitHub
bash
Copy
Edit
git clone https://github.com/username/username.github.io.git
cd username.github.io

---

📦 Inisialisasi Bundler
bash
Copy
Edit
bundle init
Perintah ini akan membuat file `Gemfile` di dalam folder proyek.  

---

✏️ Edit Gemfile
Tambahkan:

ruby
Copy
Edit
source "https://rubygems.org"
gem "jekyll"
Install:

bash
Copy
Edit
bundle install

---

📄 Buat index.html
html
Copy
Edit
<!DOCTYPE html>
<html>
  <head>
    <title>My Jekyll Site</title>
  </head>
  <body>
    <h1>Hello World from Jekyll 👋</h1>
    <p>This is a simple personal site powered by Jekyll and GitHub Pages.</p>
  </body>
</html>


---

🔧 Jalankan Jekyll Secara Lokal
🔨 Build
bash
Copy
Edit
jekyll build
🚀 Jalankan Server
bash
Copy
Edit
jekyll serve
Buka di browser:
📡 http://localhost:4000

💡 Live reload:

bash
Copy
Edit
jekyll serve --livereload

---

🐧 6. Linux Tips (Optional)
Edit Gemfile.lock
Tambahkan:

nginx
Copy
Edit
PLATFORMS
  ruby
  x86_64-linux
```

---

⬆️ Push ke GitHub
bash
Copy
Edit
git add .
git commit -m "Initial Jekyll site"
git push origin main    

---

⚙️ 8. Otomatisasi dengan GitHub Actions
Buat folder dan file:

bash
Copy
Edit
mkdir -p .github/workflows
touch .github/workflows/jekyll.yml
Isi file jekyll.yml:

yaml
Copy
Edit
name: Jekyll Deploy

on:
  push:
    branches:
      - main

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2

      - name: Setup Ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: '2.7'

      - name: Install dependencies
        run: bundle install

      - name: Build site
        run: JEKYLL_ENV=production bundle exec jekyll build

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./_site
Push kembali:

bash
Copy
Edit
git add .
git commit -m "Add CI/CD GitHub Actions"
git push origin main    

---

🌐 9. Selesai!
✅ Website kamu siap diakses via:

bash
Copy
Edit
https://username.github.io

---

🛠️ Troubleshooting

Masalah	Solusi
❌ Port Konflik	jekyll serve --host 0.0.0.0 --port 4001
❌ Build gagal	Pastikan Ruby dan Bundler sudah terpasang
❌ GitHub Pages kosong	Pastikan branch utama: main
```