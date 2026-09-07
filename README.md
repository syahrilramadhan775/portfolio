# Portofolio — Backend Developer

Website statis (HTML/CSS/JS murni, tanpa build tool) siap dijalankan di localhost dan di-hosting mandiri.

## Menjalankan di localhost

Pilih salah satu:

**Python** (biasanya sudah terpasang):
```
cd portfolio
python3 -m http.server 8000
```
Lalu buka http://localhost:8000

**Node.js:**
```
cd portfolio
npx serve .
```

**Atau paling sederhana:** klik dua kali `index.html` untuk membukanya langsung di browser.

## Yang perlu Anda ganti

Buka `index.html` dan cari lalu ganti bagian berikut dengan data Anda:

- `Nama Anda` — nama lengkap (muncul di title, nav, hero, footer)
- Foto profil: ganti `assets/profile/profile.svg` dengan foto Anda (format `.jpg`/`.png` juga bisa — tinggal ubah `src` pada tag `<img>` di dalam `<div class="hero-photo">` pada `index.html`). Foto ini tampil besar di sisi kanan hero.
- CV/Resume: ganti `assets/resume.pdf` dengan file CV Anda yang sebenarnya (nama file boleh diganti, asal disesuaikan juga dengan `href` pada tombol "Unduh CV")
- `email.anda@contoh.com` — email aktif (ada 2 tempat: hero & contact, plus `mailto:` di nav)
- `username-anda` — link LinkedIn Anda
- Bagian **Tentang**: ringkasan pengalaman dan filosofi kerja Anda
- Bagian **Pengalaman**: nama perusahaan, jabatan, rentang tanggal, dan deskripsi tiap posisi (tambah/hapus `<article class="timeline-item">` sesuai jumlah pengalaman)
- Bagian **Proyek**: ganti `Nama Proyek 1/2/3`, deskripsi, tech stack (`project-tech`), dan link `Lihat detail`
- Bagian **Stack**: sesuaikan bahasa, framework, database, dan tools yang Anda pakai. Icon brand (Go, Node.js, Laravel, dst) diambil otomatis dari `cdn.simpleicons.org` berdasarkan nama slug-nya — ganti `src` ke slug tool lain jika perlu (cek nama slug di simpleicons.org), atau ganti `<img>` dengan elemen `<svg class="stack-icon">` custom seperti yang dipakai di bagian Praktik kalau tool-nya tidak ada di simple-icons. Icon ini butuh koneksi internet saat halaman dibuka; kalau ingin bisa dipakai 100% offline, unduh SVG-nya dan simpan lokal di `assets/`.
- Bagian **Pendidikan**: nama kampus dan jurusan
- Bagian **Media Sosial**: ganti `href` tiap kartu dengan link profil Anda (GitHub, GitLab, Instagram, TikTok). Mau tambah platform lain (X, YouTube, dsb)? Duplikasi satu `<a class="social-card">`, ganti link icon-nya ke slug yang sesuai di simpleicons.org, dan ganti label teksnya. Mau kurangi? Hapus saja blok `<a>` yang tidak dipakai.

## Mengganti gambar proyek

Gambar slider ada di folder `assets/projects/`. Saat ini isinya placeholder (`project1-1.svg`, `project1-2.svg`, dst — 3 gambar per proyek).

Cara ganti:
1. Siapkan screenshot Anda (format `.jpg`/`.png`/`.webp` semua bisa)
2. Timpa file placeholder dengan nama yang sama, atau ubah `src` di `index.html` supaya menunjuk ke file baru Anda
3. Untuk menambah/mengurangi jumlah gambar dalam satu slider, tinggal tambah/hapus elemen `<div class="slide"><img ...></div>` di dalam `.slider-track` proyek terkait — dot navigasi akan menyesuaikan otomatis
4. Untuk menambah proyek baru, duplikasi satu blok `<article class="project-card">...</article>` lalu ubah isinya

Slider mendukung klik tombol panah, klik titik navigasi, dan swipe di layar sentuh.

## Deploy ke domain sendiri

Karena ini situs statis, tinggal upload ketiga file (`index.html`, `style.css`, `script.js`) ke hosting mana pun:
- Shared hosting biasa: upload lewat FTP/cPanel ke folder `public_html`
- Netlify / Vercel / Cloudflare Pages: drag-and-drop folder ini, gratis dan otomatis dapat HTTPS
- VPS sendiri: taruh di folder yang di-serve Nginx/Apache

Tidak ada dependency backend maupun database — murni file statis.
