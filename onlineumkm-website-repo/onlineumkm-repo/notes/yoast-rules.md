# Aturan Yoast SEO — onlineumkm.id
*Referensi cepat saat menulis atau mengedit artikel*

## Meta Description
- Maksimal **142 karakter** (bukan 155 — Yoast versi ini lebih ketat)
- Wajib mengandung keyword utama
- Harus persuasif (ajakan baca)
- Cara ganti: Ctrl+A → Delete di kolom meta Yoast sebelum paste

## Heading & Keyword
- Minimal **30%** dari semua heading (H2+H3+H4) mengandung keyword atau sinonim
- Yoast terbaru menghitung SEMUA level heading, bukan hanya H2
- Kalau banyak H3, tambahkan keyword di H3

## Alt Text Gambar
- Keyword di alt text: **maksimal 1–2 gambar per artikel**
- Lebih dari 2 → Yoast kasih peringatan oranye

## Format Wajib per Artikel
- `<hr>` di antara setiap section H2
- Minimal 2 gambar dengan alt text relevan
- Minimal 3 internal link per artikel
- FAQ block di bagian akhir (format Yoast FAQ block)
- H2 terpisah WAJIB sebelum FAQ block

## Gaya Penulisan
- Em dash (—) dan en dash (–): **DILARANG**
- "Berikutnya": tidak dikenali Yoast sebagai kata transisi
- Tone: selalu **"kamu"** (bukan Anda)
- Panjang paragraf: maksimal 150 kata
- Subheading: setiap 300 kata harus ada H2 atau H3

## Pembuka yang Dilarang
- "Di era digital ini..."
- "Dalam persaingan yang semakin ketat..."
- "Tentu saja..."

## Permanent Limitations Homepage (Jangan Diulangi)
- "Frasa kunci di awal" → MERAH PERMANENT (WordPress paksa `<p><style>`)
- "Kata transisi" → MERAH PERMANENT (CSS dihitung sebagai kalimat)
- Jangan coba optimasi 2 item ini lagi — sudah final
