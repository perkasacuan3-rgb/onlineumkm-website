# Status Patch — Logo Update Homepage
**Tanggal:** 25 Juni 2026
**Sesi:** Penggantian logo di nav, hero card, dan footer homepage

---

## Latar Belakang

Ronald ingin mengganti logo lama (logo flat original) di seluruh homepage dengan dua logo baru hasil generate AI yang lebih modern. Dua logo berbeda digunakan untuk konteks berbeda:
- Logo glossy (3D effect, background putih) → nav & hero card
- Logo rounded black edge (background gelap/rounded corner) → footer

---

## File Logo Baru

| File | Dipakai di | Ukuran asli | Setelah konversi |
|---|---|---|---|
| `ChatGPT_Image_23_Jun_2026__00_40_28_glossy_latest.png` | Nav + Hero card | 1.210 KB PNG | **17,9 KB WebP** (700×466 px) |
| `full_logo_rounded_edge_black.png` | Footer | 992 KB PNG | **10,4 KB WebP** (440×293 px) |

**Proses konversi:** Python Pillow → resize → WebP q=80, method=6.
**Pengurangan ukuran:** 98–99% lebih kecil dari PNG aslinya.

---

## Perubahan — Homepage (`main-block.html`)

### Logo Nav (atas)
**Sebelum:** `logo-onlineumkm-680-untuk-web.webp` (logo lama)
**Sesudah:** `logo-online-umkm-glossy.webp`
```html
<img src="https://onlineumkm.id/wp-content/uploads/2026/06/logo-online-umkm-glossy.webp"
     width="700" height="466"
     alt="Jasa website dan SEO lokal untuk UMKM Medan - Online UMKM"
     fetchpriority="high" decoding="async" />
```
Atribut `fetchpriority="high"` dipertahankan dari versi sebelumnya.

### Logo Hero Card
**Sebelum:** `logo-onlineumkm-680-untuk-web.webp` (logo lama)
**Sesudah:** `logo-online-umkm-glossy.webp`
```html
<img src="https://onlineumkm.id/wp-content/uploads/2026/06/logo-online-umkm-glossy.webp"
     width="700" height="466"
     alt="Online UMKM"
     decoding="async" />
```
Tidak ada `loading="lazy"` — sesuai CWV fix (15 Juni 2026), karena ini elemen LCP di mobile.

### Logo Footer
**Sebelum:** `logo-onlineumkm-680-untuk-web.webp` (logo lama)
**Sesudah:** `logo-online-umkm-footer.webp` (logo berbeda — rounded black)
```html
<img src="https://onlineumkm.id/wp-content/uploads/2026/06/logo-online-umkm-footer.webp"
     width="440" height="293"
     alt="Online UMKM - Jasa website dan SEO untuk UMKM Indonesia"
     loading="lazy" decoding="async" />
```
`loading="lazy"` dipertahankan — posisi footer jauh di bawah fold, tidak memengaruhi LCP.

**Catatan penting:** Base64 embedding sempat dicoba untuk footer namun dibatalkan karena `loading="lazy"` tidak efektif pada base64 (data sudah ada di HTML saat parsing). Pendekatan URL terbukti lebih optimal.

---

## URL Logo di WordPress Media Library

| File | URL |
|---|---|
| Logo glossy (nav + hero) | `https://onlineumkm.id/wp-content/uploads/2026/06/logo-online-umkm-glossy.webp` |
| Logo footer (rounded black) | `https://onlineumkm.id/wp-content/uploads/2026/06/logo-online-umkm-footer.webp` |

---

## GitHub Sync

- **Repo:** `perkasacuan3-rgb/onlineumkm-website`
- **File:** `onlineumkm-website-repo/onlineumkm-repo/homepage/main-block.html`
- **Commit:** `5b367282e52f` — "Ganti logo nav+hero (glossy) & footer (rounded black) [25/06/2026]"
- **Ukuran file:** 43.675 bytes (turun dari 44.709 bytes)
- **PAT:** Digunakan dan langsung dihapus setelah push berhasil ✅

---

## Status Akhir

- [x] Logo nav diganti → logo-online-umkm-glossy.webp
- [x] Logo hero card diganti → logo-online-umkm-glossy.webp
- [x] Logo footer diganti → logo-online-umkm-footer.webp
- [x] Semua file dikonversi PNG → WebP (hemat 98–99%)
- [x] WordPress Block Editor diupdate
- [x] GitHub synced (commit 5b367282e52f)
- [x] LiteSpeed Cache di-flush
- [x] Verifikasi live di website ✅ — tidak ada kendala

---

## Pelajaran Teknis

- **Base64 vs URL untuk logo:** URL selalu lebih optimal untuk gambar yang bisa di-lazy-load. Base64 di HTML membuat `loading="lazy"` tidak efektif karena data sudah ikut ter-download saat parsing HTML.
- **Dimensi `width`/`height` wajib diisi:** Mencegah layout shift (CLS) — browser bisa alokasi ruang sebelum gambar dimuat.
- **Hero card = elemen LCP mobile:** CSS `.hero-right{order:-1}` memindahkan hero card ke atas di mobile, sehingga logo di sana menjadi LCP. Jangan pernah tambahkan `loading="lazy"` ke hero card img.
- **Konversi PNG → WebP:** Resize ke dimensi tampil maksimal (2× retina), WebP q=80 method=6 — hasil optimal tanpa penurunan kualitas visual yang terlihat.
