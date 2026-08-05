# Handoff Sesi Belajar SEO: Sesi 22
**Tanggal:** 31 Juli 2026
**Topik:** Tindak lanjut index Pillar (GSC), orientasi Google Site Kit, klarifikasi pembagian project, praktik WhatsApp Business Marketing (Katalog)
**Status:** WhatsApp Business Marketing, Katalog selesai (3/3 paket live), Label & Broadcast belum dimulai
**Melanjutkan dari:** handoff-sesi-21-belajar-seo.md (26 Jul). Catatan: antara 26 sampai 30 Jul ada beberapa update lain (Artikel #4/#5/#13, kebijakan GitHub baru) yang sudah tercatat lengkap di `status-aktif-v2.md` v2.34, tidak diulang di sini, rujuk file itu untuk detail penuh.

---

## 1. Foto & Topik 22: Tetap Ditunda

Dikonfirmasi ulang di awal sesi, foto Ronald untuk halaman Tentang Kami masih belum tersedia. Topik 22 (Local Citation Building) juga masih terblokir dokumen/device, tidak ada perubahan. Status tetap "ditunda", bukan "gagal".

---

## 2. Tindak Lanjut Index Artikel #1 Pillar (GSC)

Ronald melapor hasil cek mandiri, dilakukan 27 Jul dan diulang 30 Jul, sebelum reminder resmi 10 Agustus. Status masih "Ditemukan, saat ini tidak diindeks", Crawl terakhir tetap T/A di kedua pengecekan. Live Test (Uji Langsung) menunjukkan halaman "dapat diindeks", tidak ada blocker teknis, jadi murni soal giliran crawl, bukan ada yang rusak.

Upaya yang sudah dilakukan Ronald sejak 27 Jul: cek sitemap, pastikan link homepage ke Pillar sehat, posting GBP yang ditautkan ke artikel Pillar, dan permintaan pengindeksan manual (2 kali, 27 Jul dan 30 Jul).

**Diverifikasi lewat Google Calendar:** reminder resmi "Cek ulang index Artikel #1 Pillar (GSC)" benar ada, terjadwal **10 Agustus 2026, 09.00 WIB**. Tidak ada tindakan tambahan yang perlu dikerjakan Ronald untuk Pillar sampai tanggal itu, termasuk disarankan berhenti klik "Minta Pengindeksan" berulang, karena GSC sendiri menyatakan pengiriman berulang tidak mengubah prioritas atau posisi antrean.

Kalau di 10 Agustus Crawl terakhir masih T/A total juga, sesuai catatan reminder kalender, ini jadi sinyal untuk naik level ke strategi backlink/citation eksternal, terhubung langsung dengan Topik 22 yang masih ditunda di atas.

---

## 3. Google Site Kit vs GA4/GSC Asli (edukasi singkat)

Ronald menunjukkan dashboard Site Kit (tab Content) di wp-admin, menampilkan data GA4 28 hari terakhir. Dijelaskan: Site Kit bukan sumber data terpisah, cuma jendela lain yang menarik data langsung dari API resmi GA4/GSC, jadi angkanya seharusnya identik dengan dashboard asli selama rentang tanggal dan filternya sama. Bedanya, Site Kit cuma tampilkan ringkasan. Untuk analisis mendalam (breakdown per kueri, per kota, dan sejenisnya, seperti yang sudah dipraktikkan untuk Artikel #2/#3) tetap wajib buka GA4/GSC asli.

---

## 4. Klarifikasi Pembagian Project

Dua pertanyaan routing dijawab pakai referensi resmi pembagian 5 project (`aturan-referensi` Bagian 6):

- **Pengisian pengeluaran pribadi dan `referensi-keuangan-bisnis.md`:** dipastikan masuk **Project Keuangan Freelance** (scope: budget, tracker, invoice, referensi keuangan), bukan project ini. Ronald melaporkan bingung memulai perhitungan ini, diarahkan untuk jadi sesi tersendiri di project itu, dengan tugas pemanasan: catat dulu satu angka, total pengeluaran wajib bulanan pribadi (di luar biaya bisnis). Biaya langganan Claude Pro (20 USD/bulan) sudah disebut Ronald, dicatat untuk dipakai nanti di kolom biaya operasional/tools, bukan di kolom pengeluaran hidup pribadi.
- **Belajar WhatsApp lebih dalam:** digali dulu maksudnya lewat pertanyaan pilihan, Ronald pilih "Fitur marketing (broadcast, label, katalog)". Ini dikonfirmasi tetap di **Project Belajar SEO & Digital Marketing** (project ini). Kalau lain waktu yang dimaksud soal komunikasi/closing ke calon klien, itu wilayah **Project Klien & Proposal** (scope: template WA).

---

## 5. WhatsApp Business Marketing, Katalog (praktik, selesai)

Materi dasar diambil dari isi live Artikel #4 sendiri (di-fetch langsung, bukan dari draft GitHub yang sudah dinyatakan tidak dipakai lagi) supaya Ronald belajar dari konten yang sudah dia setujui sendiri untuk klien, lalu dipraktikkan ke akun WhatsApp Business Online UMKM.

Konsep diajarkan: tiga fitur (Katalog, Label, Broadcast) saling berurutan. Katalog dulu (etalase), baru Label (segmentasi kontak), baru Broadcast (baru efektif kalau target sudah tersegmentasi). Sesi ini fokus ke Katalog saja.

**Hasil praktik:** ketiga paket jasa (UMKM Mulai Online, UMKM Tampil di Google, UMKM Tumbuh Digital) sudah dibuat dan live di katalog WhatsApp, dikonfirmasi Ronald sudah lolos review Meta. Diverifikasi tambahan: Ronald mengirim katalog ke nomor teman, dikonfirmasi bisa dibuka dan tampilannya terlihat normal dari sisi penerima, tes yang lebih valid dari instruksi awal (kirim ke nomor sendiri).

Detail spesifikasi gambar katalog yang dipakai sebagai acuan (diverifikasi lewat web search, bukan dari ingatan, karena rentan berubah): ukuran ideal 1080x1080 px rasio 1:1, minimum aman 500x500 px, maksimal file 5MB, format JPG atau PNG (PNG disarankan untuk Ronald karena kontennya berupa mockup atau teks, bukan foto produk asli).

**Catatan penting:** topik WhatsApp Business Marketing ini tidak punya baris resmi di `progresstrackerbelajar.xlsx` (dicek di roadmap bagian "Digital Marketing, Pendamping", tidak tercantum eksplisit). Statusnya sama seperti kasus "Long-form vs Short-form Content" di Sesi 19: praktik tambahan yang bermanfaat, tapi bukan bagian resmi 47 topik, jangan diasumsikan perlu update tracker.

---

## Pelajaran Kunci Sesi Ini

1. **Selalu verifikasi klaim "kamu sudah buat reminder ini" lewat tool, jangan cuma percaya dari ingatan.** Ronald menyebut ada reminder Google Calendar untuk 10 Agustus, dicek langsung via `Google Calendar:list_events`, terkonfirmasi benar ada. Pola ini perlu terus dipakai untuk klaim serupa ke depannya.
2. **Spesifikasi teknis platform pihak ketiga (ukuran gambar, limit file) juga rentan berubah, bukan cuma navigasi UI-nya.** Sebelum jawab pertanyaan ukuran foto katalog WhatsApp, dilakukan web search dulu, bukan dari ingatan pelatihan, karena beberapa sumber tahun 2026 menunjukkan variasi angka yang cukup luas.
3. **Kesalahan proses:** nama Ronald sempat tidak muncul di awal 2 sampai 3 balasan berturut-turut, melanggar aturan wajib. Sudah dikoreksi dan ditegaskan ulang di tengah sesi, perlu tetap dijaga konsisten di sesi-sesi berikutnya.
4. **Materi WhatsApp Business untuk praktik pribadi Ronald sengaja diambil dari artikel live miliknya sendiri (Artikel #4), bukan ditulis ulang dari nol,** mempercepat proses karena kontennya sudah pernah diverifikasi dan disetujui sebelumnya untuk konteks klien.

---

## Sesi Berikutnya

**Lanjutan langsung:** WhatsApp Business Marketing, **Label (segmentasi kontak)** dan **Broadcast**, melengkapi Katalog yang sudah selesai sesi ini. Rencana pembagian kontak mengikuti 4 kategori dari Artikel #4 (pelanggan baru, aktif, lama tidak repeat, setia), disesuaikan ke konteks leads/klien jasa Online UMKM.

**Item lama yang masih menunggu (tidak berubah):** foto Ronald, Topik 22 (Local Citation Building).

**Dirutekan ke project lain (tidak perlu ditindaklanjuti di sini):** pengisian `referensi-keuangan-bisnis.md`, arahkan ke Project Keuangan Freelance.

---

*Handoff Sesi 22, 31 Juli 2026.*
