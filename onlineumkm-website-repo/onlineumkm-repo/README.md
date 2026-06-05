# onlineumkm-website

Repository backup kode dan dokumen operasional untuk **OnlineUMKM.id**  
Jasa Website & SEO untuk UMKM Indonesia — oleh Ronald Huson, Medan

---

## Struktur Folder

```
onlineumkm-website/
├── homepage/
│   ├── main-block.html        ← Blok HTML utama homepage (CSS + nav + semua section)
│   └── fix-script.html        ← Blok fix script (semua event listener & tombol)
├── articles/
│   ├── artikel-01-cara-promosi-warung-makan-online.html
│   ├── artikel-02-warung-makan-sepi-padahal-enak.html
│   ├── artikel-03-cara-daftar-google-business-profile.html
│   ├── artikel-04-cara-promosi-lewat-whatsapp.html
│   └── artikel-05-cara-daftar-gofood.html
├── handoff/
│   └── mentor-master-handoff-v4.4.md   ← Konteks penuh bisnis & status terkini
├── notes/
│   ├── yoast-rules.md                  ← Aturan Yoast yang sudah dikuasai
│   └── wordpress-teknis-notes.md       ← Catatan teknis penting WordPress
└── README.md
```

---

## Cara Pakai Repo Ini

### Saat edit homepage
1. Edit kode di WordPress
2. Copy kode terbaru → paste ke file yang sesuai di sini
3. Commit dengan pesan singkat: `"Fix tombol WhatsApp"` atau `"Update hero text"`

### Saat ada masalah / website rusak
1. Buka file yang relevan di repo ini
2. Ambil versi terakhir yang berfungsi
3. Paste kembali ke WordPress

### Saat tanya Claude
1. Klik `+` di input chat → **Tambah dari GitHub**
2. Pilih file yang ingin dibahas
3. Tanya Claude langsung — tidak perlu copy-paste kode

---

## Aturan Edit Penting (Jangan Sampai Lupa)

| Situasi | Yang Harus Dilakukan |
|---|---|
| Edit fix-script.html di WordPress | Ctrl+A → Delete → Paste baru (jangan tumpuk) |
| WordPress hapus onclick inline | Pakai addEventListener — sudah ada di fix-script |
| Ada `<p>` muncul di `<style>` | Biarkan — WordPress otomatis tambahkan, tidak bisa dicegah |
| Setelah edit besar | Bersihkan cache via hPanel Hostinger |

---

## Info Bisnis

- **Website:** https://onlineumkm.id  
- **WhatsApp:** +62 877-9180-8667  
- **Hosting:** Niagahoster (WordPress + Elementor)  
- **Plugin SEO:** Yoast SEO  
- **Batas meta description:** 142 karakter  

---

*Repository ini dikelola bersama Claude Pro — diperbarui setiap ada perubahan signifikan.*
