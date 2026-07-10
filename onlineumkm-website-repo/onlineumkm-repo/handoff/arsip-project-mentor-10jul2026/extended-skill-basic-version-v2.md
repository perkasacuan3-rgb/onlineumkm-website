# Extended Skill Basic Version — v2.0
## Handoff File | Project: Skill Maker

**Versi:** 2.0
**Diperbarui:** Mei 2026
**Dari sesi:** Sesi pembangunan infrastruktur Claude lengkap
**Status:** Siap untuk sesi baru

---

## BAGIAN 1: KONTEKS PENGGUNA

### Identitas
- **Nama:** Ronald Huson
- **Lokasi:** Medan, Sumatera Utara, Indonesia
- **Pekerjaan utama:** Data entry & customer service (shift panjang, rotating pagi/malam)
- **Waktu tersedia:** Terbatas — kerja bisnis di sela-sela shift
- **Claude plan:** Pro ($20/bulan)

### Bisnis — onlineumkm.id
- **Nama:** Online UMKM
- **Domain:** onlineumkm.id *(bukan .com)*
- **Tagline:** Bantu UMKM Indonesia Ditemukan di Google
- **WhatsApp:** +6287791808667
- **Status saat ini:** Fase persiapan — **belum ada klien**, sedang membangun fondasi

### Jasa yang Ditawarkan
1. Pembuatan website WordPress (company profile, landing page, toko online, biro jasa)
2. Jasa SEO (audit teknis, riset keyword, optimasi GBP, laporan bulanan)
3. Jasa Setup & Maintenance SaaS untuk UMKM *(jasa terbaru, belum diluncurkan)*

### Target Klien
- UMKM dan usaha kecil lokal (Segmen A)
- Toko online/e-commerce (Segmen B)
- Startup dan bisnis baru (Segmen C)
- Biro jasa lokal — pengurusan izin, pajak (Segmen D)

### Claude Setup
- **MCP aktif:** Gmail, Google Calendar, Google Drive
- **Fitur Pro aktif:** Projects, Deep Research, Artifacts, Extended Thinking, File Creation
- **Plugin SEO WordPress:** Yoast *(bukan RankMath — jangan sarankan migrasi kecuali diminta)*
- **Bahasa default:** Indonesia

### Preferensi Komunikasi
- Topik **teknis** → jawaban singkat dan langsung
- Topik **strategi/bisnis** → jawaban lengkap dan menyeluruh
- Contoh konkret dan angka > teori abstrak
- Output actionable — bisa langsung dieksekusi
- Tidak suka filler, tidak suka bertele-tele

---

## BAGIAN 2: ARSITEKTUR SKILL — 11 SKILL AKTIF

> **Catatan:** `ai-prompting` dibatalkan atas keputusan Ronald.
> Alasan valid: output yang diinginkan sudah tercapai tanpa skill ini.

---

### KELOMPOK A: SKILL INTI BISNIS (6 skill)

#### 1. `konteks-bisnis-umkm`
**Status:** ✅ Sudah ada & aktif
**Domain:** Konteks dan identitas bisnis onlineumkm.id
**Trigger:** Konten website, proposal, email penawaran, halaman jasa, harga, WA klien, onboarding
**⚠️ PERLU UPDATE:** Tambahkan "Jasa Setup & Maintenance SaaS" ke daftar layanan
**Dependency:** Dibaca oleh `copywriting` sebelum menulis konten bisnis

#### 2. `bisnis-marketing`
**Status:** ✅ Sudah ada & aktif
**Domain:** Analisis & perencanaan strategis bisnis dan marketing
**Trigger:** Strategi jualan, rencana bisnis, cara dapat klien, SWOT, positioning, financial projection
**TIDAK untuk:** Menulis konten (→ `copywriting`), eksekusi kampanye (→ `digital-marketing`), SEO teknis (→ `seo`)

#### 3. `copywriting`
**Status:** ✅ Sudah ada & aktif
**Domain:** Semua tugas menulis dan editing konten
**Trigger:** Tulis, buat teks, headline, CTA, artikel, caption, script, email, newsletter, proofread
**Dependency:** Baca `konteks-bisnis-umkm` untuk konten bisnis; gunakan `stop-slop-indonesia` untuk semua output Indonesia

#### 4. `seo`
**Status:** ✅ Sudah ada & aktif
**Domain:** Audit dan optimasi SEO
**Trigger:** SEO, meta tags, schema, sitemap, robots.txt, GSC, local SEO, Yoast, RankMath, website tidak muncul Google
**TIDAK untuk:** Kecepatan/security/hosting WP (→ `wordpress-teknis`), ads/sosmed (→ `digital-marketing`)

#### 5. `wordpress-teknis`
**Status:** ✅ Baru dibuat sesi ini — **siap install** | versi: v1.1 (sudah diperbaiki)
**Domain:** Troubleshooting, development, dan maintenance teknis WordPress
**Trigger:** Error WP, white screen, 500 error, database, plugin conflict, Elementor, Gutenberg, custom CSS, PHP, hosting, backup, migrasi, staging, cPanel, SSL, DNS, WooCommerce, loading lambat, Core Web Vitals, security, hack
**TIDAK untuk:** SEO (→ `seo`), menulis konten (→ `copywriting`), strategi harga (→ `bisnis-marketing`)
**Perubahan v1.1:** Plugin wajib diubah dari "RankMath" menjadi "Yoast (default) + RankMath untuk setup baru". Ditambahkan panduan migrasi Yoast → RankMath.

#### 6. `saas-ecosystem-umkm`
**Status:** ✅ Baru dibuat sesi ini — **siap install** | versi: v1.1 (description diperbaiki)
**Domain:** Jasa setup, konfigurasi, dan maintenance SaaS tools untuk klien UMKM
**Trigger:** SaaS, tools UMKM, POS, kasir digital, CRM, akuntansi online, invoice digital, booking, WhatsApp API, WA blast, inventory, stok, aplikasi bisnis, setup tools, konfigurasi, maintenance, Moka, iSeller, Jurnal, Kledo, BukuKas, Pawoon, Midtrans, Xendit, Fonnte, Wati, HubSpot
**TIDAK untuk:** Build SaaS sendiri, SEO (→ `seo`), WordPress (→ `wordpress-teknis`), strategi marketing (→ `bisnis-marketing`)
**Perubahan v1.1:** Description diperpendek dari 1102 → 781 karakter (limit Claude.ai: 1024 karakter)

---

### KELOMPOK B: SKILL OPERASIONAL (2 skill)

#### 7. `keuangan`
**Status:** ✅ Baru dibuat sesi ini — **siap install** | versi: v1.0
**Domain:** Keuangan pribadi dan operasional bisnis freelance
**Trigger:** Uang, gaji, tabungan, pengeluaran, pemasukan, invoice, pajak, cash flow, break even, margin, budget, dana darurat, investasi, hitung biaya
**TIDAK untuk:** Pricing strategy untuk pitch (→ `bisnis-marketing`), keputusan investasi besar (→ `counsel`)
**Coverage:** Budgeting 50/30/20, dana darurat, rekening terpisah, hitung harga jasa, break-even, margin, invoice, pajak PPh 0,5%, investasi dasar Indonesia

#### 8. `digital-marketing`
**Status:** ✅ Baru dibuat sesi ini — **siap install** | versi: v1.0
**Domain:** Eksekusi dan operasional kampanye digital marketing
**Trigger:** Posting, content calendar, iklan, ads, campaign, email blast, analytics, GA4, UTM, reach, engagement, hashtag, reels, carousel, boost, target audience, conversion, lead magnet
**TIDAK untuk:** Strategi level tinggi (→ `bisnis-marketing`), menulis teks (→ `copywriting`), SEO (→ `seo`)

---

### KELOMPOK C: SKILL PROSES & MINDSET (2 skill)

#### 9. `counsel`
**Status:** ✅ Sudah ada & aktif
**Domain:** Pengambilan keputusan dan saran
**Trigger:** Sebaiknya saya..., menurut kamu..., lebih baik mana..., bimbang, pilih antara, apakah ide ini bagus
**TIDAK untuk:** Ideation (→ `brainstorm`), analisis formal (→ `bisnis-marketing`)

#### 10. `brainstorm`
**Status:** ✅ Baru dibuat sesi ini — **siap install** | versi: v1.0
**Domain:** Ideation dan pemecahan masalah kreatif
**Trigger:** Ide, gimana ya, apa yang bisa saya lakukan, cara kreatif, stuck, buntu, eksplorasi, alternatif, what if, coba pikirkan
**TIDAK untuk:** Keputusan final (→ `counsel`), analisis formal (→ `bisnis-marketing`), eksekusi menulis (→ `copywriting`)
**Teknik:** SCAMPER, First Principles, Reverse Brainstorming, Analogi Lintas Industri, Constraint Flipping

---

### KELOMPOK D: SKILL TULISAN & KUALITAS (2 skill — ai-prompting DIBATALKAN)

#### 11. `stop-slop-indonesia`
**Status:** ✅ Sudah ada & aktif
**Domain:** Menghilangkan pola tulisan AI dari bahasa Indonesia
**Trigger:** Semua penulisan bahasa Indonesia (companion otomatis)

#### ~~`ai-prompting`~~
**Status:** ❌ Dibatalkan atas keputusan Ronald
**Alasan:** Output yang diinginkan sudah tercapai tanpa skill ini. Tidak perlu ditambahkan.

---

## BAGIAN 3: PETA ANTI-TUMPANG TINDIH

```
SITUASI                                          → SKILL YANG BENAR
────────────────────────────────────────────────────────────────────
Menulis artikel/copy/caption/email               → copywriting
Strategi bisnis, SWOT, positioning               → bisnis-marketing
SEO: meta, schema, keyword, GSC                  → seo
WordPress: error, plugin, tema, hosting          → wordpress-teknis
Setup/config SaaS tools untuk klien             → saas-ecosystem-umkm
Uang: budget, invoice, pajak, hitung harga      → keuangan
Kampanye: ads, posting, analytics, UTM           → digital-marketing
Cari ide, brainstorming, eksplorasi              → brainstorm
Pilih antara opsi, ambil keputusan              → counsel
Cara pakai Claude/AI lebih efektif              → (tidak ada skill — tanya langsung)
Konten spesifik onlineumkm.id                   → konteks-bisnis-umkm + copywriting
Semua tulisan bahasa Indonesia                  → stop-slop-indonesia (companion)
```

### Kasus Ambiguitas Umum

| Pertanyaan | Skill | Alasan |
|---|---|---|
| "Berapa harga jasa website saya?" | `keuangan` | Perhitungan cost-based |
| "Strategi pricing untuk proposal besar" | `bisnis-marketing` | Value-based positioning |
| "Buat konten Instagram promosi website" | `copywriting` + `digital-marketing` | Tulis + distribusi |
| "Error 500 di website klien" | `wordpress-teknis` | Technical fix |
| "Meta description halaman website" | `seo` | SEO on-page |
| "Apakah ganti ke RankMath?" | `counsel` | Keputusan dengan trade-off |
| "Setup Kledo untuk klien restoran" | `saas-ecosystem-umkm` | Setup SaaS |
| "Template invoice bulanan" | `keuangan` | Finance document |
| "Ide konten untuk bulan ini" | `brainstorm` | Ideation dulu |

---

## BAGIAN 4: STATUS INSTALL SKILL

| # | Skill | Status Install | File Tersedia | Aksi |
|---|---|---|---|---|
| 1 | `konteks-bisnis-umkm` | ✅ Aktif | Di sistem | Update: tambah jasa SaaS |
| 2 | `bisnis-marketing` | ✅ Aktif | Di sistem | — |
| 3 | `copywriting` | ✅ Aktif | Di sistem | — |
| 4 | `seo` | ✅ Aktif | Di sistem | — |
| 5 | `counsel` | ✅ Aktif | Di sistem | — |
| 6 | `stop-slop-indonesia` | ✅ Aktif | Di sistem | — |
| 7 | `keuangan` | 🔴 Belum install | keuangan/SKILL.md | Install via Settings → Skills |
| 8 | `digital-marketing` | 🔴 Belum install | digital-marketing/SKILL.md | Install via Settings → Skills |
| 9 | `brainstorm` | 🔴 Belum install | brainstorm/SKILL.md | Install via Settings → Skills |
| 10 | `wordpress-teknis` | 🔴 Belum install | wordpress-teknis/SKILL.md (v1.1) | Install via Settings → Skills |
| 11 | `saas-ecosystem-umkm` | 🔴 Belum install | saas-ecosystem-umkm-fixed/SKILL.md (v1.1) | Install via Settings → Skills |

### Cara Install Skill di Claude.ai
1. Buka file SKILL.md yang didownload → copy semua isinya
2. Claude.ai → Settings → Skills → Add Skill
3. Paste isi SKILL.md → klik Simpan
4. Test dengan satu prompt relevan setelah install

---

## BAGIAN 5: MEMORY — STATUS TERKINI

| # | Memory | Status |
|---|---|---|
| 1 | User adalah pengguna Claude Pro | ✅ Aktif |
| 2 | Domain bisnis: onlineumkm.id (bukan .com) | ✅ Aktif |
| 3 | Status bisnis: fase persiapan, belum ada klien | ✅ Aktif |
| 4 | Preferensi jawaban: teknis = singkat, strategi = lengkap | ✅ Aktif |
| 5 | Area bantuan personal: keuangan pribadi + pengembangan diri | ✅ Aktif |
| 6 | Plugin SEO: Yoast (jangan sarankan RankMath kecuali diminta) | ✅ Aktif |

**Yang perlu diupdate saat kondisi berubah:**
- Memory #3: Update ketika klien pertama masuk ("Sudah ada X klien aktif")

---

## BAGIAN 6: PENDING ITEMS — LANJUTKAN DI SESI BERIKUTNYA

### Prioritas Tinggi
- [ ] **Install 5 skill baru** ke Claude.ai (keuangan, digital-marketing, brainstorm, wordpress-teknis, saas-ecosystem-umkm)
- [ ] **Update skill `konteks-bisnis-umkm`** → tambahkan "Jasa Setup & Maintenance SaaS" ke daftar layanan
- [ ] **Setup Projects** di Claude.ai (5 project sesuai workstream)

### Prioritas Menengah
- [ ] **Eksekusi checklist launch jasa SaaS** (file: checklist-launch-jasa-saas.md) — mulai Fase 1: daftar free trial Kledo + Fonnte
- [ ] **Eksekusi checklist Claude Pro** (file: checklist-claude-pro.md) — mulai milestone Minggu 1

### Prioritas Rendah
- [ ] Pertimbangkan skill `saas-tools-umkm` (terpisah untuk pengetahuan tools) jika scope `saas-ecosystem-umkm` terlalu lebar
- [ ] Evaluasi semua skill setelah 2-4 minggu dipakai — mana yang perlu direvisi

---

## BAGIAN 7: KEPUTUSAN PENTING YANG SUDAH DIBUAT

Catat di sini agar tidak perlu dibahas ulang:

| Keputusan | Pilihan | Alasan |
|---|---|---|
| Plugin SEO | Yoast (tetap) | Sudah aktif, tidak perlu migrasi |
| Skill ai-prompting | Dibatalkan | Output sudah tercapai tanpa skill ini |
| Model SaaS | Model 3: jasa setup & maintenance (bukan build sendiri) | Lebih realistis untuk fase awal |
| Cara upload skill | Klik Simpan lebih praktis dari ZIP (untuk 1-file skill) | Sama hasilnya, Simpan lebih cepat |
| Naming skill SaaS | `saas-ecosystem-umkm` | Sudah final |

---

## BAGIAN 8: PRINSIP DESAIN SKILL

### Aturan Wajib
1. **Satu skill, satu domain** — tidak ada tumpang tindih
2. **Description ≤ 1024 karakter** — limit keras Claude.ai (error jika lebih)
3. **Trigger pushy** — banyak sinonim dan variasi kata kunci
4. **Batas eksplisit** — section "Batas Skill Ini" wajib ada di setiap skill
5. **Konteks Indonesia-first** — contoh, angka, regulasi mengacu Indonesia
6. **Output siap pakai** — template, formula, checklist; bukan teori abstrak
7. **Kalibrasi fase awal** — Ronald solopreneur, waktu terbatas, belum ada klien

### Tanda Skill Perlu Direvisi
- Output terlalu generic (kurang contoh spesifik UMKM Indonesia)
- Sering konflik dengan skill lain (trigger terlalu broad)
- Tidak pernah aktif (tambah trigger keywords)
- Output terlalu panjang (pecah menjadi dua skill)

---

## BAGIAN 9: SKILL KANDIDAT MASA DEPAN

| Skill Kandidat | Trigger | Kapan Dibutuhkan |
|---|---|---|
| `project-management` | Tracking klien, deadline, milestone, SOP | Saat handle 3+ klien aktif |
| `client-relations` | Negosiasi, keluhan, revisi berlebihan, kontrak | Saat ada konflik dengan klien |
| `personal-branding` | Reputasi online, personal website, LinkedIn | Saat transisi ke full freelance |

---

## BAGIAN 10: PANDUAN UNTUK SESI SKILL MAKER

### Memulai Sesi Baru
1. Upload atau paste file ini sebagai konteks pertama
2. Sebutkan fokus sesi: "Sesi ini saya ingin [X]"
3. Claude akan langsung paham konteks tanpa perlu dijelaskan ulang

### Membuat Skill Baru
1. Cek tabel anti-overlap — topik sudah dicakup skill mana?
2. Jika gap → tulis description ≤ 1024 karakter (hitung dulu)
3. Gunakan struktur: frontmatter YAML → penjelasan 1 baris → batas skill → konten A/B/C → "Batas Skill Ini"
4. Update tabel status di handoff ini setelah install

### Merevisi Skill yang Ada
1. Baca file skill yang ada terlebih dahulu
2. Edit surgical — jangan rewrite total kecuali terpaksa
3. Jangan ubah `name:` — identifier skill tidak boleh berubah
4. Catat perubahan di kolom "Perubahan" pada tabel status

### Format Laporan Akhir Sesi
```
Sesi: [tanggal]
Skill dibuat/direvisi: [nama]
Perubahan utama: [deskripsi singkat]
Status: [draft / siap install / installed]
Pending: [item yang belum selesai]
```

---

## BAGIAN 11: PENGINGAT UNTUK HANDOFF BERIKUTNYA

Setiap kali membuat handoff file baru, pastikan mencakup:
- [ ] Status Claude Code (CLI) / Claude Cowork — apakah sudah diinstall?
- [ ] Update `konteks-bisnis-umkm` — sudah ditambahkan jasa SaaS?
- [ ] Update Extended Skill Basic Version — arsitektur & status terkini
- [ ] Memory terbaru — ada yang perlu ditambah/direvisi/dihapus?
- [ ] Pending items dari sesi sebelumnya — mana yang sudah selesai?

---

*Extended Skill Basic Version v2.0 — Selesai diperbarui Mei 2026*
*Versi selanjutnya: v2.1 — setelah 5 skill baru berhasil diinstall dan dievaluasi*
