# Handoff Sesi Belajar SEO — Sesi 23
**Tanggal:** 5 Agustus 2026
**Topik:** Praktik lanjutan decision tree striking distance — klaster merchant dan klaster warung Artikel #5 GoFood (kelanjutan dari klaster HP/iPhone yang ditutup sesi sebelumnya)
**Status:** ✅ Selesai
**Melanjutkan dari:** handoff-sesi-22-belajar-seo.md (evaluasi GSC Artikel #5 selesai, 3 klaster striking distance ditemukan, klaster HP/iPhone ditutup)

---

## 1. Konsep baru: tiga pilihan saat menemukan klaster striking distance

Sebelum klaster ditangani, dibahas dulu kerangka umum: begitu ketemu klaster kueri di posisi 10-18 (jarak tembak), ada tiga opsi — (1) tambah section kalau maksud pencari butuh jawaban baru, (2) bikin artikel baru kalau maksud pencari sudah beda topik, (3) selaraskan kosakata di tempat yang sudah ada kalau maksud pencari sudah dijawab, cuma kata kuncinya belum muncul di posisi berbobot (SEO title, H1, paragraf pembuka). Tes satu kalimat: kalau pencari mendarat di artikel ini hari ini, apakah dia butuh artikel/section lain, atau cuma butuh kata yang tepat di tempat yang tepat?

Pelajaran tambahan yang muncul saat eksekusi: bedakan **kosakata mati** (kasus Artikel #3 dulu — kata lama dibuang total, diganti) dari **kosakata kurang lengkap** (kasus klaster merchant — kata lama dipertahankan, disisipi kata baru). Salah membaca ini bisa bikin keyword yang masih menghasilkan malah dibuang.

---

## 2. Klaster Merchant — Ditutup (Penyelarasan Kosakata)

**Data (setelah dikoreksi):** 6 kueri, 22 tayangan, posisi 10,0-18,0 (bukan 28 tayangan seperti catatan v2.37 — kueri iPhone sempat terhitung ganda di dua klaster karena sama-sama mengandung kata "merchant").

**Diagnosis:** Semua 6 kueri berbagi satu maksud (mendaftar jadi GoFood Merchant), cuma beda susunan kata. Dicek langsung ke artikel: frasa "GoFood Merchant" **tidak ada** di SEO title, H1, atau paragraf pembuka — cuma muncul di satu H3 baru dan caption gambar. Kesimpulan: artikel sudah meraih tayangan ini tanpa modal di posisi berbobot, jadi penyelarasan kosakata adalah pengungkit termurah.

**Eksekusi:**
- SEO title: "Cara Daftar GoFood untuk Warung Makan: Panduan dari Awal" → **"Cara Daftar GoFood Merchant untuk Warung Makan dari Awal"** (56 karakter, Yoast hijau)
- H1: disisipi "Merchant" jadi sama dengan SEO title
- Paragraf pembuka: 1 penyebutan wajar ditambahkan
- Slug, fokus frasa kunci Yoast, deskripsi meta: sengaja tidak diubah (slug hindari redirect; fokus frasa kunci tidak dikirim ke Google jadi tidak berdampak)
- Live 4 Agustus 2026, dikonfirmasi Ronald via screenshot wp-admin dan live page

**Catatan kecil belum dieksekusi:** deskripsi meta masih menulis "GoFood merchant" (m kecil, bukan nama resmi platform "GoFood Merchant"). Tidak berdampak ranking, cuma soal kerapian. Tidak mendesak.

---

## 3. Klaster Warung — Ditutup (Penyelarasan Heading Internal)

**Data:** 5 kueri, 18 tayangan, posisi 10,0-24,0 — yang masuk jarak tembak (5-18) cuma 4 baris teratas. Didominasi "cara buka warung di gofood" (12 tayangan, posisi 10,4).

**Diagnosis beda dari klaster merchant:** "Warung Makan" sudah ada di SEO title, H1, dan paragraf pembuka sejak awal — pengungkit termurah sudah terpakai. Pembeda klaster ini bukan kata sifat, tapi **kata kerja**: pencari memakai "buka warung", penulis memakai "daftar". Dicek HeadingsMap: frasa "Cara Daftar GoFood" berulang di 4 dari total heading — terlalu seragam, dan menambah section baru untuk "buka warung" akan tumpang tindih dengan H2 "Cara Daftar GoFood Langkah demi Langkah" yang sudah ada.

**Keputusan:** tukar 1 dari 4 pengulangan, bukan tambah section. Kandidat: H2 pertama (section alasan/urgensi), karena kueri "buka warung" secara alami cocok dengan bingkai "kenapa ini penting", bukan bingkai "caranya".

**Iterasi penulisan heading (latihan penting, bukan cuma hasil akhir):**
- Ronald sempat menulis 3 variant yang gagal ("Buka Peluang...", "Buka Usaha...", "Buka Akses Rezeki...") — kata "buka" muncul tapi tidak menempel jadi frasa utuh "buka warung di GoFood", dan frasa lama "Cara Daftar GoFood" masih tersisa di semua variant (pengulangan tidak berkurang)
- Diberi 3 syarat eksplisit: (1) memuat frasa "Buka Warung di GoFood" utuh, (2) tidak lagi memuat "Cara Daftar GoFood", (3) tetap terbaca sebagai alasan bukan langkah
- Contoh diberikan dengan menukar 1 potongan dari kalimat asli (bukan menulis ulang total): "Kenapa Buka Warung di GoFood Wajib Jadi Prioritas Sekarang"
- Ronald menulis 2 variant baru, keduanya lolos syarat. Sempat salah menyebut fungsi H2 sebagai "call to action" — dikoreksi: H2 itu papan penunjuk arah, bukan ajakan bertindak

**Eksekusi:** H2 pertama diubah dari "Kenapa Cara Daftar GoFood Wajib Jadi Prioritas Warung Makan Sekarang" jadi **"Kenapa Buka Warung di GoFood Wajib Jadi Prioritas Sekarang"**. Hanya heading yang diubah, paragraf di bawahnya tidak disentuh. Live 5 Agustus 2026, dikonfirmasi Ronald via screenshot.

---

## 4. Google Calendar — Reminder Cek Ulang Dibuat dan Diperbarui

Reminder baru **1 September 2026, 09:00 WIB** (popup + email 24 jam sebelumnya) dibuat untuk mengukur efek ketiga perubahan Artikel #5 sekaligus (H3 iPhone, penyelarasan Merchant — keduanya 4 Agustus, dan heading warung — 5 Agustus). Dicek dulu tidak ada duplikat di rentang tanggal tersebut (ditemukan 1 event lain: reminder Artikel #9 di 31 Agustus, tidak bentrok).

Jendela 4 minggu dipilih (bukan 2 minggu) dengan alasan eksplisit: Google butuh waktu merayapi ulang, dan klaster-klaster ini kecil (18-22 tayangan/3 bulan) sehingga jendela pendek tidak akan mengumpulkan data cukup untuk dibandingkan.

Event awalnya dibuat sebelum klaster warung selesai, sehingga deskripsi dan judul event diperbarui ulang di akhir sesi untuk mencakup ketiga perubahan (bukan cuma dua).

---

## 5. Koreksi Tanggal (housekeeping)

Sempat terjadi kekeliruan kecil soal tanggal: draf awal deskripsi event dan log sesi menulis penyelarasan Merchant sebagai "live 5 Agustus", padahal sebenarnya live 4 Agustus (sesuai catatan v2.37 sebelumnya) — cuma heading warung yang live hari ini, 5 Agustus. Ronald mengoreksi, sudah diperbaiki di deskripsi event dan status-aktif.

---

## 6. Status Fase Belajar

Tidak ada topik kurikulum resmi baru yang dibuka sesi ini — ini murni praktik lanjutan dari evaluasi GSC Artikel #5 (maintenance/latihan, sama seperti pola evaluasi GSC artikel lain). Progress resmi tetap 32/47 (68%), Fase 4 masih 3/4 (Content Refresh masih 🔄, terikat ke hasil cek index Pillar 10 Agustus).

**Antrean disepakati Ronald untuk sesi berikutnya:** audit tayangan per negara Artikel #5 (2 kueri Vietnam, 22 tayangan gabungan) → lanjut Broadcast WhatsApp (tuntaskan label ke semua kontak dulu) → baru mulai Fase 5 (Off-Page SEO, topik pembuka Backlink Fundamentals), yang jadi relevan langsung kalau 10 Agustus nanti Artikel #1 Pillar masih belum terindeks.

---

## 7. File yang Diperbarui Sesi Ini

- `status-aktif-v2.md` → v2.38 (klaster merchant & warung ditutup, pending items diperbarui, tabel jadwal GSC Bagian 6 diperbarui, "Selesai terakhir" ditambah 3 entri)
- `handoff-sesi-23-belajar-seo.md` (file ini)

**Belum diupload Ronald ke Project Belajar SEO & Digital Marketing** — perlu diupload manual, lalu handoff sesi 19-22 bisa dikeluarkan dari project knowledge (arsip ke GitHub `handoff/`) mengikuti aturan retensi yang sudah berjalan.
