# Handoff Sesi Belajar SEO — Sesi 19
**Tanggal:** 25 Juli 2026
**Topik:** Fase 4 lanjutan — Long-form vs Short-form Content (praktik, opsional), E-E-A-T Signals (Topik 33, lanjutan signifikan)
**Status:** 🔄 Topik 33 belum ditutup, sisanya selesai
**Melanjutkan dari:** handoff-sesi-18-belajar-seo.md (Fase 4: 2/4 tracker, E-E-A-T belum dimulai, Content Refresh blocked)

---

## 1. Foto & Topik 22 — Tetap Ditunda

Di awal sesi, dua item pending (upload foto Ronald, Topik 22 Local Citation) dikonfirmasi ulang masih terblokir: foto belum tersedia, akses/dokumen untuk citation masih terbatas. Dicatat sebagai "ditunda", bukan "gagal" — konsisten dengan prinsip yang sudah berlaku di project ini.

---

## 2. Long-form vs Short-form Content (opsional, tidak ada baris tracker resmi)

Diajarkan lewat analogi 2 warung (menu 20 halaman vs selembar) — panjang konten harus mengikuti kebutuhan intent, bukan angka kata target. Dipraktikkan langsung sebagai content gap analysis pada Artikel #4 (WhatsApp), dibandingkan ke 3 kompetitor riil di Google:

- **Rank #1 — bola.com:** listicle 50 contoh kalimat template, situs portal olahraga (off-niche total). Kemungkinan besar ranking karena otoritas domain raksasa, bukan kualitas konten.
- **Rank #2 — dazo.id:** setelah di-fetch langsung, ternyata JAUH lebih pendek dari Artikel #4 (reading time 5 menit vs 14 menit) — kebalikan dari asumsi awal Ronald. Tapi tetap ada 5 gap konkret yang genuinely hilang dari Artikel #4: segmentasi kontak, kecepatan respons (dengan statistik kompetitor yang TIDAK dipakai karena sumbernya tidak terverifikasi), nuansa grup VIP pelanggan setia, kalender konten mingguan, desain poster promosi.
- **Rank #3 — mokapos.com:** juga lebih pendek dari klaim awal Ronald (4 menit baca), artikel dari 2021 tidak pernah di-update, isinya generik/permukaan. Klaim "kedalaman Artikel #4 lebih unggul" dari Ronald terkonfirmasi benar. Ditemukan statistik dubious ("konversi hingga 110%" dari sumber "Leads360" yang tidak bisa diverifikasi) — dicatat sebagai contoh red flag, jangan dicontoh. Satu nuansa minor ditemukan (sesuaikan bahasa promosi per karakter grup penerima) tapi tidak ditambahkan ke draft karena dianggap low-value untuk konteks ini.

**Pelajaran kunci:** "Panjang bukan proxy buat lengkap." Kesan visual pas scroll manual bisa menipu (banyak gambar/spasi terasa "panjang" padahal teks aslinya pendek) — reading-time metadata dan fetch langsung jauh lebih bisa dipercaya daripada feeling.

**Output:** draft 5 section tambahan dibuat (`draft-tambahan-artikel-4-whatsapp.md`, dikirim sebagai file terpisah sesi ini), lengkap dengan instruksi "sisipkan di" per section, styling tabel warna standar (`#00BFA5`) untuk kalender konten. Diproses Ronald lewat Project Konten & Copywriting, dipaste, dan **live** di Artikel #4. ~878 kata ditambahkan, 0 em dash, internal link tidak berubah (tetap 6).

---

## 3. E-E-A-T Signals (Topik 33) — Lanjutan Signifikan

### Recap konsep (sudah diajarkan sesi sebelumnya)
4 komponen (Experience, Expertise, Authoritativeness, Trust) + audit awal ke onlineumkm.id sudah dibahas sebelum sesi ini. Dua titik lemah teridentifikasi: Authoritativeness (citation belum tuntas) dan Trust (0 review, foto belum ada, 0 klien) — keduanya masih terblokir sesi ini juga.

### Author bio & byline — dieksekusi penuh sesi ini

Ronald kirim screenshot artikel live: byline cuma tampilkan nama tanpa kotak bio, format tanggal salah ("Juni 17, 2026" — urutan Inggris dengan nama bulan Indonesia).

**3 perbaikan dieksekusi:**
1. **Byline diseragamkan** — "Ronald H" (nama tampilan lama) diganti jadi "Ronald Huson" via Pengguna > Profil, otomatis berlaku ke semua artikel sekaligus.
2. **Format tanggal diperbaiki** — bukan masalah Astra/WPCode, murni setting bawaan WordPress: Pengaturan > Umum > Format Tanggal > Sesuaikan > `j F Y`. Hasil: "17 Juni 2026" (dan tanggal lain otomatis ikut format ini).
3. **Author bio box** — dicek dulu apakah Astra Pro terpasang (perlu untuk fitur Author Box bawaan Astra). **Dikonfirmasi via screenshot Plugin: tidak ada Astra Pro** (11 plugin aktif: Elementor, Hostinger AI, Hostinger Reach, Image Optimization, LiteSpeed Cache, Redirection, Site Kit by Google, Tool Hostinger, UpdraftPlus, WPCode Lite, Yoast SEO). Jalur Astra native tidak tersedia, dialihkan ke WPCode.

### Implementasi teknis: WPCode PHP Snippet

Kode PHP dibuat menggunakan filter `the_content` + pengecekan `is_single()`, mengambil `display_name` dan `description` dari profil WordPress penulis, menampilkan kotak styling `#00BFA5` (konsisten dengan CTA Section & tabel artikel) berisi nama, bio, dan link ke `/tentang/`. Karena logikanya self-contained di dalam kode (bukan bergantung ke lokasi Auto Insert tertentu), cukup pakai "Run Everywhere" — otomatis cuma render di halaman artikel.

Draft bio ditulis dan sudah diisi Ronald ke field Info Biografi profil WordPress: jujur, tanpa klaim kredensial yang tidak bisa dibuktikan (prinsip sama dengan larangan pasang schema `AggregateRating` sebelum ada review asli).

**Percobaan pertama gagal tampil.** Diagnosis dilakukan via 3 screenshot yang diminta (profil bio, daftar snippet, detail snippet): bio field terisi benar, kode PHP tersimpan benar sebagai Code Type "PHP Snippet" — tapi toggle statusnya "Inactive". Penyebabnya WPCode secara default menyimpan snippet baru dalam kondisi nonaktif sebagai pengaman. Diaktifkan manual + klik Update.

**Hasil akhir:** kotak "Tentang Penulis" terverifikasi live di Artikel #12 Jakarta (screenshot dikirim Ronald), tampil rapi di antara FAQ dan navigasi Previous/Next. Karena pakai filter global, otomatis berlaku ke **semua 12 artikel sekaligus** tanpa perlu setup ulang per artikel.

### Gap Trust baru ditemukan

Dari eksplorasi author box ini, dua gap baru teridentifikasi dan dicatat ke pending:
1. **Halaman Kontak dan Kebijakan Privasi belum ada sama sekali** di situs (dikonfirmasi Ronald).
2. **Link "Hubungi Kami" di kolom Navigasi footer artikel** kemungkinan mengarah ke halaman yang belum ada (404) — belum dicek, perlu verifikasi setelah Halaman Kontak dibuat.

Karena kedua gap ini belum dieksekusi, **Topik 33 TIDAK ditutup di sesi ini**, tetap 🔄 Sedang Berjalan.

---

## Pelajaran Kunci Sesi Ini

1. **Verifikasi data mengalahkan kesan visual.** Dua kali dalam sesi ini asumsi Ronald soal panjang artikel kompetitor terbukti salah setelah di-fetch langsung dan dicek reading-time-nya. Jangan simpulkan dari scroll cepat.
2. **Statistik dari kompetitor tidak otomatis dipakai.** Dua statistik menarik ditemukan di kompetitor (response time 53%, konversi 110%) dan keduanya SENGAJA tidak dipakai di konten sendiri karena sumbernya tidak bisa diverifikasi — konsisten dengan prinsip anti-fabrikasi data yang sudah berlaku di project ini.
3. **"Sudah dipasang" belum tentu "sudah aktif".** WPCode Lite default menyimpan snippet baru sebagai Inactive — pelajaran teknis baru, perlu ditambahkan ke `aturan-referensi` supaya tidak terulang di snippet berikutnya.
4. **Jangan asumsikan fitur tema tersedia tanpa verifikasi screenshot** — pola yang sama dengan kasus Astra Footer Builder sebelumnya (Bagian 8 aturan-referensi). Kali ini dicek DULU sebelum kasih instruksi (screenshot Plugin), bukan sesudah instruksi gagal.
5. **Satu perbaikan teknis bisa menyelesaikan banyak artikel sekaligus** — author box lewat `the_content` filter menyelesaikan 12 artikel dalam satu snippet, bukan kerja manual per artikel.

---

## Progress Tracker

`progresstrackerbelajar.xlsx`: **tidak berubah**, tetap 31/47 (66%). Topik 33 (E-E-A-T) masih 🔄 belum ditandai selesai karena ada 2 item aksi yang belum dieksekusi (Halaman Kontak, Kebijakan Privasi). Long-form vs Short-form Content tetap tidak tercatat di tracker resmi (opsional, konsisten dengan Competitor Content Audit sesi 18).

Fase 4 (Content SEO & Authority): tetap 2/4 tracker resmi, tapi Topik 33 sekarang jauh lebih maju secara substansi (author bio box selesai) dibanding sebelum sesi ini (belum dimulai sama sekali).

---

## Sesi Berikutnya

**Lanjutan Topik 33 (E-E-A-T):**
1. Buat Halaman Kontak — perlu diputuskan dulu isinya apa (WhatsApp, email, jam operasional, dll)
2. Buat Halaman Kebijakan Privasi — bisa pakai generator dasar lalu disesuaikan, atau ditulis dari nol
3. Setelah kedua halaman jadi, cek link "Hubungi Kami" di footer artikel — arahkan ke Halaman Kontak yang baru
4. Setelah itu semua selesai, Topik 33 baru bisa ditandai ✅ dan Fase 4 naik ke 3/4 tracker

**Setelah 27 Juli (reminder GSC index Pillar):**
- Cek ulang status index Pillar, lanjut evaluasi impresi & CTR kalau sudah terindeks

**Terlewat sesi ini, perlu dicek sesi depan:**
- Cek GSC Artikel #3 GBP — jadwalnya 25 Juli, belum sempat dikerjakan

**Lain-lain yang masih menggantung:**
- Topik 22 — Local Citation Building (masih ditunda, blocker dokumen/akses)
- Artikel #13 & #14 (target 28 Jul–10 Agt)
- Sync GitHub manual (akses tulis masih diblokir)

File project yang perlu diupload ulang: `status-aktif-v2.md` (naik ke v2.24). File ini (`handoff-sesi-19`) untuk arsip GitHub `handoff/`, BUKAN untuk project knowledge — sync manual lewat GitHub web UI kapan sempat, karena akses tulis connector masih diblokir.

---

*Handoff Sesi 19 — 25 Juli 2026.*
