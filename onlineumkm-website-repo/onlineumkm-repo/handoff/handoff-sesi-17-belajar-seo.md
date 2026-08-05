# Handoff Sesi Belajar SEO — Sesi 17
**Tanggal:** 13 Juli 2026
**Topik:** Topik 23 (Review Management), Topik 24 (Local Keyword Strategy), Topik 25 (LocalBusiness Schema Homepage) — Fase 3, Local SEO — **KETIGANYA SELESAI**
**Status:** ✅ Selesai
**Melanjutkan dari:** handoff-sesi-16-belajar-seo.md (Topik 22 masih ditunda, tidak dilanjut sesi ini)

---

## 1. Topik 23 — Review Management

- Prinsip Google Local Pack: prominence (dibentuk signifikan oleh review) sama pentingnya dengan relevansi & jarak.
- Aturan wajib dibahas: jangan beli review, jangan review gating, jangan beri imbalan sebagai syarat review.
- 2 template WA dibuat:
  1. **Minta Review** — dikirim H+1 setelah website live, pakai link "Minta ulasan" dari dashboard GBP (bukan link Maps biasa)
  2. **Respon Review Negatif** — formula 4 langkah (terima kasih → empati → klarifikasi faktual opsional → ajak ke WA pribadi)
- Sistem pemantauan: digabung ke jadwal cek GSC mingguan yang sudah ada di Google Calendar, bukan rutinitas terpisah.
- Target realistis: 3–5 review pertama setelah klien pertama, masuk perlahan (bukan dikejar cepat, demi menghindari pola tidak wajar yang bisa memicu penghapusan otomatis Google).
- Cara tangani review palsu: fitur "Laporkan ulasan" di GBP, balas netral tanpa emosi.
- Aturan schema: JANGAN pasang `Review`/`AggregateRating` sebelum ada review asli terverifikasi (prinsip anti-fabrikasi data, konsisten dengan aturan referensi).
- **Output:** 2 template disimpan permanen di `citation-tracker-onlineumkm.xlsx` sheet baru **"Template Review"** (format konsisten dengan sheet Citation Tracker — header biru `#1F4E78`).

---

## 2. Topik 24 — Local Keyword Strategy

### Riset dijalankan 2 putaran (Ronald screenshot manual)

**Putaran 1 — Bing/Edge** (tanpa sadar, karena browser default beda dari yang dimaksud):
- Autocomplete 3 kota (Medan/Surabaya/Bandung) untuk "jasa website umkm [kota]": tidak ada match persis, saran tidak nyambung (jasa AC, universitas, dll).
- Local Pack (peta TomTom) tetap menampilkan kompetitor nyata: JasaWebMedan (sejak 2009), OMG, Bekerza (Medan); Bulban Digital, Malang Creative, Juraganweb (Surabaya); Giwangan Studio, Global Fikri Infotech, Anikworks, Segiatech (Bandung).

**Putaran 2 — Google langsung** (diulang atas permintaan, untuk pembanding platform utama):
- Autocomplete Google juga nyaris kosong (cuma saran nama provinsi/tahun).
- Organic + Local Pack Google jauh lebih padat: WebNesia (4,9★, 2.964 ulasan, Medan), Resolusiweb (4,9★, 3.742 ulasan, Bandung), Global Fikri Infotech muncul konsisten di Bing & Google (konfirmasi lintas platform = bisnis aktif nyata).

### Kesimpulan kunci
**Autocomplete kosong ≠ tidak ada demand.** Organic result & Local Pack adalah sinyal jauh lebih kuat untuk niat pencarian lokal — search engine sendiri yang menilai relevansi lokal cukup untuk menampilkan Local Pack.

### Strategi silo kota dikonfirmasi tetap valid
- Kota utama (Medan) = klaim kuat, selaras GBP.
- Kota ekspansi (Surabaya, Bandung, Jakarta, dst.) = trafik informasional, WAJIB tetap jujur soal sifat layanan remote — jangan klaim "kami di kota X".
- Pola kalender konten (#9–#12, format "Promosi Online Warung Makan [Kota]") sudah sesuai prinsip silo lokal ini.

### Gap teridentifikasi
Belum ada artikel **hub** yang menghubungkan semua kota jadi satu klaster (mis. "Panduan Promosi Warung Makan Online: Medan, Surabaya, Bandung, dst.") — dicatat untuk content calendar mendatang.

### 8 Kompetitor dicatat untuk Topik 30 (Competitor Content Audit, Fase 4)
Resolusiweb, WebNesia, UKMGO Digital, Sekawan Media, Malang Creative, Juraganweb, Bekerza, Dokterweb.

*(Catatan: nama-nama ini juga relevan untuk Topik 26 — Competitor Local Analysis, yang jadi topik berikutnya di roadmap Fase 3.)*

---

## 3. Topik 25 — LocalBusiness Schema Homepage

### Temuan kunci: koreksi catatan lama soal lokasi sumber schema
Catatan sesi 18 Juni sebelumnya mencatat schema "ditambahkan manual via WPCode Lite" tanpa lokasi spesifik. Setelah investigasi (cek Yoast Site Representation → cek WPCode Code Snippets → keduanya nihil), sumber sebenarnya ditemukan di **WPCode → Header & Footer** (kolom Header, bukan menu "Code Snippets"/"All Snippets"). Ini sudah dikoreksi di `aturan-referensi` v1.6.

### Validasi awal (validator.schema.org)
3 item terdeteksi tanpa error: WebPage, LocalBusiness, CreativeWork. Tapi field `LocalBusiness` bermasalah:
- `areaServed: "Indonesia"` — bertabrakan dengan keputusan final GBP (area layanan Medan saja, bukan level negara)
- `openingHours` — kosong

### Perbaikan dieksekusi
1. `areaServed`: "Indonesia" → **"Medan"**
2. `openingHours`: ditambahkan **"Mo-Su 09:00-21:00"** (dari data GBP, format 24 jam sesuai standar schema.org meski GBP tampilkan AM/PM)
3. `description`: "...UMKM Indonesia" → **"...UMKM Medan"** (diselaraskan Ronald sendiri, konsistensi tambahan)

### Hasil akhir (validasi terakhir)
LocalBusiness schema: **TIDAK ADA KESALAHAN, TIDAK ADA PERINGATAN**. `address` tetap tanpa `streetAddress` (benar untuk SAB, alamat tetap tersembunyi).

### Pelajaran teknis baru (masuk `aturan-referensi` v1.6, Bagian 8)
- Sumber schema LocalBusiness homepage = WPCode Header & Footer, bukan Code Snippets/Yoast.
- Aturan edit JSON-LD manual: baris terakhir sebelum `}` TIDAK boleh diakhiri koma, baris lain WAJIB diakhiri koma. Validasi ulang di validator.schema.org setelah tiap edit.

---

## Pelajaran Kunci Sesi Ini

1. **Cek nama browser/platform sebelum tarik kesimpulan riset.** Screenshot pertama Ronald ternyata dari Bing/Edge (ciri: tile peta TomTom), bukan Google — sempat menimbulkan analisis yang perlu direvisi begitu putaran kedua (Google asli) dikirim.
2. **Catatan lama soal lokasi teknis bisa kurang presisi dan menyesatkan sesi berikutnya** — catatan "via WPCode Lite" tanpa spesifik menu Header & Footer vs Code Snippets sempat bikin pencarian muter di 2 tempat salah dulu sebelum ketemu sumber sebenarnya.
3. **Nomor topik di `progresstrackerbelajar.xlsx` TIDAK sama dengan penomoran di roadmap/handoff/status-aktif.** Tracker: Topik 27=Review, 28=Local Keyword, 29=LocalBusiness Schema. Roadmap/status: Topik 23/24/25 untuk hal yang sama. Ini bukan kesalahan sesi ini, tapi perlu disadari — kalau perlu, bisa disamakan penomorannya di sesi lain (tidak mendesak).
4. **Tracker aktual cuma 46 topik**, bukan 47 seperti tertulis di roadmap dan beberapa file. Perlu dicek ulang sumber ketidaksesuaiannya kapan-kapan.
5. **Review kompetitor dengan ribuan ulasan (WebNesia 2.964, Resolusiweb 3.742) jadi bukti nyata kenapa Topik 23 (Review Management) penting** — bukan cuma teori, tapi gap kompetitif yang konkret buat Online UMKM yang masih 0 review.

---

## Progress Tracker

Topik 23, 24, 25 ditandai ✅ Selesai di `progresstrackerbelajar.xlsx` (baris 32, 33, 34 — nomor tracker 27, 28, 29). Progress keseluruhan naik dari 25/46 → **28/46 topik (61%)**.

Fase 3 (Local SEO): dari 2/7 → **5/7**. Tersisa: Topik 22 (ditunda, blocker dokumen/device) dan Topik 26 (Competitor Local Analysis, belum mulai).

---

## Sesi Berikutnya

**Opsi lanjutan Fase 3:**
1. **Topik 26 — Competitor Local Analysis** — 8 kompetitor sudah tercatat dari sesi ini, tinggal dianalisis mendalam (harga, USP, konten, kekuatan/kelemahan)
2. **Topik 22 — Local Citation Building** — lanjut kalau blocker (ID/passport, NPWP, laptop) sudah teratasi, atau coba ulang KlikDirektori

Setelah salah satu atau keduanya selesai, Fase 3 (Local SEO) tuntas 7/7, lanjut ke Fase 4 (Content SEO & Topical Authority).

File project sudah diupload Ronald ke seluruh project (status-aktif v2.5, aturan-referensi v1.6, progresstrackerbelajar, citation-tracker dengan sheet Template Review). Sesi berikutnya bisa dimulai chat baru dengan konteks penuh dari project knowledge.

---

*Handoff Sesi 17 — 13 Juli 2026.*
