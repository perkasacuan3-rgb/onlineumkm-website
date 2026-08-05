# Handoff Sesi Belajar SEO — Sesi 21
**Tanggal:** 26 Juli 2026
**Topik:** E-E-A-T Signals (Topik 33) — lanjutan: Halaman Kontak dibuat & didesain ulang, link footer diarahkan
**Status:** 🔄 Topik 33 masih belum ditutup — 1 item pindah ke Project Website onlineumkm.id
**Melanjutkan dari:** handoff-sesi-20-belajar-seo.md (E-E-A-T: author bio box selesai, Halaman Kontak & Kebijakan Privasi masih pending)

---

## 1. Halaman Kontak — Dibuat, Live, Didesain Ulang

### v1 (fungsional, live pertama kali)
Halaman baru `/kontak/` dibuat: WhatsApp (tombol utama), email `onlineumkm@onlineumkm.id` (email domain, bukan Gmail), jam operasional (Senin-Minggu 09.00-21.00 WIB, selaras GBP), area layanan (Medan + remote Indonesia, sesuai prinsip silo lokal — tidak klaim "kami di kota X"). Sengaja tanpa contact form — form dinilai bertentangan dengan positioning "hubungi saya langsung tanpa antre tiket", dan tidak ada plugin form di stack situs.

### v2 (upgrade visual, live)
Atas permintaan Ronald untuk tampilan lebih premium/elegan, ditambahkan:
- Hero section: gradient gelap `#0B1D30 → #103B4C → #0B2E28` (sama dengan CTA Section homepage/artikel, BUKAN gradient hijau terang — dihindari karena gagal kontras WCAG AA untuk teks putih, 1.89:1, sudah tercatat di aturan warna)
- 4 info card (WhatsApp, Email, Jam Operasional, Area Layanan) dengan icon SVG inline, layout grid 2 kolom
- Palet mengikuti homepage (`--navy`, `--teal-dark`, `--green-bg`), konsisten dengan aturan Bagian 11 (halaman situs pakai palet homepage, bukan `#00BFA5` palet artikel)

**Bug ditemukan (belum dikonfirmasi perbaikan):** SVG icon WhatsApp di kartu info salah path, tampil sebagai lingkaran kosong. Path pengganti sudah dikirim ke Ronald, **status penerapan belum dikonfirmasi** — cek di sesi berikutnya.

Yoast (SEO title, slug `kontak`, meta description) sudah diisi sejak v1, tidak berubah di v2.

---

## 2. Link "Hubungi Kami" — Footer Artikel Beres, Footer Homepage Belum

### Footer artikel (WPCode → Header & Footer) — ✅ SELESAI
Baris `<li><a href="https://wa.me/6287791808667?..." rel="noopener">Hubungi Kami</a></li>` diubah Ronald sendiri jadi `<li><a href="https://onlineumkm.id/kontak/" rel="noopener">Hubungi Kami</a></li>`. Dikonfirmasi live: klik di footer artikel sekarang mendarat di halaman Kontak.

### Footer homepage (Blok HTML Utama, Elementor) — 🔄 BELUM SELESAI, DIPINDAH KE PROJECT WEBSITE
Ronald tidak menemukan `href="https://wa.me/..."` menempel di teks "Hubungi Kami" pada Blok HTML Utama. **Dugaan kuat:** sesuai aturan situs ("WordPress selalu menghapus atribut `onclick` saat save — pakai `addEventListener`"), link ini kemungkinan besar berupa `id`/`class` polos di Blok HTML Utama, dengan URL tujuan disuntik lewat `addEventListener` di **Blok Fix Script** (blok terpisah, isi semua event listener) — bukan `href` langsung.

**Keputusan:** item ini dipindahkan ke **Project Website onlineumkm.id**, karena itu wilayah teknis homepage (Elementor, Blok HTML Utama, Blok Fix Script), bukan wilayah project Belajar SEO ini. Konsisten dengan pembagian project yang sudah berlaku.

**Konteks untuk dibawa ke chat baru Project Website:**
> Perlu ganti link "Hubungi Kami" di footer homepage dari WhatsApp ke `https://onlineumkm.id/kontak/`. Sudah dicari teks "Hubungi Kami" di Blok HTML Utama tapi tidak ketemu `wa.me`. Dugaan: link pakai `id`/`class` + `addEventListener` di Blok Fix Script (karena WordPress selalu hapus atribut `onclick`), bukan `href` langsung. Perlu bantuan cari baris persisnya di Fix Script, lalu ganti URL tujuannya. Footer artikel (WPCode) sudah beres duluan dan sudah dikonfirmasi mengarah ke `/kontak/`.

Ronald disarankan tempel isi Blok Fix Script (atau bagian yang menyebut "hubungi"/"footer") di chat baru tersebut.

---

## 3. GitHub Connector — Klarifikasi, Bukan Perubahan Status

Ronald sempat menyebut "pindah ke project onlineumkm website" — diklarifikasi ini BUKAN soal GitHub (connector `github-write` akses tulis masih diblokir sejak 19-20 Juli, tidak berubah di sesi ini), melainkan pindah ke **Project Website onlineumkm.id** (project Claude yang menangani hal teknis homepage). Tidak ada perubahan status connector di sesi ini.

---

## Pelajaran Kunci Sesi Ini

1. **"Tidak ketemu kode di HTML" bisa berarti kode itu ada di blok lain.** Situs ini punya 2 blok terpisah (HTML Utama vs Fix Script) — link yang terlihat seperti `<a href>` polos bisa jadi sebenarnya `id` kosong yang di-handle JS di blok lain, konsekuensi dari aturan "WordPress hapus onclick, pakai addEventListener".
2. **Halaman baru butuh link internal sejak awal, bukan cuma tujuan link dari tempat lain.** `/kontak/` sempat berisiko jadi halaman yatim (orphan) — footer artikel jadi sumber link pertama sebelum footer homepage menyusul.
3. **Pembagian project (Belajar SEO vs Website onlineumkm.id) perlu ditegakkan aktif** — pekerjaan teknis Elementor/Fix Script yang kompleks lebih tepat dikerjakan di project yang memang menangani hal teknis, bukan dipaksakan di sesi belajar.
4. **Desain "premium/elegan" itu subjektif — bertanya dulu elemen spesifik (hero/card/icon) sebelum menggambar, lebih efisien daripada menebak lalu revisi total.**

---

## Progress Tracker

Tidak ada perubahan di `progresstrackerbelajar.xlsx` — sesi ini eksekusi teknis lanjutan Topik 33 (E-E-A-T), bukan topik kurikulum baru. Tetap **31/47 (66%)**. Topik 33 masih 🔄, item tersisa: konfirmasi icon fix, footer homepage (pindah ke Project Website), Kebijakan Privasi (belum dimulai, baru dipetakan 6 bagian: data yang dikumpulkan, penggunaan data, cookie & GA4, pihak ketiga, hak pengunjung, perubahan kebijakan).

**status-aktif belum diupdate di sesi ini** — file di project ini read-only (salinan), pembaruan versi (menuju v2.26) perlu dilakukan di sesi/project yang punya akses tulis ke project knowledge asli. Poin yang perlu masuk ke situ:
- ✅ Halaman Kontak v1 + v2 (premium hero+card) live
- ✅ Footer artikel → `/kontak/` (WPCode)
- 🔄 Footer homepage → `/kontak/` — pending, dipindah ke Project Website onlineumkm.id
- 🔄 Bug icon WhatsApp SVG — perbaikan dikirim, penerapan belum dikonfirmasi
- Pending Kebijakan Privasi tetap ada, belum mulai

---

## Sesi Berikutnya

**Di Project Website onlineumkm.id:**
1. Cari & ganti link "Hubungi Kami" footer homepage di Blok Fix Script → `https://onlineumkm.id/kontak/`
2. Konfirmasi icon WhatsApp SVG di halaman Kontak sudah diperbaiki

**Di Project Belajar SEO (sesi berikutnya, setelah dua item di atas beres):**
1. Mulai **Kebijakan Privasi** — bahas per bagian, mulai Bagian 1 (data yang dikumpulkan: GA4 + apa yang dikirim lewat WA/email)
2. Setelah Kebijakan Privasi jadi, Topik 33 (E-E-A-T) baru bisa ditutup ✅, Fase 4 naik ke 3/4 tracker

**Menggantung dari sesi-sesi sebelumnya (tidak berubah):**
- Reminder GSC Artikel #1 Pillar — cek ulang **27 Juli 2026**
- Artikel #4 WhatsApp — jadwal cek GSC **29 Juli 2026**
- Topik 22 — Local Citation Building — masih ditunda
- Artikel #13 & #14 — target 28 Jul-10 Agt
- Sync GitHub manual — akses tulis masih diblokir

File ini untuk arsip (GitHub `handoff/` atau referensi Ronald) — BUKAN untuk diupload sebagai project knowledge, konsisten dengan protokol status patch yang berlaku.

---

*Handoff Sesi 21 — 26 Juli 2026.*
