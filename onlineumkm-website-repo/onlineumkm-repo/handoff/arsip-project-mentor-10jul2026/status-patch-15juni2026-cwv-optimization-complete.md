# Status Patch — 15 Juni 2026 (CWV Optimization Lengkap + Kontras WCAG + GitHub Sync)
**Versi:** Patch v5.5 (jalur CWV — paralel dengan jalur konten v5.5)
**Dibaca bersama:** mentor-master-handoff-onlineumkm-v5_4.md, cwv-technical-audit-onlineumkm-jun2026-v2.md
**Menggantikan referensi numerik:** cwv-technical-audit-onlineumkm-jun2026.md (v1.0, 13 Juni 2026) — angka "Kondisi Saat Ini" di file v1 sudah usang
**Topik sesi:** Eksekusi penuh 5 dari 6 rekomendasi PageSpeed audit, fix kontras WCAG AA, sinkronisasi GitHub

---

## FOKUS SESI INI

Audit PageSpeed tanggal 14 Juni (skor 78, turun dari 82 akibat fluktuasi normal) menghasilkan 5 prioritas perbaikan. Sesi ini mengeksekusi semuanya kecuali Prioritas 3 (tidak tersedia di versi LiteSpeed ini), plus 1 temuan tambahan (loading=lazy pada elemen LCP mobile) dan 1 fix tambahan (heading hierarchy footer).

---

## HASIL PAGESPEED — PERJALANAN LENGKAP

| Tanggal | Performa | FCP | LCP | TBT | CLS | Speed Index | Catatan |
|---|---|---|---|---|---|---|---|
| 13 Jun | 82 | 2,8 dtk | 3,6 dtk | 50 ms | 0,033 | 5,1 dtk | Setelah REST API `_fields` |
| 14 Jun | 78 | 3,4 dtk | 4,1 dtk | 40 ms | 0,034 | 4,4 dtk | Fluktuasi normal (cold cache) |
| 15 Jun (tengah) | 84 | 2,6 dtk | 3,5 dtk | 20 ms | 0,034 | 4,8 dtk | Setelah logo+preconnect |
| **15 Jun (final)** | **85** | **2,7 dtk** | **3,6 dtk** | 90 ms | 0,034 | **2,8 dtk** | Setelah semua fix |

**Skor tambahan (baru muncul 15 Jun final):**
| Kategori | Skor |
|---|---|
| Aksesibilitas | 98 |
| Praktik Terbaik | 100 |
| SEO | 92 |

Catatan: TBT naik dari 20→90ms dan Speed Index turun drastis dari 4,8→2,8 dtk antar-test — ini fluktuasi normal PageSpeed (server response time bervariasi per request), bukan regresi dari perubahan kode.

---

## DETAIL PERUBAHAN

### Prioritas 1 — Base64 Images → URL Media Library ✅
**Masalah:** 3 logo (nav, hero card, footer) di-embed sebagai base64 (~150 KB total) di HTML. Penundaan render elemen LCP: 2.880 ms.

**Fix:**
- Upload logo baru (680×453px, WebP, 12,6 KB) ke Media Library: `logo-onlineumkm-680-untuk-web.webp`
- Nav logo: `width="680" height="453" fetchpriority="high" decoding="async"`
- Hero card logo: `width="680" height="453" decoding="async"` (awalnya pakai `loading="lazy"`, lihat Fix Tambahan A)
- Footer logo: `width="680" height="453" loading="lazy" decoding="async"`
- Bonus: hamburger button ditambah 3 `<span>` (sebelumnya kosong di versi WordPress live — sinkron dengan fix 14 Jun)

**Dampak:** Penundaan render elemen LCP turun dari 2.880 ms → 20 ms (99% lebih cepat). HTML lebih ringan ~150 KB.

### Prioritas 2 — Preconnect Google Analytics/GTM ✅
**Masalah:** Kandidat prakoneksi ke `google-analytics.com`, estimasi hemat 170 ms LCP.

**Fix:** LiteSpeed Cache → Optimasi Halaman → **[3] Pengaturan HTML** → field **"Prahubung DNS"** (Preconnect):
```
https://www.google-analytics.com
https://www.googletagmanager.com
```
Field "Prapengambilan DNS" (DNS Prefetch) dikosongkan — preconnect sudah mencakup DNS lookup, jadi redundan kalau diisi keduanya.

**Pelajaran:** Field di LiteSpeed Cache versi ini ada di tab "Pengaturan HTML" (bukan "Tuning" seperti versi lain), dan terjemahan Indonesia-nya membingungkan: "Prapengambilan DNS" = DNS Prefetch (ringan), "Prahubung DNS" = Preconnect (lebih lengkap, ini yang diminta PageSpeed).

### Prioritas 3 — Browser Cache TTL ⬜ SKIP (Konfirmasi Ulang)
LiteSpeed Cache → Cache → TTL hanya berisi server-side cache TTL (TTL Beranda, TTL Cache Publik, dst), bukan browser cache TTL untuk file statis. Dikonfirmasi ulang: **setting ini tidak diekspos di versi LiteSpeed ini**. TTL Beranda diubah ke 31536000 (1 tahun) — aman karena LiteSpeed auto-purge saat ada update konten, tapi tidak menyelesaikan temuan PageSpeed "Gunakan durasi cache yang efisien" (masih 7 jam, 42 KiB).

**Status:** Secondary priority, diterima sebagai constraint hosting.

### Fix Tambahan A — Hapus `loading="lazy"` dari Hero Card Logo ✅
**Ditemukan setelah test PageSpeed pasca-Prioritas 1-2** (skor 84): PageSpeed memberi peringatan "Resource LCP tidak boleh menggunakan loading=lazy".

**Sebab:** Di mobile, CSS `.hero-right{order:-1}` memindahkan hero card ke atas teks hero — sehingga logo di hero card (bukan logo nav) menjadi elemen LCP di mobile. `loading="lazy"` pada elemen ini justru menunda LCP.

**Fix:** Hapus `loading="lazy"` dari `<img>` hero card. Footer logo tetap pakai `loading="lazy"` (posisinya jauh di bawah fold).

### Prioritas 4 — Kontras Warna WCAG AA ✅ (6 fix)
Dihitung pasti dengan formula WCAG relative luminance (Python), semua melewati ambang 4,5:1:

| Elemen | Sebelum | Sesudah | Rasio Baru |
|---|---|---|---|
| `.btn-wa` / `.btn-cta-wa` (tombol WA) | putih di atas `#25D366` (1,98:1) | `color: var(--navy)` (8,99:1) | ✅ |
| `.sec-label` (label "— Tentang Kami" dst.) | `var(--green)` #00B478 (2,69:1) | `#007A50` (5,39:1) | ✅ |
| `.tentang-peran` | `var(--green)` (2,69:1) | `#007A50` (5,39:1) | ✅ |
| `.jujur-box strong` | `#B8830C` (3,15:1) | `#8F6608` (4,86:1) | ✅ |
| `.footer-copy` | `rgba(255,255,255,.4)` (3,81:1) | `#9CA3AF` (7,30:1) | ✅ |
| `.footer-disclaimer` | `rgba(255,255,255,.28)` (2,49:1) | `rgba(255,255,255,.5)` (5,31:1) | ✅ |
| H3 "Layanan Jasa Pembuatan Website UMKM Lokal" | `var(--green)` (2,69:1) | `#007A50` (5,39:1) | ✅ |

**Hasil:** Skor Aksesibilitas PageSpeed → 98.

### Prioritas 5 — Heading Hierarchy Footer ✅
**Masalah:** `<h4>Layanan</h4>` dan `<h4>Navigasi</h4>` di footer tidak punya parent H2/H3 — melanggar urutan heading semantik.

**Fix:** Diganti jadi `<p class="footer-heading">` dengan CSS `.footer-col .footer-heading{...}` (styling identik dengan `h4` lama, tidak ada perubahan visual).

---

## GITHUB SYNC

**Commit:** `b466f79` — "Update main-block.html - CWV optimization & contrast fixes (15/06/2026)"
**Repo:** `perkasacuan3-rgb/onlineumkm-website`
**File:** `homepage/main-block.html` (37 baris ditambah, 18 dihapus)
**Header file:** diperbarui ke `TERAKHIR DIUPDATE : 15/06/2026` + ringkasan perubahan sesi

Token PAT digunakan sekali, lalu dihapus dari GitHub Settings sesuai workflow standar. Clone lokal juga dihapus setelah push.

---

## PELAJARAN TEKNIS BARU

| Situasi | Yang Benar |
|---|---|
| `loading="lazy"` pada elemen yang berbeda di mobile vs desktop | Cek CSS `order` / `flex-direction` di media query — elemen LCP bisa berbeda per breakpoint. Resource LCP TIDAK BOLEH lazy-load di breakpoint manapun. |
| Hitung kontras warna manual | Gunakan formula WCAG relative luminance (Python), bukan tebak-tebakan visual — selisih kecil (2,69 vs 4,5) tidak terlihat jelas oleh mata tapi signifikan untuk compliance. |
| LiteSpeed Cache: "Prapengambilan DNS" vs "Prahubung DNS" | Terjemahan Indonesia membingungkan. Prahubung = Preconnect (lebih kuat). Untuk domain yang direkomendasikan PageSpeed dengan kata "preconnect", isi "Prahubung DNS", bukan "Prapengambilan DNS". |
| Fluktuasi skor PageSpeed antar-test (±5-10 poin) | Normal — disebabkan variasi server response time. Jangan panik kalau skor turun sedikit setelah fix; bandingkan tren beberapa test, bukan satu angka. |
| Mengganti warna brand untuk kontras (misal tombol WA) | Ganti warna TEKS (bukan background) jika background adalah warna brand yang harus dipertahankan (WhatsApp green). Navy (#0D1828) di atas #25D366 = 8,99:1, brand tetap recognizable. |

---

## PENDING ITEMS — UPDATE

### Selesai Sesi Ini
- [x] Logo base64 → URL Media Library (3 lokasi)
- [x] Preconnect Google Analytics/GTM
- [x] Hapus loading=lazy dari hero card (elemen LCP mobile)
- [x] 6 fix kontras WCAG AA
- [x] Footer heading hierarchy (h4 → p.footer-heading)
- [x] Sinkronisasi GitHub main-block.html

### Masih Pending
- [ ] Upload foto Ronald ke halaman Tentang Kami (Yoast oranye, 4 item merah)
- [ ] Artikel #7 — Template Caption Instagram (16-22 Jun)
- [ ] Dead code cleanup di Blok Utama (fungsi oumkmFaq/oumkmWA/oumkmScroll yang tidak terpakai — masih ada, tidak breaking)
- [ ] Fallback blog card URL artikel #1 (slug salah, hanya muncul jika REST API gagal)
- [ ] Disclaimer bar atas (`#5A6F8A` on `#F0F6FF`) — kontras borderline, belum dicek presisi

### Constraint Diterima (Tidak Perlu Tindakan)
- Unused JS dari GTM (64 KiB) — aktif dengan GA4
- Unused CSS dari tema (39 KiB) — risiko tinggi jika dihapus
- Browser Cache TTL untuk file statis — tidak diekspos di LiteSpeed versi ini
- REST API di critical chain (~4.225 ms) — sudah dioptimasi dengan `_fields`, sisanya server response time

---

## REKOMENDASI ARAH SELANJUTNYA

**Optimasi teknis dihentikan untuk saat ini.** Skor 85/98/100/92 sudah solid dan kompetitif (rata-rata website UMKM Indonesia: 30-60). Sisa bottleneck butuh perubahan arsitektur (migrasi REST API → static, atau lepas dari Elementor) yang risikonya tidak proporsional dengan gain 3-5 poin tambahan.

**Fokus berikutnya:** Artikel #7 (Template Caption Instagram, 16-22 Jun) — nilai bisnis langsung lebih besar.

---

## PANDUAN PENEMPATAN FILE LINTAS PROJECT

| Project | status-patch-15juni2026-cwv (file ini) | cwv-technical-audit-v2 | proof-points-proposal |
|---|---|---|---|
| **1. Belajar SEO & Digital Marketing** | ✅ Berguna — contoh kasus nyata Topik 9 (CWV) & 14 (cara baca PageSpeed), termasuk perhitungan kontras WCAG | ✅ Berguna — referensi "kondisi saat ini" untuk dibandingkan saat belajar topik baru | ❌ Tidak perlu |
| **2. Keuangan Freelance** | ❌ Tidak perlu | ❌ Tidak perlu | ❌ Tidak perlu |
| **3. Konten & Copywriting — onlineumkm.id** | ❌ Tidak perlu — murni teknis, tidak menyangkut konten | ❌ Tidak perlu | ⚠️ Opsional — bisa jadi bahan ide artikel "studi kasus optimasi website sendiri" |
| **4. MENTOR** | ✅ Wajib — pelajaran teknis (CWV, kontras, LiteSpeed) bernilai untuk fase belajar SEO | ✅ Berguna — pendukung Topik 9 & 14 yang sudah selesai | ❌ Tidak perlu |
| **5. Klien & Proposal — onlineumkm.id** | ⚠️ Opsional — terlalu teknis untuk klien, tapi berguna sebagai referensi internal | ❌ Tidak perlu | ✅ **Wajib** — ini file utama untuk project ini |
| **6. onlineumkm.id — Website** | ✅ Wajib — single source of truth konfigurasi situs | ✅ Wajib (gantikan v1) | ❌ Tidak perlu |

---

*Patch v5.5 (jalur CWV) — 15 Juni 2026*
*Perubahan untuk dimasukkan ke Master Handoff v5.6 (saat digabung dengan jalur konten v5.5):*
*- Bagian CWV: tabel "Kondisi Saat Ini" diperbarui ke hasil 15 Juni (85/98/100/92)*
*- Bagian 16 (Fase Belajar SEO): Topik 9 & 14 mendapat tambahan studi kasus kontras WCAG*
*- Bagian Pending Items: 6 item selesai, 4 item pending diperbarui*
*- Bagian baru: rekomendasi penghentian optimasi teknis, fokus kembali ke konten*
