# Status Patch — NAP Consistency Fix (OnlineUMKM.id → Online UMKM)
**Tanggal:** 20 Juni 2026
**Sesi:** Lanjutan dari Topik 20 (Google Business Profile) — menyelaraskan nama brand di website dengan nama bisnis terdaftar di GBP

---

## Latar Belakang

Saat setup GBP di Topik 20 (lihat Master Handoff v6.0, Bagian 13), ditemukan quirk teknis: nama bisnis **"OnlineUMKM.id"** ditolak validator Google di deskripsi profil karena pola `kata + ".id"` terdeteksi sebagai URL. Solusinya saat itu: pakai **"Online UMKM"** tanpa domain di body text GBP.

Ini menciptakan inkonsistensi NAP (Name-Address-Phone) — nama bisnis di GBP berbeda dengan nama yang tampil di website. Sesi ini menyelaraskan kedua sumber tersebut.

---

## Perubahan — Homepage (`main-block.html`)

**7 lokasi** brand mention "OnlineUMKM.id" → "Online UMKM":

| # | Lokasi |
|---|---|
| 1 | Disclaimer bar atas |
| 2 | Alt text logo navbar (sempat terlewat di hitungan awal, ditemukan saat audit ulang) |
| 3 | Avatar role — section Tentang (homepage) |
| 4 | Bio paragraf — section Tentang (homepage) |
| 5 | Jujur box |
| 6 | Footer copyright |
| 7 | Footer disclaimer |

**Tidak diubah:** semua URL/domain literal (`src=`, `href=` ke `onlineumkm.id`) — tetap domain asli. Alt text hero-card image dan footer-brand image sudah pakai "Online UMKM" sejak sesi CWV 15 Juni, tidak disentuh ulang.

---

## Perubahan — Tentang Kami (`tentang.html`)

**10 lokasi** brand mention "OnlineUMKM.id" → "Online UMKM":

| # | Lokasi |
|---|---|
| 1 | Hero `<h2>` |
| 2 | Hero subtitle |
| 3 | Disclaimer box (kalimat pertama) |
| 4 | Tombol WA founder card (teks pesan WhatsApp) |
| 5 | Label "Kisah di Balik..." (sempat terlewat di hitungan awal, ditemukan saat verifikasi grep) |
| 6 | Paragraf cerita founder — "Saya membangun..." |
| 7 | Paragraf cerita founder — kalimat penutup |
| 8 | Tabel legalitas — field "Nama Usaha" |
| 9 | Legal disclaimer bawah |
| 10 | Tombol CTA bawah (teks pesan WhatsApp) |

**Keputusan eksplisit Ronald (20/06/2026):** kalimat *"Nama domain **onlineumkm.id** menggunakan istilah UMKM sebagai deskripsi target layanan kami..."* **TIDAK diubah** — itu referensi ke domain literal, bukan brand mention, jadi tetap huruf kecil tanpa spasi.

---

## Verifikasi Teknis

Sebelum paste ke WordPress dan sebelum commit GitHub, dilakukan verifikasi otomatis via `grep`:
- 0 sisa "OnlineUMKM.id" (brand form) di konten yang tampil ke pengunjung
- Jumlah "Online UMKM" baru cocok dengan jumlah lokasi yang ditargetkan
- Domain literal `onlineumkm.id/` di URL tetap utuh (11 occurrence di homepage, semua link blog/gambar)
- Tag `<div>` seimbang di kedua file (homepage: 116=116, Tentang Kami: 92=92) — memastikan tidak ada struktur HTML yang rusak akibat edit

---

## GitHub — Sinkronisasi

| File | Commit | Pesan |
|---|---|---|
| `onlineumkm-website-repo/onlineumkm-repo/homepage/main-block.html` | `ce8490c` | Fix NAP consistency: OnlineUMKM.id → Online UMKM, 7 lokasi (20/06/2026) |
| `onlineumkm-website-repo/onlineumkm-repo/pages/tentang.html` | `21c0ae6` | Fix NAP consistency: OnlineUMKM.id → Online UMKM, 10 lokasi (20/06/2026) |

Token PAT dibuat khusus sesi ini, sudah dihapus Ronald setelah dipakai sesuai SOP.

**Catatan:** Satu sisa "OnlineUMKM.id" tetap ada di file GitHub — tapi hanya di **komentar dokumentasi header** (menjelaskan riwayat perubahan), bukan di konten antara marker `wp:html` yang live ke pengunjung. Ini disengaja sebagai jejak audit.

---

## Pelajaran Baru untuk Sesi Mendatang

| Pelajaran | Detail |
|---|---|
| Hitung manual jumlah lokasi rawan meleset 1 | Di homepage hitungan awal 6 ternyata 7 (alt text logo terlewat); di Tentang Kami hitungan awal 9 ternyata 10 (label "Kisah di Balik..." terlewat). Solusi: setelah edit selesai, selalu `grep -c` untuk validasi jumlah penggantian sebelum present ke Ronald — jangan percaya hitungan manual saja. |
| Brand mention vs domain literal butuh keputusan eksplisit per kasus | "OnlineUMKM.id" sebagai nama brand (ganti) vs "onlineumkm.id" sebagai referensi domain literal dalam kalimat penjelasan (jangan ganti) — tidak bisa diasumsikan otomatis, perlu konfirmasi dari Ronald di tempat yang ambigu. |
| Verifikasi struktur HTML setelah edit besar | Cek jumlah tag `<div>` buka vs tutup via `grep -c` sebelum present file — cara cepat mendeteksi kalau ada tag yang ikut terhapus/rusak saat proses replace manual. |
| GitHub backup file punya struktur dokumentasi tersendiri | Header comment (FILE/FUNGSI/LOKASI/CARA UPDATE/RINGKASAN PERUBAHAN) + marker `wp:html` bukan bagian dari apa yang di-paste ke WordPress — hanya untuk dokumentasi GitHub. Saat update file ini, header diperbarui dengan ringkasan perubahan sesi, isi konten (antara marker) diganti penuh. |
| `tentang.html` di GitHub punya struktur ganda `wp:html` | Ada blok kosong `<!-- wp:html --><p>&nbsp;</p><!-- /wp:html -->` sebelum blok konten utama — pola ini dipertahankan apa adanya saat update, bukan dihapus, untuk menjaga konsistensi dengan format yang sudah ada di repo. |

---

## Hubungan dengan Fase 3 — Local SEO

Pekerjaan ini adalah pondasi untuk **Topik 21: NAP Consistency Audit** (lihat Master Handoff v6.0, Bagian 16) yang memang sudah dijadwalkan setelah Topik 20. Saat Topik 21 dikerjakan, audit bisa langsung fokus ke citation eksternal (Google Maps, direktori bisnis, dll) karena sumber utama (website + GBP) sudah selaras.

---

## Item Masih Terbuka (Tidak Berubah dari Sesi Sebelumnya)

| Item | Lokasi | Prioritas |
|---|---|---|
| Upload foto Ronald ke halaman Tentang Kami | Yoast oranye, 4 item merah | Sedang — butuh file foto dari Ronald |
| Artikel #7 — Template Caption Instagram | — | Sedang |
| Em dash di CTA homepage: *"🚀 Terbatas — Hanya 3–5 Slot Tersisa"* | `main-block.html`, `.cta-pre` | Rendah — kosmetik |
| Logo navbar tidak bisa diklik (tidak ada `href`/event listener) | `main-block.html`, `.nav-logo` | Rendah |
| Fungsi `oumkmFaq`, `oumkmWA`, `oumkmScroll` tidak terpakai (dead code) | `main-block.html`, script bawah | Sangat rendah |
| Fallback blog card URL — slug artikel #1 salah | `main-block.html` | Rendah — hanya muncul jika REST API gagal |
| Base64 images sisa (jika ada) | — | Rendah |

---

## Panduan Penempatan File Lintas Project

| Project | Relevansi file ini |
|---|---|
| **Website** | ✅ Wajib — single source of truth konfigurasi situs terbaru |
| **Konten & Copywriting** | ⚠️ Opsional — menyangkut brand name, bukan konten artikel |
| **Mentor** | ✅ Berguna — pelajaran teknis (verifikasi grep, brand vs domain literal) relevan untuk Topik 21 |

---

*Status Patch — 20 Juni 2026*
*Dibaca bersama: `mentor-master-handoff-onlineumkm-v6_0.md` (dokumen utama, tidak digantikan oleh patch ini)*
*Versi berikutnya: v6.1 — setelah Topik 21 (NAP Consistency Audit) selesai*
