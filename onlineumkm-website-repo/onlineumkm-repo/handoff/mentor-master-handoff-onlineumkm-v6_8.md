# Mentor Operasional OnlineUMKM.id — Master Handoff Status, Sistem & Roadmap
# Mentor Operasional OnlineUMKM.id — Master Handoff Status, Sistem & Roadmap
**Versi:** Master v6.8
**Dibuat:** 1 Juni 2026
**Diperbarui:** 9 Juli 2026 (Sesi 22 — Ronald konfirmasi CTA Section berwarna sudah terpasang di Artikel #8, #9, #10, menggantikan soft CTA teks lama. Semua 10 artikel terbit sekarang konsisten pakai CTA Section. Drift proses dari sesi sebelumnya resmi ditutup.)
**Menggantikan:** v6.7
**Cakupan:** Status lengkap website, artikel, sistem Claude, semua project, roadmap konten, dan pengingat pola pikir
**Cakupan:** Status lengkap website, artikel, sistem Claude, semua project, roadmap konten, dan pengingat pola pikir

---

## PETUNJUK PENGGUNAAN FILE INI

File ini adalah satu-satunya referensi yang perlu Claude baca di awal setiap sesi.
Berisi seluruh konteks bisnis, status terkini, arsitektur teknis, dan roadmap.
Tidak perlu baca file lama.

---

## BAGIAN 1: PROFIL BISNIS & IDENTITAS

### Pemilik
- **Nama:** Ronald Huson
- **Usia:** 45 tahun
- **Lokasi:** Medan, Sumatera Utara
- **Catatan operasional (20 Jun 2026):** Saat ini Ronald sedang di luar negeri. Janji temu/pertemuan langsung tidak bisa dilakukan sampai ±2 tahun ke depan — relevan untuk setting GBP (opsi "janji temu online" sengaja diset Tidak) dan ekspektasi timeline kerja klien ke depan. Pekerjaan jasa (website, SEO) tetap berjalan remote/online seperti biasa.
- **Pekerjaan utama:** Data entry & customer service (shift panjang, rotating pagi/malam)
- **Waktu tersedia untuk bisnis:** Terbatas — di sela-sela shift kerja
- **Cara belajar terbaik:** Contoh konkret, perbandingan, analogi. Langkah demi langkah.
- **Claude plan:** Pro ($20/bulan) — gunakan Sonnet sebagai default; Opus hanya untuk analisis sangat kompleks (lihat Bagian 8)

### Bisnis
- **Nama:** Online UMKM
- **Domain:** onlineumkm.id *(bukan .com)*
- **Tagline:** Bantu UMKM Indonesia Ditemukan di Google
- **WhatsApp:** +6287791808667
- **Status:** Fase persiapan — **belum ada klien aktif**

### Layanan yang Ditawarkan
1. Pembuatan website WordPress (company profile, landing page, toko online, biro jasa)
2. Jasa SEO (audit teknis, riset keyword, optimasi GBP, laporan bulanan)
3. Jasa Setup & Maintenance SaaS untuk UMKM

### Target Klien
- UMKM dan usaha kecil lokal
- Toko online / e-commerce
- Startup dan bisnis baru
- Biro jasa lokal (pengurusan izin, pajak, dll)

### Cara Berkomunikasi dengan Ronald
- Gaya semi-formal — seperti mentor sekaligus teman
- Bahasa Indonesia (default)
- Teknis → jawaban singkat dan langsung
- Strategi/bisnis → jawaban lengkap dan menyeluruh
- Contoh konkret dan angka lebih berguna dari teori

---

## BAGIAN 2: STATUS WEBSITE KESELURUHAN (14 Juni 2026)

| Komponen | Status |
|---|---|
| Homepage live | ✅ |
| Blog section — auto-update via REST API | ✅ Aktif (dioptimasi dengan _fields parameter) |
| Halaman Tentang Kami `/tentang/` | ✅ Live — bio terpasang, internal links aktif |
| Foto profil Ronald di Tentang Kami | ⚠️ Belum diupload |
| Plugin Redirection | ✅ Terpasang dan aktif |
| Yoast Homepage — tab SEO | ✅ HIJAU |
| Yoast Homepage — tab Keterbacaan | 🟠 Oranye |
| Yoast Blog `/blog/` — tab SEO | 🔴 Merah (normal untuk posts archive) |
| Yoast Tentang Kami — skor SEO | 🟢 Hijau |
| Yoast Tentang Kami — tab Keterbacaan | 🔴 Merah |
| 10 Skills Claude | ✅ Semua aktif |
| 5 Projects Claude | ✅ Semua aktif |
| LiteSpeed Cache — CSS Async (QUIC.cloud) | ✅ AKTIF — render-blocking turun dari 2.020 ms ke 600 ms |
| LiteSpeed Cache — JS Defer | ❌ NONAKTIF — tidak kompatibel Elementor (TBT naik 6x) |
| LiteSpeed Cache — TTL Publik | ✅ 604800 (1 minggu) |
| LiteSpeed Cache — TTL REST | ✅ 604800 (1 minggu) — REST API cache aktif |
| Google Tag Manager | ✅ Aktif — GA4 (G-0MMKSRC1K4), 13 halaman |
| Homepage — Hamburger menu mobile | ✅ Fixed ulang 19 Jun 2026 — sempat regresi karena diedit lewat widget Elementor yang salah (lihat Bagian 13a), sekarang dikonfirmasi live di widget HTML yang benar |
| GitHub repo | ✅ Aktif — tersync ke Project Website onlineumkm.id, struktur: articles/, homepage/ (main-block.html, fix-script.html), pages/tentang.html (baru 19 Jun), notes/, handoff/ |
| Sitemap (`sitemap_index.xml`) | ✅ 11 URL (7 post + 2 page + 2 category) — turun dari 31, tag taxonomy di-noindex 14 Jun 2026 |
| robots.txt | ✅ Sehat — `Disallow:` kosong (semua boleh dirayapi), Sitemap terdaftar |
| Canonical tags | ✅ Sehat — self-referencing otomatis via Yoast, 0 duplicate/canonical issue di GSC (audit 15 Jun 2026) |
| Redirect `/blog-umkm/` → `/blog/` | ✅ 301 via plugin Redirection — dieksekusi & diverifikasi 15 Jun 2026 |
| GSC Page Indexing — isu coverage | ✅ 5 temuan (404, redirect, crawled-not-indexed, dll) dianalisis 15 Jun 2026, semua resolved/normal |
| Schema markup artikel (Rich Results Test) | ✅ Article, Breadcrumb, FAQ — 3/3 valid (FAQ rich result sudah deprecated Google, schema tetap dipertahankan) |
| Schema markup homepage (Rich Results Test) | ✅ Breadcrumb — 1/1 valid (Organization/WebSite tidak tercover tool ini by design, normal) |
| Klien aktif | ❌ Belum ada |

### Detail Yoast Homepage (FINAL — tidak perlu dioptimasi lagi)

| Item | Status |
|---|---|
| Tautan ke luar | ✅ Hijau |
| Frasa kunci dalam atribut alt gambar | ✅ Hijau |
| Gambar | ✅ Hijau |
| Tautan internal | ✅ Hijau |
| Kepadatan frasa kunci | ✅ Hijau (8 kali) |
| Frasa kunci dalam subjudul | ✅ Hijau |
| Frasa kunci di awal | 🔴 PERMANENT — WordPress limitation |
| Kata transisi | 🔴 PERMANENT — WordPress limitation |

**⚠️ Jangan optimasi 2 item merah di atas lagi — sudah final.**

---

## BAGIAN 2a: STATUS GOOGLE BUSINESS PROFILE (20 Juni 2026 — Topik 20)

**Nama profil publik:** Online UMKM *(bukan "OnlineUMKM.id" — domain dengan ".id" terdeteksi sebagai URL oleh validator Google, lihat Bagian 13)*

| Item | Status |
|---|---|
| Tipe profil | ✅ Service Area Business — alamat tersembunyi dari publik |
| Alamat (internal, tidak publik) | Alamat rumah ibu Ronald — asli, dipakai untuk syarat verifikasi saja |
| Area layanan | ✅ Medan (sempat salah-setting mencakup "Indonesia" nasional, sudah dipangkas) |
| Kategori utama | Layanan pemasaran internet di Medan, Sumatera Utara |
| Jam buka | ✅ Disamakan dengan jam aktivitas WhatsApp Business |
| Telepon | 0877-9180-8667 (= +6287791808667, sama dengan WhatsApp bisnis) |
| Deskripsi bisnis | ✅ Tersimpan — 692/750 karakter |
| Daftar layanan | ✅ 3 kategori lengkap (lihat detail Topik 20 di Bagian 16) |
| Opsi janji temu online | Tidak — sesuai kondisi Ronald saat ini (di luar negeri) |
| Verifikasi | ✅ Aktif, tidak diminta verifikasi ulang setelah ganti ke SAB |
| Foto bisnis | ⏳ Belum — menunggu materi otentik (belum ada klien) |
| Kredit iklan Google Ads Rp 3.000.000 | ⏳ Dilewati — revisit saat masuk topik Google Ads di kurikulum |

**Cara akses menu Layanan:** BUKAN di panel "Informasi Bisnis" (tab Tentang/Kontak/Lokasi/Jam buka/Lainnya) — ada di menu terpisah **"Edit layanan"** di dashboard utama profil bisnis.

---

## BAGIAN 3: STATUS ARTIKEL (9 Juli 2026 — update v6.6)

**Total terbit: 10 artikel**
**Catatan CTA (9 Jul 2026):** CTA Section berwarna sudah terpasang di semua 10 artikel — #1–7 sejak Juni, #8–10 dikonfirmasi Ronald hari ini. Sistem CTA sekarang konsisten di seluruh artikel.

| # | Judul | Slug | Terbit | Yoast SEO | Yoast Baca |
|---|---|---|---|---|---|
| 1 | Cara Promosi Warung Makan Online: Panduan Lengkap untuk UMKM | `/cara-promosi-warung-makan-online/` | 9 Mei 2026 | ✅ | ✅ |
| 2 | Kenapa Warung Makan Sepi Padahal Enak? Ini Jawabannya | `/kenapa-warung-makan-sepi-padahal-enak/` | 22 Mei 2026 | ✅ | ✅ |
| 3 | Cara Daftar Google Business Profile untuk Warung Makan, Gratis dan Mudah | `/cara-daftar-google-business-profile/` | 25 Mei 2026 | ✅ | ✅ |
| 4 | Cara Promosi Warung Makan lewat WhatsApp yang Efektif dan Tidak Ganggu | `/cara-promosi-warung-makan-lewat-whatsapp/` | 29 Mei 2026 | ✅ | ✅ |
| 5 | Cara Daftar GoFood untuk Warung Makan: Panduan dari Nol | `/cara-daftar-gofood/` | 3 Jun 2026 | ✅ | ✅ |
| 6 | Cara Foto Makanan Pakai HP biar Terlihat Enak dan Bikin Orang Langsung Pesan | `/cara-foto-makanan-pakai-hp/` | 9 Jun 2026 | ✅ | ✅ |
| 7 | 30 Template Caption Instagram Warung Makan Siap Pakai | `/template-caption-instagram-warung-makan/` | 17 Jun 2026 | ✅ | 🟠 |
| 8 | SEO Warung Makan Lokal Medan: Cara Naik Peringkat di Google Maps | `/seo-warung-makan-lokal-medan/` | 25 Jun 2026 | ✅ | ✅ |
| 9 | Promosi Online Warung Makan Medan: Panduan Lengkap | `/promosi-online-warung-makan-medan/` | 1 Jul 2026 | ✅ | — |
| 10 | Promosi Online Warung Makan Surabaya: Panduan Lengkap | `/promosi-online-warung-makan-surabaya/` | 9 Jul 2026 | ✅ | — |

> **Catatan mulai artikel #6:** Yoast hanya berlaku untuk SEO title, slug, dan meta description.
> Isi artikel mengikuti standar Google dan Master Prompt Artikel Kelas Dunia v1.2.

> **ℹ️ Redirect Artikel #2 — TERPECAHKAN (Topik 17, 16 Jun 2026):** Slug `/kenapa-warung-makan-sepi-padahal-enak/` adalah slug resmi (post ID 129, Telah Terbit). URL `/kenapa-warung-makan-sepi/` adalah redirect otomatis ke slug ini. Sumber redirect: **WordPress `_wp_old_slug`** (fitur core bawaan, bukan plugin Redirection, bukan Yoast Redirects). Verifikasi whatsmydns.net: 1 hop bersih (301 → 200), tidak ada chain. Tidak perlu tindakan lebih lanjut.

### Artikel #1 — Pillar Page
URL: `https://onlineumkm.id/cara-promosi-warung-makan-online/`
**Semua artikel baru wajib internal link ke pillar page ini.**
**Update 10 Juni 2026:** Paragraf GoFood dan kalimat Facebook/TikTok sudah ditambahkan.
**Catatan heading (audit 11 Jun):** Over-optimization parah (keyword di 9 heading), H4 berlebihan, heading generic, em dash & emoji di heading. Semua ditahan sampai data GSC tersedia.
**Content length (12 Jun):** 2.629 kata vs kompetitor 546–1.693 kata. Lebih panjang dari kompetitor tapi justified untuk pillar page. Tahan sampai GSC 9 Juli 2026.

### Artikel #2 — Kenapa Warung Makan Sepi
**Content length (12 Jun):** 1.763 kata vs kompetitor 735–969 kata — 2x lebih panjang. Kandidat audit konten setelah GSC 22 Juli 2026. Jika time on page pendek, pertimbangkan pangkas.

### Artikel #5 — Cara Daftar GoFood
**Catatan snippet (11 Jun):** Format list snippet dioptimasi. H2 utama "Cara Daftar GoFood Langkah demi Langkah via Aplikasi GoBiz" — paragraf pembuka dipangkas dari 3 kalimat menjadi 2 kalimat. Kalimat klarifikasi kritis dipertahankan ("di GoBiz, bukan di website GoFood"). Kalimat transisi redundan ke-3 dihapus.

### Artikel #6 — Ditulis dengan Standar Baru
Artikel pertama yang menggunakan Master Prompt Artikel Kelas Dunia v1.1.
Nilai unik: tabel sudut foto per jenis makanan Indonesia + instruksi spesifik HP Xiaomi/Redmi & Oppo/Realme + section Kesalahan Umum.
SEO title: `7 Cara Foto Makanan Pakai HP agar Terlihat Enak` | Meta: 137 karakter ✅
**Catatan snippet (11 Jun):** Format list snippet dioptimasi. H2 utama "7 Trik Foto Makanan Pakai HP yang Bisa Langsung Dipraktikkan" — paragraf pembuka dipangkas dari 3 kalimat menjadi 1 kalimat.
**Content length (12 Jun):** 1.765 kata vs kompetitor 1.238–1.881 kata — well-calibrated.
**Update 25 Jun 2026:** Link ke Artikel #7 (Caption Instagram) ditambahkan di section penutup artikel — gap internal link #7 resmi ditutup dari sisi ini.

### Artikel #7 — 30 Template Caption Instagram Warung Makan Siap Pakai
**SEO Title:** `30 Template Caption Instagram Warung Makan Siap Pakai` (53 karakter) | **Meta:** 141 karakter ✅
**Slug:** `/template-caption-instagram-warung-makan/`
**Terbit:** 17 Juni 2026 | **Panjang:** 2.163 kata
**Featured image:** ✅ Sudah diupload dan terpasang di artikel.

**Nilai unik:** Tabel adaptasi caption per jenis makanan warung (nasi/lauk, mie/bakso/soto, minuman, snack/gorengan) dengan kata kunci, emoji, dan hashtag spesifik per kategori — tidak ditemukan di kompetitor manapun untuk niche warung makan kecil. 30 caption dikelompokkan ke 5 kategori konten (promo harian, menu baru, testimoni, behind the scenes, hari besar). Section Kesalahan Umum mencakup panduan jam posting optimal. 5 FAQ dengan konteks warung UMKM.

**Catatan Yoast Baca:** Satu temuan "Kata transisi" (13,9% kalimat). Sesuai aturan sejak Artikel #6, ini metrik keterbacaan Yoast saja, bukan checklist wajib Google — tidak perlu dioptimasi. Tab SEO Yoast (3 temuan: frasa kunci di awal, kepadatan frasa kunci, frasa kunci dalam subjudul) juga sesuai ekspektasi karena isi artikel mengikuti standar Google, bukan checklist Yoast.

**Catatan teknis publish:** Blok Yoast FAQ sempat menampilkan error "Blok ini mengandung konten yang tidak diinginkan atau tidak valid" setelah paste ke Block Editor. **Resolved** via tombol "Upayakan pemulihan" tanpa perlu rebuild manual. Pola yang sama pernah terjadi di Artikel #6 — solusi identik. Lihat Bagian 13 untuk catatan teknis lengkap.

**Gap internal link ditutup 25 Jun 2026:** Artikel #7 kini menerima 2 incoming link dari: Artikel #6 (Foto Makanan) — konteks foto bagus + caption bagus, dan Artikel #4 (WhatsApp) — konteks caption bisa dipakai ulang sebagai template broadcast WhatsApp.

### Artikel #8 — SEO Warung Makan Lokal Medan: Cara Naik Peringkat di Google Maps
**SEO Title:** `SEO Warung Makan Lokal Medan: Naik Peringkat Google Maps` (56 karakter) | **Meta:** 133 karakter ✅
**Slug:** `/seo-warung-makan-lokal-medan/`
**Terbit:** 25 Juni 2026 | **Panjang:** ~1.781 kata
**Standar:** Master Prompt Artikel Kelas Dunia v1.2
**Intent:** Mixed (Informational + Commercial) — CTA Section berwarna terpasang sebelum FAQ block ✅ (dikonfirmasi 9 Jul 2026)

**Nilai unik:** Konteks hiperlokal Medan (Petisah, Sunggal, Helvetia, Polonia, Medan Kota, Hamparan Perak, Sunggal Barat, Medan Baru) + template deskripsi GBP siap pakai untuk warung Sumatera Utara + template pesan WhatsApp minta ulasan siap kirim + timeline realistis berdasarkan persaingan area di Medan.

**Internal link tertanam (4 link):**
- Artikel #1 Pillar (di section soft CTA)
- Artikel #2 Kenapa Sepi (di H2 pertama, konteks akar masalah visibilitas)
- Artikel #3 GBP (di H3 Langkah 1, referensi panduan daftar GBP)
- Artikel #6 Foto Makanan (di H3 Langkah 5, konteks kualitas foto Google Maps)
**External link:** support.google.com/business/answer/7091?hl=id (panduan resmi Google peringkat lokal)

**Catatan Yoast FAQ:** Jika muncul error "Blok ini mengandung konten yang tidak diinginkan" saat paste — klik "Upayakan pemulihan". Pola berulang dari Artikel #6 dan #7, solusi sudah terbukti.

### Artikel #9 — Promosi Online Warung Makan Medan: Panduan Lengkap
**SEO Title:** `Promosi Online Warung Makan Medan: Panduan Lengkap` (50 karakter) | **Meta:** 133 karakter ✅
**Slug:** `/promosi-online-warung-makan-medan/`
**Terbit:** 1 Juli 2026 | **Panjang:** ~1.750 kata
**Standar:** Master Prompt Artikel Kelas Dunia v1.3
**Intent:** Mixed (Informational + Transactional) — CTA Section berwarna terpasang sebelum FAQ block ✅ (dikonfirmasi 9 Jul 2026)

**Nilai unik:** Artikel hub Medan yang merangkum seluruh channel promosi dalam satu panduan komprehensif — Google Maps/GBP, WhatsApp Business, marketplace GoFood/GrabFood, dan konten visual — dengan internal link ke tiap artikel channel spesifik untuk pembaca yang mau pendalaman.

**Internal link tertanam (6 link):**
- Artikel #1 Pillar (di section soft CTA/penutup)
- Artikel #2 Kenapa Sepi (di section pembuka)
- Artikel #3 GBP (di section Google Maps)
- Artikel #8 SEO Lokal Medan (di section Google Maps — menutup gap incoming link #8)
- Artikel #4 WhatsApp (di section WhatsApp)
- Artikel #5 GoFood (di section marketplace)
- Artikel #7 Caption Instagram (di section konten visual)
**External link:** support.google.com/business/answer/7091?hl=id (panduan resmi Google peringkat lokal)

**⚠️ Insiden legacy redirect (1 Jul 2026) — RESOLVED:** Setelah publish, artikel otomatis mengarah (301) ke Artikel #1 Pillar (`/cara-promosi-warung-makan-online/`) karena slug `/promosi-online-warung-makan-medan/` pernah terdaftar di plugin Redirection dari rencana lama sebelum artikel ini dijadwal ulang ke slot #9 (lihat catatan lama di Bagian 1 Content Calendar — kekeliruan judul dengan pillar page). Dua redirect rule dengan source URL yang sama (0 hits dan 68 hits) ditemukan di Peralatan → Pengalihan. **Solusi:** hapus (bukan disable) kedua rule, purge cache LiteSpeed Cache dan hPanel Hostinger, verifikasi via incognito. Berhasil — artikel sekarang live tanpa redirect. Link sudah dikirim ke GSC untuk indexing. Aturan pencegahan baru ditambahkan: cek tabel Redirection untuk konflik slug sebelum publish artikel baru (lihat Content Calendar Bagian 5 dan checklist Bagian 11).

**Catatan teknis publish:** Blok Yoast FAQ error "Blok ini mengandung konten yang tidak diinginkan" muncul lagi (ketiga kalinya). **"Upayakan pemulihan" GAGAL untuk pertama kali** — diselesaikan dengan input manual (hapus blok, ketik ulang pertanyaan/jawaban langsung di Block Editor). Lihat Bagian 13 untuk detail fallback lengkap.

**GSC reminder dibuat:** 31 Agustus 2026 (publish date + 61 hari).

**Gap internal link ditutup 9 Jul 2026:** Artikel #9 kini menerima incoming link dari Artikel #10 (Surabaya) — konteks perbandingan strategi antar kota.

### Artikel #10 — Promosi Online Warung Makan Surabaya: Panduan Lengkap
**SEO Title:** `Promosi Online Warung Makan Surabaya: Panduan Lengkap` (53 karakter) | **Meta:** 136 karakter ✅
**Slug:** `/promosi-online-warung-makan-surabaya/`
**Terbit:** 9 Juli 2026 | **Panjang:** ~1.490 kata
**Standar:** Master Prompt Artikel Kelas Dunia v1.3
**Intent:** Mixed (Informational + Transactional)

**Nilai unik:** Artikel kota kedua Cluster C (Taktik Lokal), format serupa Artikel #9 tapi konteks hiperlokal Surabaya (Gubeng, Rungkut, Wiyung, Wonokromo, Jemursari) dan penekanan pada persaingan GoFood/GrabFood karena penetrasi ojek online tinggi di kota ini. 4 kesalahan umum spesifik promosi warung Surabaya.

**Internal link tertanam (6 link):**
- Pillar Page (di intro)
- Artikel #3 GBP (di Langkah 1)
- Artikel #4 WhatsApp (di Langkah 2)
- Artikel #5 GoFood (di Langkah 3)
- Artikel #6 Foto Makanan (di Langkah 4)
- Artikel #9 Medan (di penutup — menutup gap incoming link #9)
**External link:** support.google.com/business/answer/7091?hl=id (panduan resmi Google peringkat lokal)

**Catatan teknis publish:** Belum ada laporan error blok Yoast FAQ untuk artikel ini — perlu dikonfirmasi Ronald apakah "Upayakan pemulihan" tetap diperlukan atau paste berjalan mulus kali ini.

**✅ CTA Section terpasang (9 Jul 2026):** Riwayat lengkap: draf awal tidak menyertakan CTA apa pun sebelum FAQ block (kesalahan proses penulisan). Ronald sempat menambahkan soft CTA teks manual ke post live. Kemudian ditemukan bahwa CTA Section berwarna adalah standar resmi sejak 11 Juni 2026 yang terlewat sejak Artikel #8 — Ronald memutuskan retrofit. Kode CTA Section diberikan, dan hari ini (9 Jul 2026) Ronald mengonfirmasi sudah terpasang, menggantikan soft CTA teks. Kasus ditutup.

**GSC reminder dibuat:** 8 September 2026 (publish date + 61 hari).

### Core Web Vitals — Status (13 Juni 2026)

**File referensi lengkap:** `cwv-technical-audit-onlineumkm-jun2026.md` (di Project Website onlineumkm.id)

| Halaman | LCP | CLS | TBT | Skor Mobile |
|---|---|---|---|---|
| Homepage (sebelum optimasi) | 4,6 dtk ❌ | 0,028 ✅ | 50 ms ✅ | ~71 |
| Homepage (setelah REST API _fields) | **3,6 dtk 🟠** | 0,033 ✅ | 50 ms ✅ | **82** |
| Artikel (contoh #6) | 2,9 dtk 🟠 | 0,027 ✅ | 40 ms ✅ | 89 |

**Metrik tambahan homepage (13 Juni 2026):**
- FCP: 2,8 dtk 🟠
- Speed Index: 5,1 dtk 🟠

**Bottleneck — Status Terkini (13 Juni 2026):**

| Bottleneck | Status | Dampak |
|---|---|---|
| REST API `/v2/posts?per_page=3&_embed=true` | ✅ PARTIALLY FIXED — _fields ditambahkan, payload turun ~80% | LCP turun 1 dtk |
| Base64 images di HTML (logo 3x + hero) | ⬜ BELUM DIFIX — bottleneck berikutnya | LCP tersisa ~1,1 dtk dari target |
| Google Tag Manager | ✅ DIAUDIT — aktif dengan GA4, dipertahankan | Normal |
| Cache TTL browser | ⬜ Setting tidak ditemukan di LiteSpeed versi ini | Secondary |

**LiteSpeed Cache — konfigurasi aktif:**
- CSS Minify, Combine, Async: ✅ AKTIF
- JS Minify: ✅ AKTIF | JS Defer: ❌ NONAKTIF (tidak kompatibel Elementor)
- QUIC.cloud Critical CSS: ✅ Sudah generate untuk homepage
- TTL Cache Publik: 604800 (1 minggu) ✅
- TTL REST: 604800 (1 minggu) ✅ — REST API cache aktif

### Peta Internal Link — Status Final (25 Juni 2026 — update v6.3)

Baris = artikel yang memberi link | Kolom = artikel yang menerima link

| | #1 Pillar | #2 Sepi | #3 GBP | #4 WA | #5 GoFood | #6 Foto | #7 Caption | #8 SEO Medan |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **#1 Pillar** | — | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| **#2 Warung Sepi** | ✅ | — | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| **#3 GBP** | ✅ | ✅ | — | ❌ | ❌ | ✅ | ❌ | ❌ |
| **#4 WhatsApp** | ✅ | ✅ | ✅ | — | ❌ | ✅ | ✅ | ❌ |
| **#5 GoFood** | ✅ | ✅ | ✅ | ✅ | — | ✅ | ❌ | ❌ |
| **#6 Foto** | ✅ | ✅ | ✅ | ❌ | ✅ | — | ✅ | ❌ |
| **#7 Caption** | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | — | ❌ |
| **#8 SEO Medan** | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | — |
| **Incoming** | **7** | **6** | **6** | **4** | **3** | **7** | **2** | **0** |

**Gap lama (tidak berubah, tidak perlu dipaksakan):** #3→#4, #3→#5, #4→#5, #6→#4.

**Gap Artikel #7 SUDAH DITUTUP (25 Jun 2026):** Link dari Artikel #6 dan Artikel #4 ke #7 berhasil ditambahkan. Incoming Artikel #7 naik dari 0 ke 2.

**Gap baru — Artikel #8 belum punya link masuk sama sekali (Incoming = 0).** Wajar untuk artikel yang baru terbit. Saran penutupan gap saat menulis Artikel #9:

| Artikel Sumber | Saran Tambahan Link ke #8 | Konteks Natural |
|---|---|---|
| #9 Promosi Medan | Link ke #8 SEO Lokal Medan | SEO Maps adalah bagian dari strategi promosi online Medan yang lebih luas |

**📌 Pengingat untuk sesi penulisan Artikel #9:** Tambahkan link ke #8 dari #9 sebagai bagian natural dari konten strategi promosi Medan.

### Heading Audit — Ringkasan (11 Juni 2026)

| # | Masalah Ditemukan | Fix Dieksekusi | Tahan GSC |
|---|---|---|---|
| 1 Pillar | Over-opt parah (9 heading), H4, generic H3, em dash, emoji | — | Semua |
| 2 Warung Sepi | Over-opt (4 H2 identik), 2 H2 tumpang tindih | — | Semua |
| 3 GBP | "Penutup" generic, H2 hampir duplikat H1 | ✅ Penutup → deskriptif | H2 duplikat |
| 4 WhatsApp | "Penutup" generic, H3 pakai titik | ✅ Keduanya | — |
| 5 GoFood | Over-opt original (4 H2 frasa identik) | ✅ 2 H2 diubah ke variasi | — |
| 6 Foto Makanan | Tidak ada masalah — referensi heading yang baik | — | — |
| 7 Caption Instagram | Tidak ada masalah — 9 H2 justified (artikel template 5 kategori) | — | — |

### Draft Revisi Title & Meta (BELUM DIIMPLEMENTASI — tunggu data GSC)
Cek pertama: **9 Juli 2026** via Google Calendar. Syarat implementasi: impresi tinggi + CTR < 3%.

| # | Title Baru | Meta Baru | Char |
|---|---|---|---|
| 1 | Cara Promosi Warung Makan Online: 5 Langkah Terbukti Efektif | Belum tahu harus mulai dari mana? Ini 5 langkah promosi warung makan online yang bisa kamu coba sendiri hari ini. | 114 |
| 2 | Kenapa Warung Makan Sepi Padahal Enak? 5 Sebab & Solusinya | Warung enak tapi sepi? Bukan soal rasa, tapi orang tidak tahu warungmu ada. Ini 5 sebab yang sering diabaikan dan cara mengatasinya. | 132 |
| 3 | Cara Daftar Google Business Profile Warung Makan [Gratis] | Warung kamu belum muncul di Google Maps? Daftar GBP gratis dalam 15 menit, dari pendaftaran, verifikasi, sampai profil aktif. | 125 |
| 4 | Promosi Warung Makan lewat WhatsApp: Efektif Tanpa Ganggu | Takut pelanggan merasa terganggu? Promosi WhatsApp yang benar justru bikin mereka menunggu pesan berikutnya. Ini caranya. | 121 |
| 5 | Cara Daftar GoFood untuk Warung Makan dari Nol sampai Aktif | Mau warungmu masuk GoFood? Ikuti 5 langkah di GoBiz, siapkan dokumen wajib, dan tips agar pesanan pertama cepat masuk. Gratis. | 126 |

---

## BAGIAN 4: ARSITEKTUR TEKNIS HOMEPAGE

### Struktur 2 Blok

| Blok | Isi | Cara Edit |
|---|---|---|
| Blok HTML Utama | CSS, nav, hero, sections, footer, script orisinal | Edit hati-hati via tab Kode |
| Blok Fix Script | Semua event listener dan interaktivitas | Selalu Ctrl+A → Delete → Paste baru |

### Aturan Wajib
- WordPress **selalu menghapus** atribut `onclick` saat save — pakai `addEventListener`
- Hamburger handler hanya boleh ada di script utama — jangan duplikasi
- Blog section pakai `id="blog-grid-dynamic"` — auto-update via REST API
- **JANGAN hapus `<p>` dari `<style>`** — WordPress kembalikan setiap save
- **REST API call:** `fetch('/wp-json/wp/v2/posts?per_page=3&_embed=true&_fields=id,title,excerpt,link,_links')` — JANGAN hapus parameter _fields
- **Hamburger menu mobile:** `<button id="oumkm-hamburger" class="hamburger">` WAJIB punya 3 elemen `<span></span>` di dalamnya. CSS `.hamburger span{...}` sudah siap mewarnai hijau — tanpa `<span>`, tidak ada yang dirender meski tombolnya tetap berfungsi (klik tetap toggle menu)

### Navigasi Saat Ini
| Nav Item | Aksi |
|---|---|
| Layanan | Scroll ke `#layanan` |
| Tentang | Buka `/tentang/` |
| Cara Kerja | Scroll ke `#proses` |
| Blog SEO | Scroll ke `#blog` |
| FAQ | Scroll ke `#faq` |
| Konsultasi Gratis | Buka WhatsApp |

---

## BAGIAN 5: HALAMAN TENTANG KAMI

**URL:** `/tentang/` *(jangan ubah slug — merusak nav links)*
**Focus keyword:** `jasa website UMKM`
**Meta Desc:** OnlineUMKM.id adalah jasa website dan SEO lokal berbasis di Medan, melayani UMKM seluruh Indonesia. Kenali Ronald Huson dan misi kami. *(134 karakter)*

**Masalah yang masih pending:**
| Masalah | Solusi |
|---|---|
| Foto profil belum ada | Upload foto Ronald, alt: `Ronald Huson pendiri jasa website UMKM OnlineUMKM Medan` |
| Panjang paragraf >150 kata | Pecah paragraf panjang jadi 2 |
| Kata transisi 22% | Tambah transisi di paragraf bio |

---

## BAGIAN 6: HALAMAN BLOG

**URL:** `/blog/`
Yoast SEO merah = normal untuk posts archive — tidak bisa diperbaiki.

---

## BAGIAN 7: ATURAN YOAST — LENGKAP & TERBARU

### ⚠️ PERUBAHAN PENTING — BERLAKU MULAI 9 JUNI 2026

**Yoast hanya mengatur tiga hal:** SEO title, slug, dan meta description.
Isi artikel (body content) dioptimasi untuk standar Google — bukan checklist Yoast.

| Aturan Yoast Lama (TIDAK BERLAKU lagi untuk isi artikel) | Keterangan |
|---|---|
| Minimal 30% heading mengandung keyword | Dihapus — aturan Yoast saja |
| Keyword density 0.5%–2.5% | Dihapus — metrik Yoast saja |
| Kata transisi tersebar merata | Dihapus — Yoast keterbacaan |
| Paragraf maks 150 kata | Tidak wajib, tetap jadi pedoman keterbacaan |
| Subheading setiap 300 kata | Tidak wajib, tetap jadi pedoman struktur |
| Kata "berikutnya" dilarang | Dihapus — ini aturan Yoast, bukan Google |

### Yang Tetap Berlaku untuk Isi Artikel (Standar Google)

| Aturan | Ketentuan |
|---|---|
| Keyword di H1 | Wajib — natural |
| Keyword di 100 kata pertama | Wajib — natural |
| Keyword di minimal 2 heading | Wajib — natural, variasi boleh |
| Alt text keyword | Maksimal 1–2 gambar per artikel |
| Internal link | Min. 3 per artikel ke halaman konten — langsung tertanam di HTML |
| External link | Min. 1 ke sumber otoritatif — langsung tertanam di HTML |
| FAQ block | Wajib di akhir artikel — format Yoast FAQ block native |
| H2 sebelum FAQ | Wajib |
| Angka di judul | Harus sesuai jumlah poin di isi artikel |

### Catatan Update Mei 2026 — FAQ Rich Result Dihentikan Google

Google resmi menghentikan **FAQ rich result** (accordion Q&A di hasil pencarian) per 7 Mei 2026 — termasuk dukungannya di Rich Results Test mulai Juni 2026. Sejak Agustus 2023, fitur ini sebenarnya sudah dibatasi hanya untuk situs gov/health, jadi mayoritas situs (termasuk onlineumkm.id) sudah lama gak dapat tampilan ini meski schema-nya valid.

**Aturan FAQ block TETAP berlaku — wajib di akhir artikel.** Yang berubah cuma alasannya:
- ❌ Bukan lagi untuk dapat accordion FAQ di SERP (fitur ini sudah mati)
- ✅ Tetap untuk: cover pertanyaan PAA (People Also Ask) dari riset LSI, peluang featured snippet paragraph (Topik 7), dan konteks tambahan untuk AI Overview/AI search

FAQPage schema tidak perlu dihapus — Google menegaskan structured data yang gak dipakai gak menimbulkan masalah, cuma gak ada efek visual lagi.

### Standar Heading (Tambahan — dari audit 11 Juni 2026)

| Aturan | Ketentuan |
|---|---|
| H1 per halaman | Satu saja — judul WordPress = H1 otomatis, jangan tambah H1 manual di konten |
| Keyword di heading | Minimal 2 heading, maksimal 3–4 heading (variasi natural) |
| Frasa keyword identik | Tidak boleh diulang lebih dari 3× di heading yang berbeda |
| Heading generic | Dilarang: "Penutup", "Tips Penting", "Kesimpulan", "Apa, sih?" |
| H4 | Hindari — jadikan paragraf dengan bold |
| Tanda baca di akhir heading | Dilarang: titik, koma, titik dua |
| Em dash / en dash di heading | Dilarang — sama seperti larangan di seluruh artikel |
| Emoji di heading | Dilarang |
| H2 duplikat H1 | Hindari — H2 harus menambah dimensi, bukan mengulang H1 |

### Standar Featured Snippet (List) — Berlaku mulai 11 Juni 2026

| Aturan | Ketentuan |
|---|---|
| Kalimat sebelum list | Maks 1–2 kalimat — 1 jika isi kalimat sama semua; 2 jika ada klarifikasi kritis |
| Kalimat transisi redundan | Hapus — "Ikuti langkah berikut" tepat sebelum list = redundan |
| Blok teks antara pengantar dan list | Tidak boleh ada — list harus langsung setelah kalimat pengantar |
| Kalimat bernilai nyata | JANGAN dipangkas meski panjang paragraf melebihi standar — contoh: klarifikasi "di GoBiz, bukan di website GoFood" |
| Snippet optimization vs kejelasan artikel | Kejelasan artikel selalu menang — jangan korbankan informasi penting demi format snippet |

### Standar Content Length — Berlaku mulai 12 Juni 2026

| Aturan | Ketentuan |
|---|---|
| Benchmark panjang | Selalu cek 3 artikel peringkat teratas untuk keyword target — jadikan referensi range yang wajar |
| Panjang artikel | Fungsi dari intent — tidak ada angka minimum universal |
| Over-length | Jika artikel 2x lebih panjang dari semua kompetitor, evaluasi apakah ada bagian yang bisa dipadatkan |
| Freshness artikel baru | Tidak perlu dikhawatirkan untuk topik evergreen — update hanya jika info sudah tidak akurat |
| Keputusan pangkas konten | Tunggu data GSC (time on page, bounce rate) sebelum potong artikel yang sudah terbit |

### Meta (Diatur Yoast — wajib hijau)

| Aturan | Ketentuan |
|---|---|
| **Meta description** | **Maksimal 142 karakter** |
| SEO title | Maksimal 60 karakter |
| Slug | Huruf kecil, tanda hubung, tanpa karakter khusus |
| Keyword di meta | Wajib muncul di meta description dan SEO title |

### Screenshot Yoast — Aturan Baru

Screenshot **tidak lagi diperlukan** untuk indikator isi artikel.
Screenshot hanya berguna untuk konfirmasi tiga field: SEO title, slug, meta description.
Kirim screenshot **hanya jika ada yang merah** di tiga field tersebut.

### Gaya Penulisan (berlaku semua artikel)
- Em dash / en dash dalam ARTIKEL: DILARANG
- Em dash / en dash dalam SARAN KONTEN dari Claude: DILARANG
- Pembuka terlarang: "Di era digital ini", "Dalam persaingan yang semakin ketat", "Tentu saja"
- Tone: **"kamu"**
- "Berikutnya": boleh digunakan jika terdengar natural

---

## BAGIAN 7a: SISTEM CTA — CTA SECTION (KOTAK WARNA) WAJIB SEMUA ARTIKEL

**⚠️ Koreksi drift proses (ditemukan dan diperbaiki 9 Juli 2026):**
Sistem CTA Section berwarna (`#00BFA5`, Custom HTML block, dua tombol) ditetapkan wajib untuk SEMUA artikel sejak 11 Juni 2026 (lihat `handoff-konten-copywriting-update-21juni2026.md`), dan sudah diterapkan penuh ke Artikel #1–#7. Mulai Artikel #8, sistem ini diam-diam tergantikan versi "soft CTA" teks polos (satu paragraf, satu link, tanpa kotak warna) — **tanpa ada keputusan resmi yang membatalkan aturan CTA Section**. Ini murni inkonsistensi antar sesi, bukan perubahan yang disengaja. Ronald mengonfirmasi 9 Juli 2026: kembalikan CTA Section sebagai standar tunggal, retrofit ke Artikel #8, #9, #10.

**Aturan final (berlaku mulai 9 Juli 2026):**
CTA Section berwarna WAJIB di semua artikel, tanpa kecuali — bukan hanya artikel mixed intent. "Soft CTA teks" (Bagian 7a versi lama) TIDAK dipakai lagi mulai sekarang.

**Format posisi di akhir artikel:**
```
[Konten utama artikel]
  ↓
[HR Separator]
  ↓
[H2 section terakhir]
  ↓
[Custom HTML block: CTA Section] ← WAJIB, semua artikel
  ↓
[Yoast FAQ block] ← Selalu paling akhir
```

**Template CTA Section (FINAL — customize H3 dan paragraf sesuai topik artikel, jangan ubah struktur/warna tanpa konfirmasi Ronald):**

```html
<!-- CTA SECTION: Konsultasi Gratis -->
<div style="background-color: #00BFA5; color: white; padding: 40px 30px; border-radius: 8px; margin-top: 50px; margin-bottom: 50px; text-align: center; font-family: -apple-system, BlinkMacSystemFont, Segoe UI, Arial, sans-serif;">
  <h3 style="margin-top: 0; font-size: 24px; font-weight: 600; margin-bottom: 15px;">[H3 spesifik topik artikel]</h3>
  <p style="font-size: 16px; line-height: 1.6; margin-bottom: 30px; max-width: 600px; margin-left: auto; margin-right: auto;">Online UMKM siap membantu kamu [kalimat spesifik topik]. Konsultasi awal gratis, tanpa kewajiban.</p>
  <div style="display: flex; flex-wrap: wrap; gap: 12px; justify-content: center;">
    <a href="https://wa.me/6287791808667?text=Halo%20Ronald%2C%20saya%20ingin%20konsultasi%20gratis" style="display: inline-block; background-color: white; color: #00BFA5; padding: 14px 32px; border-radius: 6px; font-weight: 600; text-decoration: none; font-size: 16px;">Konsultasi Gratis via WhatsApp</a>
    <a href="https://onlineumkm.id/#layanan" style="display: inline-block; background-color: transparent; color: white; padding: 14px 32px; border: 2px solid white; border-radius: 6px; font-weight: 600; text-decoration: none; font-size: 16px;">Lihat Layanan Kami</a>
  </div>
</div>
<!-- END CTA SECTION -->
```

**Catatan koreksi teks (9 Jul 2026):** Template asli 11 Juni pakai "OnlineUMKM.id" di paragraf deskripsi. Ini dibuat sebelum audit NAP 20 Juni yang menetapkan "Online UMKM" (tanpa .id) sebagai nama kanonik di semua channel publik. Template di atas sudah dikoreksi — pakai "Online UMKM" di teks, domain `onlineumkm.id` tetap dipakai apa adanya di URL.

**Aturan CTA Section:**
- Warna: `#00BFA5` BUKAN `#00C853`
- Teks: TANPA em dash / en dash
- Nama brand dalam teks: "Online UMKM" — bukan "OnlineUMKM.id"
- Tombol utama: Konsultasi Gratis via WhatsApp
- Tombol sekunder: Lihat Layanan Kami → `#layanan`
- Implementasi: WordPress Custom HTML block
- Warning "blok tidak valid" saat edit Custom HTML block di editor = NORMAL, diabaikan (beda dengan error blok FAQ)

**Status CTA Section per artikel (9 Juli 2026 — update v6.8, semua selesai):**

| # | Artikel | CTA Section | Catatan |
|---|---|---|---|
| 1–5 | Pillar s/d GoFood | ✅ Selesai | Diterapkan 14 Jun 2026 |
| 6 | Foto Makanan | ✅ Selesai | Diterapkan sejak awal (11 Jun 2026) |
| 7 | Caption Instagram | ✅ Selesai | Diterapkan sejak awal (21 Jun 2026) |
| 8 | SEO Lokal Medan | ✅ Selesai | Dikonfirmasi Ronald 9 Jul 2026, menggantikan soft CTA teks lama |
| 9 | Promosi Warung Makan Medan | ✅ Selesai | Dikonfirmasi Ronald 9 Jul 2026, menggantikan soft CTA teks lama |
| 10 | Promosi Warung Makan Surabaya | ✅ Selesai | Dikonfirmasi Ronald 9 Jul 2026, menggantikan paragraf soft CTA manual |
| 11+ | Artikel mendatang | Wajib dari draf pertama | Claude wajib sertakan CTA Section langsung di draf HTML, bukan lagi soft CTA teks |

**Semua 10 artikel terbit sekarang konsisten pakai CTA Section berwarna. Drift proses resmi ditutup.**

---

## BAGIAN 8: SISTEM CLAUDE — 10 SKILLS AKTIF

| # | Skill | Domain |
|---|---|---|
| 1 | `konteks-bisnis-umkm` | Identitas & konteks bisnis onlineumkm.id |
| 2 | `bisnis-marketing` | Analisis & perencanaan strategis |
| 3 | `copywriting` | Menulis konten & copy |
| 4 | `seo` | Audit & optimasi SEO (Yoast) |
| 5 | `wordpress-teknis` | Error, plugin, tema, hosting |
| 6 | `saas-ecosystem-umkm` | Setup & maintenance SaaS tools klien |
| 7 | `keuangan` | Keuangan pribadi & bisnis freelance |
| 8 | `digital-marketing` | Eksekusi kampanye: ads, analytics, sosmed |
| 9 | `brainstorm` | Ideation & pemecahan masalah kreatif |
| 10 | `counsel` | Pengambilan keputusan & saran |
| + | `stop-slop-indonesia` | Companion otomatis — semua tulisan Indonesia |

**Plugin SEO:** Yoast (jangan sarankan migrasi ke RankMath kecuali diminta)
**MCP aktif:** Gmail, Google Calendar, Google Drive
**GitHub:** ✅ Aktif — repo `onlineumkm-website` tersync ke Project Website onlineumkm.id

### Panduan Pilihan Model Claude (Pro Plan)

| Tugas | Model | Alasan |
|---|---|---|
| Sesi belajar SEO | Sonnet ✅ | Default — cukup untuk semua sesi pembelajaran |
| Audit artikel 1–2 file | Sonnet ✅ | Cukup untuk analisis standar |
| Nulis / revisi artikel | Sonnet ✅ | Skill copywriting sudah mengkompensasi |
| Quick questions, GSC check | Sonnet ✅ | Overkill pakai Opus |
| Audit mendalam multi-file sekaligus | Opus 💡 | Reasoning lebih teliti untuk analisis kompleks |
| Keputusan strategis bisnis besar | Opus 💡 | Nuansa pertimbangan lebih dalam |
| Analisis data GSC + rekomendasi tindakan | Opus 💡 | Pola data butuh reasoning lebih kuat |

**⚠️ Catatan:** Opus menghabiskan kuota 3–5x lebih cepat dari Sonnet. Kombinasi Opus + percakapan panjang = paling boros. Solusi: mulai percakapan baru untuk tugas berbeda, kirim file handoff di awal.

---

## BAGIAN 9: PROJECTS CLAUDE — 5 AKTIF

| # | Nama Project | Status | File yang Ada |
|---|---|---|---|
| 1 | Project Website onlineumkm.id | ✅ Aktif | Homepage files + handoff + GitHub repo tersync |
| 2 | Project Klien & Proposal | ✅ Aktif | Template WA, brief form klien, template proposal 1 halaman |
| 3 | Project Konten & Copywriting | ✅ Aktif | Keyword research + handoff + content calendar + heading-hierarchy-standards.md |
| 4 | Project Keuangan Freelance | ✅ Aktif | budget-bulanan-template.xlsx, tracker-keuangan-bisnis.xlsx, template-invoice.xlsx, referensi-keuangan-bisnis.md |
| 5 | Project Belajar SEO & Digital Marketing | ✅ Aktif | progresstrackerbelajar.xlsx, roadmap-belajar-seo.md, handoff-sesi-1 s/d sesi-11 |

### GitHub Repo — Detail Integrasi
- **Nama repo:** `onlineumkm-website` (Private)
- **Akun GitHub:** perkasacuan3-rgb
- **Cara Claude akses:** Tersync ke Project Website onlineumkm.id — Claude baca langsung dari repo
- **Struktur folder (per 19 Jun 2026):**
  - `articles/` — file artikel HTML (artikel-01 s/d artikel-06; artikel-07 disarankan ditambahkan di sesi berikutnya)
  - `homepage/main-block.html` — blok HTML utama homepage (CSS, nav, hero, sections, footer, script)
  - `homepage/fix-script.html` — blok event listener & interaktivitas terpisah
  - `pages/tentang.html` — ditambahkan 19 Jun 2026, sebelumnya halaman Tentang tidak ditrack
  - `notes/` — wordpress-teknis-notes.md, yoast-rules.md
  - `handoff/` — versi lama master handoff (v4.4), tidak dipakai aktif lagi
- **Penting:** File di repo berisi komentar dokumentasi header DAN marker `<!-- wp:html -->`/`<!-- /wp:html -->` untuk referensi — saat paste ke WordPress, HANYA ambil konten DI ANTARA kedua marker tersebut (lihat Bagian 13)

---

## BAGIAN 10: CONTENT CALENDAR — RINGKASAN

### Sudah Terbit (10 artikel)
| # | Judul | Terbit | Standar |
|---|---|---|---|
| 1 (Pillar) | Cara Promosi Warung Makan Online | 9 Mei 2026 | Standar lama |
| 2 | Kenapa Warung Makan Sepi Padahal Enak | 22 Mei 2026 | Standar lama |
| 3 | Cara Daftar Google Business Profile | 25 Mei 2026 | Standar lama |
| 4 | Cara Promosi Warung Makan lewat WhatsApp | 29 Mei 2026 | Standar lama |
| 5 | Cara Daftar GoFood untuk Warung Makan | 3 Jun 2026 | Standar lama |
| 6 | Cara Foto Makanan Pakai HP biar Terlihat Enak | 9 Jun 2026 | ✅ Master Prompt v1.1 |
| 7 | 30 Template Caption Instagram Warung Makan Siap Pakai | 17 Jun 2026 | ✅ Master Prompt v1.1 |
| 8 | SEO Warung Makan Lokal Medan: Cara Naik Peringkat di Google Maps | 25 Jun 2026 | ✅ Master Prompt v1.2 |
| 9 | Promosi Online Warung Makan Medan: Panduan Lengkap | 1 Jul 2026 | ✅ Master Prompt v1.3 |
| 10 | Promosi Online Warung Makan Surabaya: Panduan Lengkap | 9 Jul 2026 | ✅ Master Prompt v1.3 |

### Jadwal Mendatang (2 artikel)
| # | Target | Judul | Keyword | Intent | Prioritas |
|---|---|---|---|---|---|
| 11 | 14–20 Jul | Promosi Online Warung Makan Bandung | promosi online warung makan Bandung | Mixed | 🔴 Tinggi |
| 12 | 21–27 Jul | Promosi Online Warung Makan Jakarta | promosi online warung makan Jakarta | Mixed | 🟡 Sedang |

**Catatan:** Artikel #11–12 (keyword lokal) = mixed intent → wajib sisipkan CTA Section berwarna langsung di draf (bukan soft CTA teks, lihat Bagian 7a — jangan sampai terlewat seperti sesi Artikel #10). Artikel #11 wajib tambah link ke Artikel #10 (Surabaya) untuk menutup gap incoming link barunya.
**Semua artikel mulai #7:** wajib mengikuti Master Prompt Artikel Kelas Dunia v1.3 + standar heading dari `heading-hierarchy-standards.md`.
**Sebelum publish artikel baru:** cek tabel Redirection (Peralatan → Pengalihan) untuk konflik slug lama — pelajaran dari insiden Artikel #9 (lihat Bagian 13).

---

## BAGIAN 11: PENDING ITEMS (9 Juli 2026 — update v6.6)

### Prioritas Tinggi
- [ ] **Upload foto Ronald ke Tentang Kami** — alt: `Ronald Huson pendiri jasa website UMKM OnlineUMKM Medan`
- [ ] **Foto bisnis GBP** — belum ada materi otentik (belum ada klien). Bisa pakai foto Ronald kerja dengan onlineumkm.id terbuka di layar, atau tunggu sampai ada hasil kerja klien pertama. Jangan pakai foto stok generik.
- [ ] **Artikel #11** — Promosi Online Warung Makan Bandung (target 14–20 Jul) — via Project Konten & Copywriting. Wajib tambah link ke Artikel #10 (Surabaya) untuk menutup gap incoming link. Cek tabel Redirection untuk slug sebelum publish. Pastikan CTA Section berwarna masuk di draf sebelum diserahkan (bukan soft CTA teks).
- [ ] **Isi referensi-keuangan-bisnis.md** — harga jasa & target keuangan (Project Keuangan Freelance)
- [ ] **Base64 images homepage** — logo muncul 3x sebagai base64 di HTML (nav, hero card, footer), hero image juga base64. Ganti dengan URL gambar aktual dari media library WordPress untuk kurangi beban HTML dan perbaiki LCP tersisa.

### Prioritas Menengah
- [ ] **Tentang Kami Keterbacaan** — pecah paragraf panjang + tambah kata transisi
- [ ] **Review judul & meta 6 artikel pertama** — nilai CTR potential (lihat draft di Bagian 3, implementasi setelah data GSC)
- [ ] **Artikel #2 content length** — evaluasi apakah ada bagian yang bisa dipadatkan, setelah GSC 22 Juli 2026
- [ ] **Heading artikel #1 & #2** — over-optimization dan masalah struktur lainnya → tahan sampai data GSC tersedia
- [ ] **Kredit iklan Google Ads Rp 3.000.000** — revisit kalau topik Google Ads sudah masuk kurikulum dan Ronald siap pasang budget riil. Cek apakah penawaran serupa masih tersedia saat itu.
- [ ] **Tambah `articles/artikel-07.html` dan `artikel-08.html` ke GitHub repo** — kedua file belum ditrack di struktur folder `articles/`

### Prioritas Rendah
- [ ] Internal link "Baca juga" di homepage
- [ ] Portofolio / demo website
- [ ] Pantau portal UMKM pemerintah (smesta.go.id, kemenkopukm.go.id)
- [ ] Pantau `/tag/instagram-bisnis/` (dan tag lain) di GSC — harus pindah dari "Di-crawl, tidak diindeks" ke "Excluded by noindex tag" dalam beberapa minggu
- [ ] Gap lama peta internal link: #3→#4, #3→#5, #4→#5, #6→#4 — tidak ada konteks natural saat ini, isi hanya jika muncul kesempatan natural di artikel mendatang

### ✅ SELESAI
- ~~Pasang CTA Section berwarna di Artikel #8, #9, #10~~ ✅ 9 Juli 2026 — dikonfirmasi Ronald, menggantikan soft CTA teks lama. Semua 10 artikel terbit sekarang konsisten
- ~~Drift proses CTA Section ditemukan dan diperbaiki~~ ✅ 9 Juli 2026 — sistem CTA Section berwarna (wajib sejak 11 Jun) ternyata tergantikan diam-diam oleh soft CTA teks mulai Artikel #8 tanpa keputusan resmi. Ronald konfirmasi retrofit ke #8, #9, #10, Bagian 7a direvisi total
- ~~Artikel #10 — Promosi Online Warung Makan Surabaya~~ ✅ Terbit 9 Juli 2026 — Yoast hijau, ~1.490 kata, 6 internal link tertanam. CTA Section berwarna terpasang (dikonfirmasi 9 Jul 2026)
- ~~Gap internal link Artikel #9 ditutup~~ ✅ 9 Juli 2026 — link dari Artikel #10 (Surabaya) ke #9 berhasil ditambahkan
- ~~Set Google Calendar GSC reminder Artikel #10~~ ✅ 9 Juli 2026 — cek pertama 8 September 2026
- ~~Artikel #8 — SEO Warung Makan Lokal Medan~~ ✅ Terbit 25 Juni 2026 — Yoast hijau, 2 gambar terpasang, ~1.781 kata, soft CTA hadir, 4 internal link tertanam
- ~~Gap internal link Artikel #7 ditutup~~ ✅ 25 Juni 2026 — link dari Artikel #6 (Foto Makanan) dan Artikel #4 (WhatsApp) ke #7 berhasil ditambahkan
- ~~Set Google Calendar GSC reminder Artikel #8~~ ✅ 25 Juni 2026 — cek pertama 25 Agustus 2026
- ~~Update deskripsi event GSC Artikel #7 di Google Calendar~~ ✅ 25 Juni 2026 — catatan gap lama dihapus, status gap ditutup dicatat
- ~~Artikel #7 — 30 Template Caption Instagram Warung Makan~~ ✅ Terbit 17 Juni 2026 — Yoast hijau, featured image terpasang, 2.163 kata
- ~~Set Google Calendar GSC reminder Artikel #7~~ ✅ 21 Juni 2026 — cek pertama 17 Agustus 2026
- ~~Topik 21 — NAP Consistency Audit~~ ✅ 20 Juni 2026 — audit 4 sumber (footer website, JSON-LD schema, GBP, WhatsApp Business). Address & phone konsisten sejak awal. Name mismatch ditemukan ("OnlineUMKM.id" vs "Online UMKM") dan diperbaiki di 17 lokasi (7 homepage + 10 Tentang Kami). Ditemukan juga: footer custom homepage TIDAK global. Detail lengkap di Bagian 16.
- ~~Topik 20 — Google Business Profile setup lengkap~~ ✅ 20 Juni 2026 — profil existing yang serampangan diaudit & diperbaiki total (SAB, area layanan, jam buka, deskripsi, daftar layanan). Detail lengkap di Bagian 2a dan Bagian 16.
- ~~Konfirmasi final Topik 19 di live site~~ ✅ 20 Juni 2026 — Ronald konfirmasi sudah klik Terbitkan, purge cache LiteSpeed, dan hamburger menu tampil normal di mobile
- ~~Sesi 13 — GitHub sync Topik 19 + debugging regresi homepage~~ ✅ 19 Juni 2026 — root cause ditemukan (widget Elementor salah), fix Topik 19 (6 URL + hamburger + CWV attributes) terverifikasi 100% live. File `pages/tentang.html` ditambahkan ke GitHub.
- ~~Topik 15 Canonical tags & duplicate content — audit 4 titik rawan (canonical artikel #6, redirect domain, GSC duplicate report, halaman kategori)~~ ✅ 15 Juni 2026 — semua aman, tidak ada tindakan
- ~~Topik 16 Crawl errors & 404 fix — audit 5 temuan GSC Page Indexing~~ ✅ 15 Juni 2026 — semua diresolve/normal
- ~~Fix redirect 301 `/blog-umkm/` → `/blog/`~~ ✅ 15 Juni 2026 — via plugin Redirection, diverifikasi browser
- ~~Request reindex Artikel #2 (`/kenapa-warung-makan-sepi/`) via GSC~~ ✅ 15 Juni 2026
- ~~Topik 12 Sitemap.xml & robots.txt — audit robots.txt (sehat) & sitemap_index.xml~~ ✅ 14 Juni 2026
- ~~Fix tag taxonomy bloat (20 tag duplikat/sinonim di post_tag-sitemap.xml)~~ ✅ 14 Juni 2026 — noindex via Yoast, sitemap turun 31→11 URL
- ~~Topik 13 Schema markup lanjutan — audit via Rich Results Test (homepage + artikel #6)~~ ✅ 14 Juni 2026 — semua valid (Article, Breadcrumb, FAQ)
- ~~Identifikasi update FAQ rich result deprecated Google (Mei 2026)~~ ✅ 14 Juni 2026 — dicatat di Bagian 7
- ~~Topik 11 Mobile-first Indexing — content parity homepage dicek via Chrome DevTools, semua lolos~~ ✅ 14 Juni 2026
- ~~Fix hamburger menu mobile homepage — tombol kosong tanpa `<span>`, 3 `<span>` ditambahkan, ikon hijau tampil normal~~ ✅ 14 Juni 2026
- ~~Sistem dapat klien (3 aset)~~ ✅
- ~~Setup Project Keuangan Freelance~~ ✅
- ~~Setup Project Belajar SEO & Digital Marketing~~ ✅
- ~~GitHub connector diintegrasikan ke Project Website onlineumkm.id~~ ✅
- ~~Homepage Yoast 2 item merah~~ — WordPress permanent limitation
- ~~Artikel #6 Foto Makanan~~ ✅ Terbit 9 Juni 2026
- ~~Master Prompt Artikel Kelas Dunia~~ ✅ v1.1 aktif
- ~~Content Calendar~~ ✅ v1.5 aktif
- ~~Tambah paragraf GoFood ke artikel pillar~~ ✅ 10 Juni 2026
- ~~Tambah kalimat Facebook & TikTok di section media sosial artikel pillar~~ ✅ 10 Juni 2026
- ~~Audit peta internal link 6 artikel~~ ✅ 10 Juni 2026
- ~~Fix slug GBP di artikel #2 (404 → benar)~~ ✅ 10 Juni 2026
- ~~Fix duplikat link GBP artikel #2 → ganti satu ke WhatsApp~~ ✅ 10 Juni 2026
- ~~Artikel #1 → tambah link ke #6 Foto Makanan~~ ✅ 10 Juni 2026
- ~~Artikel #3 → tambah link ketiga ke #6 Foto Makanan~~ ✅ 10 Juni 2026
- ~~Artikel #4 → ubah teks "yang akan datang" menjadi link aktif ke #6~~ ✅ 10 Juni 2026
- ~~Artikel #5 → tambah link ke #6 Foto Makanan~~ ✅ 10 Juni 2026
- ~~Request reindex Artikel #2 via GSC~~ ✅ 10 Juni 2026
- ~~Artikel #6 → tambah link ke Artikel #3 (GBP)~~ ✅ 11 Juni 2026
- ~~Audit heading semua 6 artikel~~ ✅ 11 Juni 2026
- ~~H2 "Penutup" Artikel #3 → ganti deskriptif~~ ✅ 11 Juni 2026
- ~~H2 "Penutup" Artikel #4 → ganti deskriptif~~ ✅ 11 Juni 2026
- ~~H3 titik di akhir Artikel #4 → dihapus~~ ✅ 11 Juni 2026
- ~~H2 over-optimization Artikel #5 → 2 H2 diubah ke variasi natural~~ ✅ 11 Juni 2026
- ~~Set Google Calendar GSC reminder semua artikel #2–#6~~ ✅ 11 Juni 2026
- ~~heading-hierarchy-standards.md dibuat untuk Project Konten & Copywriting~~ ✅ 11 Juni 2026
- ~~Featured snippet format dioptimasi Artikel #5 & #6~~ ✅ 11 Juni 2026
- ~~Soft CTA ditambahkan ke semua 6 artikel yang sudah terbit~~ ✅ 12 Juni 2026
- ~~Content length audit 3 artikel vs kompetitor~~ ✅ 12 Juni 2026
- ~~Fase 1 On-Page SEO Mendalam — semua 8 topik selesai~~ ✅ 12 Juni 2026
- ~~cwv-technical-audit-onlineumkm-jun2026.md dibuat~~ ✅ 13 Juni 2026
- ~~Core Web Vitals audit homepage & artikel #6~~ ✅ 13 Juni 2026
- ~~CSS Async QUIC.cloud diaktifkan — render-blocking turun 70%~~ ✅ 13 Juni 2026
- ~~Google Tag Manager audit~~ ✅ 13 Juni 2026 — aktif dengan GA4, 13 halaman, dipertahankan
- ~~REST API _fields optimization~~ ✅ 13 Juni 2026 — payload turun ~80%, LCP turun 1 dtk (4,6 → 3,6), skor mobile naik 11 poin (71 → 82)

---

## BAGIAN 12: KEPUTUSAN PENTING YANG SUDAH FINAL

| Keputusan | Pilihan | Catatan |
|---|---|---|
| Plugin SEO | Yoast (tetap) | Tidak perlu migrasi |
| Slug Tentang Kami | tetap `/tentang/` | Jangan diubah |
| Batas meta description | **142 karakter** | Berlaku mulai 3 Juni 2026 |
| Homepage Yoast 2 item merah | DITERIMA sebagai permanent | Tidak perlu dioptimasi lagi |
| Sistem pembayaran klien | DP 50% di muka, pelunasan 50% setelah selesai | Template invoice mengikuti ini |
| Revisi artikel lama | Tunda sampai ada data Search Console | Tunggu 2–3 bulan, baru optimasi berbasis data |
| Soft CTA di artikel mixed intent | WAJIB sebelum FAQ block | Berlaku untuk artikel #8–12 (dan sudah diimplementasi di artikel #1–7) |
| **Yoast scope rule** | **Yoast hanya untuk SEO title, slug, meta description** | Berlaku mulai artikel #6 |
| **Link di artikel** | Internal & external link wajib langsung tertanam di HTML | Tidak boleh placeholder |
| **Screenshot Yoast** | Hanya untuk SEO title, slug, meta desc — kirim hanya jika merah | Berlaku mulai 9 Juni 2026 |
| **Standar artikel** | Master Prompt Artikel Kelas Dunia v1.1 | Wajib untuk semua artikel mulai #6 |
| **Penamaan project** | Gunakan nama lengkap atau nama awal file | Jangan sebut "Project 1/2/3/4/5" |
| **Format link dalam saran artikel** | HTML: `<a href="URL">teks</a>` — bukan markdown | Berlaku mulai 10 Juni 2026 |
| **Tipe profil GBP** | Service Area Business (alamat tersembunyi) | Ronald kerja remote tanpa lokasi tetap — finalisasi 20 Jun 2026 |
| **Nama bisnis dalam teks GBP (deskripsi dll)** | Tulis "Online UMKM" — JANGAN "OnlineUMKM.id" | Google validator deteksi ".id" sebagai pola URL dan menolak teks, ditemukan 20 Jun 2026 |
| **Area layanan GBP** | Medan saja — JANGAN set ke level negara ("Indonesia") | Area terlalu luas melemahkan sinyal local SEO |
| **Nama bisnis kanonik (NAP)** | "Online UMKM" — dipakai di SEMUA channel publik (GBP, WhatsApp, JSON-LD, homepage, Tentang Kami) | Finalisasi 20 Jun 2026 (Topik 21). "OnlineUMKM.id" tetap dipakai HANYA saat merujuk literal nama domain (mis. "nama domain onlineumkm.id menggunakan istilah...") |
| **Model Claude default** | Sonnet untuk semua sesi rutin | Opus hanya untuk analisis sangat kompleks |
| **Heading generic** | DILARANG — "Penutup", "Tips Penting", dll. | Structural fix, boleh diubah kapanpun |
| **Heading over-optimization** | Max 3 heading dengan keyword (variasi natural) | Frasa persis yang sama di 4+ heading = over-opt |
| **H4 di artikel blog** | HINDARI — jadikan paragraf dengan bold | H4 hampir tidak pernah diperlukan |
| **Featured snippet — kalimat pembuka** | Maks 1–2 kalimat sebelum list | Kalimat klarifikasi kritis tetap dipertahankan meski lewati batas 1 kalimat |
| **Content length benchmark** | Selalu cek 3 artikel top kompetitor untuk range yang wajar | Tidak ada angka minimum universal |
| **Freshness artikel evergreen** | Tidak perlu di-refresh kecuali ada info yang tidak akurat | Semua artikel onlineumkm.id = evergreen |
| **JS Defer di Elementor** | JANGAN AKTIFKAN — tidak kompatibel, TBT naik 6x | Berlaku untuk semua site Elementor |
| **CSS Async (QUIC.cloud)** | AMAN untuk Elementor — pertahankan AKTIF | Render-blocking turun 70% |
| **GTM** | PERTAHANKAN — aktif dengan GA4 (G-0MMKSRC1K4), 13 halaman | Audit selesai 13 Juni 2026 |
| **LiteSpeed TTL** | BIARKAN 604800 (1 minggu) — sudah optimal | Berlaku untuk TTL Publik dan TTL REST |
| **REST API _fields** | PERTAHANKAN `&_fields=id,title,excerpt,link,_links` | Payload turun ~80%, LCP turun 1 dtk — JANGAN dihapus |
| **Hamburger menu mobile** | WAJIB punya 3 `<span>` di dalam `<button class="hamburger">` | Tanpa ini CSS `.hamburger span` tidak ada yang dirender — bug ditemukan & diperbaiki 14 Jun 2026 |
| **Tag taxonomy (Tags)** | NOINDEX — "Show Tags in search results" = No di Yoast | Berlaku 14 Jun 2026. Tag tetap dipakai untuk organisasi internal WordPress, tapi `/tag/...` tidak diindeks & dikecualikan dari sitemap. Sitemap turun 31→11 URL |
| **Canonical tags** | TIDAK PERLU setting manual — Yoast sudah self-referencing otomatis | Audit 15 Jun 2026: 4/4 titik rawan duplicate content aman (canonical, redirect domain, GSC report, halaman kategori) |
| **Plugin redirect** | Plugin Redirection — 301 adalah default, tidak perlu pilih tipe manual | Form dasar (Source URL + Target URL) cukup; opsi advanced (tipe redirect lain) ada di ikon gerigi |
| **Slug Artikel #2** | `/kenapa-warung-makan-sepi-padahal-enak/` (terkonfirmasi via wp-admin 15 Jun 2026) | `/kenapa-warung-makan-sepi/` adalah redirect ke slug ini via WordPress `_wp_old_slug` — terpecahkan di Topik 17 (16 Jun 2026) |
| **FAQ block di artikel** | DIPERTAHANKAN — wajib di akhir artikel | Tujuan berubah sejak FAQ rich result dihentikan Google (Mei 2026): bukan lagi untuk accordion SERP, tapi untuk featured snippet paragraph & PAA coverage |
| **Error blok FAQ saat paste ke Block Editor** | Coba "Upayakan pemulihan" dulu. Kalau gagal, hapus blok dan input manual (ketik langsung di editor, bukan paste HTML) | Pola berulang: Artikel #6, #7 (berhasil via pemulihan), Artikel #9 (pemulihan gagal, fallback manual berhasil) |
| **Penanda waktu di judul (tahun, "terbaru")** | Default TIDAK dipakai untuk konten evergreen how-to. Hanya untuk konten yang isinya benar-benar terikat waktu | Lihat Master Prompt v1.3 Bagian 3 |
| **H1 vs SEO Title** | Default sama/searah satu judul. SEO Title boleh dipangkas ringkas dari H1 (bukan hook beda) kecuali eksperimen berbasis data GSC | Lihat Master Prompt v1.3 Bagian 3 |
| **Legacy redirect pada slug baru** | Cek tabel Redirection (Peralatan → Pengalihan) untuk konflik slug SEBELUM publish artikel baru. Kalau slug pernah dipakai untuk rencana lama, hapus rule lama dulu, baru purge cache | Ditemukan di Artikel #9 — slug sempat 301 ke Artikel #1 karena rule redirect lama tersisa dari rencana yang dibatalkan |
| **Cek schema Organization/WebSite** | Gunakan validator.schema.org, BUKAN Rich Results Test | Rich Results Test cuma cek tipe schema yang punya rich result feature (Article, FAQ, Breadcrumb, dll) |
| **Edit homepage di Elementor** | WAJIB cari widget bertipe "HTML" via Navigator/Struktur — JANGAN asal klik area di canvas | Widget "Penyunting Teks" (Text Editor) terlihat mirip tapi merusak CSS/HTML. Ditemukan 19 Jun 2026 setelah regresi berulang |
| **Verifikasi widget HTML benar** | Field harus "Kode HTML" satu kotak polos — BUKAN ada tab Visual/Kode terpisah | Tab Visual/Kode terpisah = tanda widget Text Editor yang salah |
| **File paste ke WordPress** | HANYA konten antara `<!-- wp:html -->` dan `<!-- /wp:html -->` | JANGAN sertakan komentar dokumentasi header file maupun marker wp:html itu sendiri |

---

## BAGIAN 13: PELAJARAN TEKNIS PENTING (JANGAN DIULANGI)

### ⚠️ TEMUAN KRITIS 19 JUNI 2026 — Elementor Punya 2 Widget Mirip yang Bisa Tertukar

**Masalah:** Ronald berulang kali paste kode homepage yang benar (CWV fixes + URL Topik 19), tapi setiap dibuka ulang, perubahan hilang — bahkan sempat memburuk (CSS pecah dengan `<br/>`/`<p>` menyisip, tombol hamburger lenyap total).

**Root cause:** Ronald mengedit widget **"Penyunting Teks" (Text Editor)** Elementor, BUKAN widget **"HTML"** asli homepage. Kedua widget ini tampak mirip di sidebar Elementor — tapi fungsinya beda total:

| Widget | Field di sidebar | Cara memproses kode | Aman untuk paste HTML/CSS/JS mentah? |
|---|---|---|---|
| Penyunting Teks (Text Editor) | "Sunting Penyunting Teks" — punya tab Visual & Kode | Diproses sebagai rich text/WYSIWYG — CSS bisa dipecah jadi paragraf, tag seperti `<button>` bisa dihapus | ❌ TIDAK |
| HTML | "Sunting HTML" — satu field "Kode HTML" polos | Output mentah tanpa diproses sama sekali | ✅ YA |

**Cara pasti menemukan widget HTML yang benar:** Buka **Navigator/Struktur** Elementor (ikon berlapis di toolbar atas) → cari elemen bertipe **HTML** (ikon `</>`) di tree struktur → klik untuk loncat dan edit di sana. Jangan asal klik area homepage di canvas, karena bisa salah kena widget Text Editor yang nyasar di lokasi serupa.

**Cara verifikasi sebelum publish:** Field "Kode HTML" hanya satu kotak kode polos tanpa tab Visual/Kode terpisah. Kalau yang muncul ada tab "Visual" dan "Kode" terpisah, itu Text Editor — salah.

**Dampak ke histori sesi sebelumnya:** Kemungkinan besar penjelasan kenapa fix CWV 15 Juni dan fix hamburger 14 Juni sempat "hilang lagi" di sesi-sesi berikutnya — bukan karena gagal tersimpan, tapi karena sesi edit berikutnya tanpa sadar mengenai widget Text Editor yang salah.

---

### ⚠️ POLA BERULANG — Error Blok Yoast FAQ Saat Paste ke Block Editor

**Gejala:** Setelah paste artikel HTML lengkap (termasuk blok `wp:yoast/faq-block`) ke WordPress Block Editor, blok FAQ menampilkan pesan "Blok ini mengandung konten yang tidak diinginkan atau tidak valid."

**Sudah terjadi 3 kali:** Artikel #6 (Foto Makanan), Artikel #7 (Caption Instagram), dan Artikel #9 (Promosi Online Warung Makan Medan) — pola yang sama persis.

**Solusi utama:** Klik tombol **"Upayakan pemulihan"** di blok yang error. WordPress membaca ulang dan memperbaiki format blok secara otomatis. Tidak perlu notifikasi sukses — kalau blok kembali tampil normal tanpa pesan error, berarti berhasil. Berhasil di Artikel #6 dan #7.

**⚠️ Fallback baru (1 Jul 2026) — Artikel #9:** "Upayakan pemulihan" **GAGAL** untuk pertama kalinya. Ronald menyelesaikan dengan **input manual** (hapus blok yang error, lalu ketik ulang pertanyaan dan jawaban satu per satu langsung di Block Editor menggunakan blok FAQ Yoast dari awal, bukan paste blok jadi). Solusi manual ini terbukti berhasil sebagai langkah kedua kalau "Upayakan pemulihan" tidak mempan.

**Urutan solusi yang direkomendasikan ke depan:**
1. Klik "Upayakan pemulihan" dulu (berhasil di 2 dari 3 kasus)
2. Kalau gagal, hapus blok FAQ yang error, lalu input manual: tambah blok FAQ Yoast baru dari awal, ketik tiap pertanyaan/jawaban langsung di editor (jangan paste HTML utuh untuk blok ini)

**Kemungkinan penyebab:** Format JSON di atribut blok (`{"questions":[...]}` atau `{"faqs":[...]}`) kadang tidak ter-parse sempurna saat proses copy-paste dari sumber ke WordPress, terutama untuk FAQ dengan banyak pertanyaan (5+). Belum ada bukti definitif, tapi pola dan kedua solusinya sudah terverifikasi.

---

| Situasi | Yang Benar |
|---|---|
| WordPress `<p><style>` | BIARKAN — tidak bisa dicegah, tidak ada dampak SEO |
| Edit homepage blok fix script | Ctrl+A → Delete → Paste baru — jangan tumpuk |
| WordPress hapus onclick | Pakai addEventListener — jangan onclick inline |
| Cache setelah edit besar | Bersihkan via hPanel Hostinger DAN LiteSpeed Cache → Toolbox → Purge All |
| Plugin Ally | Jangan install — tidak kompatibel Elementor |
| Screenshot Yoast | Hanya untuk SEO title, slug, meta desc |
| GitHub — edit file | Navigate ke branch `main` dulu |
| Judul artikel dengan angka | Angka di judul harus sesuai isi artikel |
| Alt text gambar | Keyword di alt text maksimal 1–2 gambar per artikel |
| Link di artikel | Internal dan external link WAJIB langsung tertanam di HTML |
| Standar konten baru | Mulai artikel #6: wajib pakai Master Prompt Artikel Kelas Dunia v1.1 |
| **Em dash audit** | Scan SELURUH artikel — em dash bisa muncul di mana saja |
| **Em dash dalam saran konten** | Claude TIDAK BOLEH menggunakan em dash dalam saran teks apapun |
| **Format link dalam saran artikel** | HTML: `<a href="URL">teks anchor</a>` — JANGAN format markdown |
| **Audit internal link** | Verifikasi dua arah: keluar DAN masuk |
| **Internal link ke homepage** | Tidak dihitung untuk standar minimum 3 link ke halaman konten |
| **Akurasi di percakapan panjang** | Mulai percakapan baru untuk tugas berbeda |
| **Heading generic** | "Penutup", "Tips Penting", "Apa, sih?" = sinyal lemah ke Google. Ganti ke deskriptif. |
| **Heading over-optimization** | Frasa keyword persis di 4+ heading = over-opt. Gunakan variasi natural. |
| **H4 di artikel** | Hampir selalu sinyal konten terlalu dalam. Jadikan paragraf dengan bold. |
| **Structural fix vs revisi konten** | Structural fix = boleh kapanpun. Revisi konten/optimasi = tunggu data GSC. |
| **H2 duplikat H1** | Redundant dari sisi SEO. Untuk artikel baru: H2 harus menambah dimensi baru. |
| **Tanda baca di akhir heading** | Heading adalah label, bukan kalimat — tidak pakai titik, koma, titik dua. |
| **Emoji di heading** | Google bisa kesulitan membaca teks di sekitar emoji — hindari di heading artikel. |
| **Featured snippet — kalimat pembuka** | Pangkas sampai maks 1–2 kalimat sebelum list. Kalimat bernilai nyata TIDAK dipangkas. |
| **Featured snippet vs kejelasan artikel** | Snippet adalah bonus, bukan tujuan. Kejelasan artikel selalu menang. |
| **Content length = fungsi intent** | Benchmark dari 3 artikel top kompetitor — bukan angka universal. |
| **Over-length artikel** | Evaluasi setelah GSC (time on page, bounce). Jangan potong tanpa data. |
| **Freshness evergreen** | Jangan rewrite artikel sehat hanya demi "terlihat fresh" — Google cukup pintar. |
| **JS Defer di Elementor** | JANGAN — TBT naik drastis karena JS Elementor dieksekusi dalam blok besar setelah defer |
| **CSS Async via QUIC.cloud** | AMAN — generate Critical CSS inline, sisa CSS dimuat belakangan. Efektif untuk Elementor |
| **Bottleneck berpindah setelah fix** | CSS Async berhasil → render-blocking turun → REST API jadi bottleneck. REST API fix → LCP turun → base64 images jadi bottleneck. |
| **REST API blog section** | SUDAH DIOPTIMASI — `_fields=id,title,excerpt,link,_links` mengurangi payload ~80%. JANGAN hapus parameter ini. |
| **PageSpeed = cold cache simulation** | PageSpeed selalu test dari kondisi cache kosong. TTL cache tidak mempengaruhi angka PageSpeed — yang mempengaruhi adalah ukuran payload dan arsitektur halaman. |
| **GTM "tidak diberi tag" ≠ GTM tidak aktif** | Halaman arsip (/blog) tidak butuh tag = normal. Harus cek dashboard GTM → Tags untuk konfirmasi ada tidaknya tag aktif. |
| **Base64 images di HTML** | Logo 3x + hero image sebagai base64 membuat HTML sangat berat. Browser tidak bisa cache gambar secara terpisah. Ganti dengan URL aktual dari media library. |
| **Skor 82 mobile Elementor** | Sudah di atas rata-rata (kebanyakan 50–75). Mencapai 90+ dengan Elementor butuh perubahan arsitektur lebih besar (lazy load, base64 → URL, dll). |
| **PageSpeed — versi Indonesia** | Opportunities = Insight; Load CSS Async = Muat CSS Secara Asinkron; JS Defer = Tangguhkan Pemuatan JS |
| **Lab data PageSpeed berfluktuasi** | Angka bisa berbeda antar test. Tren lebih penting dari satu angka |
| **INP tidak muncul di site baru** | INP = field data, butuh traffic Chrome nyata. TBT = proxy yang tersedia di lab data |
| **Mobile-first indexing** | Sejak Maret 2018, Google index versi MOBILE sebagai basis utama ranking — bukan desktop. Content parity (teks, alt text, internal link, schema) wajib identik di mobile & desktop. |
| **GSC Mobile Usability report** | SUDAH DIHAPUS Google sejak Desember 2023. Jangan cari laporan ini di Search Console — gunakan PageSpeed Insights tab Mobile + Chrome DevTools (Ctrl+Shift+M) sebagai gantinya. |
| **CSS siap tapi HTML kosong** | CSS `.hamburger span{...}` sudah benar dan menunggu, tapi `<button>` tidak punya `<span>` di dalamnya = tidak ada yang dirender. Lighthouse/PageSpeed tidak flag ini — harus dicek visual manual di mobile. Tombol tetap berfungsi (klik tetap jalan) meski tampilannya kosong. |
| **robots.txt `Disallow:` kosong** | Artinya semua boleh dirayapi — beda total dengan `Disallow: /` yang block seluruh situs. onlineumkm.id sehat, tidak ada yang ke-block tanpa sengaja. |

---

## BAGIAN 14: KAPAN BOLEH REVISI ARTIKEL LAMA

### 🚩 FLAG 1 — Revisi Prematur Tanpa Data

**Yang benar:** CTR optimization harus berbasis data. Revisi prematur = buang waktu.

**Pengecualian — boleh dikerjakan kapanpun:**
- Structural fix: heading generic, heading dengan tanda baca, broken link
- Faktual error atau info outdated
- Tambah internal link ke artikel baru yang relevan (additive)
- Featured snippet format: pangkas kalimat redundan sebelum list (jika tidak mengorbankan nilai konten)
- Content length: pangkas konten redundan HANYA setelah ada data GSC yang mendukung

**Cara Claude mengingatkan:**
> "Artikel ini baru [X] minggu. Belum ada data GSC yang cukup. Lebih efektif publish artikel baru dulu."

---

### 🚩 FLAG 3 — Fokus Perkakas, Lupa Tujuan Bisnis

**Cara Claude mengingatkan:**
> "Ini berguna, tapi apakah ini mendekatkan kita ke klien pertama minggu ini? Kalau tidak, boleh ditunda — artikel #[X] lebih prioritas."

---

### 🚩 FLAG 4 — Optimasi CTR Tanpa Data

**Yang benar:** Validasi dari data — impresi tinggi + CTR rendah = baru perlu direvisi.

---

### ✅ Kapan Revisi Artikel Boleh Dilakukan

| Kondisi | Aksi |
|---|---|
| Artikel < 2 bulan | Jangan revisi — tunggu data |
| Artikel > 2 bulan, impressi tinggi, CTR < 3% | Revisi title & meta saja |
| Artikel > 2 bulan, impressi rendah | Evaluasi apakah keyword salah |
| Faktual error / info outdated | Boleh revisi kapanpun |
| Additive (konten baru yang belum ada) | Boleh kapanpun |
| Structural fix (heading, broken link) | Boleh kapanpun |
| Featured snippet format (kalimat redundan sebelum list) | Boleh kapanpun — selama tidak mengorbankan nilai konten |
| Content length (potong konten redundan) | Setelah ada data GSC — time on page dan bounce rate |

---

## BAGIAN 15: REFERENSI — KOMPETITOR ARTIKEL #7

Dipakai sebagai pembanding saat menulis Artikel #7 (30 Template Caption Instagram Warung Makan):

| Kompetitor | Gap yang Ditemukan | Cara onlineumkm.id Mengisi Gap |
|---|---|---|
| Paxel — 70 Kata-Kata Promosi Makanan | Caption generik, tidak spesifik platform, tidak spesifik jenis makanan | Tabel adaptasi caption per jenis makanan (nasi/lauk, mie/bakso/soto, minuman, snack) |
| TokoElmanna — 30 Ide Konten Instagram Cafe Restoran | Ide konten untuk cafe/restoran kelas menengah-atas, bukan warung kecil; tidak ada template siap pakai | 30 template caption siap copy-paste, dirancang khusus untuk warung makan kecil dengan budget dan waktu terbatas |
| GloriaFood — Restaurant Social Media Post Captions | Konten berbahasa Inggris, konteks pasar internasional | Bahasa Indonesia natural, konteks lokal Indonesia (hashtag lokal, momen hari besar Indonesia) |

---

## BAGIAN 16: FASE BELAJAR SEO — STATUS (20 Juni 2026, update v6.1)

| Fase | Status | Catatan |
|---|---|---|
| Fase 0 — Dasar | ✅ Selesai | Sudah dikuasai |
| Fase 1 — On-Page SEO Mendalam | ✅ Selesai | Semua 8 topik selesai — 12 Juni 2026 |
| Fase 2 — Technical SEO | ✅ Selesai | Topik 9-19 selesai (10/10) — 18 Jun 2026 |
| Fase 3 — Local SEO | 🟡 Sedang | Topik 20-21/7 selesai — dimulai 20 Jun 2026 |
| Fase 4 — Content SEO & Authority | ⬜ Belum | — |
| Fase 5 — Off-Page SEO | ⬜ Belum | — |
| Fase 6 — SEO untuk Klien | ⬜ Belum | — |

### Detail Topik Fase 3

| # | Topik | Status | Tgl |
|---|---|---|---|
| 20 | Google Business Profile — setup lengkap | ✅ Selesai | 20 Jun 2026 |
| 21 | NAP consistency audit | ✅ Selesai | 20 Jun 2026 |
| 22 | Local citation building Indonesia | ⬜ Belum | — |
| 23 | Review management & templates | ⬜ Belum | — |
| 24 | Local keyword strategy | ⬜ Belum | — |
| 25 | LocalBusiness schema di homepage | ⬜ Belum | — |
| 26 | Competitor local analysis | ⬜ Belum | — |

### Insight Penting dari Fase 3 (Topik yang Sudah Selesai)

**Topik 21 (NAP Consistency Audit):** Audit 4 sumber (footer website, JSON-LD schema, GBP, WhatsApp Business) menemukan address & phone sudah konsisten sejak awal, tapi name terbelah dua: "OnlineUMKM.id" dipakai di homepage footer dan halaman Tentang Kami, sementara WordPress Site Title asli, GBP, WhatsApp Business, dan JSON-LD schema semua pakai "Online UMKM". Investigasi lanjutan (fetch live site) mengungkap temuan struktural: footer custom homepage dengan NAP lengkap **TIDAK global** — cuma ada di widget HTML homepage, sementara halaman artikel lain pakai footer default tema Astra yang otomatis menampilkan "Online UMKM" (dari WordPress Site Title), tanpa alamat/telepon. Ini memperkuat bahwa "Online UMKM" adalah identitas struktural situs. Fix dieksekusi: 17 lokasi (7 di homepage: disclaimer bar, alt text logo navbar, avatar role, bio paragraf, jujur box, footer copyright, footer disclaimer; 10 di Tentang Kami: hero h2, hero subtitle, disclaimer box, tombol WA founder, label kisah, 2 paragraf cerita founder, field Nama Usaha tabel legalitas, legal disclaimer, tombol CTA bawah) diganti ke "Online UMKM" — referensi literal "nama domain onlineumkm.id" sengaja dipertahankan karena itu domain asli, bukan nama brand. Keputusan final: "Online UMKM" jadi nama kanonik di semua channel publik (lihat Bagian 12).

**Topik 20 (Google Business Profile):** Profil GBP ternyata sudah ada dan ter-klaim (125 interaksi pelanggan) sejak sebelumnya, dibuat serampangan — sesi jadi audit + perbaikan, bukan setup dari nol. Perbaikan utama: diubah ke Service Area Business (alamat rumah ibu Ronald disembunyikan dari publik, karena kerja remote tanpa lokasi tetap), area layanan dipangkas dari salah-setting "Indonesia" nasional ke Medan saja, jam buka disamakan dengan WhatsApp Business untuk konsistensi. Ditemukan quirk teknis: nama bisnis "OnlineUMKM.id" di deskripsi ditolak validator Google karena ".id" terdeteksi sebagai pola URL — solusi pakai "Online UMKM" tanpa domain. Menu Layanan ternyata terpisah dari panel Informasi Bisnis utama. Foto bisnis dan kredit iklan Google Ads sengaja ditunda (foto karena belum ada materi otentik, kredit karena belum waktunya). Detail lengkap di Bagian 2a.

### Detail Topik Fase 2

| # | Topik | Status | Tgl |
|---|---|---|---|
| 9 | Core Web Vitals (LCP, CLS, INP) | ✅ Selesai | 13 Jun 2026 |
| 10 | Kecepatan loading WordPress (cache, REST API, JS) | ✅ Selesai | 13 Jun 2026 |
| 11 | Mobile-first indexing | ✅ Selesai | 14 Jun 2026 |
| 12 | Sitemap.xml & robots.txt | ✅ Selesai | 14 Jun 2026 |
| 13 | Schema markup lanjutan (LocalBusiness, Service, Review) | ✅ Selesai | 14 Jun 2026 |
| 14 | Google PageSpeed Insights — cara baca | ✅ Selesai | 13 Jun 2026 |
| 15 | Canonical tags & duplicate content | ✅ Selesai | 15 Jun 2026 |
| 16 | Crawl errors & 404 fix | ✅ Selesai | 15 Jun 2026 |
| 17 | Redirect 301 vs 302 lanjutan | ✅ Selesai | 16 Jun 2026 |
| 18 | Structured data JSON-LD manual | ✅ Selesai | 18 Jun 2026 |
| 19 | Screaming Frog — site crawl audit | ✅ Selesai | 18 Jun 2026 |

### Insight Penting dari Fase 2 (Topik yang Sudah Selesai)

**Topik 9 & 14 (Core Web Vitals + PageSpeed):**
CLS dan TBT onlineumkm.id sudah bagus sejak awal. LCP 4,6 dtk jadi satu-satunya masalah. JS Defer gagal karena Elementor — pelajaran penting bahwa page builder kompleks punya constraint optimasi. CSS Async via QUIC.cloud berhasil menurunkan render-blocking 70%. Bottleneck pertama teridentifikasi: REST API blog section.

**Topik 10 (Kecepatan Loading WordPress):**
REST API dioptimasi dengan _fields parameter — payload turun ~80% (87 KB → ~15-20 KB), LCP turun 1 dtk (4,6 → 3,6), skor mobile naik 11 poin (71 → 82). GTM diaudit: aktif dengan GA4, dipertahankan. LiteSpeed TTL sudah 1 minggu — tidak perlu diubah. Bottleneck berikutnya teridentifikasi: base64 images di HTML (logo 3x + hero image).

**Topik 11 (Mobile-first Indexing):**
Konsep mobile-first indexing (sejak Maret 2018, Google index versi mobile sebagai basis utama) dan content parity dipahami. Koreksi penting: laporan "Kegunaan Seluler" di GSC sudah dihapus Google Desember 2023 — pengganti yang relevan adalah PageSpeed Insights tab Mobile dan Chrome DevTools (sudah dipakai sejak Topik 9-10). Praktik content parity di homepage (nav, hero, blog section) lolos — tapi ditemukan bug nyata: tombol hamburger di homepage kosong karena HTML `<button>` tidak punya `<span>` di dalamnya, padahal CSS sudah siap mewarnai hijau. Bug ini tidak terdeteksi PageSpeed/Lighthouse karena bukan masalah performa — hanya kelihatan lewat cek visual manual di mobile. Fix dieksekusi (tambah 3 `<span>`) dan diverifikasi langsung — ikon hamburger hijau sekarang tampil normal.

**Topik 12 (Sitemap.xml & robots.txt):**
robots.txt onlineumkm.id sehat (`Disallow:` kosong = semua boleh dirayapi, sitemap terdaftar). Audit `sitemap_index.xml` via GSC menemukan 31 URL: 7 post, 2 page, 2 category, dan 20 tag. Tag-tag ini mayoritas duplikat/sinonim (contoh: artikel GoFood punya 6 tag berbeda — gofood, go-food, gobiz, tips-daftar-gofood, dst). Setiap tag = 1 halaman arsip otomatis, sehingga 1 artikel bisa punya 6 halaman thin/duplicate yang bersaing untuk keyword yang sama (cannibalization) dan membuang crawl budget. Fix: Yoast Settings > Categories & tags > Tags > "Show Tags in search results" = No — satu toggle, langsung exclude semua `/tag/...` dari sitemap dan index. Hasil: `post_tag-sitemap.xml` hilang total, sitemap turun dari 31 menjadi 11 URL.

**Topik 13 (Schema Markup Lanjutan):**
Schema/JSON-LD dipahami sebagai enabler rich result (bukan ranking factor langsung). Yoast sudah auto-generate Organization/WebSite/WebPage, Article, BreadcrumbList, dan FAQPage (dari FAQ block). Verifikasi via Rich Results Test: artikel #6 = 3/3 valid (Article, Breadcrumb, FAQ), homepage = 1/1 valid (Breadcrumb — Organization/WebSite tidak tercover tool ini by design). LocalBusiness dan Service schema ditunda ke Fase 3 / sampai ada halaman jasa terpisah; Review/AggregateRating ditunda sampai ada klien dan testimoni asli (tidak boleh fabrikasi). **Temuan besar:** Google resmi menghentikan FAQ rich result (accordion Q&A di SERP) per 7 Mei 2026, melanjutkan pembatasan yang sudah dimulai Agustus 2023 (saat itu dibatasi ke situs gov/health). FAQ block tetap dipertahankan di artikel, tapi tujuannya bergeser dari "dapat accordion SERP" ke "cover PAA & peluang featured snippet paragraph".

**Topik 15 (Canonical Tags & Duplicate Content):**
Duplicate content dipahami sebagai masalah "Google bingung pilih versi mana yang utama" — bukan penalti seperti yang sering disangka. Canonical tag (`<link rel="canonical">`) memberi tahu Google versi resmi suatu halaman, dan Yoast sudah pasang ini otomatis (self-referencing) di setiap halaman tanpa setting tambahan. Audit 4 titik rawan duplicate content paling umum di WordPress — http/www vs https, trailing slash, parameter URL, dan halaman kategori — semuanya aman di onlineumkm.id: canonical artikel #6 bersih dan self-referencing, redirect domain ke https tanpa www berjalan otomatis, GSC tidak melaporkan duplicate/canonical issue, dan halaman kategori menampilkan excerpt (bukan full content). Pelajaran kunci: hasil audit yang "bersih" adalah hasil valid — tujuan audit memastikan tidak ada masalah, bukan harus selalu menemukan masalah.

**Topik 18 (Structured Data JSON-LD Manual):**
LocalBusiness schema dibuat manual dan dipasang via WPCode Lite (Header & Footer) — gratis, tanpa install. Elementor Custom Code dan Yoast Redirects keduanya Premium, tidak tersedia. Validasi Google Rich Results Test dari live URL: 3 schema valid (Breadcrumb dari Yoast + LocalBusiness baru + Organization dari Yoast). "Masalah non-kritis" = recommended fields belum diisi (openingHours, image, geo) — normal, tidak membatalkan validasi. Aturan kunci: jangan fabrikasi data — kalau jam buka belum ditetapkan, jangan isi openingHours.

**Topik 19 (Site Crawl Audit):**
Seobility dipakai menggantikan Screaming Frog karena komputer kantor (tidak bisa install aplikasi desktop). Hasil audit: 75% on-page score, 20 halaman di-crawl, 12 indexable, 73 masalah (mayoritas informasional/false positive). Tiga temuan dieksekusi: (1) H1 duplikat di /tentang/ — tag h1 di HTML widget diubah ke h2 dan CSS selector `.ab-hero h1` diupdate ke `.ab-hero h2` agar tampilan tidak berubah; (2) 6 URL lama di homepage (2x `/blog` tanpa trailing slash, 2x slug lama Artikel 1, 2x slug lama Artikel 3) diupdate ke URL benar; (3) external link gobiz.co.id (redirect tidak aman ke gofoodmerchant.co.id) diupdate langsung ke `https://gofoodmerchant.co.id/` di artikel. wa.me redirect warnings = false positive (normal behavior WhatsApp link). Category/archive H1 issues = halaman auto-generated WordPress, bukan masalah nyata. Fase 2 selesai sempurna.

**Topik 17 (Redirect 301 vs 302 Lanjutan):**
301 = permanen + link equity mengalir (~90–99%); 302 = sementara + link equity tidak diteruskan. Kesalahan paling umum di lapangan: pakai 302 untuk perpindahan permanen = link equity dari backlink lama hilang diam-diam. Redirect chain (A→B→C) = kebocoran equity + memperlambat loading, Google rekomendasikan maks 1 lompatan. Mystery redirect Artikel #2 (`/kenapa-warung-makan-sepi/` → `/kenapa-warung-makan-sepi-padahal-enak/`) terpecahkan: bukan dari plugin Redirection, bukan dari Yoast Redirects (fitur Premium, tidak tersedia di free version) — sumbernya adalah **WordPress `_wp_old_slug`**, fitur core bawaan WordPress yang otomatis menyimpan slug lama sebagai post meta dan menangani redirect 301 ke slug baru setiap kali slug post diubah. Verifikasi via whatsmydns.net: 1 hop clean (301 → 200), tidak ada chain, tidak ada tindakan diperlukan.

**Topik 16 (Crawl Errors & 404 Fix):**
Konsep crawling (Google membaca halaman) vs indexing (Google menyimpannya untuk hasil pencarian) dipahami — halaman bisa di-crawl tapi sengaja tidak diindeks. Audit GSC Page Indexing report menemukan 5 kategori "Penyebab halaman tidak diindeks", semuanya diinvestigasi sampai ke URL spesifik: (1) `/blog-umkm/` 404 karena slug archive blog berubah jadi `/blog/` — fix nyata dengan redirect 301 via plugin Redirection, diverifikasi langsung di browser; (2) `/author/perkasacuan3gmail-com/` "halaman dengan pengalihan" — ternyata BUKTI konfigurasi benar (WordPress author archive sengaja di-redirect ke homepage); (3) `/tag/instagram-bisnis/` "di-crawl, tidak diindeks" — status transisi normal setelah noindex tag diterapkan di Topik 12, Google masih memproses; (4) `/kenapa-warung-makan-sepi/` "kesalahan pengalihan" — ternyata data basi dari crawl 28 Mei, live test 15 Jun mengonfirmasi halaman sehat ("URL tersedia untuk Google", FAQ + Breadcrumb valid), reindex diminta; (5) "ditemukan, tidak diindeks" — riwayat 10-15 halaman (kemungkinan sisa sitemap lama 31 URL sebelum Topik 12) sudah resolve ke 0 dengan validasi lulus 6 Jun. Pelajaran terbesar: tidak semua status "tidak diindeks" berarti masalah — beberapa adalah bukti sistem bekerja sesuai rencana (redirect, noindex) atau sekadar data lama yang belum di-refresh.

**Bonus temuan Topik 16 — redirect tersembunyi TERPECAHKAN di Topik 17:**
Investigasi #4 awalnya membuat slug Artikel #2 di handoff (`/kenapa-warung-makan-sepi-padahal-enak/`) terlihat salah, karena live test GSC pada `/kenapa-warung-makan-sepi/` (tanpa "-padahal-enak") menunjukkan halaman valid dengan FAQ + Breadcrumb. Setelah dicek langsung di wp-admin, slug `/kenapa-warung-makan-sepi-padahal-enak/` terkonfirmasi BENAR (post ID 129, Telah Terbit) — tabel di Bagian 3 sudah benar sejak awal. Penjelasannya: `/kenapa-warung-makan-sepi/` adalah redirect ke slug asli, dikonfirmasi dua arah — live test GSC mengikuti redirect dan melaporkan halaman tujuan, dan tes browser langsung Ronald juga otomatis lompat ke `/kenapa-warung-makan-sepi-padahal-enak/`. Redirect berjalan normal (diverifikasi Topik 17). **Sumber redirect:** WordPress `_wp_old_slug` — bukan Yoast Redirects (Premium) dan bukan plugin Redirection. Verifikasi whatsmydns.net: 1 hop (301 → 200), clean.

### Detail Topik Fase 1

| # | Topik | Status | Tgl |
|---|---|---|---|
| 1 | Title tag & meta description lanjutan | ✅ Selesai | 6 Jun 2026 |
| 2 | Search intent mendalam (4 jenis + mixed intent) | ✅ Selesai | 6 Jun 2026 |
| 3 | Keyword density vs semantic SEO + LSI konsep | ✅ Selesai | 10 Jun 2026 |
| 4 | LSI & NLP keywords — praktik riset | ✅ Selesai | 10 Jun 2026 |
| 5 | Internal linking strategy + crawl budget | ✅ Selesai | 10 Jun 2026 |
| 6 | Heading hierarchy lanjutan | ✅ Selesai | 11 Jun 2026 |
| 7 | Featured snippet optimization | ✅ Selesai | 11 Jun 2026 |
| 8 | Content-length & freshness | ✅ Selesai | 12 Jun 2026 |

---

## BAGIAN 17: JADWAL CEK GSC ARTIKEL

| Artikel | Terbit | Cek Pertama | Status Kalender |
|---|---|---|---|
| #1 Pillar | 9 Mei 2026 | **9 Jul 2026** | ✅ Di Google Calendar |
| #2 Warung Sepi | 22 Mei 2026 | **22 Jul 2026** | ✅ Ditambahkan 11 Jun 2026 — slug `/kenapa-warung-makan-sepi-padahal-enak/` (terkonfirmasi via wp-admin 15 Jun). `/kenapa-warung-makan-sepi/` adalah redirect ke slug ini via `_wp_old_slug`, berfungsi normal (lihat Bagian 16) |
| #3 GBP | 25 Mei 2026 | **25 Jul 2026** | ✅ Ditambahkan 11 Jun 2026 |
| #4 WhatsApp | 29 Mei 2026 | **29 Jul 2026** | ✅ Ditambahkan 11 Jun 2026 |
| #5 GoFood | 3 Jun 2026 | **3 Agt 2026** | ✅ Ditambahkan 11 Jun 2026 |
| #6 Foto Makanan | 9 Jun 2026 | **9 Agt 2026** | ✅ Ditambahkan 11 Jun 2026 |
| #7 Caption Instagram | 17 Jun 2026 | **17 Agt 2026** | ✅ Ditambahkan 21 Jun 2026. Deskripsi event diperbarui 25 Jun 2026 — catatan gap link lama dihapus, gap sudah ditutup |
| #8 SEO Warung Makan Medan | 25 Jun 2026 | **25 Agt 2026** | ✅ Ditambahkan 25 Jun 2026 — event Google Calendar dibuat langsung di sesi ini |
| #9 Promosi Warung Makan Medan | 1 Jul 2026 | **31 Agt 2026** | ✅ Ditambahkan 1 Jul 2026 — event Google Calendar dibuat langsung di sesi ini |
| #10 Promosi Warung Makan Surabaya | 9 Jul 2026 | **8 Sep 2026** | ✅ Ditambahkan 9 Jul 2026 — event Google Calendar dibuat langsung di sesi ini. Deskripsi event mencatat soft CTA belum ditambahkan ke post live |
| #2 khusus (slug fix) | 22 Mei 2026 | — | ✅ Reindex diminta 10 Jun 2026 |
| #2 khusus (live test redirect error) | — | — | ✅ Live test + tes browser lolos 15 Jun 2026 (Topik 16) — redirect `/kenapa-warung-makan-sepi/` → slug asli berfungsi normal |

**Syarat implementasi revisi:** Setiap cek GSC — jika impresi tinggi + CTR < 3%, revisi title & meta menggunakan draft di Bagian 3.

---

*Master Handoff v6.8 — Diperbarui 9 Juli 2026*
*Perubahan dari v6.7:*
*- Header: versi v6.8, tanggal dan deskripsi diperbarui*
*- Bagian 3: Catatan CTA Artikel #8, #9, #10 dikoreksi jadi ✅ selesai (dikonfirmasi Ronald)*
*- Bagian 7a: Tabel status CTA Section — semua 10 artikel sekarang ✅ Selesai. Drift proses resmi ditutup*
*- Bagian 11: Item retrofit CTA Section dipindah dari Prioritas Tinggi ke ✅ SELESAI*
*Versi berikutnya: v6.9 — setelah Artikel #11 (Bandung) dibuat atau terbit*
