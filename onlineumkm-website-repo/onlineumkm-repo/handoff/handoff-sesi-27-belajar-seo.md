# Handoff Sesi Belajar SEO — Sesi 27
**Tanggal:** 11 Agustus 2026
**Topik:** Verifikasi index Artikel #1 Pillar (BLOCKED sejak Mei) + audit mandiri GSC Artikel #6 Foto Makanan sebagai uji kemandirian
**Status:** ✅ Selesai
**Melanjutkan dari:** handoff-sesi-25-belajar-seo.md, handoff-sesi-26 (chat terpisah, 6 Agt: konsep #5 kosakata mati vs kurang lengkap dituntaskan — antrean konsep resmi habis, tersisa 9 Agt audit mandiri Artikel #6 dan 10 Agt cek Pillar)

---

## 1. Artikel #1 Pillar: Terindeks, Item BLOCKED Ditutup

Ronald membuka sesi dengan dugaan bahwa perubahan yang dia lakukan sebelumnya (caption, gambar unggulan, footer, paragraf CTA, kata di H2, kapitalisasi judul) yang menyebabkan Pillar tidak kunjung terindeks.

**Dugaan ini dikoreksi, arahnya terbalik:** halaman yang berubah adalah alasan Google merayapi ulang, bukan alasan berhenti. Yang benar-benar bisa menahan index cuma dua hal — larangan teknis (noindex, robots.txt, canonical menyimpang) atau keputusan Google sendiri (status "Ditemukan, saat ini tidak diindeks", yang memang status Pillar selama ini).

**Dua kesalahan alat ukur turut dikoreksi di sesi ini:**
1. Laporan Performa (tayangan/klik) tidak bisa membuktikan status index — itu ukuran penampilan di pencarian, bukan status crawl. Alat yang benar: Inspeksi URL.
2. Laporan "Halaman yang diindeks" (agregat situs) punya jeda beberapa hari dari data live — Pillar sempat tidak muncul di daftar 32 halaman bukan karena gagal, tapi karena grafiknya belum sampai ke tanggal crawl Pillar.

**Verifikasi lewat Inspeksi URL (screenshot Ronald):**
- Status: "URL ada di Google", "Halaman diindeks"
- Crawl terakhir: **8 Agustus 2026, 14.52**, oleh Smartphone Googlebot
- Crawl diizinkan: Ya. Pengindeksan diizinkan: Ya
- Kanonis yang dipilih Google = URL yang diperiksa (tidak menyimpang)

**Kesimpulan:** Pillar terindeks, kemungkinan besar cuma soal antrean crawl Google yang panjang untuk situs baru. Konsekuensi: jam data baseline baru mulai berjalan 8 Agustus, bukan 9 Mei (tanggal terbit). Evaluasi GSC penuh belum bisa dikerjakan sampai 3 bulan data terkumpul dari tanggal terindeks.

**Item pending lama ditutup**, digantikan dua reminder Calendar baru:
- **8 September 2026, 10.00 WIB** — cek cepat: sudah ada tayangan atau masih nol (satu pertanyaan saja, tidak ambil keputusan)
- **8 November 2026, 09.00 WIB** — evaluasi GSC penuh pertama, baseline 3 bulan sah

Keduanya dicek tidak ada duplikat sebelum dibuat.

---

## 2. Audit Mandiri Artikel #6 Foto Makanan — Uji Kemandirian

Jadwal semula 9 Agustus 2026, terlaksana 11 Agustus (jeda 2 hari, bukan masalah data). Ronald memimpin penuh dari buka GSC sampai keputusan akhir; Claude di peran koreksi saja, sesuai kesepakatan 6 Agustus.

**Baseline 3 bulan (dibaca benar oleh Ronald):** 2 klik, 276 tayangan, CTR 0,7%, posisi rata-rata 13,1.

**Tiga kesalahan pembacaan data ditemukan dan dikoreksi:**

1. **Posisi 46,4 diklasifikasi Ronald sebagai Jarak Tembak — keliru, ini kotak Terlalu Jauh.** Rentang yang disepakati 6 Agustus adalah 5-18; posisi 46,4 (halaman 5) perlu melompat lebih dari 35 posisi, jauh di luar jangkauan pengungkit on-page. Pelajaran: jangan memaksakan kerangka klasifikasi supaya ada "pekerjaan" — kalau satu-satunya kueri yang tersedia tidak memenuhi syarat kotak manapun yang bisa dieksekusi, jawabannya tetap tidak ada tindakan.

2. **"Kueri hanya ada 1" — keliru, yang benar cuma 1 kueri BERNAMA yang tampil di tabel.** Tabel menampilkan 50 dari 276 tayangan (~82% kueri anonim/tersembunyi, sesuai pelajaran kueri anonim 5 Agustus). Temuan menarik: posisi rata-rata keseluruhan halaman (13,1) jauh lebih baik daripada satu-satunya baris terlihat (46,4) — mengindikasikan (bukan membuktikan, karena kotak ringkasan dan tabel dua alat ukur berbeda) mayoritas tayangan tersembunyi justru berperingkat jauh lebih baik daripada baris yang dipakai Ronald sebagai dasar keputusan awal.

3. **Diagnosis kosakata ("tips" sebagai kata jarak tembak) tidak relevan di posisi 46.** Konsep 6 Agustus berlaku: kalau posisi tetap di angka 40-an meski kosakata lengkap, itu urusan otoritas bukan kosakata. Tambahan: "tips" cuma sinonim dari "cara" yang sudah ada di judul, bukan celah makna baru seperti "Merchant" di kasus Artikel #5 — menaruhnya di H1/paragraf pembuka/H2 sekaligus juga akan mengulang masalah pengulangan heading yang baru dibereskan di Artikel #5.

**Keputusan akhir: TIDAK ADA TINDAKAN.** Sejalan dengan pola Artikel #2, #3, #4, #5 — tahan revisi judul/meta, CTR rendah di posisi ini gejala halaman, bukan gejala judul.

**Nilai:** pengambilan data lulus (filter benar, jendela benar, empat angka baseline dibaca lengkap, disiplin tidak menyentuh WordPress sebelum lapor). Pembacaan data belum — pola yang muncul: memaksakan kerangka supaya ada pekerjaan, dan mengambil kesimpulan dari sebagian data tanpa cek berapa besar bagian yang hilang.

---

## 3. Sesi Tambahan: Operator Filter Halaman (dipicu tugas verifikasi Ronald)

Saat diminta memverifikasi apakah dua tampilan performa memakai filter yang sama, Ronald menemukan sendiri (dengan koreksi) bahwa Performa GSC punya dua operator filter Halaman:
- **URL persis** — otomatis terpasang kalau mengklik baris URL di tab Halaman
- **URL berisi** — default kalau menambah filter manual lewat "Tambahkan Filter"

Cara membedakan tanpa membuka dropdown: chip filter di bilah alamat browser — `page=!...` untuk persis, `page=*...` untuk berisi.

**Kenapa ini penting untuk situs ini:** operator "berisi" berisiko mencampur artikel yang URL-nya saling menjadi awalan. Pillar (`/cara-promosi-warung-makan-online/`) adalah awalan huruf dari Artikel #4 (`/cara-promosi-warung-makan-lewat-whatsapp/`). Untuk kasus hari ini (URL lengkap sampai garis miring penutup) hasilnya identik, tapi ini bukan jaminan untuk kasus lain.

**Temuan sampingan:** dua percobaan Ronald mengubah dua variabel sekaligus (operator DAN waktu, karena jendela 3 bulan GSC bergulir), sehingga selisih kecil (276 vs 279 tayangan, posisi 13,1 vs 13,3) tidak murni disebabkan operator filter. Pelajaran metodologi: untuk membandingkan dua pengaturan, ubah satu variabel saja.

**Dua pelajaran ini dikunci ke `pelajaran-teknis-v1.md` (naik v1.1).**

---

## 4. Koreksi Housekeeping: Update Sempat Ditulis ke File yang Salah

Setelah update sesi ini selesai, Ronald menyadari ada satu file yang lupa disertakan ke project knowledge dan baru menguploadnya: `pelajaran-teknis-v1.md`. File itu ternyata mengubah tempat penulisan yang benar.

**Isi header file tersebut:** `pelajaran-teknis-v1.md` v1.0 dibuat 9 Agustus 2026, hasil pemisahan utuh dari `aturan-referensi-v1.md` Bagian 8 saat file aturan naik versi mayor jadi `aturan-referensi-v2.md` (v2.0). Nomor heading "8" sengaja dipertahankan supaya rujukan lama tetap bisa dilacak. Sifat file: HIDUP, dan menyatakan eksplisit bahwa **pelajaran teknis baru ditulis di sana, bukan di `aturan-referensi`**.

**Akibatnya, dua kekeliruan di update sesi ini:**
1. Dua pelajaran baru hari ini ditulis ke `aturan-referensi-v1.md` Bagian 8, padahal Bagian 8 sudah tidak tinggal di sana.
2. `aturan-referensi-v1.md` sempat dinaikkan ke v1.23, padahal berkas itu sudah digantikan `aturan-referensi-v2.md`. Menaikkan versinya berarti membuat cabang baru di atas berkas yang sudah mati.

**Perbaikan yang dijalankan:** kedua tambahan di `aturan-referensi-v1.md` (entri changelog v1.23 dan 2 baris tabel pelajaran cepat) dibatalkan penuh, file dikembalikan persis ke keadaan v1.22. Kedua pelajaran ditulis ulang ke `pelajaran-teknis-v1.md` sebagai entri lengkap plus 2 baris tabel, file naik ke v1.1. Rujukan di `status-aktif` v2.48 dan handoff ini ikut dikoreksi.

**Kedua gap ditutup di hari yang sama.** Ronald menemukan `aturan-referensi-v2.md` dan menguploadnya, lalu mengeluarkan `aturan-referensi-v1.md` dari project knowledge. Pemeriksaan isi v2 mengonfirmasi pemisahan 9 Agustus benar-benar dieksekusi, bukan sekadar rencana: Bagian 8 sudah tinggal satu baris penunjuk ke `pelajaran-teknis-v1.md`, nomor Bagian 9 sampai 12 sengaja dipertahankan supaya rujukan lama tidak putus, dan 5 penunjuk hidup ke Bagian 8 sudah diarahkan ulang.

**Penyelarasan rujukan silang dijalankan serentak di tiga file** supaya tidak ada yang menunjuk versi basi: `aturan-referensi` v2.0 jadi v2.1 (rujukan silang saja, isi aturan tidak berubah), `pelajaran-teknis` v1.1 jadi v1.2 (rujukan silang saja), `status-aktif` v2.48 jadi v2.49.

**Dua item baru masuk Pending Items:**
1. **Cek trio file di keempat project lain.** Aturan Bagian 10 `aturan-referensi` mewajibkan `status-aktif` + `aturan-referensi` + `pelajaran-teknis` ada bersama di kelima project. `pelajaran-teknis` baru lahir 9 Agustus dan Project Belajar SEO sendiri baru lengkap 11 Agustus, jadi keempat project lain patut dicurigai masih memegang `aturan-referensi-v1.md` yang sudah pensiun.
2. **Keputusan soal saling kunci nomor versi antar file.** Ketiga file saling mencantumkan nomor versi satu sama lain di baris "Pasangan file", sehingga satu perubahan kecil memaksa dua file lain ikut naik versi walau isinya tidak berubah — persis yang terjadi hari ini. Usulan: cukup `status-aktif` yang mencantumkan nomor versi dua file lain, sedangkan dua file statis saling menyebut nama pasangan tanpa nomor. Menunggu keputusan Ronald.

**Pelajaran proses:** protokol cek versi (baca versi terkini dari project knowledge sebelum menulis update) berjalan benar hari ini, tapi tidak bisa menangkap kasus ini karena filenya memang belum ada di project knowledge. Protokol itu melindungi dari versi yang basi, bukan dari file yang hilang. Penambal yang mungkin: saat sebuah file menyebut ada file pasangan, cek keberadaan file pasangan itu, jangan cuma cocokkan nomor versinya.

---

## 5. Status Fase Belajar

Tidak ada topik kurikulum resmi baru dibuka sesi ini — audit mandiri Artikel #6 adalah uji kemandirian (praktik), bukan topik baru. Progress resmi tetap 32/47 (68%), Fase 4 tetap 3/4. Fase 4 kini tidak lagi terhambat status index Pillar, tapi Content Refresh tetap menunggu baseline 3 bulan yang sah (8 November 2026).

**Antrean disepakati untuk sesi berikutnya:**
1. Broadcast WhatsApp (tuntaskan label ke semua kontak dulu — label sudah disiapkan dengan alur 6 tahap)
2. Fase 5 Off-Page SEO, topik pembuka Backlink Fundamentals

---

## 6. File yang Diperbarui Sesi Ini

- `status-aktif-v2.md` → **v2.49** (v2.48: (Pillar terindeks, item BLOCKED ditutup, verdict Artikel #6, dua reminder baru Bagian 4 dan 6, status Fase 4 Bagian 5 diperbarui, "Selesai terakhir" +2 entri. v2.49: penutupan dua gap file, penyelarasan rujukan silang, +2 pending item)
- `pelajaran-teknis-v1.md` → **v1.2** (v1.1: 2 pelajaran baru — jendela 3 bulan Performa GSC bergulir, operator filter URL persis vs URL berisi, tabel pelajaran cepat +2 baris. v1.2: penyelarasan rujukan silang)
- `aturan-referensi-v2.md` → **v2.1** (rujukan silang saja, isi aturan tidak berubah sama sekali)
- `aturan-referensi-v1.md` → **pensiun**, dikeluarkan Ronald dari project knowledge. File ini sempat keliru dinaikkan ke v1.23 di sesi ini, dibatalkan penuh sebelum pensiun — lihat Bagian 4
- `handoff-sesi-27-belajar-seo.md` (file ini)
- 2 event Google Calendar baru dibuat: "Cek GSC Artikel #1 Pillar: sudah ada tayangan atau belum" (8 Sep 2026, 10.00 WIB) dan "Evaluasi GSC penuh Artikel #1 Pillar (baseline 3 bulan pertama)" (8 Nov 2026, 09.00 WIB), keduanya popup+email 24 jam sebelumnya, dicek tidak ada duplikat.

**Belum diupload Ronald ke Project Belajar SEO & Digital Marketing** — `status-aktif-v2.md` dan `aturan-referensi-v1.md` perlu diupload manual menggantikan versi lama di project knowledge, plus file handoff ini ditambahkan baru.
