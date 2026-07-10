# Status Patch — Fix Posisi Floating Badge Hero Card
**Tanggal:** 26 Juni 2026
**Sesi:** Perbaikan posisi badge "📍 Berbasis di Medan" yang menutupi hero tags

---

## Masalah

Badge floating `fb2` ("📍 Berbasis di Medan") di hero card memiliki posisi `bottom:24px` — menempatkannya di dalam area card sehingga menutupi tag "Mobile-Friendly" dan "Loading Cepat".

Terlihat di:
- Desktop: badge menutupi tag "Mobile-Friendly"
- Mobile: badge menututupi tag "Loading Cepat"

---

## Perubahan CSS di `main-block.html`

### Desktop (global)
```css
/* SEBELUM */
.oumkm-page .fb2{bottom:24px;left:-28px;...}

/* SESUDAH */
.oumkm-page .fb2{bottom:-20px;left:-28px;...}
```

### Mobile (`@media max-width:820px`)
```css
/* SEBELUM */
.oumkm-page .fb2{left:-8px}

/* SESUDAH */
.oumkm-page .fb2{left:-8px;bottom:-16px}
```

**Logika:** Nilai `bottom` negatif mendorong badge keluar dari batas bawah card sehingga tidak lagi overlap dengan konten di dalam card.

---

## GitHub Sync

- **Commit:** `2ab3cf3b1316` — "Fix posisi floating badge fb2 (Berbasis di Medan) — tidak menutupi hero tags [26/06/2026]"
- **File:** `onlineumkm-website-repo/onlineumkm-repo/homepage/main-block.html`
- **Ukuran:** 43.689 bytes
- **PAT:** Digunakan dan langsung dihapus ✅

---

## Status Akhir

- [x] CSS `.fb2` desktop: `bottom:24px` → `bottom:-20px`
- [x] CSS `.fb2` mobile: tambah `bottom:-16px`
- [x] GitHub synced (commit 2ab3cf3b1316)
- [x] WordPress Block Editor perlu diupdate manual dari GitHub Raw

---

## State Lengkap Homepage Saat Ini

### Logo (3 lokasi)
| Lokasi | File | Atribut kunci |
|---|---|---|
| Nav | `logo-online-umkm-glossy.webp` (700×466) | `fetchpriority="high"` |
| Hero card | `logo-online-umkm-glossy.webp` (700×466) | `decoding="async"` |
| Footer | `logo-online-umkm-footer.webp` (440×293) | `loading="lazy"` |

### Floating Badges Hero Card
| Badge | Class | Posisi desktop | Posisi mobile |
|---|---|---|---|
| ⭐ Website GRATIS terpilih | `.fb1` | `top:-16px;right:-20px` | `right:-8px` |
| 📍 Berbasis di Medan | `.fb2` | `bottom:-20px;left:-28px` | `left:-8px;bottom:-16px` |

---

## Pelajaran Teknis

Floating badge dengan `position:absolute` dan nilai `bottom` positif dihitung dari dalam batas container (`.hero-card`). Untuk memposisikan badge **di luar** card (di bawahnya), gunakan nilai `bottom` negatif. Makin besar nilai negatifnya, makin jauh badge turun dari batas bawah card.
