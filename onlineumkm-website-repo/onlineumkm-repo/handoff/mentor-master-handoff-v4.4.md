# Mentor Operasional OnlineUMKM.id — Master Handoff Status, Sistem & Roadmap
**Versi:** Master v4.4
**Dibuat:** 1 Juni 2026
**Diperbarui:** 5 Juni 2026
**Menggantikan:** v4.3 dan semua handoff sebelumnya
**Cakupan:** Status lengkap website, artikel, sistem Claude, semua 5 projects, dan roadmap konten

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
- **Pekerjaan utama:** Data entry & customer service (shift panjang, rotating pagi/malam)
- **Waktu tersedia untuk bisnis:** Terbatas — di sela-sela shift kerja
- **Cara belajar terbaik:** Contoh konkret, perbandingan, analogi. Langkah demi langkah.
- **Claude plan:** Pro ($20/bulan)

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

## BAGIAN 2: STATUS WEBSITE KESELURUHAN (5 Juni 2026)

| Komponen | Status |
|---|---|
| Homepage live | ✅ |
| Blog section — auto-update via REST API | ✅ Aktif |
| Halaman Tentang Kami `/tentang/` | ✅ Live — bio terpasang, internal links aktif |
| Foto profil Ronald di Tentang Kami | ⚠️ Belum diupload |
| Plugin Redirection | ✅ Terpasang dan aktif |
| Yoast Homepage — tab SEO | ✅ **HIJAU** (icon smiley hijau) |
| Yoast Homepage — tab Keterbacaan | 🟠 Oranye |
| Yoast Blog `/blog/` — tab SEO | 🔴 Merah (normal untuk posts archive) |
| Yoast Blog `/blog/` — tab Keterbacaan | 🟠 Oranye |
| Yoast Tentang Kami — skor SEO keseluruhan | 🟢 Hijau |
| Yoast Tentang Kami — masalah detail | 🔴 Ada masalah — lihat Bagian 5 |
| Yoast Tentang Kami — tab Keterbacaan | 🔴 Merah |
| 10 Skills Claude | ✅ Semua aktif |
| 5 Projects Claude | ✅ Semua aktif |
| Klien aktif | ❌ Belum ada |

### Detail Yoast Homepage (FINAL — tidak perlu dioptimasi lagi)

**SEO Tab:**
| Item | Status |
|---|---|
| Tautan ke luar | ✅ Hijau |
| Frasa kunci dalam atribut alt gambar | ✅ Hijau |
| Gambar | ✅ Hijau |
| Tautan internal | ✅ Hijau |
| Kepadatan frasa kunci | ✅ Hijau (8 kali) |
| Panjang frasa kunci | ✅ Hijau |
| Frasa kunci dalam subjudul | ✅ Hijau |
| Frasa kunci di awal | 🔴 **PERMANENT** — WordPress limitation |
| Frasa kunci pada judul SEO | 🟠 Oranye — acceptable |

**Keterbacaan Tab:**
| Item | Status |
|---|---|
| Kalimat pasif | ✅ Hijau |
| Kalimat berurutan | ✅ Hijau |
| Sebaran sub judul | ✅ Hijau |
| Panjang paragraf | ✅ Hijau |
| Panjang kalimat | ✅ Hijau |
| Kata transisi | 🔴 **PERMANENT** — WordPress limitation |

**⚠️ PENTING: Jangan coba optimasi 2 item merah di atas lagi.**
Keduanya adalah permanent limitation (lihat Bagian 13).

---

## BAGIAN 3: STATUS ARTIKEL (5 Juni 2026)

**Total terbit: 5 artikel**

| # | Judul Aktual di Website | Slug | Terbit | Yoast SEO | Yoast Baca |
|---|---|---|---|---|---|
| 1 | Cara Promosi Warung Makan Online: Panduan Lengkap untuk UMKM | `/cara-promosi-warung-makan-online/` | 9 Mei 2026 | ✅ | ✅ |
| 2 | Kenapa Warung Makan Sepi Padahal Enak? Ini Jawabannya | `/kenapa-warung-makan-sepi-padahal-enak/` | 22 Mei 2026 | ✅ | ✅ |
| 3 | Cara Daftar Google Business Profile untuk Warung Makan, Gratis dan Mudah | `/cara-daftar-google-business-profile/` | 25 Mei 2026 | ✅ | ✅ |
| 4 | Cara Promosi Warung Makan lewat WhatsApp yang Efektif dan Tidak Ganggu | `/cara-promosi-warung-makan-lewat-whatsapp/` | 29 Mei 2026 | ✅ | ✅ |
| 5 | Cara Daftar GoFood untuk Warung Makan: Panduan dari Nol | `/cara-daftar-gofood/` | 3 Jun 2026 | ✅ | ✅ |

### Artikel #1 — Pillar Page
URL: `https://onlineumkm.id/cara-promosi-warung-makan-online/`
Focus keyword: `cara promosi warung makan online`
**Semua artikel baru wajib internal link ke pillar page ini.**

---

## BAGIAN 4: ARSITEKTUR TEKNIS HOMEPAGE

### Struktur 2 Blok (PENTING — Jangan Salah Edit)

| Blok | Isi | Cara Edit |
|---|---|---|
| Blok HTML Utama | Seluruh halaman: CSS, nav, hero, sections, footer, script orisinal | Edit hati-hati via tab Kode |
| Blok Fix Script | Semua event listener dan interaktivitas | Selalu Ctrl+A → Delete → Paste baru |

### Aturan Wajib
- WordPress **selalu menghapus** atribut `onclick` saat save — jangan pakai onclick inline
- Semua interaksi pakai `addEventListener` via blok fix script
- Hamburger handler **hanya boleh ada di script utama** — jangan duplikasi
- Blog section pakai `id="blog-grid-dynamic"` — auto-update via REST API
- Publish artikel baru = otomatis muncul di homepage, tanpa edit kode
- **JANGAN hapus `<p>` dari `<style>`** — WordPress akan kembalikan setiap save

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

**URL:** `/tentang/`
**Focus keyword:** `jasa website UMKM`
**SEO Title:** Tentang OnlineUMKM.id | Jasa Website & SEO UMKM Medan
**Meta Desc:** OnlineUMKM.id adalah jasa website dan SEO lokal berbasis di Medan, melayani UMKM seluruh Indonesia. Kenali Ronald Huson dan misi kami.
*(134 karakter — di bawah batas 142)*
**Slug:** tentang *(jangan diubah — akan merusak semua nav links)*

**Status konten:**
- Bio Versi Ringkas — ✅ sudah di-paste
- Foto Ronald — ⚠️ **Belum diupload**
- Internal links terpasang ✅

**Yoast SEO skor keseluruhan:** 🟢 Hijau
**Yoast Keterbacaan:** 🔴 Merah

**Masalah Tentang Kami yang masih pending:**

| Masalah | Solusi |
|---|---|
| Foto profil belum ada | Upload foto Ronald, alt: `Ronald Huson pendiri jasa website UMKM OnlineUMKM Medan` |
| Frasa kunci dalam alt gambar | Terselesaikan otomatis setelah foto diupload |
| Panjang paragraf >150 kata | Pecah paragraf panjang jadi 2 paragraf |
| Kata transisi 22% | Tambah transisi di paragraf bio |

---

## BAGIAN 6: HALAMAN BLOG

**URL:** `/blog/`
**Yoast SEO:** 🔴 Merah (normal untuk posts archive — tidak bisa diperbaiki)
**Yoast Keterbacaan:** 🟠 Oranye

---

## BAGIAN 7: ATURAN YOAST — LENGKAP & TERBARU

### Meta Description
| Aturan | Ketentuan |
|---|---|
| **Batas karakter** | **Maksimal 142 karakter** |
| Mengandung keyword | Wajib |
| Elemen persuasif | Wajib |

### Heading & Keyword
- Minimal 30% dari semua heading (H2+H3+H4) mengandung keyword atau sinonim
- Yoast versi terbaru menghitung **semua level heading**
- Untuk artikel banyak H3 → tambahkan keyword di H3

### Alt Text Gambar
- Keyword di alt text **maksimal 1–2 gambar per artikel**
- Lebih dari itu → Yoast beri peringatan oranye

### Format HTML Wajib per Artikel
- `<hr>` antara setiap section H2
- Minimal 2 gambar dengan caption dan alt text relevan
- Minimal 3 internal link per artikel
- FAQ block wajib di bagian akhir — format Yoast FAQ block
- **H2 terpisah wajib sebelum FAQ block**
- Tidak ada onclick inline

### Gaya Penulisan
- Em dash / en dash: DILARANG
- Kata "Berikutnya": TIDAK dikenali Yoast sebagai transisi
- Pembuka terlarang: "Di era digital ini", "Dalam persaingan yang semakin ketat", "Tentu saja"
- Tone: **"kamu"**
- Panjang paragraf: maksimal 150 kata
- Subheading: setiap 300 kata harus ada H2 atau H3

---

## BAGIAN 8: SISTEM CLAUDE — 10 SKILLS AKTIF

| # | Skill | Domain |
|---|---|---|
| 1 | `konteks-bisnis-umkm` | Identitas & konteks bisnis onlineumkm.id |
| 2 | `bisnis-marketing` | Analisis & perencanaan strategis |
| 3 | `copywriting` | Menulis konten & copy |
| 4 | `seo` | Audit & optimasi SEO (Yoast) |
| 5 | `wordpress-teknis` | Error, plugin, tema, hosting, Gutenberg |
| 6 | `saas-ecosystem-umkm` | Setup & maintenance SaaS tools klien |
| 7 | `keuangan` | Keuangan pribadi & bisnis freelance |
| 8 | `digital-marketing` | Eksekusi kampanye: ads, analytics, sosmed |
| 9 | `brainstorm` | Ideation & pemecahan masalah kreatif |
| 10 | `counsel` | Pengambilan keputusan & saran |
| + | `stop-slop-indonesia` | Companion otomatis — semua tulisan Indonesia |

**Plugin SEO:** Yoast (jangan sarankan migrasi ke RankMath kecuali diminta)
**MCP aktif:** Gmail, Google Calendar, Google Drive
**Connector tersedia tapi belum diintegrasikan ke workflow:** GitHub

---

## BAGIAN 9: PROJECTS CLAUDE — 5 AKTIF

| # | Nama Project | Status | File yang Ada |
|---|---|---|---|
| 1 | onlineumkm.id — Website | ✅ Aktif | Homepage files + handoff |
| 2 | Klien & Proposal | ✅ Aktif | Template WA, brief form klien, template proposal 1 halaman |
| 3 | Konten & Copywriting | ✅ Aktif | Keyword research (perplexity_keyword.txt) + handoff + content calendar |
| 4 | Keuangan Freelance | ✅ Aktif | budget-bulanan-template.xlsx, tracker-keuangan-bisnis.xlsx, template-invoice.xlsx, referensi-keuangan-bisnis.md, handoff |
| 5 | Belajar SEO & Digital Marketing | ✅ Aktif | progress-tracker-belajar.xlsx, roadmap-belajar-seo.md, handoff |

### Project 2 — Klien & Proposal: Aset yang Sudah Dibuat
- ✅ Template balasan WhatsApp (untuk calon klien masuk)
- ✅ Form brief klien (8 pertanyaan onboarding)
- ✅ Template proposal penawaran 1 halaman

### Project 4 — Keuangan Freelance: Aset yang Sudah Dibuat
- ✅ `budget-bulanan-template.xlsx` — perencanaan bulanan dengan target vs aktual
- ✅ `tracker-keuangan-bisnis.xlsx` — 3 sheet: Log Transaksi, Proyek Klien, Pajak Bulanan
- ✅ `template-invoice.xlsx` — invoice siap kirim ke klien
- ✅ `referensi-keuangan-bisnis.md` — harga jasa, biaya operasional, target keuangan (perlu diisi)

### Project 5 — Belajar SEO & Digital Marketing: Aset yang Sudah Dibuat
- ✅ `progress-tracker-belajar.xlsx` — 44 topik, 3 sheet: Progress, Sertifikasi, Tools
- ✅ `roadmap-belajar-seo.md` — kurikulum 6 fase + digital marketing + sertifikasi gratis

---

## BAGIAN 10: CONTENT CALENDAR — RINGKASAN

**File lengkap:** `content-calendar-onlineumkm-update-1.md` (ada di Project 3)

### Sudah Terbit (5 artikel)
| # | Judul | Terbit |
|---|---|---|
| 1 (Pillar) | Cara Promosi Warung Makan Online | 9 Mei 2026 |
| 2 | Kenapa Warung Makan Sepi Padahal Enak | 22 Mei 2026 |
| 3 | Cara Daftar Google Business Profile | 25 Mei 2026 |
| 4 | Cara Promosi Warung Makan lewat WhatsApp | 29 Mei 2026 |
| 5 | Cara Daftar GoFood untuk Warung Makan | 3 Jun 2026 |

### Jadwal Mendatang (7 artikel)
| # | Target | Judul | Keyword | Prioritas |
|---|---|---|---|---|
| 6 | 9–15 Jun | Cara Foto Makanan Pakai HP biar Terlihat Enak | cara foto makanan pakai HP | 🔴 Tinggi |
| 7 | 16–22 Jun | 30 Template Caption Instagram Warung Makan | template caption Instagram warung makan | 🟡 Sedang |
| 8 | 23–29 Jun | SEO Warung Makan Lokal Medan | SEO warung makan lokal Medan | 🔴 Tinggi |
| 9 | 30 Jun–6 Jul | Promosi Online Warung Makan Medan: Panduan Lengkap | promosi online warung makan Medan | 🔴 Tinggi |
| 10 | 7–13 Jul | Promosi Online Warung Makan Surabaya | promosi online warung makan Surabaya | 🟡 Sedang |
| 11 | 14–20 Jul | Promosi Online Warung Makan Bandung | promosi online warung makan Bandung | 🟡 Sedang |
| 12 | 21–27 Jul | Promosi Online Warung Makan Jakarta | promosi online warung makan Jakarta | 🟢 Rendah |

---

## BAGIAN 11: PENDING ITEMS (5 Juni 2026)

### Prioritas Tinggi
- [ ] **Upload foto Ronald ke Tentang Kami** — alt: `Ronald Huson pendiri jasa website UMKM OnlineUMKM Medan`
- [ ] **Artikel #6** — Cara Foto Makanan (9–15 Jun) — via Project 3
- [ ] **Isi referensi-keuangan-bisnis.md** — lengkapi harga jasa & target keuangan (Project 4)
- [ ] **Mulai Fase 1 SEO** — topik pertama: Search Intent Mendalam (Project 5)

### Prioritas Menengah
- [ ] **Tentang Kami Keterbacaan** — pecah paragraf panjang + tambah kata transisi
- [ ] **Integrasikan GitHub connector** ke workflow yang relevan (backup code, homepage HTML)

### Prioritas Rendah
- [ ] Alt text gambar homepage (logo & hero image)
- [ ] Internal link "Baca juga" di homepage
- [ ] Portofolio / demo website
- [ ] Pantau portal UMKM pemerintah (smesta.go.id, kemenkopukm.go.id)

### ✅ SELESAI (5 Juni 2026 — tidak perlu dikerjakan lagi)
- ~~Sistem dapat klien (3 aset: template WA, brief form, proposal)~~ ✅
- ~~Setup Project 4 — Keuangan Freelance~~ ✅
- ~~Setup Project 5 — Belajar SEO & Digital Marketing~~ ✅
- ~~Homepage "frasa kunci di awal"~~ — WordPress permanent limitation
- ~~Homepage "kata transisi"~~ — WordPress permanent limitation

---

## BAGIAN 12: KEPUTUSAN PENTING YANG SUDAH FINAL

| Keputusan | Pilihan | Catatan |
|---|---|---|
| Plugin SEO | Yoast (tetap) | Tidak perlu migrasi |
| Skill ai-prompting | Dibatalkan | Output tercapai tanpa ini |
| Model SaaS | Jasa setup & maintenance | Lebih realistis fase awal |
| Slug Tentang Kami | tetap `/tentang/` | Jangan diubah |
| Redirect artikel lama | Plugin Redirection — aktif | 301 redirect terpasang |
| Edit konten artikel | Visual Editor (Block Editor) | Bukan tab Kode |
| Batas meta description | **142 karakter** | Berlaku mulai 3 Juni 2026 |
| Laporan analisis SEO | Hanya setelah artikel final dikonfirmasi | Berlaku mulai 3 Juni 2026 |
| Homepage Yoast 2 item merah | **DITERIMA sebagai permanent** | Tidak perlu dioptimasi lagi |
| Sistem pembayaran klien | DP 50% di muka, pelunasan 50% setelah selesai | Template invoice sudah mengikuti skema ini |

---

## BAGIAN 13: PELAJARAN TEKNIS PENTING (JANGAN DIULANGI)

| Situasi | Yang Benar |
|---|---|
| **WordPress `<p><style>` di Custom HTML block** | WordPress SELALU menambahkan `<p>` ke `<style>` saat save. TIDAK BISA dicegah. Jangan coba hapus — akan kembali. |
| **Homepage Yoast tidak 100% hijau** | Normal untuk Custom HTML homepage. 14 item hijau + 1 merah permanent = kondisi optimal. |
| Yoast "frasa kunci dalam subjudul" merah | Yoast terbaru hitung H2+H3+H4. Perlu 30-75% heading mengandung keyword. |
| Meta description masih panjang setelah diganti | Ctrl+A → Delete di kolom meta description Yoast sebelum paste |
| Alt text terlalu banyak keyword | Yoast peringatan oranye. Max 1–2 gambar per artikel |
| Sebaran subjudul merah walau ada H3 | FAQ block tidak punya heading internal — tambah H2 sebelum FAQ block |
| Edit artikel | Selalu Visual Editor. HTML lengkap hanya untuk paste artikel baru |
| Edit homepage blok fix script | Ctrl+A → Delete → Paste baru |
| WordPress menghapus onclick | Pakai addEventListener — jangan onclick inline |
| Cache setelah edit besar | Bersihkan via hPanel Hostinger |
| Plugin aksesibilitas Ally | Tidak kompatibel Elementor — jangan install |
| "Berikutnya" sebagai transisi | Yoast tidak mengenalinya |
| Screenshot Yoast untuk diagnosis | Crop hanya panel "Hasil analisis" — hemat token |

---

## BAGIAN 14: INSTRUKSI UNTUK CLAUDE DI SEMUA PROJECT

1. Baca file ini sebagai sumber kebenaran tunggal
2. Jangan tanya ulang informasi yang sudah ada di sini
3. Jika ada konflik antara file ini dan file lain → file ini yang menang
4. Saat memulai sesi baru, konfirmasi ke Ronald apakah ada update sebelum memulai
5. Setiap sesi produktif yang mengubah status → ingatkan Ronald untuk update file ini
6. **Meta description semua artikel: maksimal 142 karakter**
7. **Laporan analisis SEO: hanya setelah Ronald konfirmasi artikel final**
8. **Homepage 2 item merah Yoast: sudah final — jangan dioptimasi lagi**

---

*Master Handoff v4.4 — Diperbarui 5 Juni 2026*
*Perubahan dari v4.3:*
*- Sistem dapat klien (3 aset) ✅ selesai*
*- Project 4 Keuangan Freelance ✅ aktif lengkap dengan 4 file*
*- Project 5 Belajar SEO & Digital Marketing ✅ aktif lengkap dengan 2 file*
*- GitHub connector dicatat (ada, belum diintegrasikan)*
*- Pending items diperbarui*
*Versi berikutnya: v4.5 — setelah artikel #6 selesai atau ada perubahan signifikan*
