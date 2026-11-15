# CLAUDE.md
# Aturan Kerja Claude untuk Repository Portofolio Andra

Dokumen ini adalah aturan kerja permanen untuk semua sesi Claude yang menyentuh repository ini. Baca seluruh dokumen sebelum memeriksa atau mengubah kode.

## 1. Identitas dan tujuan repository

Repository ini berisi website portofolio pribadi Andra Nooryanto.

Profil yang boleh digunakan:
- Nama: Andra Nooryanto.
- Status: mahasiswa Program Studi Informatika di Universitas Bina Sarana Informatika (UBSI), kampus Karawang.
- Minat: programming, web development, computer networking, dan cyber security.
- Proyek unggulan saat ini: Avenqor.

Jangan mengarang pengalaman kerja, gelar profesional, sertifikasi, klien, jumlah pengguna, jumlah proyek, pencapaian, statistik, atau kemampuan yang belum diberikan atau dikonfirmasi oleh Andra. Jangan mengubah status mahasiswa menjadi profesional berpengalaman.

Repository ini adalah website statis yang menggunakan HTML, CSS, dan JavaScript. Tidak ada framework aplikasi atau proses build yang dibutuhkan untuk struktur yang ada saat ini.

## 2. Aturan paling penting: batas kewenangan Claude

**Claude hanya boleh melakukan tindakan yang secara jelas diminta oleh Andra. Jangan memperluas ruang lingkup pekerjaan berdasarkan inisiatif sendiri.**

Aturan ini wajib dipatuhi:

1. Sebelum mengedit, buat ringkasan singkat tentang file yang akan disentuh dan perubahan yang akan dilakukan jika ruang lingkup permintaan belum sangat jelas.
2. Jika sebuah tindakan tidak disebutkan atau tidak diperlukan secara langsung untuk menyelesaikan permintaan, jangan lakukan tindakan tersebut.
3. Jika tindakan tambahan terlihat berguna, hentikan proses dan tanyakan persetujuan Andra terlebih dahulu.
4. Jangan menganggap diam, konteks percakapan lama, atau instruksi umum "maintain website" sebagai izin untuk melakukan perubahan besar.
5. Jika ada dua interpretasi yang masuk akal dan hasilnya berbeda secara material, tanyakan sebelum memilih.
6. Jangan mengubah, menghapus, memindahkan, mengganti nama, atau menimpa file di luar ruang lingkup tugas.
7. Jangan melakukan refactor besar saat diminta memperbaiki bug kecil. Terapkan perubahan paling kecil yang menyelesaikan masalah.
8. Jangan mengubah konten personal atau klaim faktual jika datanya belum tersedia. Tanyakan kepada Andra.
9. Jangan membuat perubahan pada repository Avenqor. Repository Avenqor hanya boleh dibaca sebagai sumber informasi proyek, kecuali Andra secara eksplisit meminta pekerjaan pada repository tersebut.
10. Persetujuan untuk satu tindakan hanya berlaku untuk tindakan dan ruang lingkup yang disebutkan. Persetujuan itu bukan izin permanen untuk tindakan lain.

### Tindakan yang selalu membutuhkan persetujuan eksplisit

Jangan lakukan hal-hal berikut tanpa perintah atau persetujuan langsung dari Andra:

- Menghapus, memindahkan, atau mengganti nama file maupun folder.
- Mengubah struktur folder atau arsitektur website.
- Menghapus atau mengganti gambar, logo, font, ikon, atau aset lain.
- Mengubah identitas, teks profil, bahasa website, atau klaim tentang Andra.
- Mengubah desain utama, tema warna, layout global, atau sistem navigasi.
- Menambahkan framework, library, dependency, package manager, build system, analytics, tracker, atau layanan pihak ketiga.
- Mengubah domain, DNS, konfigurasi hosting, GitHub Pages, file CNAME, atau workflow deployment.
- Mengubah konfigurasi repository, permission, secret, atau pengaturan keamanan.
- Mengganti branch, membuat branch, merge, rebase, cherry-pick, atau memindahkan pekerjaan antar-branch.
- Membuat commit, push, pull request, release, tag, atau melakukan deploy.
- Menjalankan perintah yang berpotensi menghapus atau menimpa data.
- Melakukan perubahan tambahan yang tidak diminta walaupun menurut Claude perubahan itu lebih baik.

Membaca file, memeriksa struktur, menjalankan pemeriksaan lokal yang aman, dan membuat laporan audit boleh dilakukan untuk memahami tugas. Pemeriksaan tersebut tidak memberi izin untuk mengubah file.

Jika alat yang digunakan otomatis akan melakukan tindakan di luar kewenangan ini, jangan lanjutkan. Jelaskan keterbatasannya dan minta persetujuan atau instruksi yang sesuai.

## 3. Struktur website yang perlu dipertahankan

Struktur yang saat ini digunakan:

```text
Portopolio/
├── index.html
├── 404.html
├── README.md
├── LICENSE
├── CNAME                         # pertahankan jika ada
├── assets/
│   └── images/
│       └── avenqor/
│           ├── logo.png
│           ├── dashboard.png
│           ├── task-details.png
│           ├── kanban-board.png
│           ├── calendar.png
│           ├── documents.png
│           └── backup-restore.png
└── projects/
    └── avenqor/
        └── index.html
```

Struktur aktual dapat berubah jika Andra memberi instruksi. Selalu periksa kondisi repository dan branch saat ini. Jangan membuat asumsi bahwa file yang tercantum di dokumen ini pasti masih ada.

Fungsi file:
- `index.html`: halaman utama, profil, skills, dan daftar proyek unggulan.
- `projects/avenqor/index.html`: halaman detail/case study Avenqor.
- `404.html`: halaman error 404 untuk website statis/GitHub Pages.
- `assets/images/avenqor/`: logo dan screenshot aplikasi Avenqor yang digunakan portofolio.
- `README.md`: dokumentasi repository portofolio.
- `CNAME`: konfigurasi domain kustom jika digunakan.
- `LICENSE`: lisensi repository.

Jangan menghapus file hanya karena file tersebut tampak tidak digunakan. Telusuri referensi HTML, CSS, JavaScript, konfigurasi hosting, dan tautan terlebih dahulu. File yang tidak direferensikan belum tentu tidak dibutuhkan.

## 4. Desain dan identitas visual yang harus dipertahankan

Pertahankan karakter visual website kecuali Andra secara eksplisit meminta perubahan desain.

Design system saat ini:
- Background utama: hitam, `#000000`.
- Accent utama: Tiffany/cyan, `#81D8D0`, disimpan sebagai CSS variable `--tiffany`.
- Teks utama: putih.
- Teks sekunder: putih dengan opacity.
- Font utama: Inter, weight 300 sampai 600.
- Komponen menggunakan glassmorphism: background transparan, blur, dan border tipis.
- Animasi menggunakan transisi yang halus, termasuk fade-up dan shimmer skeleton.
- Layout responsif untuk mobile dan desktop.
- Navigasi berbentuk pill/floating navigation.
- Radius komponen dominan membulat.
- Gaya keseluruhan minimal, gelap, rapi, dan tidak ramai.

Jangan mengganti tema menjadi terang, mengubah accent color, menghapus efek glass, atau mengganti font global tanpa instruksi.

Jangan memaksakan tema website ke tampilan aplikasi Avenqor. Tampilan Avenqor di screenshot memang menggunakan tema terang dan accent indigo. Screenshot harus ditampilkan sebagaimana aslinya, jangan diedit atau diberi filter kecuali diminta.

## 5. Konten dan aturan penulisan

- Bahasa konten website saat ini adalah bahasa Inggris. Pertahankan bahasa Inggris kecuali Andra meminta bahasa lain.
- Gunakan kalimat yang jelas, ringkas, profesional, dan tidak berlebihan.
- Jangan mengubah fakta menjadi klaim pemasaran yang tidak terbukti.
- Jangan menampilkan statistik seperti "10+ projects", "6 years experience", klien, atau pencapaian jika tidak ada data yang diberikan.
- Bedakan dengan jelas antara fitur yang sudah tersedia, fitur yang sedang dikerjakan, dan rencana masa depan.
- Jangan menyebut fitur roadmap Avenqor sebagai fitur yang sudah tersedia.
- Jangan menyebut sinkronisasi otomatis antara Windows dan Android. Kedua versi Avenqor memiliki data lokal yang terpisah.
- Jangan mengklaim bahwa Avenqor membutuhkan akun atau koneksi internet. Avenqor dirancang local-first dan fitur aplikasinya berjalan offline tanpa akun.
- Jika informasi teknis terbaru diperlukan, baca README dan dokumentasi Avenqor yang relevan. Jangan menebak versi, teknologi, atau status fitur.
- Jangan menambahkan email, nomor telepon, akun sosial, lokasi rinci, atau informasi pribadi lain yang belum diberikan.

## 6. Informasi Avenqor yang menjadi acuan

Untuk halaman proyek Avenqor, gunakan repository sumber:
https://github.com/andra-gs/Avenqor

README Avenqor adalah referensi awal, tetapi periksa dokumentasi relevan jika klaim yang akan ditulis membutuhkan detail tambahan.

Fakta proyek yang telah didokumentasikan:
- Avenqor adalah local-first project manager untuk Windows dan Android.
- Aplikasi mengatur Workspace, Project, Tasks, deadlines, checklist, notes, labels, documents, dan activity.
- Ada Kanban board dengan kolom To Do, In Progress, Review, dan Done.
- Ada calendar, My Tasks, pencarian, filter, dan reminder Windows saat aplikasi sedang terbuka.
- Ada fitur backup dan restore.
- Data disimpan secara lokal menggunakan SQLite.
- Aplikasi tidak membutuhkan akun dan tidak melakukan network request untuk fitur aplikasinya.
- Data Windows dan Android terpisah dan tidak tersinkron otomatis.
- Technology stack yang tercantum di README: Tauri 2, Rust, React 19, TypeScript 6, Vite, React Router, Tailwind CSS 4, dan SQLite.

Periksa README atau dokumentasi sumber lagi sebelum mengubah detail yang bisa berubah, seperti versi aplikasi, platform, fitur, status roadmap, dan teknologi.

## 7. Aturan aset gambar

- Simpan gambar website di bawah `assets/images/`.
- Kelompokkan aset berdasarkan proyek atau kegunaannya. Contoh: `assets/images/avenqor/`.
- Gunakan nama file huruf kecil, deskriptif, dan kebab-case.
- Hindari nama seperti `image1.png`, `final-final.png`, atau nama dengan spasi.
- Jangan mengganti screenshot aplikasi dengan ilustrasi buatan atau gambar stok tanpa persetujuan Andra.
- Jangan mengubah isi, crop, kompres, atau mengonversi gambar yang ada tanpa perintah.
- Jika menambahkan gambar baru, pastikan sumber dan hak penggunaannya jelas.
- Setelah memindahkan atau mengganti nama aset dengan izin Andra, perbarui seluruh referensi yang relevan.
- Periksa relative path dari lokasi HTML yang menggunakan aset tersebut. Halaman di `projects/avenqor/index.html` menggunakan jalur relatif ke root seperti `../../assets/images/avenqor/dashboard.png`.
- Pastikan gambar berhasil dimuat setelah perubahan.

## 8. Area yang boleh diperbarui ketika diminta

Daftar berikut menjelaskan area yang dapat dikerjakan. Daftar ini bukan izin untuk mengubahnya kapan saja. Perubahan tetap harus sesuai dengan permintaan spesifik Andra.

### Konten
- Deskripsi profil, about, skills, pendidikan, dan minat.
- Nama, deskripsi, screenshot, teknologi, serta tautan proyek.
- Judul halaman, meta description, dan konten README.
- Teks navigasi, tombol, footer, dan halaman 404.

### UI dan styling
- Detail CSS pada section tertentu.
- Responsivitas dan layout halaman.
- Spacing, typography, alignment, hover state, dan animasi.
- Perbaikan visual tanpa mengubah identitas desain utama.

### Fungsionalitas
- Tautan internal dan eksternal.
- Navigasi antarhalaman.
- Interaksi JavaScript sederhana.
- Validasi link dan asset.
- Accessibility dasar dan semantic HTML.
- Perbaikan bug yang secara langsung berkaitan dengan permintaan.

### Dokumentasi dan struktur
- README dan dokumentasi maintenance.
- Folder aset baru atau halaman proyek baru hanya jika diminta.
- Penghapusan file hanya setelah Andra secara eksplisit menyebutkan file atau menyetujui daftar penghapusan.

## 9. Alur kerja wajib

Ikuti urutan ini untuk setiap tugas.

### Langkah 1: Pahami permintaan
- Identifikasi hasil akhir yang diminta.
- Tentukan halaman dan file yang kemungkinan terlibat.
- Bedakan kebutuhan wajib dari ide tambahan.
- Tanyakan jika ada informasi penting yang belum jelas.

### Langkah 2: Audit sebelum mengedit
- Baca CLAUDE.md.
- Periksa branch aktif dan status working tree.
- Baca file yang relevan secara utuh, jangan hanya mengandalkan cuplikan.
- Telusuri link, asset path, CSS selector, dan JavaScript yang berkaitan.
- Periksa apakah file yang akan disentuh memiliki perubahan lokal yang belum disimpan.
- Jangan menimpa perubahan yang bukan milik tugas saat ini.

### Langkah 3: Konfirmasi ruang lingkup
Untuk perubahan yang jelas dan terbatas, jelaskan file yang akan diubah dan lanjutkan hanya dalam ruang lingkup permintaan.
Untuk perubahan yang berisiko, ambigu, destruktif, atau melibatkan beberapa pilihan, minta persetujuan eksplisit sebelum bertindak.

### Langkah 4: Implementasi
- Ubah sesedikit mungkin file.
- Gunakan pola dan gaya kode yang sudah ada.
- Hindari duplikasi yang tidak diperlukan.
- Jangan melakukan refactor tidak terkait.
- Jangan menambahkan dependency untuk masalah yang dapat diselesaikan dengan HTML, CSS, atau JavaScript yang sudah ada.
- Jangan mengubah file lain untuk "sekalian merapikan".

### Langkah 5: Verifikasi
Sesuai jenis tugas, periksa:
- Syntax HTML, CSS, dan JavaScript.
- Link internal dan eksternal yang diubah.
- Relative path untuk gambar, CSS, dan halaman.
- Tampilan responsif pada ukuran mobile dan desktop.
- Console error dan network error jika browser/devtools tersedia.
- Perilaku tombol dan interaksi yang disentuh.
- Pastikan perubahan tidak menghapus konten atau fungsi yang tidak terkait.

Jangan mengklaim pengujian visual/browser sudah dilakukan jika memang tidak dilakukan. Jelaskan batas pengujian secara jujur.

### Langkah 6: Laporan
Setelah tugas selesai, berikan ringkasan:
1. File yang diubah.
2. Apa yang diubah dan alasannya.
3. Pemeriksaan yang dilakukan dan hasilnya.
4. Masalah yang belum dapat diverifikasi.
5. Perubahan tambahan yang disarankan, jika ada. Jangan menerapkan saran itu tanpa persetujuan.

## 10. Standar implementasi

- Pertahankan HTML semantik dan struktur heading yang masuk akal.
- Gunakan nama class yang mengikuti konvensi yang sudah ada.
- Jangan menghapus accessibility label, alt text, atau atribut penting.
- Gunakan `rel="noopener noreferrer"` untuk tautan eksternal dengan `target="_blank"`.
- Jangan meninggalkan tautan placeholder `href="#"` untuk aksi yang seolah-olah berfungsi.
- Jangan mengubah relative path tanpa menghitung lokasi file tujuan.
- Jangan memasukkan secret, token, password, atau credential ke source code.
- Jangan menambahkan tracking, telemetry, analytics, cookie, atau pengumpulan data pengguna.
- Hindari inline script/style baru jika pola yang sudah ada menyediakan tempat yang lebih tepat, kecuali perubahan kecil memang paling aman dilakukan secara lokal.

## 11. Git dan deployment

- Jangan berpindah branch tanpa perintah.
- Jangan membuat commit, push, pull request, merge, tag, release, atau deploy tanpa instruksi eksplisit.
- Jangan mengubah konfigurasi GitHub Pages, domain, DNS, CNAME, atau workflow.
- Jangan menjalankan perintah Git yang destruktif seperti `reset --hard`, `clean -fd`, atau force push.
- Jangan menghapus atau menimpa perubahan lokal yang belum di-commit.
- Sebelum tindakan Git yang telah diizinkan, tampilkan branch aktif dan perubahan yang akan masuk.
- Jika Andra meminta commit atau push, batasi hanya pada file dan branch yang telah disetujui.

## 12. Jika menemukan masalah di luar ruang lingkup

Jangan memperbaikinya secara otomatis.

Laporkan dengan format:
- Temuan: apa masalahnya.
- Dampak: apa yang mungkin terpengaruh.
- Usulan: tindakan yang disarankan.
- Persetujuan yang diperlukan: perubahan spesifik yang perlu diizinkan.

Lanjutkan pekerjaan utama jika pekerjaan itu tetap aman dan tidak bergantung pada masalah tersebut. Jika masalah tersebut membuat tugas utama tidak aman, berhenti dan tanyakan.

## 13. Aturan akhir

**Jangan pernah menafsirkan permintaan Andra sebagai izin untuk mengambil keputusan produk, desain, konten, struktur, keamanan, atau deployment di luar ruang lingkup yang disebutkan.**

Lebih baik berhenti dan bertanya daripada melakukan perubahan yang tidak diminta. Jangan menganggap "best practice", "cleanup", "optimization", atau "improvement" sebagai alasan untuk melewati aturan persetujuan ini.


## 14. Acuan desain dari template awal portofolio

Website ini awalnya dibuat berdasarkan brief desain "Adrian Dabrowski - Web Designer". Brief tersebut adalah referensi visual dan teknis, bukan sumber identitas atau konten yang boleh dipulihkan.

Gunakan bagian yang masih relevan di bawah ini untuk menjaga karakter visual website. Implementasi aktual pada repository adalah acuan utama jika terdapat perbedaan dengan deskripsi template lama.

### 14.1 Identitas visual inti

Pertahankan detail berikut saat mengerjakan perubahan desain:

- Background utama `#000000`.
- Warna accent wajib `#81D8D0` untuk highlight, glow, pulse, dan selection.
- Teks utama putih. Teks sekunder menggunakan putih dengan opacity.
- Font Inter dari Google Fonts dengan weight 300, 400, 500, dan 600.
- CSS variable utama: `--tiffany: #81D8D0`.
- Selection: `::selection { background-color: #81D8D0; color: #000000; }`.
- Kurva easing utama: `cubic-bezier(0.16, 1, 0.3, 1)`.
- Gaya visual minimal, gelap, rounded, dan menggunakan glassmorphism.

Jangan mengganti nilai accent dengan warna yang hanya mirip. Gunakan nilai hex yang tepat.

### 14.2 Glassmorphism

Glassmorphism adalah bagian inti dari identitas desain.

Class utama:
```css
.ios-glass {
  background: rgba(30, 30, 30, 0.4);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.08);
}
```

Ketentuan:
- Pertahankan karakter transparan, blur 20px, dan border tipis.
- Gunakan `.ios-glass` untuk kartu dan elemen glass sesuai pola yang sudah ada.
- Jangan mengganti glassmorphism dengan solid cards atau shadow-heavy cards tanpa instruksi.
- Periksa kontras teks setelah mengubah opacity atau background.

### 14.3 Background layer dan stacking

Pertahankan background dekoratif di belakang konten:

- Background layer memakai `position: fixed`, memenuhi viewport, dan `z-index: 0`.
- Blob kiri atas berukuran 600px, berwarna `#81D8D0`, opacity 0.07, blur 120px, dan `mix-blend-mode: screen`.
- Blob kanan bawah berukuran 500px, menggunakan biru gelap, opacity 0.1, blur 120px, dan `mix-blend-mode: screen`.
- Navigasi fixed berada di atas dengan `z-index: 50`.
- Konten utama berada di atas background dengan `z-index: 10`.
- Elemen dekoratif dan tombol overlay harus tetap berada pada stacking context yang benar.

Jangan menghapus `mix-blend-mode: screen` atau mengubah stacking context tanpa memahami dampaknya.

### 14.4 Scrollbar dan responsive layout

Perilaku scrolling merupakan bagian dari desain awal:

- Smooth scrolling tetap aktif.
- Scrollbar disembunyikan menggunakan `scrollbar-width: none`, `-ms-overflow-style: none`, dan `::-webkit-scrollbar { width: 0px; }`.
- Jangan menonaktifkan kemampuan scrolling hanya untuk menyembunyikan scrollbar.

Susunan Hero memiliki aturan khusus:
- Pada mobile, widget/profile grid muncul sebelum hero text.
- Implementasi saat ini menggunakan `.hero-widgets { order: 1; }` dan `.hero-text { order: 2; }`.
- Pada desktop, susunannya berubah menjadi hero text di kiri dan widget grid di kanan.
- Desktop menggunakan grid 12 kolom, hero text span 7 kolom dan widget grid span 5 kolom.
- Widget grid memiliki dua kolom.
- Jangan membalik urutan mobile dan desktop secara tidak sengaja.

Pertahankan responsive behavior pada breakpoint yang sudah digunakan. Jika mengubah breakpoint atau urutan, periksa kembali mobile dan desktop.

### 14.5 Hero, widget, dan interaksi visual

Pertahankan pola desain berikut selama masih digunakan:

- Navigasi floating berbentuk pill, fixed di bagian atas, dan terpusat.
- Availability indicator memakai pulse/ping berwarna `#81D8D0`.
- Heading besar memakai gradient putih ke putih transparan, tracking rapat, dan line-height yang sesuai.
- Profile card memiliki avatar bulat dan Tiffany glow.
- Toggle bergaya iOS menggunakan pola checkbox dan label.
- Toggle "Learning Mode" pada halaman utama adalah elemen visual. Jangan menambahkan fungsi pergantian tema atau menghubungkannya dengan dark mode tanpa instruksi.
- Widget, tombol, dan social links harus mempertahankan ukuran serta alignment responsif.

### 14.6 Animasi dan transisi

Pertahankan karakter motion yang halus:

- `fadeUp`: dari opacity 0 dan translateY(20px) scale(0.98) menjadi opacity 1 dan posisi normal.
- Easing utama: `cubic-bezier(0.16, 1, 0.3, 1)`.
- `spin-slow` pada elemen yang memang membutuhkan rotasi menggunakan durasi 10 detik dan linear timing.
- Pulse availability menggunakan animasi ping.
- Skeleton shimmer hanya tampil selama loading sesuai mekanisme halaman.
- Card transitions menggunakan durasi sekitar 300ms sampai 500ms sesuai komponen.
- Hover visual pada thumbnail boleh menggunakan scale ringan seperti scale(1.03).

Jangan menghapus atau mengganti animasi global hanya untuk menyelesaikan perubahan kecil pada satu komponen. Hindari menambahkan animasi yang mengganggu aksesibilitas atau performa.

### 14.7 Thumbnail proyek dan media

Ada dua jenis media yang harus dibedakan.

**Thumbnail pada halaman utama:**
- Prinsip desain awal menggunakan CSS-generated visualizer, bukan stock photography.
- Bentuk visual dapat dibuat dari gradient, border, rounded panels, line visualizers, dan abstract UI shapes.
- Thumbnail Avenqor saat ini menggunakan visual CSS pada homepage.
- Jika membuat thumbnail proyek lain, gunakan visual CSS sesuai karakter desain tersebut kecuali Andra meminta penggunaan gambar.

**Media pada halaman detail Avenqor:**
- Gunakan screenshot asli aplikasi Avenqor yang tersimpan di `assets/images/avenqor/`.
- Screenshot menunjukkan interface aplikasi yang sebenarnya dan tidak boleh diganti dengan stock images atau mockup rekaan tanpa instruksi.
- Jangan mengubah crop, isi, warna, atau rasio gambar tanpa instruksi.
- Pertahankan perbedaan tema: website portofolio menggunakan dark glassmorphism, sedangkan aplikasi Avenqor menggunakan light theme dan indigo accent. Jangan mengubah screenshot agar mengikuti warna website.

### 14.8 Struktur section halaman utama

Pertahankan pola layout halaman utama yang sedang digunakan:

- Navigation: pill navigation untuk menuju section dan contact.
- Hero: intro pribadi, CTA, social link, dan widget grid.
- About: deskripsi Andra dan informasi latar belakang.
- Skills: tiga kartu berbentuk grid untuk Web Development, Programming, serta Networking & Cyber Security.
- Featured Project: saat ini hanya Avenqor. Kartu membuka halaman case study internal, bukan langsung membuka repository GitHub.
- Footer: identitas Andra dan tautan yang benar-benar tersedia.

Template lama menggunakan judul "What I Do" dan "Selected Work". Konten yang sekarang berlaku menggunakan "What I'm Learning" dan "Featured Project". Jangan mengembalikan judul, daftar proyek, label, atau teks lama kecuali Andra meminta.

### 14.9 Icon system dan dependency

- Icon system saat ini menggunakan Lucide dari `https://unpkg.com/lucide@latest`.
- Icon dipanggil melalui atribut `data-lucide` dan dirender dengan `lucide.createIcons()`.
- Pertahankan inisialisasi icon setelah konten dinamis dirender.
- Gunakan icon yang sesuai dan tersedia pada Lucide.
- Jangan mengganti icon system atau menambahkan library icon lain tanpa persetujuan.

Brief awal menyebut Tailwind CSS CDN, tetapi implementasi repository saat ini menggunakan CSS custom/native. Jangan menambahkan `https://cdn.tailwindcss.com`, konfigurasi Tailwind, build process, atau dependency Tailwind hanya untuk mengikuti brief lama. Penambahan tersebut mengubah stack dan membutuhkan izin Andra.

### 14.10 Bagian template lama yang tidak boleh dipulihkan otomatis

Berikut adalah konten demo dari template awal, bukan spesifikasi konten website saat ini:

- Nama Adrian Dabrowski dan profesi Web Designer.
- Klaim "85+ Projects Shipped".
- Badge "Available for new projects".
- Statistik klien, tahun pengalaman, dan produk yang diakuisisi.
- Social link Dribbble, Twitter, dan LinkedIn yang tidak dikonfirmasi.
- Layanan Visual Identity, Websites & Stores, dan SEO Optimization.
- Project demo Lumina Finance, Zenith AI, Chronos Mobile, dan Structure Inc.
- Copy "Designed in California".
- Alamat email demo Adrian.

Jangan mengembalikan salah satu item di atas. Pertahankan konten Andra yang sudah dikonfirmasi dan proyek aktual yang tercantum di repository.

### 14.11 Urutan prioritas jika terdapat konflik

Jika ada perbedaan antara brief desain awal, CLAUDE.md, dan implementasi terbaru, gunakan urutan prioritas berikut:

1. Instruksi terbaru dan eksplisit dari Andra.
2. Aturan batas kewenangan pada bagian 2 dokumen ini.
3. Konten dan struktur aktual pada branch yang sedang dikerjakan.
4. Design system aktual pada file HTML/CSS.
5. Poin template awal yang masih relevan pada bagian 14 ini.

Template awal tidak boleh digunakan untuk membatalkan perubahan konten, identitas, atau struktur yang sudah disetujui Andra.

Jika konflik tidak dapat diselesaikan dengan urutan prioritas ini, jangan menebak. Tanyakan kepada Andra sebelum mengubah file.
