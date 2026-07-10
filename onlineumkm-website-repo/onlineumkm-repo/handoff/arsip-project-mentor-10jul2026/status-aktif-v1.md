# OnlineUMKM.id — Status Aktif
**Versi:** Status v1.0 (hasil pemecahan Master Handoff v6.8)
**Diperbarui:** 10 Juli 2026
**Pasangan file:** `aturan-referensi-v1.md` (aturan teknis, keputusan final, pelajaran — statis, jarang berubah)
**Arsip lengkap:** GitHub `handoff/` (versi v6.8 dan sebelumnya)

## PETUNJUK PENGGUNAAN
File ini berisi status terkini, pending items, jadwal, dan roadmap. Ini SATU-SATUNYA file yang diupdate tiap sesi.
Untuk aturan Yoast, template CTA, arsitektur homepage, keputusan final, dan pelajaran teknis → baca `aturan-referensi-v1.md`.
Detail artikel lengkap ada di GitHub `articles/` — tidak diulang di sini.

---

## 1. STATUS WEBSITE (per 9 Juli 2026)

| Komponen | Status |
|---|---|
| Homepage live | ✅ |
| Blog section — auto-update via REST API (_fields aktif) | ✅ |
| Halaman `/tentang/` live | ✅ — foto profil Ronald ⚠️ belum diupload |
| Plugin Redirection | ✅ Aktif |
| Yoast Homepage SEO | ✅ Hijau | Keterbacaan 🟠 (diterima, final) |
| Yoast `/blog/` | 🔴 Merah (normal untuk posts archive) |
| Yoast `/tentang/` SEO | 🟢 Hijau | Keterbacaan 🔴 (pending fix) |
| LiteSpeed: CSS Async ✅ / JS Defer ❌ (final) / TTL 604800 ✅ | ✅ |
| GTM + GA4 (G-0MMKSRC1K4) | ✅ Aktif, 13 halaman |
| Hamburger menu mobile | ✅ Live di widget HTML yang benar |
| GitHub repo tersync | ✅ — artikel-07 & 08 belum ditrack |
| Sitemap 11 URL, robots.txt sehat, canonical sehat | ✅ |
| Schema markup (Article, Breadcrumb, FAQ, LocalBusiness) | ✅ Valid |
| Klien aktif | ❌ Belum ada |

### Google Business Profile (setup 20 Juni 2026)
- Tipe: Service Area Business, alamat tersembunyi. Area layanan: Medan saja.
- Nama publik: **Online UMKM** (bukan "OnlineUMKM.id" — lihat aturan NAP di file referensi)
- Deskripsi ✅ (692/750), daftar layanan ✅, jam buka ✅ (= WhatsApp Business)
- ⏳ Foto bisnis: menunggu materi otentik. ⏳ Kredit Google Ads Rp 3jt: ditunda.

### Core Web Vitals (13 Juni 2026)
| Halaman | LCP | Skor Mobile |
|---|---|---|
| Homepage | 3,6 dtk 🟠 | 82 |
| Artikel (#6) | 2,9 dtk 🟠 | 89 |

**Bottleneck berikutnya:** base64 images di HTML homepage (logo 3x + hero) → ganti ke URL media library. Detail audit: `cwv-technical-audit-onlineumkm-jun2026-v2.md`.

---

## 2. STATUS ARTIKEL (per 9 Juli 2026)

**Total terbit: 10.** Semua sudah pakai CTA Section berwarna (dikonfirmasi 9 Jul 2026 — drift proses ditutup).

| # | Judul singkat | Slug | Terbit | Yoast |
|---|---|---|---|---|
| 1 | Cara Promosi Warung Makan Online (PILLAR) | `/cara-promosi-warung-makan-online/` | 9 Mei | ✅ |
| 2 | Kenapa Warung Makan Sepi | `/kenapa-warung-makan-sepi-padahal-enak/` | 22 Mei | ✅ |
| 3 | Cara Daftar Google Business Profile | `/cara-daftar-google-business-profile/` | 25 Mei | ✅ |
| 4 | Promosi lewat WhatsApp | `/cara-promosi-warung-makan-lewat-whatsapp/` | 29 Mei | ✅ |
| 5 | Cara Daftar GoFood | `/cara-daftar-gofood/` | 3 Jun | ✅ |
| 6 | Cara Foto Makanan Pakai HP | `/cara-foto-makanan-pakai-hp/` | 9 Jun | ✅ |
| 7 | 30 Template Caption Instagram | `/template-caption-instagram-warung-makan/` | 17 Jun | ✅ |
| 8 | SEO Warung Makan Lokal Medan | `/seo-warung-makan-lokal-medan/` | 25 Jun | ✅ |
| 9 | Promosi Online Warung Makan Medan | `/promosi-online-warung-makan-medan/` | 1 Jul | ✅ |
| 10 | Promosi Online Warung Makan Surabaya | `/promosi-online-warung-makan-surabaya/` | 9 Jul | ✅ |

**Aturan wajib artikel baru:** internal link ke Pillar (#1), Master Prompt v1.3, CTA Section langsung di draf, cek tabel Redirection sebelum publish. Detail aturan → file referensi.

### Catatan yang masih actionable
- **#1 Pillar:** heading over-optimization + content length 2.629 kata → tahan sampai data GSC (cek 9 Jul 2026).
- **#2:** content length 1.763 kata (2x kompetitor) → kandidat pangkas setelah GSC 22 Jul 2026.
- **#10:** belum dikonfirmasi apakah paste blok FAQ mulus atau butuh "Upayakan pemulihan".

### Peta internal link — ringkasan gap
- Gap lama (tidak dipaksakan): #3→#4, #3→#5, #4→#5, #6→#4.
- Gap #7, #8, #9 sudah ditutup. **#10 baru** → tutup via link dari Artikel #11 (Bandung).
- Matriks lengkap: arsip v6.8 di GitHub `handoff/`.

### Draft revisi title & meta (BELUM DIIMPLEMENTASI — tunggu GSC)
Syarat: impresi tinggi + CTR < 3%. Cek pertama 9 Juli 2026.

| # | Title Baru | Meta Baru |
|---|---|---|
| 1 | Cara Promosi Warung Makan Online: 5 Langkah Terbukti Efektif | Belum tahu harus mulai dari mana? Ini 5 langkah promosi warung makan online yang bisa kamu coba sendiri hari ini. |
| 2 | Kenapa Warung Makan Sepi Padahal Enak? 5 Sebab & Solusinya | Warung enak tapi sepi? Bukan soal rasa, tapi orang tidak tahu warungmu ada. Ini 5 sebab yang sering diabaikan dan cara mengatasinya. |
| 3 | Cara Daftar Google Business Profile Warung Makan [Gratis] | Warung kamu belum muncul di Google Maps? Daftar GBP gratis dalam 15 menit, dari pendaftaran, verifikasi, sampai profil aktif. |
| 4 | Promosi Warung Makan lewat WhatsApp: Efektif Tanpa Ganggu | Takut pelanggan merasa terganggu? Promosi WhatsApp yang benar justru bikin mereka menunggu pesan berikutnya. Ini caranya. |
| 5 | Cara Daftar GoFood untuk Warung Makan dari Nol sampai Aktif | Mau warungmu masuk GoFood? Ikuti 5 langkah di GoBiz, siapkan dokumen wajib, dan tips agar pesanan pertama cepat masuk. Gratis. |

---

## 3. CONTENT CALENDAR — JADWAL MENDATANG

| # | Target | Judul | Keyword | Intent | Prioritas |
|---|---|---|---|---|---|
| 11 | 14–20 Jul | Promosi Online Warung Makan Bandung | promosi online warung makan Bandung | Mixed | 🔴 Tinggi |
| 12 | 21–27 Jul | Promosi Online Warung Makan Jakarta | promosi online warung makan Jakarta | Mixed | 🟡 Sedang |

**Checklist artikel #11:** CTA Section langsung di draf + link ke Artikel #10 (Surabaya) + cek tabel Redirection sebelum publish + Master Prompt v1.3 + heading-hierarchy-standards.md.

---

## 4. PENDING ITEMS

### Prioritas Tinggi
- [ ] **Upload foto Ronald ke Tentang Kami** — alt: `Ronald Huson pendiri jasa website UMKM OnlineUMKM Medan`
- [ ] **Foto bisnis GBP** — tunggu materi otentik (bukan foto stok). Opsi: foto Ronald kerja dengan onlineumkm.id di layar.
- [ ] **Artikel #11 Bandung** (target 14–20 Jul) — via Project Konten & Copywriting. Checklist di Bagian 3.
- [ ] **Isi referensi-keuangan-bisnis.md** — harga jasa & target keuangan (Project Keuangan Freelance)
- [ ] **Base64 images homepage** → ganti URL media library (perbaiki LCP tersisa)

### Prioritas Menengah
- [ ] Tentang Kami Keterbacaan — pecah paragraf panjang + kata transisi
- [ ] Review judul & meta artikel #1–6 — implementasi setelah data GSC (draft di Bagian 2)
- [ ] Artikel #2 content length — evaluasi setelah GSC 22 Jul 2026
- [ ] Heading artikel #1 & #2 — tahan sampai data GSC
- [ ] Kredit Google Ads Rp 3jt — revisit saat topik Google Ads masuk kurikulum
- [ ] Tambah `articles/artikel-07.html` & `artikel-08.html` ke GitHub repo

### Prioritas Rendah
- [ ] Internal link "Baca juga" di homepage
- [ ] Portofolio / demo website
- [ ] Pantau portal UMKM pemerintah (smesta.go.id, kemenkopukm.go.id)
- [ ] Pantau `/tag/...` di GSC — harus pindah ke "Excluded by noindex tag"
- [ ] Gap internal link lama — isi hanya jika muncul konteks natural

### Selesai terakhir (9 Juli 2026)
- ✅ CTA Section terpasang di #8, #9, #10 — semua 10 artikel konsisten, drift proses ditutup
- ✅ Artikel #10 Surabaya terbit + gap link #9 ditutup + GSC reminder dibuat (8 Sep 2026)

*Riwayat lengkap item selesai (Mei–Juli 2026): arsip v6.8 di GitHub `handoff/`.*

---

## 5. FASE BELAJAR SEO — STATUS

| Fase | Status |
|---|---|
| 0 — Dasar | ✅ Selesai |
| 1 — On-Page SEO Mendalam (8 topik) | ✅ Selesai 12 Jun 2026 |
| 2 — Technical SEO (Topik 9–19) | ✅ Selesai 18 Jun 2026 |
| 3 — Local SEO (Topik 20–26) | 🟡 Sedang — 2/7 selesai |
| 4 — Content SEO & Authority | ⬜ Belum |
| 5 — Off-Page SEO | ⬜ Belum |
| 6 — SEO untuk Klien | ⬜ Belum |

### Fase 3 — Topik tersisa
| # | Topik | Status |
|---|---|---|
| 22 | Local citation building Indonesia | ⬜ Berikutnya |
| 23 | Review management & templates | ⬜ |
| 24 | Local keyword strategy | ⬜ |
| 25 | LocalBusiness schema di homepage | ⬜ (schema dasar sudah terpasang via WPCode — Topik 18) |
| 26 | Competitor local analysis | ⬜ |

*Insight lengkap Topik 1–21: arsip v6.8 + handoff sesi di Project Belajar SEO.*

---

## 6. JADWAL CEK GSC ARTIKEL

Syarat revisi: impresi tinggi + CTR < 3% → revisi title & meta pakai draft di Bagian 2.

| Artikel | Terbit | Cek Pertama | Kalender |
|---|---|---|---|
| #1 Pillar | 9 Mei | **9 Jul 2026** | ✅ |
| #2 Warung Sepi | 22 Mei | **22 Jul 2026** | ✅ |
| #3 GBP | 25 Mei | **25 Jul 2026** | ✅ |
| #4 WhatsApp | 29 Mei | **29 Jul 2026** | ✅ |
| #5 GoFood | 3 Jun | **3 Agt 2026** | ✅ |
| #6 Foto Makanan | 9 Jun | **9 Agt 2026** | ✅ |
| #7 Caption Instagram | 17 Jun | **17 Agt 2026** | ✅ |
| #8 SEO Medan | 25 Jun | **25 Agt 2026** | ✅ |
| #9 Promosi Medan | 1 Jul | **31 Agt 2026** | ✅ |
| #10 Promosi Surabaya | 9 Jul | **8 Sep 2026** | ✅ |

---

*Status Aktif v1.0 — dipecah dari Master Handoff v6.8 pada 10 Juli 2026.*
*Update file ini di akhir tiap sesi. Jika tembus 300 baris: pindahkan konten selesai/lama ke arsip GitHub, jangan buat file ketiga.*
