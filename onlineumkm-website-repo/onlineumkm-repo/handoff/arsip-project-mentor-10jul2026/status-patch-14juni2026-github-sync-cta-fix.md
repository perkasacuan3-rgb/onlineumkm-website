# Status Patch — 14 Juni 2026 (GitHub Sync Lengkap + CTA Section + Bug Fix + Audit Homepage)
**Versi:** Patch v5.4 (final)
**Dibaca bersama:** mentor-master-handoff-onlineumkm-v5_4.md
**Menggantikan:** Versi awal patch ini (tanpa audit homepage dan main-block sync)
**Topik sesi:** CTA Section selesai semua 6 artikel, sinkronisasi GitHub lengkap (3 file homepage + 6 artikel), bug fix CTA Artikel #2, audit HTML homepage

---

## FOKUS SESI INI

1. Tambah CTA Section (Custom HTML, background `#00BFA5`) ke Artikel #1–#5 — sebelumnya hanya Artikel #6 yang punya CTA
2. Sinkronisasi pertama kali repo GitHub dengan kondisi WordPress terkini
3. Update `fix-script.html` di GitHub — `_fields` parameter (sebelumnya tertinggal 7 hari dari WordPress)
4. Update `main-block.html` di GitHub — hamburger 3 spans + tanggal (sebelumnya tertinggal 8 hari)
5. Backup HTML lengkap semua 6 artikel ke GitHub (sebelumnya file placeholder kosong)
6. Bug ditemukan & diperbaiki: CTA Section Artikel #2 rusak — HTML terpotong, FAQ section menyatu ke kotak CTA
7. Audit menyeluruh HTML homepage — semua elemen dicek, hasilnya bersih

---

## STATUS CTA SECTION — SEMUA ARTIKEL SELESAI ✅

| # | Artikel | Judul CTA (H3) | Status |
|---|---|---|---|
| 1 | Cara Promosi Warung Makan Online | "Siap Mulai Promosi Online Warungmu?" | ✅ |
| 2 | Kenapa Warung Makan Sepi Padahal Enak | "Warungmu Enak tapi Masih Sepi? Kita Bisa Bantu." | ✅ (sempat rusak, sudah diperbaiki) |
| 3 | Cara Daftar Google Business Profile | "Mau Warungmu Mudah Ditemukan di Google Maps?" | ✅ |
| 4 | Cara Promosi lewat WhatsApp | "Mau Promosi WhatsApp Warungmu Lebih Terstruktur?" | ✅ |
| 5 | Cara Daftar GoFood | "Mau Warungmu Masuk GoFood Tanpa Bingung?" | ✅ |
| 6 | Cara Foto Makanan Pakai HP | "Butuh Bantuan Mengeksekusi Strategi Ini?" (dibuat sesi 11 Jun, kustom topik) | ✅ |

**Format CTA standar (Artikel #1–#5):**
- Background `#00BFA5`, padding 40px 30px, border-radius 8px
- Tombol 1: "Konsultasi Gratis via WhatsApp" (solid putih)
- Tombol 2: "Lihat Layanan Kami" (outline putih, link ke `/#layanan`)
- Posisi: Custom HTML block sebelum Yoast FAQ block
- Wajib ada komentar `<!-- END CTA SECTION -->` — bukan kosmetik, ini penanda penutup struktur (lihat Pelajaran Teknis)

---

## GITHUB REPO — SINKRONISASI LENGKAP ✅

**Repo:** `perkasacuan3-rgb/onlineumkm-website`

```
onlineumkm-website-repo/onlineumkm-repo/
├── README.md
├── articles/
│   ├── artikel-01-cara-promosi-warung-makan-online.html    ✅ 14/06/2026
│   ├── artikel-02-warung-makan-sepi-padahal-enak.html      ✅ 14/06/2026
│   ├── artikel-03-cara-daftar-google-business-profile.html ✅ 14/06/2026
│   ├── artikel-04-cara-promosi-lewat-whatsapp.html         ✅ 14/06/2026
│   ├── artikel-05-cara-daftar-gofood.html                  ✅ 14/06/2026
│   └── artikel-06-cara-foto-makanan-pakai-hp.html          ✅ 14/06/2026 (baru dibuat)
├── homepage/
│   ├── fix-script.html   ✅ 14/06/2026 — _fields parameter sinkron
│   └── main-block.html   ✅ 14/06/2026 — hamburger 3 spans + tanggal
├── handoff/
└── notes/
```

### Status Sinkronisasi per File

| File | Sebelum | Sesudah | Perubahan |
|---|---|---|---|
| `fix-script.html` | Versi 06/06 tanpa `_fields` | Versi 13/06 dengan `_fields` | REST API payload turun ~80% |
| `main-block.html` | Versi 06/06 tanpa hamburger spans | Versi 14/06 dengan 3 `<span>` | Hamburger mobile tampil 3 garis hijau |
| `artikel-01` s/d `artikel-05` | Placeholder kosong | HTML lengkap + info CTA di header | Backup fungsional |
| `artikel-06` | Belum ada | Dibuat baru + header lengkap | File baru di repo |

### Catatan Penting tentang Backup Artikel
Judul artikel (`post_title`) **tidak** ikut ter-copy dari WordPress Code Editor — WordPress menyimpan judul terpisah di database. Judul sudah didokumentasikan di komentar header setiap file sebagai referensi.

### Workflow Token GitHub (PAT) — Standar untuk Sesi Berikutnya

1. Buat token classic di GitHub → Settings → Developer settings → Personal access tokens
2. Scope: **`repo`** saja
3. Expiration: **7 hari**
4. Setelah sesi selesai: **hapus token** segera
5. Token tidak pernah disimpan di file atau memory — hanya dipakai sekali per sesi

---

## FIX-SCRIPT.HTML — SINKRONISASI

**Sebelum:** GitHub versi 06/06/2026 — belum ada `_fields` parameter
**Sesudah:** GitHub versi 13/06/2026 — sinkron dengan WordPress live

```
fetch('/wp-json/wp/v2/posts?per_page=3&_embed=true&_fields=id,title,excerpt,link,_links')
```

**Catatan trade-off yang disadari:** karena `_fields` tidak memuat `content`, estimasi waktu baca di blog card homepage sekarang default **3 menit** untuk semua artikel (sebelumnya dihitung dari word count konten asli). Ini konsekuensi yang sudah diterima demi payload lebih kecil — tidak perlu "diperbaiki" kecuali ada keluhan akurasi.

---

## MAIN-BLOCK.HTML — SINKRONISASI

**Sebelum:** GitHub versi 06/06/2026 — hamburger button kosong tanpa markup span
**Sesudah:** GitHub versi 14/06/2026 — 3 `<span>` ditambahkan + tanggal header diperbarui

```html
<!-- SEBELUM -->
<button id="oumkm-hamburger" class="hamburger" aria-label="Menu"></button>

<!-- SESUDAH -->
<button id="oumkm-hamburger" class="hamburger" aria-label="Menu"><span></span><span></span><span></span></button>
```

**Diverifikasi:** screenshot mobile menunjukkan ikon hamburger 3 garis hijau tampil normal ✅

---

## BUG FIX: CTA SECTION ARTIKEL #2

### Gejala
Di halaman live `/kenapa-warung-makan-sepi-padahal-enak/`, kotak CTA hijau dan section FAQ tampil menyatu jadi satu kotak besar. Tombol kedua hanya bertuliskan "Lihat" tanpa border, tanpa teks "Layanan Kami".

### Akar Masalah
Custom HTML block CTA terpotong di tengah — tag `<a>` kedua dan `<div>` pembungkus tidak pernah ditutup:

```html
<!-- SEBELUM (rusak) -->
    <a href="https://onlineumkm.id/#layanan" style="...">
      Lihat
<!-- /wp:html -->
```

Karena `<div>` CTA tidak ter-close, browser menganggap semua elemen setelahnya (termasuk heading dan FAQ block) masih berada *di dalam* kotak CTA — sehingga background hijau "menelan" section berikutnya.

### Fix
Lengkapi HTML yang terpotong:

```html
<!-- SESUDAH (benar) -->
    <a href="https://onlineumkm.id/#layanan" style="...">
      Lihat Layanan Kami
    </a>
  </div>

</div>
<!-- END CTA SECTION -->
```

Diperbaiki di **WordPress** (Custom HTML block, Edit kode) dan **GitHub backup** — keduanya sudah terverifikasi live.

---

## AUDIT HTML HOMEPAGE — HASIL LENGKAP (14 Juni 2026)

Audit dilakukan terhadap seluruh HTML Blok Utama yang di-copy dari WordPress Code Editor.

### ✅ Lolos (Tidak Ada Masalah)

| Elemen | Status | Catatan |
|---|---|---|
| CSS custom properties | ✅ | `--navy`, `--green`, `--teal` dll. konsisten |
| Sticky nav | ✅ | `z-index:9999`, backdrop-filter blur aktif |
| Mobile responsive | ✅ | Breakpoint 768px dan 820px |
| Hamburger mobile | ✅ | 3 spans hijau, handler di script utama |
| Hero section | ✅ | H1, badge, trust rows, 2 tombol |
| Layanan cards | ✅ | 4 kartu, featured card dengan gradient |
| Tentang section | ✅ | Avatar, bio, skill tags, jujur-box |
| Proses/Cara Kerja | ✅ | 5 langkah berurutan |
| Blog auto-update | ✅ | `id="blog-grid-dynamic"` ada, fallback cards tersedia |
| FAQ accordion | ✅ | 6 item, struktur `.faq-q` + `.faq-a` benar |
| CTA section | ✅ | Dark background, gradient, 2 tombol |
| Footer | ✅ | 3 kolom, disclaimer bar atas + bawah |
| WhatsApp links | ✅ | Semua URL benar `wa.me/6287791808667` |
| Scroll anchors | ✅ | `#layanan`, `#proses`, `#blog`, `#faq`, `#kontak` |
| Disclaimer hukum | ✅ | Bar atas + footer disclaimer lengkap |

### ⚠️ Temuan Non-Kritis (tidak breaking, untuk kesadaran)

**1. Dead code di script Blok Utama (~1.5 KB)**
Fungsi `oumkmFaq()`, `oumkmWA()`, `oumkmScroll()` didefinisikan tapi tidak pernah dipanggil — karena WordPress menghapus `onclick` inline. Semua interaksi sudah ditangani Fix Script via `addEventListener`. Fungsi-fungsi ini jadi dead code. Tidak perlu dihapus sekarang — risikonya rendah dan menghapusnya butuh testing menyeluruh.

**2. URL fallback blog card tidak cocok dengan slug aktual**
Fallback card artikel #1 mengarah ke `/promosi-online-warung-makan-medan/` — slug asli artikel #1 adalah `/cara-promosi-warung-makan-online/`. Hanya terlihat kalau REST API gagal (jarang). Risiko rendah, bisa diperbaiki kapan saja.

**3. Base64 images (sudah di pending list)**
Logo muncul 3x sebagai base64 (nav, hero card, footer) + hero image juga base64. Total ~20 KB ditambahkan ke HTML. Sudah tercatat di pending items handoff v5.4 untuk diganti URL Media Library.

### ❌ Tidak Ada Bug Aktif
Audit selesai tanpa menemukan bug breaking. Homepage berfungsi normal di desktop dan mobile.

---

## PELAJARAN TEKNIS BARU

| Situasi | Yang Benar |
|---|---|
| Custom HTML block — section berikutnya "tertelan" ke dalam kotak section sebelumnya | Cek tag penutup `</div>` — kemungkinan ada `<div>` yang tidak di-close, biasanya akibat copy-paste terpotong |
| Komentar `<!-- END CTA SECTION -->` hilang dari Custom HTML block | Sinyal kuat bahwa kode terpotong — komentar ini berfungsi sebagai penanda struktur, bukan sekadar dokumentasi |
| Backup GitHub vs WordPress live berbeda | Selalu verifikasi visual di halaman live dulu sebelum asumsi mana yang benar — bisa jadi keduanya salah dengan cara berbeda |
| File placeholder GitHub kosong | Cek isi file sebelum asumsi sudah terisi — placeholder dengan instruksi tetap "valid" secara git tapi tidak berguna sebagai backup |
| Artikel dengan CTA kustom (beda dari template generik) | Bukan otomatis error — bisa jadi penyesuaian topik yang sengaja dibuat di sesi sebelumnya (contoh: Artikel #6) |
| WordPress Code Editor vs live site bisa berbeda | HTML yang di-copy dari Code Editor mungkin belum mencerminkan perubahan terakhir jika blok belum di-save ulang — selalu verifikasi di halaman live dan screenshot mobile |
| Dead code di Blok Utama (fungsi tanpa pemanggil) | Tidak breaking tapi menambah payload — catat dan bersihkan saat ada maintenance besar, jangan saat ada perubahan kecil |

---

## PENDING ITEMS — UPDATE

### Selesai Sesi Ini
- [x] ~~CTA Section Artikel #1–#5~~ ✅ Semua 6 artikel kini punya CTA
- [x] ~~Sinkronisasi GitHub pertama kali~~ ✅ Semua file tersinkron (fix-script + main-block + 6 artikel)
- [x] ~~fix-script.html GitHub tertinggal~~ ✅ Sinkron dengan versi `_fields` 13/06/2026
- [x] ~~main-block.html GitHub tertinggal~~ ✅ Hamburger spans + tanggal 14/06/2026
- [x] ~~Bug CTA Artikel #2~~ ✅ Diperbaiki di WordPress dan GitHub
- [x] ~~Audit HTML homepage~~ ✅ Bersih, tidak ada bug aktif

### Masih Pending
- [ ] Upload foto Ronald ke halaman Tentang Kami (Yoast oranye, 4 item merah)
- [ ] Artikel #7 — Template Caption Instagram (16–22 Jun)
- [ ] Base64 images homepage → ganti dengan URL Media Library (memperbaiki LCP)
- [ ] Dead code cleanup di Blok Utama (fungsi oumkmFaq/oumkmWA/oumkmScroll yang tidak terpakai)
- [ ] Fallback blog card URL — update slug artikel #1 dari `/promosi-online-warung-makan-medan/` ke slug aktual

---

## PANDUAN PENEMPATAN FILE LINTAS PROJECT

| File | Project Website | Project Konten & Copywriting | Project Mentor |
|---|---|---|---|
| `status-patch-14juni2026-github-sync-cta-fix.md` (file ini) | ✅ Wajib | ✅ Berguna — status CTA & pelajaran | ✅ Wajib — pelajaran debugging + GitHub workflow |
| `mentor-master-handoff-onlineumkm-v5_4.md` | ✅ Tetap | ⚠️ Opsional | ✅ Wajib — dokumen utama |
| `cwv-technical-audit-onlineumkm-jun2026.md` | ✅ Wajib | ❌ Tidak perlu | ✅ Berguna — pendukung Topik 9 & 14 |
| `perplexity_keyword.txt` | ⚠️ Opsional | ✅ Wajib | ❌ Tidak perlu |
| `status-patch-12juni2026-featured-image-fix.md` | ✅ Tetap | ❌ Tidak perlu | ✅ Berguna — contoh diagnosa REST API |

**Prinsip umum:**
- **Project Website**: kumpulkan semua status patch + master handoff + audit teknis — ini jadi "single source of truth" konfigurasi situs
- **Project Konten & Copywriting**: cukup file yang menyangkut konten (CTA, keyword, status artikel) — tidak perlu detail token GitHub atau audit CWV
- **Project Mentor**: master handoff selalu wajib (akan terus berevolusi v5.x), ditambah status patch yang punya nilai *pembelajaran* — bukan sekadar log perubahan

---

*Patch v5.4 (final) — 14 Juni 2026*
*Perubahan untuk dimasukkan ke Master Handoff v5.5:*
*- Bagian 3/16: Topik 10 (REST API _fields) terverifikasi tersinkron antara WordPress live dan GitHub*
*- Bagian 4: main-block.html tanggal GitHub diperbarui ke 14/06/2026*
*- Bagian 11: CTA Section semua 6 artikel → ✅ Selesai*
*- Bagian 11: Tambah 3 pending baru (dead code cleanup, fallback URL, base64 replacement)*
*- Bagian 13: 7 pelajaran teknis baru (debugging HTML terpotong, dead code, verifikasi Code Editor vs live)*
*- Bagian baru: GitHub repo structure + workflow token PAT + status sinkronisasi per file*
*- Bagian baru: Hasil audit HTML homepage lengkap*
*- Bagian baru: Panduan penempatan file lintas project*
*Versi berikutnya: v5.5 — setelah Artikel #7 terbit atau foto Tentang Kami selesai*
