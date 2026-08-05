# Handoff Sesi Belajar SEO — Sesi 16
**Tanggal:** 21 Juni 2026
**Topik:** Topik 22 — Local Citation Building Indonesia (Fase 3, Local SEO) — **BELUM SELESAI, lanjut sesi berikutnya**
**Durasi estimasi:** ~2,5 jam
**Status:** 🔄 Sedang Berjalan
**Melanjutkan dari:** handoff-sesi-15-belajar-seo.md

---

## Konteks Awal Sesi

Lanjutan langsung dari Topik 21 (NAP Consistency) yang selesai sesi sebelumnya. NAP standar yang dipakai di semua pendaftaran sesi ini: nama **"Online UMKM"**, telepon **0877-9180-8667**, website **https://onlineumkm.id/**.

---

## 1. Bing Places for Business

- Berhasil disinkron dari GBP. Status tetap **🟡 Pending Publish** sepanjang sesi.
- **Bug ditemukan & diperbaiki:** Website tersinkron sebagai `http://` bukan `https://` → diperbaiki di GBP, re-sync, terkonfirmasi sudah `https://onlineumkm.id/` di Bing.
- **Kategori:** awalnya salah sync jadi "Business advertising". Percobaan pertama ganti ke "Website Designer"/"Marketing Agency" di GBP gagal — penyebabnya Ronald mengetik manual lalu langsung Simpan, padahal Google mewajibkan pilih dari dropdown saran saat mengetik. Setelah diarahkan ulang, berhasil — Bing sekarang menampilkan kategori **"Web designer"**.
- **Temuan kritis — limitasi platform permanen:** Google SAB tidak pernah mengirim alamat fisik sama sekali (truly hidden, bukan sekadar disembunyikan dari tampilan). Bing sebaliknya **mewajibkan alamat fisik untuk verifikasi** (baru bisa disembunyikan dari hasil pencarian setelah tersimpan) — tapi field Address/Phone/City/State/Zip di Bing **terkunci total** selama status listing "Synced with Google" (dikonfirmasi: kursor jadi ikon terlarang saat hover, dan menu "..." cuma punya opsi "Manage users" / "Delete listing from this account", tidak ada opsi "stop sync"/"manage manually").
- **Kesimpulan:** Listing Bing kemungkinan besar akan **stuck di "Pending Publish" permanen** — field Address wajib tapi tidak pernah bisa terisi selama tersinkron, dan Google tidak pernah mengirim data itu. Ini limitasi struktural platform, bukan kesalahan eksekusi.
- **Keputusan:** Tidak hapus & buat ulang listing manual (biaya: verifikasi ulang 7-14 hari, kehilangan auto-sync, tetap butuh alamat asli juga). Dibiarkan apa adanya, prioritas rendah.

---

## 2. Facebook Business Page

Tetap **ditunda** — kendala jaringan, belum dicoba sama sekali sepanjang sesi ini.

---

## 3. Diskusi Strategis: Rencana Reveal Alamat (~2 Tahun Mendatang)

Ronald bertanya soal risiko & persiapan kalau suatu saat ingin menampilkan alamat fisik untuk kredibilitas. Poin kunci yang dibahas:

**Risiko saat perubahan terjadi:**
- GBP minta re-verifikasi (postcard/telepon/video call), listing bisa suspend sementara 3-7 hari+
- Ranking lokal berfluktuasi sementara
- **Risiko terbesar:** semua citation yang terdaftar tanpa alamat selama periode SAB harus diupdate serentak — makin banyak citation terdaftar sekarang, makin banyak yang harus diupdate nanti
- Kalau alamat rumah yang dipakai: terindeks permanen, sulit ditarik kembali

**Persiapan yang direkomendasikan:**
- Catat semua platform citation di satu tempat (→ lahir ide Citation Tracker)
- Tentukan tipe alamat (rumah vs virtual office) mendekati waktunya
- Jaga akses login semua platform tetap aktif
- Eksekusi update SEMUA platform serentak dalam 1 hari kerja: website (footer+schema) → GBP → Bing → direktori lain
- Hindari periode pitch klien aktif

Detail lengkap disimpan di sheet "Rencana Alamat Masa Depan" pada file Citation Tracker.

---

## 4. Citation Tracker Dibuat & Diupdate

File `citation-tracker-onlineumkm.xlsx` dibuat di awal sesi (2 sheet: Citation Tracker + Rencana Alamat Masa Depan), lalu **diupdate ulang di akhir sesi** dengan seluruh temuan poin 1, 5, 6, 7, 8 di bawah. Lihat file terlampir untuk versi final.

---

## 5. Infobisnis.id — Tidak Relevan

Diperiksa langsung (fetch konten situs): ternyata **portal berita/media bisnis** (artikel-artikel seperti "Modal Awal Membuka Usaha Laundry Kiloan"), bukan direktori listing. Tidak ada fitur tambah bisnis. **Dicoret dari daftar target**, jangan dicoba lagi di sesi mendatang.

---

## 6. Yellow Pages — Berhasil Daftar, Tapi Salah Platform

Ronald mendaftar di **yellowpages.net** (Yellow Pages Network, dioperasikan YPMEDIA LLC) — **bukan** yellowpages.co.id (Yellow Pages Indonesia yang berafiliasi Telkom/Infomedia, yang dimaksud di rekomendasi awal). Dua brand "Yellow Pages" ini tidak berafiliasi satu sama lain.

**Proses pendaftaran:**
- Company Name diperbaiki dari "Online umkm" → "Online UMKM"
- Activity: Services, Single-location business, Year of establishment: **2026**
- Alamat diisi (Street: Setia Jadi No. 2A, City: Medan, Province: Sumatera Utara) dengan toggle **"Menampilkan alamat perusahaan di halaman bisnis" dimatikan (OFF)** sebelum submit
- Kontak: website https://onlineumkm.id/, telepon +62 877-9180-8667, role: Owner

**Hasil:** Listing berhasil dibuat, status **"Pending review", belum publik**. Pencarian di yellowpages.id (sister/front-end domain dari jaringan yang sama) belum menemukan listing — wajar, karena memang belum melewati moderasi.

**Temuan penting:** Model bisnis platform ini freemium agresif — listing gratis pada dasarnya tidak menampilkan apapun ke publik (bahkan alamat sepertinya ikut tersembunyi di tier gratis); phone & website baru publik 24/7 setelah bayar paket mulai **USD 9.90/tahun**. **Keputusan: tidak bayar** — tidak sepadan di tahap pra-klien-pertama ini. Listing dibiarkan pending/gratis, prioritas rendah.

---

## 7. Multibisnisindo.com — Diperiksa Mendalam, TIDAK Direkomendasikan

Atas permintaan Ronald untuk verifikasi lebih teliti, dilakukan fetch langsung ke halaman registrasi. Ditemukan multiple red flags:

1. Tombol CTA utama "Daftar Sekarang" mengarah ke URL **localhost** yang rusak (`http://localhost/mda/pages/registrasi-mitra/`)
2. Semua link "Legal & Trust" (Kebijakan Privasi, Syarat & Ketentuan, Terdaftar Resmi, Garansi Layanan) cuma mengarah balik ke homepage — badge kepercayaan palsu/kosong
3. Counter pengunjung ("Visitors Today: 1407" dll) terlihat dibuat-buat
4. Ini bukan direktori netral — judul halamannya "Registrasi Mitra" untuk jadi mitra dari **"Multibisnisindo Digital Agency"**, sebuah agency jasa website & digital marketing — bisnis yang sama persis dengan onlineumkm.id
5. Domain sangat baru (~1 bulan, berdasarkan tanggal upload aset situs)

**Keputusan: skip total, tidak didaftarkan.**

---

## 8. Dua Direktori Pengganti — Terverifikasi Mendalam

Setelah 2 dari 3 rekomendasi sebelumnya gagal verifikasi, dilakukan riset lebih ketat. Dua kandidat lolos verifikasi:

### LinkedIn Company Page
Sudah ada di rencana awal (sempat tertunda). Otoritas domain tertinggi, gratis, tanpa red flag. **Prioritas berikutnya** — diperkirakan butuh pembahasan cukup panjang di sesi terpisah (setup kategori, deskripsi, dll), makanya sesi ini ditutup dulu sebelum mulai.

### Indonetwork.co.id
Terverifikasi: dioperasikan **PT. Indonetwork Adi Perkasa**, berdiri sejak **2001** (24+ tahun), kantor fisik nyata di Jakarta (Warung Jati Barat No. 36, Ragunan) dan Surabaya, 1+ juta member, media sosial aktif & konsisten di LinkedIn/Instagram/Twitter/Facebook/YouTube (termasuk postingan lowongan kerja — tanda perusahaan aktif beroperasi). Ada tier **Free Member** terkonfirmasi — cukup pakai itu, **jangan upgrade** ke Priority Membership (Rp 1,7-2,1 juta/tahun, tidak perlu di tahap ini).

Catatan: fokus utama Indonetwork adalah perdagangan B2B, bukan jasa digital secara spesifik — tapi mereka sendiri pakai hashtag #buatwebsite #seo #sem di media sosial mereka, jadi kategori jasa digital tetap relevan di sana.

---

## Pelajaran Kunci Sesi Ini

1. **Verifikasi mendalam wajib sebelum rekomendasi direktori** — nama domain yang terdengar meyakinkan (Infobisnis.id, Multibisnisindo.com) bisa ternyata bukan direktori sama sekali, atau punya red flag serius. Cek fetch konten asli, link legal/footer berfungsi atau tidak, dan tombol CTA mengarah ke mana.
2. **Beda platform = beda kebijakan alamat SAB.** Google: tidak pernah minta alamat sama sekali. Bing: wajib alamat untuk verifikasi + toggle sembunyikan, TAPI field terkunci total kalau listing dalam mode synced — toggle jadi tidak relevan. Yellow Pages Network: wajib alamat + toggle sembunyikan yang benar-benar berfungsi karena input manual (bukan sync).
3. **Brand "Yellow Pages" dipakai banyak entitas tak berafiliasi** — yellowpages.co.id (Telkom/Infomedia) ≠ yellowpages.net (YPMEDIA LLC global). Nama domain mirip bukan jaminan perusahaan yang sama.
4. **Ciri direktori abal-abal:** link kebijakan/legal yang semua mengarah ke homepage, tombol CTA rusak/mengarah ke localhost, counter pengunjung mencurigakan, model bisnis "jadi mitra" alih-alih listing netral.
5. **Ciri domain authority yang bisa diverifikasi nyata:** umur domain lama (idealnya 5+ tahun), alamat kantor fisik yang bisa dicek di peta, kehadiran media sosial aktif & konsisten, halaman LinkedIn perusahaan resmi.

---

## Progress Tracker

**Topik 22 belum ditandai selesai** — masih 🔄 Sedang Berjalan di `progresstrackerbelajar.xlsx`. Progres keseluruhan tetap **25/47 topik (53%)**, tidak berubah dari sesi 15.

---

## Sesi Berikutnya

**Lanjutan Topik 22:**
1. Setup **LinkedIn Company Page** (diperkirakan pembahasan panjang — kategori, deskripsi, dll)
2. Daftar gratis di **Indonetwork.co.id**
3. Setelah keduanya selesai (atau Bing/Facebook ada perkembangan), Topik 22 baru bisa ditandai ✅ Selesai dan Master Handoff naik ke **v6.2**

---

*Handoff Sesi 16 — 21 Juni 2026*
