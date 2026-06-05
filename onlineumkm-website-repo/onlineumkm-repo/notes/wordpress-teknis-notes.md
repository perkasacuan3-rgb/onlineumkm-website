# Catatan Teknis WordPress — onlineumkm.id
*Pelajaran dari trial & error — jangan diulangi*

## Arsitektur Homepage
Homepage terdiri dari 2 blok Custom HTML terpisah:

| Blok | Isi | File Backup |
|---|---|---|
| Blok 1 (besar) | CSS + nav + hero + sections + footer + script asli | `homepage/main-block.html` |
| Blok 2 (kecil) | Semua event listener & tombol | `homepage/fix-script.html` |

## Aturan Wajib

### Edit Fix Script
1. Klik blok fix script
2. **Ctrl+A → Delete** (hapus semua dulu)
3. Paste kode baru lengkap
4. Save
→ Kalau tidak ikuti urutan ini: semua tombol mati sekaligus

### WordPress & onclick
WordPress SELALU menghapus atribut `onclick` saat save.
→ Solusi: pakai `addEventListener` di fix script

### WordPress & `<p><style>`
WordPress otomatis tambahkan `<p>` di dalam `<style>` block.
→ BIARKAN saja — tidak bisa dicegah, tidak ada dampak ke Google

### Navigasi Homepage
| Item | Aksi |
|---|---|
| Layanan | Scroll ke `#layanan` |
| Tentang | Buka `/tentang/` (halaman terpisah) |
| Cara Kerja | Scroll ke `#proses` |
| Blog SEO | Scroll ke `#blog` |
| FAQ | Scroll ke `#faq` |
| Konsultasi Gratis | Buka WhatsApp |

## Plugin Penting yang Terpasang
- **Yoast SEO** — on-page optimization
- **Redirection** — 301 redirect aktif
- **LiteSpeed Cache** — cache (bersihkan via hPanel setelah edit besar)
- **Google Site Kit** — Search Console + Analytics di dashboard

## Yang JANGAN Diinstall
- Plugin Ally (aksesibilitas) → tidak kompatibel dengan Elementor

## Cache
Setelah edit besar: bersihkan cache via **hPanel Hostinger** (bukan via WordPress)
