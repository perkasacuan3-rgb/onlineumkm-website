# Handoff Sesi Belajar SEO — Sesi 25
**Tanggal:** 6 Agustus 2026
**Topik:** Praktik lanjutan konsep #3 dari antrean sesi 24 — cara menentukan rentang jarak tembak, dipraktikkan pakai data nyata Artikel #2 (Warung Sepi)
**Status:** ✅ Selesai
**Melanjutkan dari:** handoff-sesi-24-belajar-seo.md (antrean: konsep #3 rentang jarak tembak → konsep #5 kosakata mati vs kurang lengkap → 9 Agt audit mandiri Artikel #6 → Broadcast WhatsApp → Fase 5)

---

## 1. Konsep #3 Dibedah Tuntas: Cara Menentukan Rentang Jarak Tembak

Analogi baru: posisi = letak warung, halaman 1 = jalan besar, halaman 2 = gang di belakangnya. Jarak tembak = warung yang cukup dekat jalan besar sehingga geser sedikit sudah kelihatan.

**Dua ujung rentang, dan kenapa masing-masing:**
- **Ujung atas (≈5):** bukan garis "sudah bagus/jelek", tapi garis ganti alat. Di atas posisi ini orang sudah melihat halamannya — kalau tidak mampir, masalahnya judul/meta. Di bawahnya, ganti judul sia-sia karena yang lewat masih sedikit.
- **Ujung bawah (≈18-20):** titik di mana pengungkit on-page (kosakata, heading, section tambahan) berhenti realistis. Lompatan lebih dari itu butuh otoritas/backlink, kelas biaya berbeda.

**Cara menetapkan sendiri:** satu pertanyaan — berapa posisi yang harus dilompati kueri ini untuk sampai halaman 1, dan apakah alat on-page murah sanggup melompat sejauh itu?

**Verifikasi web:** tidak ada definisi baku industri untuk "jarak tembak" (striking distance). Rentang yang dikutip bervariasi 5-20, 11-20, sampai 11-30 tergantung tingkat kompetisi niche — sumber-sumber sepakat sendiri bahwa angkanya bukan aturan tetap. Skill `seo` internal kita mencatat 5-15 di decision tree-nya. Selisih beberapa posisi ini tidak penting — yang penting alasan di kedua ujung.

**Disepakati untuk onlineumkm.id:** rentang **5-18** — dipilih di ujung sempit kisaran umum karena situs masih baru dan otoritasnya terbatas (belum ada backlink); situs seperti ini jarang melompat 12+ posisi cuma dari tweak on-page.

---

## 2. Latihan Klasifikasi Artikel #2 — 2 Putaran (BUKAN evaluasi resmi)

**Penting:** ini latihan membaca data GSC untuk melatih kerangka klasifikasi. Bukan evaluasi resmi Artikel #2 — jadwal evaluasi resmi tetap **13 Agustus 2026** sesuai reminder Calendar yang sudah ada, tidak digeser. Tidak ada perubahan apapun dieksekusi ke WordPress/Yoast selama latihan ini.

### Putaran 1 (data belum disortir Posisi)
Dua kesalahan konsep besar ditemukan dan dikoreksi:

1. **Kueri "makan di tempat yang sepi" (posisi 7,4) sempat dimasukkan ke kotak "terlalu jauh".** Keliru — posisinya justru sangat dekat. Masalahnya bukan jarak, tapi maksud pencari yang beda (orang cari tempat makan tenang untuk diri sendiri, bukan pemilik warung yang dagangannya sepi). Ini melahirkan kebutuhan **kotak keempat: "Bukan Target"** — disaring PERTAMA berdasarkan maksud pencari, sebelum kueri dinilai posisinya sama sekali.
2. **CTR 0% di posisi 7-8 sempat disimpulkan "artikel kurang kedalaman".** Keliru dan berisiko. CTR ditentukan SEBELUM pembaca membuka artikel — oleh posisi, judul/meta, dan fitur SERP lain (AI Overview dll), bukan oleh isi artikel. Kedalaman konten baru relevan SETELAH klik terjadi. Turunannya: **revisi judul/meta menaikkan KLIK di posisi yang sama, bukan menaikkan POSISI itu sendiri** — salah paham ini berbahaya kalau terucap ke klien karena menjanjikan hasil yang tidak bisa diberikan pekerjaan itu.

### Putaran 2 (data sudah disortir Posisi dengan benar)
Tiga kesalahan lanjutan ditemukan dan dikoreksi:

1. **Kotak "urusan judul" sempat diisi kueri posisi 9-10**, dengan alasan "coba judul dulu, kalau gagal baru masuk jarak tembak". Keliru — kotak klasifikasi adalah diagnosis berdasarkan angka + maksud pencari, bukan urutan preferensi alat mana yang mau dicoba duluan. Batas atas kotak ini tetap 5, tidak bergeser.
2. **Dua kueri bermakna identik** ("makan di tempat sepi" vs "tempat makan sepi") sempat masuk ke dua kotak berbeda. Cara mencegah: baca dan kelompokkan seluruh daftar kueri berdasarkan kemiripan makna DULU, baru klasifikasikan per kotak — jangan klasifikasi baris demi baris dari atas ke bawah setelah sortir posisi, karena kueri kembar sering terpisah jauh letaknya di tabel.
3. **Satu angka salah kutip dari layar** (ditulis 17,9/0, layar sebenarnya 17,0/1) — pengingat selalu cek ulang angka sebelum masuk laporan/klien. **Kueri dengan tayangan sangat rendah** ("warung saya", 1 tayangan) sempat diberi kesimpulan padahal datanya belum cukup — masuk kategori "belum bisa diputuskan", bukan dipaksa ke salah satu dari 4 kotak.

---

## 3. Kerangka Klasifikasi Jarak Tembak — Versi Final 4 Kotak (hasil sesi ini)

| Kotak | Penentu | Tindakan |
|---|---|---|
| **Bukan Target** | maksud pencari beda dari topik artikel | abaikan — disaring PERTAMA, sebelum lihat posisi |
| **Urusan Judul** | posisi di atas ujung atas rentang (< 5) | revisi judul & meta |
| **Jarak Tembak** | posisi di dalam rentang (5-18) | pengungkit on-page termurah (kosakata, heading, section) |
| **Terlalu Jauh** | posisi di bawah ujung bawah rentang (> 18) | butuh otoritas/backlink, bukan tweak |

Kueri bertayangan sangat rendah (≈1-2 dalam 3 bulan): tidak diklasifikasi ke kotak manapun, masuk "belum bisa diputuskan" sampai data cukup.

**Urutan prioritas di dalam kotak Jarak Tembak:** tayangan dulu (besar hadiah), posisi jadi pemutus hanya kalau tayangan seri. Bukan sebaliknya.

---

## 4. Insight Tambahan: Posisi Beda per Kueri ≠ Mutu Artikel Beda

Ronald sempat menyimpulkan "kenapa warung sepi" (posisi 8,2) menandakan artikel "lebih baik" dibanding kueri "kenapa warung makan sepi" (posisi 17,9) — padahal keduanya kueri yang mendarat di HALAMAN YANG SAMA (Artikel #2), bukan dua artikel berbeda. Dikoreksi: Google menilai kecocokan satu halaman terhadap tiap kueri secara terpisah, bukan menilai "mutu artikel" secara umum. Kata "makan" mengubah lawan yang muncul di SERP, itu sebabnya posisinya beda jauh.

**Relevansi ke klien:** kalau klien bertanya kenapa satu artikel bisa "posisi 8 untuk satu kata kunci, posisi 18 untuk kata kunci lain", jawabannya kuerinya yang berbeda, bukan artikelnya yang berubah.

---

## 5. Hasil Klasifikasi Latihan Artikel #2 (data GSC 3 bulan, bukan tindakan resmi)

- **Bukan Target:** tempat makan ramai setelah kita datang (11,8), makan di tempat sepi (10,0), tempat makan sepi (10,5), makan di tempat yang sepi (7,4)
- **Jarak Tembak:** kenapa warung sepi pembeli (92 tayangan, 7,5), penyebab warung sepi pembeli (26, 7,8), kenapa warung sepi (9, 8,2), kenapa warung makan sepi (9, 17,9), warung sepi pembeli (1, 17,0), penyebab warung sepi (6, 9,3), warung mak oyah sekarang sepi (2, 8,5)
- **Terlalu Jauh:** warung sepi (30,0)
- **Belum Bisa Diputuskan:** warung saya (11,0, 1 tayangan)
- **Urusan Judul:** kosong — Artikel #2 belum punya kueri manapun di posisi di atas 5

**Prioritas tertinggi kalau kotak Jarak Tembak dieksekusi:** "kenapa warung sepi pembeli" (92 tayangan) — Ronald menjawab benar dengan alasan tayangan besar. Menariknya, kueri ini SUDAH tertangani lewat revisi judul/meta Juli 2026 yang menambahkan kata "pembeli" (lihat log `status-aktif` 23 Jul). Latihan ini cuma mengonfirmasi keputusan lama itu sudah tepat sasaran — bukan menemukan peluang baru untuk dieksekusi.

---

## 6. Status Fase Belajar

Tidak ada topik kurikulum resmi baru dibuka sesi ini — murni praktik lanjutan/maintenance dari antrean konsep #3 sesi 24. Progress resmi tetap 32/47 (68%), Fase 4 masih 3/4.

**Antrean disepakati untuk sesi berikutnya:**
1. Konsep #5 — beda kosakata mati vs kosakata kurang lengkap. Jembatan baru: pasangan kueri "kenapa warung sepi" (8,2) vs "kenapa warung makan sepi" (17,9) di data Artikel #2 sendiri adalah contoh hidup kosakata kurang lengkap — bisa dipakai sebagai bahan konkret, bukan contoh abstrak.
2. **9 Agustus 2026:** Ronald memimpin sendiri audit GSC Artikel #6 Foto Makanan dari awal sampai akhir (jadwal sudah ada di Calendar), Claude cuma mengoreksi — uji kemandirian atas seluruh rangkaian konsep jarak tembak dan kerangka 4 kotak.
3. Setelah itu: Broadcast WhatsApp (tuntaskan label ke semua kontak dulu), baru Fase 5 Off-Page SEO.

**Catatan:** evaluasi GSC resmi Artikel #2 tetap 13 Agustus 2026 sesuai reminder Calendar — latihan sesi ini tidak menggantikan atau mempercepat jadwal itu.

---

## 7. File yang Diperbarui Sesi Ini

- `status-aktif-v2.md` → v2.42 (entri log sesi 25 ditambahkan, "Selesai terakhir" +1 entri)
- `handoff-sesi-25-belajar-seo.md` (file ini)

**Belum diupload Ronald ke Project Belajar SEO & Digital Marketing** — perlu diupload manual. Sekalian cek apakah handoff sesi 23-24 juga masih tertunda upload.
