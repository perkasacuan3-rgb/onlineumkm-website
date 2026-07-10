# Status Patch — Keputusan Repositioning Layanan & Homepage
**Tanggal:** 4 Juli 2026
**Sesi:** Diskusi strategis (Project Klien & Proposal / Riset Pasar)
**Status keseluruhan:** ⚠️ **KEPUTUSAN BELUM DIEKSEKUSI** — dokumen ini adalah hasil diskusi strategi, bukan pekerjaan yang sudah selesai
**Dibaca bersama:** riset-pasar-konsolidasi-onlineumkm.md, mentor-master-handoff-onlineumkm-v6_5.md, content-calendar-onlineumkm-v1_7.md

---

## Latar Belakang

Riset pasar konsolidasi (Juli 2026) merekomendasikan pergeseran dari menjual jasa satuan (website, SEO, toko online, company profile — dijual terpisah) ke menjual 3 paket bundling dengan harga terbuka. Ronald ingin mengubah tampilan homepage dan penawaran jasa sesuai arahan riset ini.

---

## Keputusan yang Diambil

Bergeser dari model **jual jasa satuan** ke model **3 paket bundling**:

| Paket | Harga (draft) | Isi |
|---|---|---|
| Starter Digital | Rp 1,5 – 3,5 juta | Website landing page/company profile sederhana, domain, hosting, email dasar, setup WhatsApp Business |
| Local Presence *(featured)* | Rp 3,5 – 7,5 juta | Website 3–5 halaman, optimasi SEO lokal, setup Google Business Profile, template follow-up WA |
| Growth Setup | Rp 7,5 – 15 juta | Website + SEO lengkap, setup tools digital dasar, 1 sesi pendampingan langsung |

**Alasan utama (dari riset):** harga tidak transparan adalah alasan #1 UMKM batal order. Paket dengan harga terbuka langsung menjawab keberatan terbesar calon klien.

---

## Alasan Strategis dari Riset

- UMKM lebih suka jasa yang dikemas sebagai *productized service* — scope, harga, waktu pengerjaan yang fixed
- "Mulai dari Rp X" lebih baik dari rentang harga — satu angka lebih mudah diingat dan dikutip ulang saat direkomendasikan
- Spesialis > generalis — bundling bukan berarti melebarkan target ke "semua UMKM", tapi memperjelas hasil yang didapat

---

## Risiko yang Sudah Diidentifikasi (5 Poin)

### 1. Diskoneksi konten blog vs positioning homepage
Sembilan artikel yang sudah terbit semuanya membangun topical authority di niche **warung makan lokal**. Pillar page: "Cara Promosi Warung Makan Online." Jika homepage bergeser ke bahasa "semua UMKM" tanpa jembatan, terjadi diskoneksi antara pengunjung yang masuk lewat artikel (warung makan) dan pesan homepage (generik).

**Rekomendasi:** Jangan buang niche warung makan — itu kekuatan, sesuai prinsip riset "spesialis > generalis." Warung makan tetap jadi klien utama yang disebut, sambil membuka pintu untuk UMKM lain.

### 2. Keyword density Yoast bisa terganggu
Focus keyword "jasa pembuatan website UMKM" saat ini muncul 8 kali tersebar di homepage (hero, subtitle, H3, kartu, CTA) — hasil kerja panjang sampai Yoast hijau. Mengubah nama kartu jasa jadi nama paket berisiko menurunkan kepadatan keyword.

**Rekomendasi:** Pertahankan keyword di deskripsi paket dan H3 yang sudah ada — jangan hilang, cukup pindah posisi. Jangan reset ke keyword baru kecuali siap membangun ulang dari nol.

### 3. Harga terbuka = komitmen publik
Begitu harga tayang di homepage, itu jadi anchor. Klien yang datang lewat WA akan menagih konsistensi harga.

**Rekomendasi:** Gunakan format "Mulai dari Rp X juta", bukan rentang "Rp X–Y juta". Rentang membuat orang expect harga terendah; "mulai dari" memberi ruang menyesuaikan scope per klien tanpa terasa tidak konsisten.

### 4. Bio "Tentang Kami" masih menyebut "slot gratis"
Bio saat ini bilang masih membuka slot gratis untuk klien perdana. Ini kontradiktif jika homepage sudah pasang harga paket berbayar.

**Rekomendasi:** Update bio setelah homepage baru jadi — hapus framing "slot gratis", ganti dengan penekanan "saya kerjakan sendiri setiap proyek, bukan diserahkan ke admin/freelancer lain."

### 5. Footer & navigasi jadi tidak sinkron
Footer punya 4 link jasa ("Pembuatan Website", "Jasa SEO Lokal", "Toko Online WooCommerce", "Company Profile") yang semua scroll ke `#layanan`. Setelah jadi 3 paket, label ini menyesatkan.

**Rekomendasi:** Ganti label footer jadi nama 3 paket saat eksekusi teknis. Jangan lupa masuk scope — mudah terlewat karena bukan bagian utama section Layanan.

---

## Dampak ke Content Calendar

| Item | Keputusan |
|---|---|
| 9 artikel yang sudah terbit | **Tidak perlu diubah.** Biarkan terus bekerja, tetap fokus warung makan |
| Artikel #10 (rencana: Promosi Online Warung Makan Surabaya) | **Lanjutkan sesuai rencana** — tidak terdampak keputusan ini |
| Artikel #11 dan seterusnya | **Perlu direview ulang** setelah homepage baru jadi. Pertimbangkan menyelipkan 1–2 artikel bertema lebih lebar dari sekadar warung makan (contoh: "Cara UMKM Ditemukan di Google Maps", "Kenapa UMKM Butuh Website di 2026") supaya blog tidak 100% warung makan saja |
| Content calendar v1.7 | Belum diubah — review ulang dijadwalkan setelah homepage baru live |

---

## Langkah Awal yang Direkomendasikan (Sebelum Sentuh Kode)

1. **Finalisasi copy 3 paket** — nama, deskripsi singkat, harga "mulai dari", teks CTA. Kerjakan di dokumen teks biasa dulu, bukan langsung di website
2. **Petakan keyword yang harus dipertahankan** — daftar keyword yang ada di section Layanan sekarang, pastikan semua tetap muncul di versi baru meski posisinya bergeser
3. **Putuskan sikap tentang niche** — apakah homepage bicara ke "UMKM umum" atau tetap memberi sinyal "terutama untuk usaha kuliner/jasa lokal"? Ini menentukan tone copy dan contoh di deskripsi paket
4. **Baru eksekusi teknis** — dilakukan di Project Web (Project 1) dengan brief yang jelas, bukan improvisasi langsung di code editor

---

## Keputusan yang Masih Menggantung

- **Belum diputuskan:** apakah homepage tetap menyebut niche warung makan secara eksplisit, atau melebar ke "semua UMKM" dengan warung makan sebagai contoh saja
- **Belum diputuskan:** format harga final — "mulai dari Rp X" per paket, atau tetap tampilkan rentang
- **Belum dikerjakan:** update bio Tentang Kami (menyusul setelah homepage)
- **Belum dikerjakan:** update label footer

---

## Preferensi Komunikasi Baru (Berlaku di Project Ini)

Mulai sesi ini, setiap balasan Claude di project ini **wajib dimulai dengan menyebut nama "Ronald"** di kalimat pertama. Sudah disimpan ke memory project ini (Project Klien & Proposal).

**Catatan penting:** Memory Claude bersifat **per-Project** — tidak otomatis berlaku di Project lain (Website, Konten & Copywriting, Keuangan Freelance, Belajar SEO). Jika aturan ini ingin berlaku di seluruh 5 Project, perlu:
1. Ditambahkan manual ke memory masing-masing Project (lewat instruksi serupa di setiap Project), **atau**
2. Dimasukkan ke Master Handoff Document dan di-upload ulang ke semua Project — tapi ini hanya membuat Claude *tahu* aturannya lewat pencarian dokumen, bukan otomatis menjalankannya seperti instruksi memory langsung

Rekomendasi: ulangi instruksi ini secara eksplisit di 4 Project lain jika memang ingin konsisten di semua tempat.

---

## Cara Melanjutkan di Sesi/Project Baru

Saat membuka sesi baru (terutama di Project Web untuk eksekusi teknis), sebutkan:

> "Lanjutkan dari status-patch 4 Juli 2026 — repositioning layanan ke 3 paket bundling. Saya sudah finalisasi copy paket, sekarang mau eksekusi teknis di homepage."

Ini memastikan konteks keputusan strategis tidak hilang meskipun sistem memory belum sempat memperbarui otomatis.

---

*Dokumen ini adalah hasil diskusi strategis — upload ke Google Drive dan re-upload ke Project yang relevan (terutama Project Web) sebelum melanjutkan eksekusi.*
