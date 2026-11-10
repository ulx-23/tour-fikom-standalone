========================================================================
VIRTUAL TOUR 360° — PAKET EKSPOR STANDALONE (STATIC HOSTING & OFFLINE)
========================================================================

Selamat! Paket virtual tour ini telah diekspor sebagai aplikasi web statis mandiri.
Paket ini 100% independen: pustaka 360° Marzipano, panorama, denah, dan seluruh tombol hotspot
sudah terhubung langsung tanpa memerlukan Next.js, database MySQL/PostgreSQL, maupun server API.

------------------------------------------------------------------------
CARA HOSTING KE VERCEL (HANYA HASIL TOUR STATIS):
------------------------------------------------------------------------

1. Ekstrak seluruh isi file ZIP ini ke sebuah folder baru.
   Pastikan folder tersebut berisi index.html, vercel.json, app.js, tour-data.js, vendor/, dan panoramas/.

2. METODE A — Vercel CLI (Paling Cepat):
   - Buka terminal / PowerShell di dalam folder hasil ekstrak.
   - Jalankan: npx vercel --prod
   - Jika ditanya pengaturan build, pilih Framework Preset: Other dan Output Directory: . (folder saat ini).
   - Hasil link Vercel langsung menampilkan Virtual Tour 360° Anda dengan semua tombol hotspot aktif.

3. METODE B — Upload ke GitHub & Deploy via Dashboard Vercel:
   - Buat repository GitHub baru khusus untuk hasil tour statis ini, lalu unggah isi folder hasil ekstrak.
   - Di Vercel Dashboard -> Add New Project -> Import repository tersebut.
   - Atur Framework Preset: Other, kosongkan Build Command, Output Directory: . (otomatis terbaca dari vercel.json).
   - Klik Deploy.

4. PENYEDIA HOSTING STATIS LAINNYA:
   Folder hasil ekstrak ini juga dapat langsung di-drop ke Netlify Drop, Cloudflare Pages,
   GitHub Pages, cPanel (public_html), atau S3 Static Website Hosting.

------------------------------------------------------------------------
CARA MENJALANKAN DI KOMPUTER LOKAL (OFFLINE):
------------------------------------------------------------------------

Karena kebijakan keamanan browser modern terhadap protokol file:// lokal,
disarankan menjalankan melalui web server statis sederhana:

- Windows: jalankan "Start tour.cmd", lalu buka http://127.0.0.1:4173.
  Launcher memerlukan Node.js yang sudah terpasang, tanpa mengunduh paket.
  Alternatif terminal: node serve.cjs

- Dengan Python 3:
  python -m http.server 8080
  Lalu buka browser di http://localhost:8080

- Dengan PHP (Laragon / XAMPP):
  php -S localhost:8080
  Lalu buka browser di http://localhost:8080

- Dengan VS Code:
  Pasang ekstensi "Live Server", klik kanan pada index.html, pilih "Open with Live Server".

------------------------------------------------------------------------
STRUKTUR FILE:
------------------------------------------------------------------------
├── index.html         -> Halaman utama virtual tour
├── vercel.json        -> Konfigurasi hosting statis & cache Vercel (tanpa build backend)
├── app.js             -> Logika player Marzipano & interaksi tombol hotspot
├── style.css          -> Tampilan responsif & estetika UI
├── tour-data.js       -> Manifest konfigurasi tur, scene & relasi tombol hotspot
├── tour.json          -> Manifest JSON murni tur
├── integrity.json     -> Daftar ukuran dan checksum SHA-256 seluruh file
├── vendor/
│   └── marzipano.js   -> Pustaka WebGL 360° Marzipano mandiri
├── panoramas/         -> Foto panorama 360° equirectangular
└── floor-plans/       -> Denah lokasi & penanda (jika ada)

Dihasilkan secara otomatis oleh Virtual Tour 360° Builder.

Tautan eksternal memerlukan internet ketika diklik dan meminta konfirmasi.
Single HTML tersedia untuk sumber maksimal 16 MiB melalui konverter aplikasi.
Paket Windows dibangun terpisah untuk komputer tanpa Node.js.

