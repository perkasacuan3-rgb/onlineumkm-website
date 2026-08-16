# Handoff Sesi Belajar SEO — Sesi 28

**Tanggal:** 13 Agustus 2026
**Topik:** Uji efek revisi title/meta Artikel #2 memakai periode pembanding, plus dua pelajaran GSC baru
**Status:** ✅ Selesai, verdict tidak konklusif dan itu hasil yang sah
**Melanjutkan dari:** handoff-sesi-27-belajar-seo.md (11 Agt: Pillar terindeks, audit mandiri Artikel #6)

---

## 1. Checklist Event Calendar Ternyata Cacat

Event reminder 13 Agustus dibuat 23 Juli dengan instruksi "rentang 28 hari sejak revisi". Revisi live 23 Juli, jadi per 13 Agustus baru lewat 21 hari. Checklist tidak bisa dijalankan apa adanya.

Sesi tidak ditunda ke 20 Agustus. Alasannya: angka 28 hari di checklist lama tidak punya dasar khusus, dan menunggu seminggu cuma menambah sekitar 80 tayangan. Yang dipakai sebagai gantinya adalah dua jendela sama panjang, 18 hari masing-masing.

**Pelajaran proses:** checklist yang ditulis berbulan-bulan sebelumnya perlu dicek kelayakannya terhadap tanggal reminder, bukan langsung dijalankan.

---

## 2. Konsep Baru: Periode Pembanding

Lima evaluasi GSC sebelumnya (#2, #3, #4, #5, #6) menjawab "artikel ini performanya bagaimana". Sesi ini menjawab pertanyaan berbeda: "apakah perubahan saya berhasil". Jendela 3 bulan bergulir tidak bisa menjawab pertanyaan kedua, karena judul baru cuma menempati 21 dari 90 hari dan efeknya larut.

Alat yang benar: filter Tanggal → **Bandingkan** → rentang buatan sendiri, dua periode sama panjang.

Rentang yang dipakai:
- **Sesudah:** 24 Juli – 10 Agustus (18 hari)
- **Sebelum:** 6 Juli – 23 Juli (18 hari)

Tanggal 23 Juli sengaja masuk periode Sebelum. Hari itu campuran judul lama dan baru, jadi lebih aman dihitung sebagai milik yang lama.

Filter halaman dipasang lewat klik baris di tab Halaman, bukan tambah filter manual. Diverifikasi dari bilah alamat: `page=!https%3A%2F%2Fonlineumkm.id%2Fkenapa-warung-makan-sepi-padahal-enak%2F`. Tanda seru berarti operator URL persis, sesuai pelajaran 11 Agustus.

---

## 3. Hasil Pengambilan Data

| Metrik | Sebelum (06/07–23/07) | Sesudah (24/07–10/08) |
|---|---|---|
| Klik | 8 | 15 |
| Tayangan | 751 | 644 |
| CTR | 1,1% | 2,3% |
| Posisi rata-rata | 6,5 | 6,2 |

Angka tabel dan kotak ringkasan dicocokkan, keduanya berasal dari satu tarikan filter yang sama.

**Pola perubahannya cocok dengan teori:** posisi hampir diam, tayangan malah turun 14%, tapi klik naik hampir dua kali lipat. Lebih sedikit orang melihat, lebih banyak yang mengklik. Antara mata melihat hasil pencarian dan jari mengklik, yang berdiri di tengah cuma tulisan yang terpampang di sana.

Ini bukti langsung untuk konsep 6 Agustus: revisi judul menaikkan klik pada posisi yang sama, bukan menaikkan posisinya.

---

## 4. Kesalahan Claude yang Dikoreksi

Sebelum data diambil, Claude memperkirakan periode Sesudah akan berisi sekitar 200 tayangan dan 1 sampai 2 klik, lalu menyuruh Ronald bersiap untuk jawaban "belum bisa disimpulkan".

Kenyataannya 644 tayangan dan 15 klik. Meleset tiga kali lipat.

Penyebabnya: 1.020 tayangan dibagi 90 hari lalu dikali 18, seolah trafiknya rata sepanjang tiga bulan. Artikel ini sedang menanjak tajam sejak Mei, hampir semua tayangannya menumpuk di Juli dan Agustus. Membagi rata angka yang sedang tumbuh menghasilkan perkiraan yang salah arah.

---

## 5. Uji Tabel Kueri Gagal, dan Itu Temuannya

Rencana awal: cari 107 tayangan yang hilang di tabel Kueri, lihat posisinya. Kalau yang hilang kebanyakan kueri posisi jauh tanpa klik, kenaikan CTR cuma aritmatika penyebut yang menyusut.

Uji ini tidak bisa dijalankan.

| | Tayangan terlihat di tabel | Total di ringkasan | Porsi terlihat |
|---|---|---|---|
| Sebelum | 110 | 751 | **14,6%** |
| Sesudah | 9 | 644 | **1,4%** |

Tabel cuma berisi 11 baris, dan itu seluruhnya ("1-11 dari 11"). Kolom Klik nol di semua baris pada kedua periode, padahal ringkasannya 15 dan 8 klik. Seluruh 23 klik lahir dari kueri yang tidak disebut namanya.

**Konsep baru:** porsi data tersembunyi yang timpang membunuh perbandingan. Periode Sebelum memperlihatkan 14,6% datanya, periode Sesudah cuma 1,4%, sepuluh kali lipat lebih sempit. Membandingkan dua daftar kueri itu seperti membandingkan foto dari pintu depan dengan foto dari lubang kunci.

Kenapa porsi tersembunyinya melonjak setajam itu, belum ada penjelasan yang meyakinkan. Dibiarkan terbuka, tidak dikarang.

**Jebakan yang berhasil dihindari.** Dua baris melompat ke mata:
- "kenapa warung sepi pembeli": 71 tayangan, posisi 7,4 → 0 tayangan
- "penyebab warung sepi pembeli": 22 tayangan, posisi 7,7 → 0 tayangan

Total 93 tayangan lenyap, persis kueri yang jadi alasan kata "pembeli" disisipkan ke judul bulan Juli. Kesimpulan yang menggoda: revisinya menghancurkan dua kueri utama. Kesimpulan itu tidak diambil, karena angka nol bisa berarti kueri betul-betul hilang atau pindah ke kantong tersembunyi, dan dengan 98,6% data periode Sesudah ada di kantong itu, kemungkinan kedua sangat terbuka.

Pola kesalahan yang sama dengan Artikel #6 tanggal 11 Agustus: mengambil kesimpulan dari bagian kecil data tanpa mengukur seberapa besar bagian yang hilang. Bedanya kali ini porsinya diukur duluan.

---

## 6. Laporan AI Generatif Menutup Sebagian Celah

Ronald membuka laporan Performa → AI generatif (Beta) tanpa diminta, dengan filter halaman dan perbandingan tanggal yang sama.

| | Tayangan AI |
|---|---|
| Sebelum (06/07–23/07) | 103 |
| Sesudah (24/07–10/08) | 53 |
| Selisih | −50 |

Dari 107 tayangan yang hilang, **50 hilang dari fitur AI**. Hampir separuh penurunan datang dari satu sumber ini, bukan dari judul.

**Uji penjelasan tandingan, lewat pintu lain.** Kalau kenaikan CTR cuma aritmatika penyebut menyusut, membuang tayangan AI seharusnya meruntuhkan kenaikan itu:

- Sebelum: 8 klik ÷ (751 − 103) = 8/648 = **1,23%**
- Sesudah: 15 klik ÷ (644 − 53) = 15/591 = **2,54%**

Rasio 2,06, sementara rasio angka aslinya 2,09. Praktis tidak berubah.

Asumsinya semua klik lahir dari tayangan non-AI, dan itu tidak bisa dipastikan karena laporan AI tidak punya kolom klik. Tapi asumsi itu justru asumsi paling keras terhadap kesimpulan, dan kesimpulannya tetap bertahan.

Fakta terverifikasi soal laporan ini ada di Bagian 8.

---

## 7. Keputusan

**Judul dan meta Artikel #2 TIDAK disentuh.** Arahnya benar, mengubahnya lagi sekarang justru menghapus kemungkinan mengukur apa pun.

**Status dicatat sebagai INDIKASI KUAT, BUKAN BUKTI.**

Alasannya: selisihnya cuma 7 klik (8 lawan 15). Hitungan kasar, selisih CTR 1,2 poin sementara sebaran wajar untuk angka sekecil ini sekitar 0,7 poin, jadi sekitar 1,7 kali sebaran. Praktisi biasanya baru menyebut sesuatu terbukti di angka 2 ke atas.

Bedanya penting waktu bicara ke klien. "Judul baru kelihatannya menaikkan klik, saya pantau sebulan lagi" itu jujur. "Judul baru terbukti menggandakan CTR" itu janji yang bisa berbalik menampar bulan depan.

**Penjelasan tandingan (CTR naik karena penyebut menyusut) melemah jauh, tidak mati sepenuhnya.**

**Penurunan tayangan punya penyebab terpisah dan di luar kendali Ronald:** Google mengurangi frekuensi menampilkan artikel ini di dalam fitur AI. Fluktuasi mingguan tayangan AI itu wajar dan sering berasal dari Google menguji tampilan antarmuka, bukan dari cacat konten.

---

## 8. Fakta Terverifikasi Sesi Ini

Semuanya dicek lewat pencarian, bukan ingatan.

**Laporan Generative AI di Search Console:**
- Diluncurkan 3 Juni 2026, masih Beta, awalnya untuk sebagian situs
- Datanya **sudah termasuk** di laporan Performa keseluruhan. Yang baru cuma tampilannya, bukan datanya
- Isinya tayangan saja. Tidak ada klik, CTR, atau nama kueri
- Klik dari dalam AI Overview tercatat di laporan Performa utama, tidak pernah di laporan AI
- Mencampur AI Overviews dan AI Mode jadi satu, tidak bisa dipisah
- AI Overview menempati satu posisi di halaman hasil, dan semua link di dalamnya mewarisi posisi itu

**Antarmuka GSC:**
- Filter Tanggal di atas halaman, lalu tombol **Bandingkan** (terverifikasi di dokumentasi resmi Search Console)
- Cuma boleh ada satu perbandingan aktif. Menambah perbandingan baru menghapus yang lama
- Kotak ringkasan tayangan di antarmuka Indonesia tertulis **"Total tayangan iklan"**. Itu kekeliruan terjemahan, tidak ada hubungannya dengan iklan. Jangan sampai terucap "iklan" ke klien

---

## 9. Reminder Calendar Dibuat

**27 September 2026, 09.00 WIB** — Uji Ulang CTR Artikel #2, jendela 63 hari. Popup dan email 24 jam sebelumnya. Dicek tidak ada duplikat.

Rentang yang akan dipakai:
- Sesudah: 24 Juli – 24 September 2026 (63 hari, seluruhnya judul baru)
- Sebelum: 22 Mei – 23 Juli 2026 (63 hari, seluruhnya judul lama, dihitung dari tanggal terbit)

Checklist di deskripsi event menambahkan dua langkah yang tidak ada di checklist lama: ukur porsi terlihat sebelum menyentuh tabel Kueri, dan buka laporan AI generatif sebelum menyimpulkan apa pun soal tayangan.

**Cacat yang sudah diketahui dan tidak bisa dihilangkan:** artikel ini menanjak sendiri sejak Mei. Periode sebelum revisi otomatis lebih lemah bukan cuma karena judulnya lama, tapi karena artikelnya masih muda. Cara memisahkan efek revisi dari pertumbuhan alami masuk antrean materi.

---

## 10. Antrean Materi Berikutnya

1. Kecukupan sampel — kapan angka cukup besar untuk dipercaya. Sudah muncul sebagai kasus nyata hari ini
2. Memisahkan efek revisi dari tren pertumbuhan alami artikel
3. Broadcast WhatsApp (audit kontak → pelabelan → Broadcast)
4. Fase 5 Off-Page SEO

Progress kurikulum resmi tidak berubah: **32/47 (68%)**, Fase 4 tetap 3/4. Sesi ini maintenance dan latihan, bukan topik kurikulum baru.

---

*Handoff Sesi 28, 13 Agustus 2026.*
