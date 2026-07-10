# Status Patch — 3 Juni 2026 (Sesi 2)
**Versi:** Patch v4.3
**Menggantikan:** status-patch-2-3juni2026.md
**Dibaca bersama:** mentor-master-handoff-onlineumkm-v4.3.md

---

## FOKUS SESI INI

Optimasi penuh Yoast SEO Homepage (post ID 114) — SEO tab + Keterbacaan tab.
Dimulai dari kondisi 4 merah SEO + 2 merah Keterbacaan.
Selesai dengan 1 merah SEO + 1 merah Keterbacaan (keduanya permanent limitation).

---

## STATUS HOMEPAGE YOAST — FINAL (3 Juni 2026)

### Tab SEO
| Item | Status | Catatan |
|---|---|---|
| **Tab icon SEO** | ✅ **HIJAU** | Smiley hijau — skor keseluruhan baik |
| Tautan ke luar | ✅ Hijau | Moz + Neil Patel links ditambahkan |
| Frasa kunci dalam atribut alt gambar | ✅ Hijau | |
| Gambar | ✅ Hijau | |
| Tautan internal | ✅ Hijau | |
| Kepadatan frasa kunci | ✅ Hijau | Keyword muncul 8 kali |
| Panjang frasa kunci | ✅ Hijau | |
| Frasa kunci dalam subjudul | ✅ Hijau | 3 H3 dengan keyword ditambahkan |
| Frasa kunci di awal | 🔴 Merah | **PERMANENT** — WordPress paksa `<p><style>` (tidak bisa diubah) |
| Frasa kunci pada judul SEO | 🟠 Oranye | Acceptable — judul mengandung sinonim |

### Tab Keterbacaan
| Item | Status | Catatan |
|---|---|---|
| **Tab icon Keterbacaan** | 🟠 Oranye | Skor menengah — 1 merah tersisa |
| Kalimat pasif | ✅ Hijau | |
| Kalimat berurutan | ✅ Hijau | |
| Sebaran sub judul | ✅ Hijau | |
| Panjang paragraf | ✅ Hijau | Diperbaiki dengan `<p>` tags di FAQ |
| Panjang kalimat | ✅ Hijau | |
| Kata transisi | 🔴 Merah | **PERMANENT** — CSS block dihitung sebagai kalimat tanpa transisi |

### Ringkasan Progres
| Kondisi | Sebelum | Sesudah |
|---|---|---|
| SEO merah | 4 | 1 (permanent) |
| Keterbacaan merah | 2 | 1 (permanent) |
| SEO hijau | ~10 | 14 |
| Keterbacaan hijau | 4 | 5 |
| Tab SEO icon | 🟠 Oranye | ✅ Hijau |
| Tab Keterbacaan icon | 🔴 Merah | 🟠 Oranye |

---

## PERUBAHAN YANG DIBUAT KE HOMEPAGE

### 1. Konten SEO — Keyword & Links
| Perubahan | Lokasi | Impact |
|---|---|---|
| Hero subtitle: tambah kata "pembuatan" | hero-sub | Keyword exact match di paragraf |
| Section layanan subtitle: tambah keyword | sec-sub layanan | Keyword instance ke-2 |
| Kartu featured card: tambah keyword | lay-desc | Keyword instance ke-3 |
| CTA subtitle: tambah keyword + transition | cta-sub | Keyword instance ke-5 |
| Blog subtitle: tambah external links Moz + Neil Patel | sec-sub blog | External links ✅ |

### 2. Heading dengan Keyword (H3)
| H3 ditambahkan | Lokasi | Teks |
|---|---|---|
| H3 baru | Section Layanan | "Jasa Pembuatan Website UMKM Kami" |
| H3 baru | Section Tentang | "Layanan Jasa Pembuatan Website UMKM Lokal" |
| H3 baru | Section FAQ | "Pertanyaan Umum tentang Jasa Pembuatan Website UMKM" |
Hasil: 3/9 heading mengandung keyword = 33% → Hijau ✅

### 3. Transition Words
| Section | Kata transisi ditambahkan |
|---|---|
| Tentang bio 1 | "Oleh karena itu" |
| Tentang bio 2 | "Dengan demikian" |
| Proses 01 | "Pertama" |
| Proses 02 | "Kemudian" |
| Proses 03 | "Selanjutnya" |
| Proses 04 | "Selain itu" |
| Proses 05 | "Akhirnya" |
| FAQ 1 | "Namun", "Dengan demikian" |
| FAQ 2 | "Selain itu" |
| FAQ 3 | "kemudian" |
| FAQ 4 | "Pertama", "Selain itu" |
| FAQ 5 | "Oleh karena itu" |
| FAQ 6 | "Dengan demikian" |
| CTA subtitle | "Pertama", "Kemudian" |

### 4. Panjang Paragraf — Fix FAQ
Semua 6 jawaban FAQ sekarang dibungkus dalam `<p>` tags di dalam `.faq-a`:
```html
<div class="faq-a"><p>Jawaban FAQ...</p></div>
```
Hasil: panjang paragraf ✅ HIJAU

---

## PELAJARAN TEKNIS BARU — PERMANENT LIMITATIONS HOMEPAGE

### ⚠️ WordPress Paksa `<p>` ke `<style>` — Tidak Bisa Diubah

| Fakta | Detail |
|---|---|
| Masalah | WordPress Custom HTML block otomatis menambahkan `<p>` ke `<style>` element saat save |
| Penyebab | WordPress wpautop() filter — berjalan pada semua blok HTML |
| Dampak Yoast | "Frasa kunci di awal" = merah karena `<p><style>` dianggap paragraf pertama (kosong) |
| Dampak Yoast | "Kata transisi" = tidak bisa 100% karena CSS dihitung sebagai kalimat |
| Sudah dicoba | Ronald hapus `<p>` sebanyak 2x — WordPress selalu mengembalikannya saat save |
| Status | **PERMANENT** — tidak bisa diatasi tanpa migrasi halaman ke Elementor penuh |
| Dampak SEO nyata | **NIHIL** — Google melihat konten visual, bukan struktur tag internal |

### Implikasi untuk Semua Sesi Berikutnya
Jika ada yang bertanya kenapa homepage Yoast tidak 100% hijau:
- "Frasa kunci di awal" dan "Kata transisi" adalah **permanent limitation** dari arsitektur Custom HTML block + WordPress
- **Tidak perlu diperbaiki lagi** — sudah optimal semaksimal mungkin
- Fokus waktu dan token ke artikel baru dan optimasi konten lain

---

## SCREENSHOT YOAST UNTUK REFERENSI (3 Juni 2026)

**Cara screenshot efisien di masa depan:**
- Hanya crop bagian "Hasil analisis" Yoast saja (bukan full page)
- Tidak perlu screenshot live website kecuali ada visual bug
- Link saja tidak cukup karena Claude tidak bisa fetch domain onlineumkm.id

---

## STATUS ARTIKEL — TIDAK BERUBAH

Sama seperti Patch v4.2:
| # | Judul | Slug | Yoast |
|---|---|---|---|
| 1 | Cara Promosi Warung Makan Online | `/cara-promosi-warung-makan-online/` | ✅✅ |
| 2 | Kenapa Warung Makan Sepi Padahal Enak | `/kenapa-warung-makan-sepi-padahal-enak/` | ✅✅ |
| 3 | Cara Daftar Google Business Profile | `/cara-daftar-google-business-profile/` | ✅✅ |
| 4 | Cara Promosi Warung Makan lewat WhatsApp | `/cara-promosi-warung-makan-lewat-whatsapp/` | ✅✅ |
| 5 | Cara Daftar GoFood untuk Warung Makan | `/cara-daftar-gofood/` | ✅✅ |

**Artikel berikutnya:** #6 — Cara Foto Makanan Pakai HP (9–15 Jun)

---

## PENDING ITEMS — UPDATE

| Item | Status | Catatan |
|---|---|---|
| Upload foto Ronald ke Tentang Kami | ⚠️ Belum | Alt text: `Ronald Huson pendiri jasa website UMKM OnlineUMKM Medan` |
| Homepage "frasa kunci di awal" | ❌ Permanent | WordPress limitation — tidak perlu diusahakan lagi |
| Homepage "kata transisi" | ❌ Permanent | WordPress limitation — tidak perlu diusahakan lagi |
| Tentang Kami — paragraf >150 kata | Belum diperbaiki | Pecah jadi 2 paragraf |
| Tentang Kami — kata transisi 22% | Belum diperbaiki | Tambah transisi di paragraf bio |
| Yoast Tentang Kami SEO | 🟢 Hijau (skor) | Ada 4 masalah detail — butuh foto terlebih dahulu |
| Artikel #6 Foto Makanan | Belum dibuat | Target 9–15 Jun 2026 |
| Sistem dapat klien | Belum dibuat | 3 aset: template WA, brief form, template proposal |

---

## ATURAN BARU DARI SESI INI

| Aturan | Detail |
|---|---|
| Homepage `<p><style>` | Jangan coba hapus tag `<p>` dari CSS block — WordPress akan kembalikan |
| Homepage Yoast | Kondisi saat ini sudah final/optimal — jangan ulangi optimasi yang sama |
| Screenshot Yoast | Crop hanya panel analisis, bukan full page — hemat token |

---

*Patch v4.3 — 3 Juni 2026 (Sesi 2)*
*Dibaca bersama mentor-master-handoff-onlineumkm-v4.3.md*
