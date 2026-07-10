# Status Patch — Repositioning Homepage & Tentang Kami (Eksekusi Teknis)
**Tanggal sesi:** 8 Juli 2026
**Project:** onlineumkm.id
**Sertakan di:** SEMUA 3 project (Website, Konten & Copywriting, Mentor)
**Referensi sebelumnya:** `handoff-repositioning-homepage-6juli2026.md`

---

## Ringkasan Sesi

Eksekusi teknis penuh dari rencana repositioning (homepage: free-slot portfolio → 3 paket berbayar) yang sebelumnya baru berupa copy final. Sesi ini: bangun ulang Blok HTML Utama + Fix Script homepage, tulis ulang halaman Tentang Kami, iterasi palet warna, dan bereskan beberapa item Yoast + bug teknis.

---

## Perubahan Selesai — Homepage

| Item | Detail |
|---|---|
| Layanan | 4 kartu generik → 3 paket (UMKM Mulai Online Rp 1,5jt / UMKM Tampil di Google Rp 3,5jt / UMKM Tumbuh Digital Rp 7,5jt), harga tampil di tiap kartu |
| Palet warna | Diturunkan dari logo glossy terbaru — navy `#0B1D30`, gradient 3-stop `#3ED67C → #12A98F → #1C6C9C`. Tombol WhatsApp tetap `#25D366` (warna resmi WA, sengaja tidak diubah) |
| Headline & subheadline | H1: "Bisnis Kamu *Susah Ditemukan* di Google?" — subheadline baru sesuai arahan Ronald |
| Konsistensi harga | Semua klaim "GRATIS" yang kontradiksi dengan paket berbayar dibersihkan (hero-trust, strip angka, floating badge, CTA penutup — sekarang bicara "transparan", bukan "gratis") |
| Section Tentang (homepage) | Fokus "Kenapa Pilih Saya" tanpa keyword (sengaja, hindari tabrakan dengan halaman `/tentang/`) |
| FAQ | 6 pertanyaan baru sesuai realita paket berbayar |
| CTA | `cta-pre` (em dash + "3-5 Slot Tersisa") dihapus total, copy baru tanpa em dash |
| Footer | 4 label layanan lama → 3 nama paket |
| Dead code | CSS `.jujur-box` dan `.skill-tags` dihapus (tidak lagi dipakai) |
| Alt text gambar | 3 gambar dioptimasi — logo nav dapat keyword, hero card dapat `fetchpriority="high"` (LCP element di mobile karena `order:-1`), footer disederhanakan (hindari keyword stuffing) |
| Kata transisi | +7 kalimat dengan kata transisi untuk usaha perbaiki Keterbacaan Yoast (22% → 22.7%, diterima apa adanya — landing page dengan banyak microcopy secara struktural sulit capai 30%) |
| Subjudul keyword | H2 Proses diubah jadi "Proses Jasa Website UMKM yang Sederhana & Transparan" |
| Bug diperbaiki | 1 `</div>` ekstra tanpa pasangan di akhir Blok Utama (sebelum `<script>`) — dihapus. Verifikasi: `<div>`=112, `</div>`=112, seimbang |

**Yoast Homepage — status akhir:** Analisis SEO 100% hijau. Keterbacaan: 1 oranye tersisa (kata transisi, diterima).

---

## Perubahan Selesai — Halaman Tentang Kami

| Item | Detail |
|---|---|
| Bio founder | Ditulis ulang total — H2 "Kenapa Saya Membangun Jasa Website UMKM Ini", hapus framing "slot gratis" dan "klien perdana", ganti narasi 3 paket berbayar |
| Nilai (4 card) | Card 4 "Slot gratis tidak mengikat..." (kontradiksi harga) diganti total |
| Suara konsisten | "kami" → "saya", "Anda" → "kamu" di seluruh halaman (solo-operator voice, konsisten dengan homepage) |
| Em dash | 0 sisa di seluruh dokumen (diverifikasi otomatis via regex) — termasuk 3 label eyebrow section (`— Kisah di Balik...` dll) diganti middle dot `·` |
| Bug diperbaiki | Hero subheadline (kalimat rancu + typo kapitalisasi "Layanan jasa website..."), disclaimer title (teks "PENTING DIBACA" nempel tanpa pemisah → dibungkus `<span>` badge yang sudah ada di CSS tapi belum dipakai) |
| Palet warna | **Tidak diubah** — tetap palet lama (`#0D1828`/`#00B478`/`#00B4A0`), di luar scope sesi ini |

**Yoast Tentang Kami:** Judul SEO & Meta description diupdate. 2 item merah (frasa kunci di awal/subjudul) **tidak bisa hijau** — halaman pakai custom HTML block, bukan widget Heading/Text Editor Elementor native, jadi Yoast tidak bisa membaca struktur H2/paragraf pertama meski kontennya sudah benar. Diterima sebagai keterbatasan alat, bukan masalah SEO nyata (H2 dan keyword tetap ada di HTML asli, Google tetap membacanya normal). Item foto + alt text masih merah — menunggu file foto dari Ronald.

---

## Verifikasi NAP Consistency (Topik 21 — Re-cek)

Setelah repositioning besar-besaran, dicek ulang: 0 kemunculan "OnlineUMKM.id" (bentuk salah) di kedua halaman, konsisten "Online UMKM" di semua tempat (7x homepage, 9x Tentang Kami). Fix NAP dari sesi 20 Juni 2026 tidak rusak oleh repositioning ini.

**Catatan koreksi:** Ronald sempat minta lanjut ke "Topik 21: NAP Consistency Audit (citation eksternal)" — dikoreksi bahwa Topik 21 (NAP internal: website/GBP/WA Business/schema) **sudah selesai** 20 Juni 2026. Yang belum dikerjakan dan cocok dengan "citation eksternal" adalah **Topik 22: Local Citation Building Indonesia** (direktori bisnis eksternal) — masih ⬜ Belum.

---

## Backup GitHub — Repo Baru

Dibuat repo cadangan terpisah dari repo utama (`perkasacuan3-rgb/onlineumkm-website`), khusus untuk rollback kalau ada kendala:

**Repo:** `perkasacuan3-rgb/new-website-Online-UMKM-web-backup-juli2026`

| File di repo | Sumber |
|---|---|
| `homepage-main-block.html` | Blok HTML Utama final (sudah termasuk fix bug div) |
| `homepage-fix-script.html` | Fix Script final (mapping 3 paket: `paket1/paket2/paket3`) |
| `tentang-kami.html` | Halaman Tentang Kami final |

Push dilakukan via GitHub API dengan token sekali pakai (sudah dihapus Ronald setelah dipakai, sesuai SOP). **Catatan:** ini backup manual/snapshot, bukan sinkronisasi otomatis dengan repo utama — kalau ada perubahan berikutnya di WordPress, backup ini tidak ikut update kecuali di-push ulang manual.

---

## WA Links — Referensi Terbaru (Homepage)

| Key | Target Pesan | Dipakai Di |
|---|---|---|
| `paket1` | Tertarik paket UMKM Mulai Online | Kartu layanan index 0 |
| `paket2` | Tertarik paket UMKM Tampil di Google | Kartu layanan index 1 |
| `paket3` | Tertarik paket UMKM Tumbuh Digital | Kartu layanan index 2 |
| `konsultasi` | Konsultasi gratis umum | Nav CTA, Hero btn-wa |
| `cta` | Konsultasi untuk menentukan paket | Tombol CTA section bawah |
| `footer` | (pesan kosong) | Footer "Hubungi Kami" |

**Perhatian:** ini beda dari WA links versi lama (`website/seo/toko/company`) yang tercatat di dokumentasi lama — jangan pakai referensi lama itu lagi.

---

## Aturan Berlaku untuk Semua Project — WAJIB

**Setiap balasan Claude di semua 3 project (Website, Konten & Copywriting, Mentor) harus dibuka dengan menyapa nama "Ronald" di awal.**

Status: sudah aktif sebagai memory edit permanen di project **Website** (dikonfirmasi 8 Juli 2026). Memory edit bersifat per-project (tidak otomatis menyebar), jadi **Ronald perlu mengulang instruksi ini secara eksplisit** di project Konten & Copywriting dan project Mentor kalau belum ada — cukup ketik sekali di masing-masing project: *"Selalu sapa saya dengan nama Ronald di awal setiap balasan, dan ingat aturan ini seterusnya."*

---

## Pending — Belum Dikerjakan

### Prioritas Tinggi
- [ ] Foto Ronald untuk halaman Tentang Kami — masih menunggu file, avatar "RH" dipakai sementara
- [ ] Topik 22 — Local Citation Building Indonesia (direktori bisnis eksternal)

### Prioritas Menengah
- [ ] Footer label — cek apakah halaman lain (artikel, dll) yang pakai footer tema Astra default juga perlu diselaraskan dengan 3 nama paket baru
- [ ] Artikel blog berikutnya (lanjutan jadwal 12 artikel/3 bulan)

### Prioritas Rendah
- [ ] Palet warna halaman Tentang Kami — masih pakai warna lama, belum diselaraskan dengan palet baru dari logo (di luar scope, belum diminta Ronald)

---

## Pelajaran Sesi Ini

| Pelajaran | Detail |
|---|---|
| Yoast + custom HTML block Elementor | Yoast tidak bisa membaca struktur H2/paragraf pertama dalam widget HTML mentah — cuma bisa baca widget Heading/Text Editor native. Ini bukan bug, keterbatasan struktural. Terjadi 2x di sesi ini (homepage awal & Tentang Kami) |
| Kata transisi di landing page | Landing page dengan banyak microcopy (badge, tag, label tombol) punya penyebut "total kalimat" yang jauh lebih besar dari artikel biasa — persentase kata transisi sulit naik signifikan meski sudah ditambah beberapa kalimat. Realistis: terima kondisi, jangan paksakan |
| Verifikasi otomatis lebih diandalkan dari hitung manual | Pola dari sesi NAP 20 Juni terulang di sesi ini — selalu `grep`/regex count untuk verifikasi (em dash, keseimbangan div, jumlah brand mention) sebelum present ke Ronald |
| Backup manual via GitHub API | Push langsung tanpa perlu SHA karena repo baru kosong (beda dari update ke repo existing yang butuh GET dulu untuk ambil SHA) |

---

*Status Patch — 8 Juli 2026*
*Upload ke ketiga project: Website (wajib), Konten & Copywriting (opsional — cuma bagian WA links & pending artikel relevan), Mentor (wajib — pelajaran teknis Yoast + verifikasi otomatis relevan untuk pembelajaran)*
*Versi berikutnya: setelah foto Ronald tersedia, atau Topik 22 dimulai*
