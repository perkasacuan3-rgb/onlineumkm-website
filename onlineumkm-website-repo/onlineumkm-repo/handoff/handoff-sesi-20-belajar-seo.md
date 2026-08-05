# Handoff Sesi Belajar SEO — Sesi 20
**Tanggal:** 25 Juli 2026
**Topik:** Evaluasi GSC Artikel #3 (Google Business Profile) — praktik lanjutan decision tree Content Refresh (Topik 34), diterapkan pada kasus impresi rendah
**Status:** ✅ Selesai
**Melanjutkan dari:** handoff-sesi-19-belajar-seo.md (E-E-A-T author bio box selesai, Halaman Kontak & Kebijakan Privasi masih pending)

---

## 1. Evaluasi GSC Artikel #3 — Praktik Decision Tree untuk Kasus Impresi Rendah

Jadwal cek GSC Artikel #3 sudah lewat (25 Mei terbit, cek pertama dijadwalkan 25 Juli). Berbeda dari Artikel #2 (kasus CTR rendah, direvisi 23 Jul), Artikel #3 ternyata kasus **impresi rendah** — cabang decision tree yang belum pernah dipraktikkan sesi-sesi sebelumnya.

### Data baseline (25 Mei–24 Jul 2026, 2 bulan)

| Metrik | Nilai |
|---|---|
| Klik | 0 |
| Tayangan | 68 |
| CTR | 0% |
| Posisi rata-rata | 8,7 |

Dibandingkan Artikel #2 (1.020 tayangan/3 bulan), laju Artikel #3 sekitar 1/10-nya. Pola grafik: spike sekitar 10 Juni (freshness boost), lalu drop nyaris nol sejak akhir Juni — indikasi visibilitas menurun, bukan stabil rendah.

### Investigasi kueri — akar masalah ditemukan

Kueri tunggal yang tampil di tab Kueri Artikel #3: *"cara mendaftarkan warung di google maps"*. Sinyal awal: audiens pakai bahasa "Google Maps", bukan istilah teknis "Google Business Profile" yang dipakai artikel.

Diverifikasi lebih lanjut dengan filter kueri situs-lebar (bukan cuma halaman Artikel #3):

| Kueri | Tayangan situs (2 bulan) |
|---|---|
| Mengandung `maps` | 2 (kueri "warung maps" posisi 2, "cara mendaftarkan warung di google maps" posisi 12) |
| Mengandung `business profile` | 0 |

**Kesimpulan:** "Google Business Profile" adalah keyword mati untuk audiens Online UMKM — 0 tayangan situs selama 2 bulan, bukan sekadar lemah. "Google Maps" ada sinyal (tipis, tapi nyata, dan kemampuan ranking-nya sudah terbukti lewat posisi 2 untuk "warung maps"). Catatan jujur: karena Google menyembunyikan sebagian besar kueri bervolume kecil (66 dari 68 tayangan Artikel #3 tidak muncul di tab Kueri), diagnosis ini dibangun dari data yang sangat terbatas — bukan sampel besar.

**Keputusan:** evaluasi keyword (bukan revisi title/meta untuk CTR — draft "[Gratis]" di status-aktif Bagian 2 sengaja TIDAK dipakai untuk Artikel #3, itu untuk kasus CTR rendah, bukan impresi rendah).

---

## 2. Eksekusi Penyelarasan Keyword

Ronald menulis sendiri 3 varian SEO title, dipilih dan disempurnakan bersama jadi: **"Cara Daftar Warung Makan di Google Maps (Gratis)"** — urutan kata mengikuti pola kueri asli ("warung ... di google maps"), plus hook "(Gratis)" untuk CTR.

**Titik yang diselaraskan ke "Google Maps":**
1. SEO title Yoast
2. Meta description
3. Fokus frasa kunci utama Yoast ("cara daftar warung makan di google maps")
4. H1 (judul WordPress)
5. Paragraf pembuka (100 kata pertama) — sudah natural sejak awal, tidak perlu ditambah
6. H2 section langkah utama
7. H2 sebelum FAQ (wajib per aturan Yoast)
8. H2 penutup sebelum CTA (sekaligus koreksi salah ketik "Google Bisnis Profile" → dibetulkan jadi konsisten)

**Yang SENGAJA tidak diubah:**
- **Slug** — tetap `cara-daftar-google-business-profile`. Alasan: mengubah slug butuh redirect 301 (plugin Redirection), risiko dan effort tidak sepadan untuk gain sekecil ini di artikel low-volume.
- **H3 "Buka Halaman Pendaftaran Google Business"** — mendeskripsikan nama halaman asli di business.google.com, akurasi lebih penting daripada keyword match di titik ini.
- **Caption gambar tombol "Mulai sekarang"** — mendeskripsikan screenshot asli, tidak diubah demi akurasi.
- **Blok FAQ (Yoast FAQ block)** — bukan heading HTML asli (dirender sebagai teks tebal, bukan H2/H3), jadi tidak kena aturan over-optimization heading. Istilah teknis "Google Business Profile" tetap tepat dipakai di sini karena pembaca sudah paham konteksnya dari isi artikel di atasnya.

**Verifikasi over-optimization:** "Google Maps" muncul di sekitar 5-6 heading total setelah perubahan. Tidak dianggap over-optimization karena ini nama topik inti artikel (sama seperti pengecualian nama kota di artikel hiperlokal, contoh Artikel #11 Bandung) — bukan frasa keyword utuh yang diulang identik.

**Hasil:** semua titik dikonfirmasi selesai oleh Ronald, disimpan/diperbarui di WordPress. Live.

---

## Pelajaran Kunci Sesi Ini

1. **Impresi rendah dan CTR rendah adalah dua cabang decision tree yang berbeda total.** CTR rendah → poles judul untuk menarik klik dari orang yang sudah melihatnya. Impresi rendah → artikel tidak match dengan bahasa yang dicari, solusinya ganti vocabulary/keyword, bukan hook judul. Draft revisi title yang sudah disiapkan untuk kasus lain (CTR) tidak otomatis relevan dipakai di kasus ini.
2. **Kueri yang disamarkan GSC (anonymized) membatasi diagnosis di artikel low-volume.** Dengan 68 tayangan, cuma 1-2 kueri yang tampil di tab Kueri — mayoritas data tersembunyi demi privasi. Filter kueri situs-lebar (bukan per-halaman) jadi cara verifikasi tambahan saat sampel per-artikel terlalu tipis.
3. **"0 tayangan" adalah sinyal lebih kuat daripada "tayangan rendah".** Nol untuk "business profile" di seluruh situs selama 2 bulan = konfirmasi keyword mati, bukan sekadar noise statistik.
4. **Fix relevansi keyword adalah structural fix, boleh dieksekusi kapan saja** — tidak perlu menunggu siklus data GSC lagi setelah keputusan diambil, beda dengan revisi title/meta murni CTR yang perlu dipantau ulang performanya.
5. **Nama produk/topik inti (di sini "Google Maps") boleh berulang di banyak heading** tanpa kena aturan over-optimization — beda kategori dari pengulangan frasa keyword identik utuh.
6. **Blok FAQ Yoast tidak dihitung sebagai heading HTML** untuk keperluan aturan optimasi heading, karena dirender sebagai teks tebal bukan tag H2/H3.

---

## Progress Tracker

Tidak ada perubahan di `progresstrackerbelajar.xlsx` — sesi ini praktik maintenance/evaluasi artikel (konsisten dengan pola evaluasi GSC Artikel #2 di sesi 18), bukan topik kurikulum baru. Progress tetap **31/47 topik (66%)**.

`status-aktif-v2.md` naik ke **v2.25** — mencatat closing evaluasi GSC Artikel #3, item pending terkait dihapus, tabel jadwal cek GSC (Bagian 6) diupdate.

---

## Sesi Berikutnya

**Belum terlewat, masih menggantung dari sesi-sesi sebelumnya:**
1. **E-E-A-T Signals (Topik 33)** — masih 🔄, nunggu Halaman Kontak dan Kebijakan Privasi (belum ada sama sekali di situs)
2. **Cek link "Hubungi Kami" di footer artikel** — verifikasi setelah Halaman Kontak jadi, kemungkinan 404
3. **Reminder GSC Artikel #1 Pillar** — cek ulang status index, **27 Juli 2026**
4. **Artikel #4 WhatsApp** — jadwal cek GSC berikutnya **29 Juli 2026**
5. **Topik 22 — Local Citation Building** — masih ditunda, blocker dokumen/akses
6. **Artikel #13 & #14** — target 28 Jul–10 Agt
7. Sync GitHub manual untuk file yang belum tersinkron (akses tulis connector masih diblokir)

File project yang perlu diupload ulang: `status-aktif-v2.md` (v2.25). File ini (`handoff-sesi-20`) untuk arsip GitHub `handoff/`, BUKAN untuk project knowledge — sync manual lewat GitHub web UI kapan sempat.

---

*Handoff Sesi 20 — 25 Juli 2026.*
