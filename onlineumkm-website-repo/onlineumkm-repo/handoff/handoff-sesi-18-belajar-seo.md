# Handoff Sesi Belajar SEO — Sesi 18
**Tanggal:** 22 Juli 2026
**Topik:** Fase 4 — Content SEO & Topical Authority: Topical Authority, Content Gap Analysis, Competitor Content Audit (dipraktikkan), Content Refresh & Update (dimulai, belum tuntas)
**Status:** 🔄 Fase 4 sebagian selesai — 2/4 topik tracker resmi ✅, 1 topik 🟡 sedang berjalan
**Melanjutkan dari:** handoff-sesi-17-belajar-seo.md (Fase 3 Local SEO 6/7, Topik 22 masih ditunda)

---

## 1. Topik 31 — Topical Authority (✅ Selesai)

- Konsep diajarkan lewat perumpamaan 2 situs fiktif (1 artikel bagus vs 8 artikel saling terhubung) — Google percaya situs yang membahas 1 topik dari banyak sudut yang saling link, bukan sekadar 1 artikel jago berdiri sendiri.
- Dipetakan langsung ke 11 artikel onlineumkm.id: klaster kanal (WhatsApp #4, GoFood #5, Instagram #7), klaster lokasi (Medan #8/#9, Surabaya #10, Bandung #11), klaster operasional (Warung Sepi #2, GBP #3, Foto Makanan #6).
- Latihan gap-finding: Ronald mengajukan "afiliasi" (valid, perlu reframe ke bahasa pencari — "kerjasama influencer") dan "hosting" (gagal filter — audiens beda, bukan pencari warung makan). Lalu "retensi & referral pelanggan" (lolos ketiga filter: belum dibahas, masih klaster promosi warung, bahasa sesuai pencari).
- **Output:** 2 gap resmi jadi Artikel #13 (kerjasama influencer/food vlogger, klaster kanal-kolaborasi) dan #14 (retensi & referral pelanggan, klaster operasional) — sudah masuk Content Calendar sejak status-aktif v2.14.

---

## 2. Topik 32 — Content Gap Analysis (✅ Selesai)

- Framework 4 langkah: (1) cek 3 artikel top untuk keyword target, (2) apa yang mereka bahas yang kita belum, (3) apa yang tidak mereka bahas tapi tetap dicari, (4) di mana bisa kasih nilai unik.
- Dipraktikkan riil pada Artikel #2 (kenapa warung sepi) vs kompetitor riil yang sama-sama ranking (duniaku.id, 2 artikel berbeda). Gap ditemukan: kecepatan penyajian & kebersihan belum eksplisit dibahas di Artikel #2.
- Keputusan penting: section baru ini **additive** (bukan revisi/pangkas), jadi boleh dieksekusi kapan saja tanpa nunggu GSC — sesuai `aturan-referensi` Bagian 9.
- **Output:** Ronald menulis sendiri section "Kecepatan Penyajian dan Kebersihan sebagai Penentu Ramai Sepinya Warung Makan" — sudah dipaste & LIVE di Artikel #2. Draft awal dari Claude sempat mengandung em dash (pelanggaran aturan sendiri, dikoreksi) — versi final Ronald lebih baik dari draft Claude di sisi detail sensorik konkret.

---

## 3. Competitor Content Audit (dipraktikkan, bukan baris tracker terpisah)

- 4 dimensi audit: struktur, kedalaman, angle/framing, CTA.
- Praktik pada artikel duniaku.id yang sama (fetch penuh): pola "problem-solution mirroring" (5 alasan sepi ↔ 4 langkah solusi yang menjawab balik), framing "Product Fallacy" (naming the problem), FAQ yang antisipasi keraguan lanjutan.
- Titik lemah kompetitor ditemukan: byline tidak konsisten dengan bio penulis, klaim "berdasarkan analisis kami" tanpa data pendukung, **tidak ada CTA jasa sama sekali** — situs itu content farm bermonetisasi iklan afiliasi, bukan bisnis riil. Ini menegaskan kekuatan positioning personal Online UMKM yang sudah live di `/tentang/`.
- **Catatan struktural:** topik ini ada di roadmap Fase 4 (8 topik) tapi TIDAK ada sebagai baris terpisah di `progresstrackerbelajar.xlsx` (Fase 4 di tracker cuma 4 baris: Topical Authority, Content Gap Analysis, E-E-A-T, Content Refresh). Konsisten dengan diskrepansi penomoran lama yang sudah dicatat di handoff sesi 17 — dibiarkan apa adanya, tidak mendesak diperbaiki.

---

## 4. Topik 34 — Content Refresh & Update (🟡 Sedang berjalan, BELUM tuntas)

### Decision tree diajarkan
Kondisi < 2 bulan → jangan sentuh. > 2 bulan + impresi tinggi + CTR < 3% → revisi title/meta. > 2 bulan + impresi rendah → evaluasi keyword. Additive → boleh kapan saja.

### Praktik pada Artikel #1 Pillar — jadi investigasi teknis panjang
Tanggal cek GSC Pillar (9 Jul) sudah lewat 2 minggu, belum pernah dikerjakan. Dimulai evaluasi, tapi ditemukan anomali:

- **Inspeksi URL:** status "URL tidak ada di Google", dan semua kolom Perayapan (Crawl terakhir, Di-crawl sebagai, dst.) **T/A** — artinya Google belum PERNAH mencoba crawl URL ini sejak terbit 9 Mei, bukan cuma "belum diindeks lama".
- **3 kemungkinan penyebab dicek satu per satu:**
  1. Uji Langsung → **bersih**, "URL tersedia untuk Google", tidak ada blocker teknis
  2. Redirect nyasar (plugin Redirection) → **bersih**, cuma 2 rule total (`/blog-umkm/` → `/blog/`), tidak menyentuh Pillar sama sekali
  3. Sitemap submission (laporan Peta Situs GSC, bukan file XML) → **bersih**, terdaftar sejak 12 Mei, terakhir dibaca 20 Jul, status Sukses
- **Kesimpulan akhir:** tidak ada kerusakan teknis apapun. Akar masalah murni jalur penemuan yang lemah sepanjang Mei–pertengahan Juli — Pillar otomatis hilang dari homepage `blog-grid-dynamic` (cuma tarik 3 post terbaru) begitu 3 artikel lebih baru terbit, dan baru dapat 5 link internal baru + 1 link statis homepage pada 19 Juli (dari audit peta internal link).
- **Aksi:** index diminta ulang manual 22 Jul (konfirmasi "Pengindeksan diminta" berhasil, beda dari percobaan sebelumnya yang gagal tanpa konfirmasi). Data baseline saat ini (filter per-halaman, 3 bulan): **0 klik / 0 tayangan / 0% CTR**.
- **Blocker:** decision tree revisi title/meta belum bisa dijalankan — percuma optimasi judul untuk halaman yang belum terindeks. Harus tunggu index beres dulu.

### Reminder Google Calendar dibuat
27 Juli 2026, 09:00 WIB — "Cek ulang index Artikel #1 Pillar (GSC)". Cek dulu duplikat (aman, tidak ada). Deskripsi event: cek tab "INDEKS GOOGLE" di Inspeksi URL, kalau sudah "URL ada di Google" lanjut evaluasi impresi & CTR untuk decision tree.

---

## 5. Orientasi Ulang Interface GSC

Ronald sempat menyatakan buta total dengan interface GSC (kendala historis, mirip pola yang sama dengan citation local & GitHub dulu). Diajarkan ulang dari nol:
- Beda tab **Performa** (data klik/impresi/CTR) vs **Inspeksi URL** (status 1 URL spesifik + minta index) vs **Halaman** (laporan agregat index seluruh situs)
- Cara filter Performa ke 1 halaman spesifik: tombol "Tambahkan filter" → Halaman → "Sama persis dengan URL" (bukan tab "HALAMAN" biasa yang cuma urut berdasar volume, tidak filter tepat)
- Beda tab **Uji Langsung** (real-time, "kalau di-crawl sekarang") vs **Indeks Google** (status tercatat di database, butuh waktu update)
- Kolom "Tambahkan peta situs baru" di menu Peta Situs BUKAN kolom pencarian — itu form submit sitemap baru, jangan diisi kalau sitemap sudah terdaftar

---

## Pelajaran Kunci Sesi Ini

1. **Artikel tertua bukan jaminan performa terbaik** — Pillar (artikel #1, paling lama) justru satu-satunya yang nol total, sementara artikel lebih baru semua sudah ada tayangan. Umur artikel tidak otomatis berkorelasi dengan kekuatan sinyal index kalau internal linking-nya lemah di awal.
2. **Diagnosis sistematis mengalahkan asumsi cepat.** Dugaan awal "tunggu saja, soal waktu" hampir diterima mentah-mentah, tapi baseline data 0/0/0% yang janggal (dibanding artikel lain yang semua ada tayangan) memicu investigasi lebih dalam — yang untungnya berujung "tidak ada yang rusak", tapi tetap perlu dibuktikan, bukan diasumsikan.
3. **Draft konten dari Claude sendiri bisa melanggar aturan situs (em dash)** — Ronald yang menangkap ini. Pengingat: Claude perlu self-check lebih ketat terhadap draft sendiri sebelum diserahkan, meskipun tahu aturannya ada di file referensi.
4. **Additive content vs revisi konten adalah pembeda penting** — section baru boleh kapan saja, tapi evaluasi title/meta wajib nunggu data GSC valid (dan sekarang, wajib nunggu index beres dulu juga).

---

## Progress Tracker

`progresstrackerbelajar.xlsx`: Topik 31 (Topical Authority) dan 32 (Content Gap Analysis) ditandai ✅ Selesai, 22 Jul 2026. Topik 34 (Content Refresh) diberi catatan progres tapi status tetap 🟡 Sedang (belum bisa ditutup — evaluasi Pillar belum tuntas). Progress keseluruhan naik dari 29/47 → **31/47 topik (66%)**.

Fase 4 (Content SEO & Authority): 0/4 → **2/4 tracker resmi**, 1 topik (Content Refresh) sedang berjalan, 1 topik (E-E-A-T) belum dimulai.

---

## Sesi Berikutnya

**Setelah 27 Juli (reminder GSC index Pillar):**
1. Cek ulang status index Pillar → kalau sudah terindeks, lanjut evaluasi impresi & CTR riil, jalankan decision tree revisi title/meta (draft sudah siap di status-aktif Bagian 2)
2. Kalau MASIH belum terindeks per 27 Jul, investigasi lanjutan diperlukan — kemungkinan minta bantuan dari sisi lain (cek Search Console lagi, atau pertimbangkan apakah perlu re-submit sitemap manual)

**Topik Fase 4 tersisa:**
3. **E-E-A-T Signals** (Topik 33) — belum dimulai
4. Sisa 4 topik roadmap Fase 4 yang tidak ada di tracker resmi (Long-form vs short-form, Featured Snippet Hunting, PAA) — opsional, bisa disisipkan kapan saja

**Lain-lain yang masih menggantung (lihat status-aktif Bagian 4 untuk daftar lengkap):**
- Topik 22 — Local Citation Building (masih ditunda, blocker dokumen)
- Artikel #13 & #14 (target 28 Jul–10 Agt)
- Sync GitHub manual untuk file 19-21 Jul (akses tulis masih diblokir)

File project sudah diperbarui: `status-aktif-v2.md` (v2.17), `progresstrackerbelajar.xlsx` (31/47). Sesi berikutnya bisa dimulai chat baru dengan konteks penuh dari project knowledge.

---

*Handoff Sesi 18 — 22 Juli 2026.*
