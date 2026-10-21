# WebCAD 2D — Demo (GitHub Pages)

Folder ini adalah **versi demo WebCAD 2D** untuk dipasang di GitHub Pages sebagai halaman coba gratis.
Pengunjung bisa mencoba semua alat gambar CAD (gambar & modifikasi, dimensi, layer, blok, layout, plumbing/MEP, listrik, HVAC, pemadam, isometrik, potongan, BOQ, viewer 3D, contoh gambar), tetapi **menyimpan proyek, ekspor DXF / IFC / OBJ, dan semua unduhan berkas** dikunci. Setiap fitur yang dikunci memunculkan
dialog *Fitur versi lengkap* dengan tombol **Beli versi lengkap** yang mengarah ke halaman produk Mayar Anda.
Badge **DEMO** dengan tombol beli juga selalu tampil di layar.

Plot dan Publish bisa dicoba, tetapi hasil cetak/PDF-nya selalu memuat watermark **DEMO**. Membuka DXF milik pengunjung tetap bisa dicoba. Demo berjalan sepenuhnya di browser tanpa server; folder `tutorial/` berisi panduan PDF (Indonesia & English) yang dibuka dari menu Bantuan.

## 1. Atur link pembelian (wajib)
Buka `config.js`, ganti `buyUrl` dengan link halaman produk Mayar Anda (link yang dibagikan ke pembeli), misalnya:
```js
buyUrl: "https://ISI-LINK-PRODUK-MAYAR-ANDA",
buyLabel: "Beli versi lengkap",
```

## 2. Publikasikan di GitHub Pages
1. Masuk ke https://github.com → **New repository** → nama mis. `webcad2d-demo` → pilih **Public** (GitHub Pages gratis untuk repo publik) → **Create repository**.
2. Klik **uploading an existing file** → seret **seluruh isi folder ini** (bukan foldernya) — `index.html`, `config.js`, `.nojekyll`, folder `tutorial/` → **Commit changes**.
   File `.nojekyll` ikut diunggah (file tersembunyi; di Windows aktifkan *View › Hidden items*, di Mac tekan Cmd+Shift+. ). Bila terlewat, buat file kosong bernama `.nojekyll` lewat **Add file › Create new file**.
3. Buka **Settings → Pages** → *Build and deployment* → Source: **Deploy from a branch** → Branch: **main**, folder **/ (root)** → **Save**.
4. Tunggu 1–3 menit, lalu demo tampil di `https://USERNAME.github.io/webcad2d-demo/` (alamatnya tertulis di halaman Settings → Pages).
5. Pasang link itu di halaman produk Mayar, media sosial, atau marketplace sebagai tombol "Coba demo".

**Domain sendiri (opsional):** Settings → Pages → *Custom domain* → isi mis. `demo.domainanda.com`, lalu di pengelola DNS buat record **CNAME** `demo` → `USERNAME.github.io`. Centang *Enforce HTTPS* setelah aktif.

**Memperbarui demo:** unggah ulang `index.html` (dan folder lain bila berubah) ke repo yang sama; GitHub Pages memperbarui otomatis dalam beberapa menit. `config.js` tidak perlu diunggah ulang.

## 3. Mencoba di komputer sebelum diunggah
Klik dua kali `index.html` (Chrome/Edge), atau jalankan server kecil di folder ini: `python -m http.server 8080` lalu buka `http://localhost:8080`.

## 4. Seberapa aman demo ini?
- Mode demo **ditanam saat build**: mengubah `config.js` tidak membuka versi lengkap, dan fungsi simpan/unduh di dalam kode sudah dimatikan (bukan sekadar disembunyikan).
- Kode JavaScript diperkecil (minify) sehingga sulit dibaca dan diubah.
- Tetap perlu diingat: semua aplikasi web yang berjalan di browser bisa dilihat kodenya oleh pengunjung. Demo ini sengaja dibuat **tidak bisa menyimpan dan tidak bisa mengekspor**, sehingga tidak berguna untuk pekerjaan nyata — itu perlindungan utamanya. File versi lengkap hanya ada di zip yang dijual lewat Mayar; jangan unggah zip itu ke GitHub.
