# Handoff Sesi Belajar SEO — Sesi 24
**Tanggal:** 5 Agustus 2026
**Topik:** Audit tayangan per negara Artikel #5 (lanjutan handoff-sesi-23) + sesi review/self-assessment 7 konsep dari rangkaian audit Artikel #5
**Status:** ✅ Selesai
**Melanjutkan dari:** handoff-sesi-23-belajar-seo.md (klaster merchant & warung ditutup, antrean: audit negara → Broadcast WhatsApp → Fase 5)

---

## 1. Audit Tayangan per Negara Artikel #5 — Ditutup

**Langkah dijalankan:** GSC → Performa → Hasil penelusuran → filter Halaman berisi "gofood", rentang 3 bulan → tab Negara.

**Temuan awal (screenshot Ronald):** 17 baris negara, total 376 tayangan kalau dijumlah manual. Vietnam 35 tayangan, posisi 60,4.

**Kesalahan pertama (dan koreksinya):** Ronald sempat menghitung porsi Vietnam 9,41% lalu menyimpulkan "di bawah 5%, tidak ditindaklanjuti" — padahal 9,41 di atas 5. Diperbaiki: pita keputusan 5-20% berarti "periksa dulu kuerinya", bukan "abaikan otomatis". Ronald sebenarnya sudah mengerjakan langkah pemeriksaan itu (klik ke tab Kueri terfilter Vietnam), cuma labelnya keliru.

**Isi 5 kueri Vietnam** (dari klik tab Negara → Kueri, filter otomatis ke Vietnam): "đăng ký nhà hàng go food" (13 tayangan), "đăng ký go food" (10), "cách đăng ký go food" (7), "cách thức đăng ký gian hàng trên gofood" (4), "đăng ký cửa hàng go food" (1). Semua bermakna identik dengan target Artikel #5 ("cara daftar GoFood"), cuma beda bahasa. Posisi 56,1-66,0 untuk semuanya, 0 klik.

**Ini koreksi data terhadap catatan lama:** v2.37/v2.38 mencatat "2 kueri Vietnam, 22 tayangan" — angka itu diambil dari daftar kueri gabungan biasa (bukan hasil filter negara), dan ternyata meleset. Filter negara yang benar menunjukkan 5 kueri, 35 tayangan. Pelajaran: daftar kueri agregat menyembunyikan ekor data (long-tail); segmentasi per dimensi (negara, perangkat, dll) yang memunculkannya secara lengkap.

**Keputusan akhir: TIDAK ADA TINDAKAN.** Tiga alasan sekaligus, bukan cuma persentase:
1. Posisi 56-66 = halaman 6-7 Google, mustahil dilihat manusia (0 klik membuktikan ini)
2. GoFood/Gojek resmi menghentikan seluruh operasinya di Vietnam sejak 16 September 2024 — tidak ada yang bisa didaftarkan di sana meski rankingnya naik
3. Artikelnya berbahasa Indonesia, tidak akan dibaca pencari Vietnam meski sampai terklik

**Prinsip yang ditekankan ke Ronald:** persentase (5-20% dsb) cuma pemicu untuk MELIHAT, bukan vonis otomatis. Yang menentukan tindakan adalah isi kuerinya. Segmen 9,3% ini tetap "tidak ditindaklanjuti" bukan karena kecil, tapi karena tiga alasan konkret di atas — beda dari kasus yang nanti mungkin muncul di mana segmen kecil justru layak dikerjakan.

---

## 2. Temuan Teknis Tak Terduga: Total Tabel GSC ≠ Total Kotak Ringkasan

Saat verifikasi silang, ditemukan total tayangan di kotak ringkasan atas grafik (1.240) jauh lebih besar dari total baris tabel Negara (376). Sempat diduga ada filter tersisa dari sesi lalu — dugaan itu salah, filter Ronald sudah bersih (3 bulan, Web, Halaman berisi gofood).

**Verifikasi ke dokumentasi resmi Google:** perbedaan ini perilaku normal GSC. Kueri anonim (kueri yang cuma dicari segelintir orang dalam 2-3 bulan) dan limit baris internal menyembunyikan sebagian data dari tabel pengelompokan, tapi data itu tetap terhitung di kotak ringkasan/diagram.

**Pembuktian tambahan yang dijalankan Ronald sendiri (latihan mandiri):** cek tab Perangkat dengan filter yang sama → hasilnya 236 Desktop + 140 Mobile = 376. Angka identik dengan tab Negara. Ini membuktikan penyembunyian data terjadi di level baris (kueri+halaman+negara+perangkat+tanggal sebagai satu kesatuan), bukan spesifik ke dimensi negara — kalau satu baris dibuang karena kuerinya anonim, seluruh info di baris itu (termasuk negara dan perangkatnya) ikut hilang dari tabel manapun.

**Ditambahkan ke `aturan-referensi` Bagian 8** (file naik ke v1.16) sebagai pelajaran teknis permanen: jangan pernah mencampur angka kotak ringkasan/diagram dengan angka total tabel dalam satu kalimat kesimpulan atau sebagai bukti troubleshooting.

---

## 3. Sesi Review — Self-Assessment 7 Konsep

Karena rangkaian audit Artikel #5 (sesi 21-24) memuat banyak konsep baru sekaligus, dilakukan sesi review terpisah alih-alih mengulang seluruh materi. Ronald menandai 7 konsep dari pengalamannya sendiri (P = paham, S = setengah, T = tidak paham):

| # | Konsep | Tanda awal | Hasil |
|---|---|---|---|
| 1 | Baseline GSC 3 bulan & alasannya | S | Diperjelas: juga supaya semua artikel diukur pakai penggaris waktu yang sama |
| 2 | Kenapa menahan revisi judul meski CTR rendah | T | Dibedah tuntas — lihat Bagian 4 di bawah |
| 3 | Jarak tembak: sortir Posisi, cara tentukan rentang 5-18 | S (paham arah, belum cara tentukan rentang) | **Masuk antrean sesi berikutnya** |
| 4 | Tiga pilihan saat klaster ditemukan | S → koreksi kecil | "Artikel baru" salah dipahami sebagai "keyword salah sasaran" — dikoreksi: keyword salah sasaran diperbaiki di artikel yang ADA (kasus Artikel #3), artikel baru dibuat kalau maksud pencarinya sudah topik lain |
| 5 | Kosakata mati vs kosakata kurang lengkap | Awalnya ditandai P, dikoreksi sendiri oleh Ronald jadi T | **Masuk antrean sesi berikutnya**, setelah #3 |
| 6 | Kenapa tukar heading, bukan tambah section (klaster warung) | S | Dilengkapi: section baru akan bertabrakan dengan H2 yang sudah menjawab pertanyaan itu, dan memperparah pengulangan heading yang sudah 4 dari 8 |
| 7 | Segmentasi negara & kueri anonim | P | Terbukti lewat latihan mandiri tab Perangkat |

**Keputusan metode:** tidak mengulang seluruh materi dari awal. Alih-alih, satu konsep bertanda T dibedah tuntas per sesi, dengan analogi baru yang berbeda dari penyampaian pertama. Sisanya diperbaiki sebagai koreksi kecil di tempat.

---

## 4. Konsep yang Dibedah Tuntas: CTR Harus Dibaca Berpasangan dengan Posisi

Analogi baru: posisi = letak warung, CTR = persentase orang lewat yang mampir, judul/meta = papan nama/spanduk. Warung di jalan ramai (posisi tinggi) dengan CTR rendah = masalah spanduk, ganti judul membantu. Warung di gang buntu (posisi rendah) dengan CTR rendah = tidak ada yang lewat, ganti spanduk sia-sia.

**Aturan baca yang diajarkan:**
- Posisi 1-5 + CTR jauh di bawah wajar → revisi judul/meta
- Posisi 10 ke bawah + CTR rendah → gejala posisi, revisi judul tidak menyelesaikan apa pun
- Posisi di antaranya → cek tren dulu (kasus Artikel #4: posisi 7,7 secara aturan mentah "harus direvisi", tapi ditahan karena tren impresi masih naik — revisi di tengah tren naik berisiko mereset pembelajaran Google DAN menghilangkan kemampuan menjelaskan sebab-akibat ke klien)

**Data pendukung (dicari via web search, bervariasi antar studi, ditandai sebagai rentang bukan angka pasti):** berbagai studi CTR 2025-2026 (seoClarity, First Page Sage, Backlinko, GrowthSRC) sepakat kurva menurun tajam sejak posisi 1, dan posisi 11 ke bawah umumnya di bawah 1% CTR — konsisten dengan Artikel #5 di posisi 16 dengan CTR 0,1%.

---

## 5. Latihan Roleplay — Balasan ke Klien

Dua skenario, Ronald diminta membalas seolah klien nyata:

**Klien A** (2.000 tayangan, CTR 0,4%, posisi 22, minta ganti judul) — Ronald: diagnosis benar (menolak permintaan klien, menjelaskan posisi belum halaman 1). Dua koreksi: (1) belum pakai analogi konkret saat menjelaskan ke klien awam, (2) menutup dengan "saya cek dulu, nanti saya kabari" padahal jawabannya sudah diketahui — pola ini disorot sebagai kebiasaan yang perlu diperbaiki.

**Klien B** (800 tayangan, CTR 1,1%, posisi 3,2, klien pikir "sudah bagus, biarkan") — Ronald: arah diagnosis benar (tidak setuju dengan klien), tapi alasan yang diberikan salah ("mengikuti tren yang berlaku" — karangan, tidak berdasar data). Alasan yang benar: posisi bagus + CTR jauh di bawah wajar untuk posisi itu = persis kasus yang butuh revisi judul/meta.

**Pola yang sama muncul di kedua balasan:** menutup dengan "saya periksa dulu" sebagai kalimat aman, padahal diagnosisnya sudah diketahui saat itu juga. Disarankan: simpan kalimat itu untuk hal yang memang belum diketahui, bukan untuk menunda menyampaikan jawaban yang sudah ada.

---

## 6. Status Fase Belajar

Tidak ada topik kurikulum resmi baru dibuka sesi ini — murni maintenance (audit lanjutan) dan review. Progress resmi tetap 32/47 (68%), Fase 4 masih 3/4.

**Antrean sesi berikutnya (disepakati):**
1. Konsep #3 — cara menentukan rentang jarak tembak (kenapa posisi 5-18, bukan angka lain)
2. Konsep #5 — beda kosakata mati vs kosakata kurang lengkap (ditandai T oleh Ronald sendiri)
3. 9 Agustus 2026: Ronald memimpin sendiri audit GSC Artikel #6 Foto Makanan dari awal sampai akhir (jadwal cek GSC sudah ada di kalender), Claude cuma mengoreksi — dipakai sebagai uji kemandirian atas seluruh rangkaian konsep Artikel #5
4. Setelah itu: Broadcast WhatsApp (tuntaskan label ke semua kontak dulu), baru Fase 5 Off-Page SEO

---

## 7. Koreksi Tambahan Setelah Pemeriksaan Ulang (masih 5 Agustus)

Ronald meminta pemeriksaan ulang atas update v2.40/v1.16 di atas — apakah `aturan-referensi` memang seharusnya ikut berubah, dan apakah protokol cek versi (Bagian 10) benar dijalankan. Hasil pemeriksaan: benar dijalankan, tapi ditemukan dua rujukan silang basi sebagai efek sampingnya sendiri, keduanya diperbaiki:

1. `aturan-referensi` sempat menunjuk `status-aktif` v2.37 (basi) sebelum sesi ini — sudah diperbaiki jadi v2.40 dalam update pertama.
2. Setelah `aturan-referensi` naik ke v1.16, `status-aktif` masih menunjuk v1.15 sesaat — diperbaiki jadi v1.16, lalu v1.17.
3. Setelah `status-aktif` naik lagi ke v2.41, `aturan-referensi` sempat menunjuk v2.40 — diperbaiki jadi v2.41.

**Keputusan kebijakan baru dalam proses ini, disetujui Ronald:** aturan lama "satu file bersama hanya boleh diedit di satu sesi per hari" (Bagian 10 `aturan-referensi`) **dicabut**, digantikan sepenuhnya oleh protokol cek versi 4 Agustus. Alasan: pembatasan sesi per hari tidak realistis dengan pola kerja Ronald yang sering menyentuh beberapa project sehari, dan terbukti hari ini sendiri — `status-aktif` diedit 4 kali (v2.38, v2.39, v2.40, v2.41) tanpa kehilangan data, karena protokol cek versi yang bekerja, bukan pembatasan jumlah sesi.

**Versi final kedua file setelah seluruh sesi ini:** `status-aktif-v2.md` → **v2.41**, `aturan-referensi-v1.md` → **v1.17**. Rujukan silang di kedua file sudah saling cocok, diverifikasi dua arah.

---

## 8. File yang Diperbarui Sesi Ini

- `status-aktif-v2.md` → **v2.41** (v2.40: audit negara ditutup, pending item dicoret, "Selesai terakhir" +2 entri; v2.41: rujukan silang ke aturan-referensi diperbaiki, keputusan pencabutan aturan "satu file per hari" dicatat — lihat Bagian 7)
- `aturan-referensi-v1.md` → **v1.17** (v1.16: Bagian 8 pelajaran teknis baru total tabel GSC vs kotak ringkasan/diagram + baris tabel pelajaran cepat, rujukan silang ke status-aktif diperbaiki; v1.17: Bagian 10 aturan "satu file per sesi per hari" dicabut, digantikan protokol cek versi 4 Agustus, rujukan silang disinkronkan ulang)
- `handoff-sesi-24-belajar-seo.md` (file ini)

**Belum diupload Ronald ke Project Belajar SEO & Digital Marketing** — ketiga file di atas perlu diupload manual menggantikan versi lama di project knowledge. Handoff sesi 23 (dari sesi sebelumnya) kemungkinan juga masih belum diupload — cek sekalian saat upload sesi ini.
