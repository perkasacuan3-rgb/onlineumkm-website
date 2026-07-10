# Goal
Membangun sistem bisnis jasa website & SEO (onlineumkm.id) yang berjalan dengan **10% usaha Ronald, 90% dikerjakan Claude** — mencakup operasional website, konten SEO, komunikasi klien, dan pengerjaan proyek klien.

---

## Current State

- Website **onlineumkm.id** live di WordPress + Elementor + Hostinger
- 3 artikel blog published — **semua Yoast hijau** ✅
- Google Search Console: sitemap bersih, hanya `/sitemap_index.xml` aktif (15 halaman terindeks)
- Halaman `/tentang/` live — berisi identitas bisnis lengkap & disclaimer hukum ✅
- Disclaimer bar terpasang di homepage + footer ✅
- Semua tombol homepage berfungsi — WhatsApp, scroll, FAQ, nav, mobile hamburger ✅
- Belum ada klien aktif — masih fase membangun fondasi
- 3 sistem utama bisnis **belum dibangun**: sistem dapat klien, sistem konten SEO, sistem kerja per klien

---

## Files in Flight

| File / Halaman | ID / URL | Status |
|---|---|---|
| Homepage | post ID 114 | Live — pending: alt text gambar & internal link blog |
| Halaman Tentang Kami | `/tentang/` | Live — berisi disclaimer hukum lengkap ✅ |
| Artikel 1 — Promosi Online Warung Makan Medan | — | Published — Yoast **semua hijau** ✅ |
| Artikel 2 — Kenapa Warung Makan Sepi Padahal Enak | post ID 129 | Published — Yoast **semua hijau** ✅ |
| Artikel 3 — Cara Daftar Google Business Profile | post ID 159 | Published — Yoast **semua hijau** ✅ |

---

## Changed (Sesi Ini)

| Item | Perubahan | Status |
|---|---|---|
| Disclaimer bar homepage | Bar tipis di atas nav + footer disclaimer — pernyataan bisnis swasta, bukan afiliasi pemerintah | ✅ Selesai |
| Halaman `/tentang/` | Dibuat baru — identitas bisnis lengkap, 4 lapis disclaimer hukum, kisah Ronald, nilai bisnis, info operasional | ✅ Selesai |
| Nav "Tentang" → `/tentang/` | Sebelumnya scroll ke section homepage, sekarang buka halaman `/tentang/` | ✅ Selesai |
| Footer "Tentang Kami" → `/tentang/` | Sama — sekarang mengarah ke halaman terpisah | ✅ Selesai |
| Disclaimer bar — link ke `/tentang/` | Tambah "Pelajari lebih lanjut →" di bar disclaimer | ✅ Selesai |
| Fix tombol homepage | Semua tombol (WhatsApp, scroll, FAQ accordion) diperbaiki via script terpisah setelah onclick handler terhapus WordPress | ✅ Selesai |
| Mobile hamburger — spans hilang | Tambah 3 `<span>` ke dalam `<button>` hamburger agar ikon 3 garis terlihat | ✅ Selesai |
| Mobile hamburger — double handler | Hapus handler hamburger dari fix script karena sudah ada di script utama — sebelumnya saling menggagalkan | ✅ Selesai |

---

## Failed Attempts

| Percobaan | Kenapa Gagal |
|---|---|
| **Claude in Chrome untuk optimasi artikel** | Tidak punya akses ke skills Project — gaya tulisan bergeser jadi generik AI. Hindari untuk penulisan konten |
| **"Berikutnya" sebagai kata transisi** | Tidak dikenali Yoast dalam daftar kata transisi Bahasa Indonesia |
| **Targeted 1 kata fix untuk kata transisi** | Persentase terlalu dekat threshold — butuh 3-4 kata sekaligus agar perubahan terdeteksi Yoast |
| **HTML widget untuk internal link blog (homepage)** | Widget masuk ke struktur section FAQ, merusak accordion di live site — di-revert via Elementor History |
| **Purge All LiteSpeed Cache** | Website tidak bisa diakses pengunjung non-login — cache server Hostinger perlu dibersihkan terpisah via hPanel |
| **Plugin Ally untuk aksesibilitas** | Tidak kompatibel dengan Elementor — mengubah simbol ✓ menjadi &#10003; di halaman live |
| **Edit disclaimer via find & replace bertahap** | Onclick handler di semua tombol terhapus WordPress saat save — semua tombol berhenti berfungsi |
| **navMap di script utama** | Script utama tidak punya navMap — ada di fix script terpisah. User tidak bisa menemukan karena beda blok |
| **Double hamburger handler** | Fix script + script utama keduanya pasang listener di hamburger — saling cancel, dropdown tidak muncul |

---

## Pending (Belum Diselesaikan)

| Item | Catatan |
|---|---|
| Yoast Artikel 1 (Promosi Online Warung Makan Medan) | ✅ Selesai — keterbacaan dan SEO semua hijau |
| Alt text semua gambar homepage | Belum dikerjakan — berpengaruh ke skor SEO Yoast homepage |
| Internal link "Baca juga" di homepage | Butuh cara aman selain HTML widget — jangan dalam section yang sama dengan FAQ |
| Portofolio / demo website | Belum dibuat |
| Sistem dapat klien | Belum dibangun — 3 aset komunikasi belum dibuat |
| Daftarkan nama usaha secara resmi | Disarankan: minimal usaha perorangan untuk perlindungan hukum domain |
| Pantau portal pemerintah UMKM | Cek smesta.go.id dan kemenkopukm.go.id berkala — antisipasi jika pemerintah rilis platform serupa |

---

## Catatan Teknis Penting

### Arsitektur Homepage
Homepage terdiri dari **2 blok HTML terpisah** di WordPress:
1. **Blok HTML utama** — seluruh halaman (CSS, nav, hero, sections, footer, script orisinal)
2. **Blok fix script** — script terpisah dengan event listener untuk semua tombol & nav

Jangan edit keduanya sekaligus tanpa sadar perbedaannya.

### Aturan Edit Homepage
- WordPress **selalu menghapus** atribut `onclick` saat save — jangan pakai onclick inline
- Gunakan `addEventListener` via blok fix script untuk semua interaksi
- Hamburger handler **hanya boleh ada di script utama** — jangan duplikasi di fix script

### Struktur Navigasi Saat Ini
| Nav Item | Aksi |
|---|---|
| Layanan | Scroll ke `#layanan` |
| Tentang | Buka `/tentang/` |
| Cara Kerja | Scroll ke `#proses` |
| Blog SEO | Scroll ke `#blog` |
| FAQ | Scroll ke `#faq` |
| Konsultasi Gratis | Buka WhatsApp |

---

# Next Step

**Bangun sistem dapat klien pertama:**

Buat 3 aset komunikasi berikut (Claude yang tulis, Ronald tinggal pakai):
1. Template balasan WhatsApp untuk calon klien yang masuk
2. Form brief klien — 8 pertanyaan untuk digali setelah konsultasi awal
3. Template proposal penawaran 1 halaman — tinggal isi nama klien dan kirim

Ini prioritas karena website, konten, dan halaman identitas hukum sudah siap — yang kurang adalah sistem untuk **menangkap dan mengonversi** calon klien yang masuk.
