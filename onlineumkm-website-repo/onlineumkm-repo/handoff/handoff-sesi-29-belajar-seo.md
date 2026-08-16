# Handoff Sesi Belajar SEO — Sesi 29

**Tanggal:** 16 Agustus 2026 (reminder aslinya 15 Agustus, sesi mundur satu hari)
**Topik:** Uji efek penyelarasan kosakata Artikel #3, plus dua kesalahan pengambilan data GSC dan satu penjelasan tandingan yang gugur
**Status:** ✅ Selesai, verdict sinyal awal positif tapi jauh dari bukti
**Melanjutkan dari:** handoff-sesi-28-belajar-seo.md (13 Agt: uji efek revisi title/meta Artikel #2 lewat periode pembanding)

---

## 1. Checklist Event Ternyata Cacat Lagi, Dua Kali

Pelajaran proses sesi 28 langsung terpakai. Event 15 Agustus dibuat 25 Juli, dan dua bagiannya tidak layak dijalankan apa adanya.

**Cacat pertama, metriknya salah sasaran.** Event dinamai "Cek Ulang CTR — Artikel #3". Tapi yang diubah 25 Juli bukan judul untuk menaikkan klik, melainkan kosakata: SEO title, H1, meta, paragraf pembuka, fokus keyphrase Yoast, dan lima H2 semuanya digeser dari "Google Business Profile" ke "Google Maps". Baseline CTR-nya 0% dari 68 tayangan. Tidak ada CTR untuk diperbaiki.

**Cacat kedua, rentangnya satu sisi.** Poin 1 checklist minta "rentang sejak 25 Juli 2026". Sesi 28 sudah membuktikan jendela tunggal tidak bisa menjawab pertanyaan "apakah perubahan saya berhasil".

---

## 2. Konsep Baru: Ukur Lapisan yang Memang Kamu Sentuh

Perubahan kosakata bekerja di lapisan **tayangan dan daftar kueri**. Perubahan judul dan meta bekerja di lapisan **klik**. Kalau kamu ukur lapisan yang salah, kamu akan menyimpulkan "tidak berhasil" padahal alatnya memang tidak menunjuk ke sana.

Analogi yang dipakai: mengganti papan nama warung dari "Konsultan Rekayasa Kuliner" jadi "Nasi Padang". Yang berubah pertama bukan berapa persen orang yang menoleh lalu masuk, tapi **siapa yang lewat dan menoleh sama sekali**.

Urutan baca untuk kasus penyelarasan kosakata: tayangan, lalu daftar kueri, lalu posisi, CTR paling terakhir dan cuma kalau tayangan cukup.

---

## 3. Dua Kesalahan Pengambilan Data, Ditemukan dari Screenshot

### (a) Filter halaman bocor

Chip filter berbunyi "Halaman: +cara-daftar-goo..." dan bilah alamat `page=*cara-daftar-google-business-profile`. Tanda bintang berarti operator "URL berisi".

Akibatnya tab Halaman menampilkan **dua baris**:

| URL | Tayangan periode Sesudah | Tayangan periode Sebelum (kotor) |
|---|---|---|
| `/cara-daftar-google-business-profile/` | 12 | 69 |
| `/cara-daftar-google-business-profile-warung-makan/` | 0 | 8 |

Slug pendek adalah awalan slug panjang. Ini **kasus nyata pertama** dari risiko yang dikunci ke `pelajaran-teknis` tanggal 11 Agustus, yang waktu itu masih berupa kemungkinan teoretis pada pasangan Pillar dan Artikel #4.

**Cara deteksi mandiri:** setelah filter halaman terpasang, selalu lirik tab Halaman. Satu artikel harus menghasilkan satu baris. Lebih dari satu berarti filter bocor.

Dua tanda tambahan tanpa perlu membaca bilah alamat: chip filter yang menampilkan potongan slug tanpa nama domain berarti "berisi", sedangkan "URL persis" menampilkan alamat penuh berawalan `https://onlineumkm.id/`.

### (b) Dua periode tidak sama panjang

Periode Sebelum terketik `2026-06-08` alih-alih `2026-07-08`. Kolom bulan meleset satu, jadi periodenya 48 hari lawan 18 hari.

Membandingkan dua periode berbeda panjang sama saja menimbang dua karung beras lalu menyimpulkan yang berat lebih bagus, padahal yang satu memang lebih besar karungnya.

**Cara deteksi mandiri:** sumbu mendatar grafik perbandingan menghitung hari. Sumbu berhenti di 48 padahal niatnya 18 berarti ada salah ketik tanggal.

### Dampak gabungan

Angka kotor periode Sebelum: **69 tayangan.** Setelah dua kesalahan dibetulkan: **3 tayangan.** Selisih 66 seluruhnya berasal dari 30 hari ekstra bulan Juni dan dari halaman kedua yang ikut tertarik, bukan dari Artikel #3 pada periode yang dimaksud.

---

## 4. Hasil Bersih

Filter diverifikasi `page=!https%3A%2F%2Fonlineumkm.id%2Fcara-daftar-google-business-profile%2F`, tab Halaman menampilkan satu baris.

| Metrik | Sebelum (08/07–25/07) | Sesudah (26/07–12/08) |
|---|---|---|
| Klik | 0 | 1 |
| Tayangan | 3 | 12 |
| Posisi rata-rata | 6,3 | 9,1 |
| Kueri bernama | 0 | 0 |

**Yang menarik bukan angka 12, tapi angka 3.** Baseline lama yang tercatat 25 Juli berbunyi 68 tayangan, dan itu benar untuk rentang 25 Mei sampai 24 Juli. Tapi di 18 hari terakhir sebelum revisi, artikel ini praktis sudah mati garis lurus meski sudah hidup dua bulan. Bacaannya bukan "3 naik jadi 12", melainkan artikel yang sudah flat mulai bergerak lagi setelah kosakatanya diganti.

---

## 5. Tabel Kueri Kosong Total, dan Itu Bukan Nol Tayangan

Porsi terlihat **0%** di kedua periode: 0 dari 12, dan 0 dari 3.

Dua belas tayangan pasti dipicu dua belas orang yang mengetik sesuatu. Kuerinya ada. GSC cuma menolak menyebutkannya karena tidak ada satu pun yang cukup sering untuk layak ditampilkan.

Analogi: 12 orang masuk ke warung, tapi buku tamu kosong karena aturan rumahnya cuma mencatat nama kalau orang yang sama datang berkali-kali. Buku tamu kosong bukan berarti warung sepi.

Ini bentuk paling ekstrem dari pelajaran kueri anonim 5 Agustus. Di Artikel #2 porsinya timpang (14,6% lawan 1,4%), di sini nol sama sekali. **Kesimpulan yang sah dari tabel itu cuma satu: tabelnya tidak bisa dipakai.** Bukan "kosakata Google Maps gagal menarik kueri".

---

## 6. Penjelasan Tandingan Diuji dan Gugur

**Hipotesis:** kenaikan 3 ke 12 bukan hasil kosakata baru. Google menyatukan dua URL jadi satu dan memindahkan tayangan dari yang mati ke yang hidup. Kalau 8 tayangan slug lama jatuh di rentang 8-25 Juli, hitungannya jadi 11 lawan 12, praktis datar.

**Uji:** filter dipasang khusus ke slug lama, rentang tanggal tidak diubah. Hasilnya **nol di kedua periode**. Delapan tayangan itu jatuh di bulan Juni, di luar jendela. Hipotesis mati.

**Uji pendukung, Inspeksi URL slug lama:**
- Status: "URL tidak ada di Google", "Halaman tidak diindeks: Halaman dengan pengalihan"
- Crawl terakhir: 21 Juni 2026
- Halaman perujuk: Artikel #3 dan `post-sitemap.xml`
- Tidak ada di wp-admin
- Ctrl+F `post-sitemap.xml` per 16 Agustus: nol hasil

**Dugaan Claude sebelumnya bahwa ada dua halaman berebut materi sama terbukti KELIRU.** Redirect sudah bekerja dan Google berhenti menghitungnya sejak Juni.

---

## 7. Data Posisi Menyusul, dan Satu Kalimat Kesimpulan Ditarik

Ronald mengirim data posisi setelah verdict awal keluar. Kalimat "arahnya benar dan cocok dengan teori" terlalu bersih, ditarik dan diganti "sinyalnya campuran".

**Posisi rata-rata bukan peringkat artikel.** Itu rata-rata tertimbang tayangan dari himpunan kueri yang kebetulan menghasilkan tayangan di periode itu. Kalau himpunan kuerinya berubah, dua angka rata-rata tidak sedang mengukur hal yang sama.

Dua penjelasan sama-sama muat di angka 6,3 ke 9,1:

**(a) Jangkauan melebar ke bawah.** Artikel mulai nyangkut di kueri yang sebelumnya tidak pernah menghasilkan tayangan sama sekali, dan kueri baru itu hampir selalu berperingkat lebih rendah. Persis karena peringkatnya rendah, dulu tidak muncul. Tambahan: angka 6,3 itu rata-rata dari 3 tayangan saja, hampir tanpa bobot.

**(b) Google sedang menilai ulang.** Title, H1, meta, pembuka, dan lima H2 diubah dalam satu hari. Selama masa penilaian ulang posisi bisa goyah. Ini risiko yang sama persis dengan alasan menahan revisi Artikel #4 tanggal 29 Juli.

**Tidak bisa dipisahkan hari ini** karena alat pemisahnya adalah tabel Kueri, dan tabelnya kosong. Kalau nanti tabel berisi: bandingkan posisi per kueri, bukan rata-rata halaman. Kueri lama tetap di sekitar 6 sementara yang baru di 12 ke atas berarti penjelasan (a) menang.

---

## 8. Verdict

**Sinyal awal positif, jauh dari bukti. TIDAK ADA TINDAKAN di WordPress.**

Alasan: 6,3 dan 9,1 dua-duanya di dalam rentang jarak tembak 5-18, tidak ada pemicu tindakan, dan menyentuh artikel ini lagi cuma menambah variabel baru di atas perubahan yang belum selesai dinilai Google.

**Peringatan yang dicatat eksplisit:** jangan pernah menulis "CTR naik dari 0% jadi 8,3%". Satu dibagi dua belas memang 8,3% secara aritmetika, tapi klik satuan tidak punya persentase. Angka seperti itu di laporan klien sama saja menjual keberuntungan sebagai prestasi.

---

## 9. Pelajaran Utama Sesi Ini

Bukan soal Artikel #3, tapi soal urutan kerjanya.

Ronald dapat hasil yang menyenangkan, naik empat kali lipat, dan sebelum merayakannya dia menguji dulu penjelasan yang membosankan: mungkin ini cuma tayangan pindah kandang. Uji itu butuh lima menit dan hasilnya bisa saja membunuh temuannya. Uji itu tetap dijalankan.

**Aturan yang bisa dibawa ke pekerjaan klien:** tiap kali angka bergerak ke arah yang kamu harapkan, tanya "apa penjelasan lain yang juga muat di angka ini". Kalau tidak ketemu satu pun, kemungkinan besar kamu belum berpikir cukup keras.

---

## 10. Tindak Lanjut

**Dijadwalkan:**
- **29 September 2026, 09.00 WIB** — uji ulang jendela 62 hari. Sesudah 26 Juli sampai 25 September, Sebelum 25 Mei sampai 25 Juli. Reminder sudah dibuat di Google Calendar (dicek tidak ada duplikat), timeZone Asia/Jakarta, popup dan email 24 jam sebelumnya. Checklist lengkap ada di deskripsi event, termasuk tiga langkah baru: cek tab Halaman untuk mendeteksi filter bocor, verifikasi panjang periode lewat sumbu grafik, dan bandingkan posisi per kueri kalau tabel Kueri akhirnya berisi.

**Aktif tapi sengaja ditunda:**
- Poin 3 checklist 25 Juli: kalau impresi masih sangat rendah setelah revisi, masalahnya bukan lagi kosakata melainkan otoritas atau internal link. Dua belas tayangan dalam 18 hari masuk kategori itu. Diagnosis terpisah, sebagian besar jawabannya ada di Fase 5 Off-Page SEO. Jangan dicampur ke sesi 29 September.

**Ditutup sesi ini:**
- Status slug lama `/cara-daftar-google-business-profile-warung-makan/` sudah dipastikan sehat, tidak perlu tindakan apa pun.
- Baris Artikel #3 dihapus dari tabel Draft Revisi Title & Meta di `status-aktif` Bagian 2, karena drafnya memakai kosakata yang justru sengaja dibuang 25 Juli.

**Belum dikerjakan, menunggu persetujuan Ronald:**
- `pelajaran-teknis` naik ke v1.4 untuk mengunci pelajaran teknis baru sesi ini.

---

## 11. Cacat yang Diketahui pada Uji Ini

Periode Sebelum uji lanjutan (29 September) dimulai tepat di tanggal terbit 25 Mei, jadi minggu-minggu awalnya berisi artikel yang baru lahir dan belum sempat dinilai Google. Sama seperti cacat Artikel #2, tidak bisa dihilangkan, cuma bisa disebutkan sebagai batas kesimpulan.

---

*Handoff sesi 29. Progress kurikulum resmi tidak berubah: 32/47 (68%), Fase 4 tetap 3/4. Sesi ini maintenance dan latihan, bukan topik kurikulum baru.*
